# Unreal Engine verification on Apple Silicon

This record supports [M0.02](https://github.com/Hagrid862/GrandTheftAgent/issues/2). The test ran on November 22, 2026, on a Mac Studio with an Apple M3 Ultra and 96 GB of memory. It used the engine's Blank C++ template in a temporary directory.

## Toolchain

| Component | Version used |
| --- | --- |
| Unreal Engine | 5.9.0, changelist 60738873, branch `++UE5+Release-5.9` |
| macOS | 27.3 |
| Architecture | arm64 |
| Xcode | 27.2, build 27B52 |
| macOS SDK | 27.2 |
| Apple Clang | 21.0.0, build `clang-2100.4.1.1` |
| Metal Toolchain | 27B47 |

The Mac's default developer directory pointed to the standalone Command Line Tools. The test used `DEVELOPER_DIR=/Applications/Xcode.app/Contents/Developer` for the Unreal commands. The Metal compiler initially reported a missing component. Installing it with `xcodebuild -downloadComponent MetalToolchain` made `xcrun metal --version` succeed.

## Verification

| Check | Result |
| --- | --- |
| Build the Blank C++ editor target for macOS | Passed using `-NoUBA` and the canonical temporary project path under `/private/tmp`. |
| Create, compile, and save a Blueprint | Passed. The editor script created `BP_Verification` and placed an instance in `Map_Verification`. |
| Reopen the project and start Play in Editor | Passed. A second editor launch loaded the saved Blueprint and map. The Play in Editor world contained the Blueprint instance. |
| Package and launch the macOS app | Passed. `BuildCookRun` exited with code 0. The Development app started outside the editor and loaded `/Game/M002/Map_Verification` as its default map. |

The first C++ build failed when Unreal Build Accelerator could not find a generated precompiled header. The retry switched to the canonical project path and passed `-NoUBA`. Both changed between runs, so the test establishes the working combination.

## Reproduction

Start with a copy of the engine's Blank C++ template in a directory with a canonical path. Set `UE_DIR` to the Unreal Engine install directory, `TEST_PROJECT` to the absolute path of the copied `.uproject`, and `ARCHIVE_DIR` to a directory for the macOS package. Create a test level, add an instance of a compiled Blueprint, and set the level as the game's default map. Save the assets, reopen the editor, then start Play in Editor and verify that the actor is present.

```sh
export DEVELOPER_DIR=/Applications/Xcode.app/Contents/Developer

"$UE_DIR/Engine/Build/BatchFiles/Mac/Build.sh" \
  TP_BlankEditor Mac Development "-Project=$TEST_PROJECT" -NoUBA -WaitMutex

"$UE_DIR/Engine/Build/BatchFiles/RunUAT.sh" BuildCookRun \
  "-project=$TEST_PROJECT" -platform=Mac -clientconfig=Development \
  -build -cook -stage -pak -package -archive "-archivedirectory=$ARCHIVE_DIR" \
  -unattended -noP4 -ubtargs=-NoUBA
```

Run the packaged executable directly, without passing a map override. Add `-stdout -FullStdOutLogOutput` to capture the runtime output and look for the default map reaching `Bringing World ... up for play`. The smoke test used offscreen rendering.

The archived test package occupied about 894 MiB. The filesystem reported 87 GiB free before the trial and 82 GiB afterward. The difference includes shared cache and other filesystem activity. Use M0.04 to measure the disk requirements of the actual project.

Use the tested Unreal Engine 5.9.0 build for the next local project setup. Keep the exact engine build in build records because Epic labels the 5.9 release notes as preview. [Epic Games release notes](https://dev.epicgames.com/documentation/en-us/unreal-engine/unreal-engine-5-9-release-notes)
