# Unreal Engine source control plan

This is the proposed workflow for [M0.03](https://github.com/Hagrid862/GrandTheftAgent/issues/3). It covers the files to track, a GitHub LFS test, and a way to coordinate edits to binary assets. Use the Unreal Engine 5.9.0 build recorded in the [macOS verification report](unreal-macos-verification.md).

## What goes into the repository

| Where | Files |
| --- | --- |
| Git | C++ source, the `.uproject` descriptor, shared settings in `Config/`, scripts, documentation, plugin source and descriptors, and project-owned inputs in `Build/`. |
| Git LFS | All `.uasset` and `.umap` files, including packages in Unreal's external actor and object directories. Add other large binary sources individually when the project needs them and their license permits storage in this repository. |
| Outside Git | Generated `Intermediate/`, `Saved/`, `DerivedDataCache/`, and `Binaries/` directories, local IDE state, and packaged builds. If a plugin requires a prebuilt binary, explicitly include the required files after checking how they can be distributed and recovered. |

Create the `.gitattributes` rules before staging the first Unreal assets. Check that the test assets are absent from the existing Git history and that a staged asset produces an LFS pointer. Keep the sample assets on a dedicated test branch. Bring the agreed tracking and ignore rules into `main` separately.

## GitHub LFS trial

1. Confirm that the Git LFS client is available or install it. At planning time, the Mac did not have the client. Check the repository owner's remaining LFS storage and download allowances and verify that paid overages are blocked before pushing the sample.
2. Use the small map and Blueprint from M0.02 if all files and dependencies are suitable for public redistribution. If any are unsuitable, build a minimal original sample with no third-party asset packs. Check the entire outgoing file list, including configuration and plugin files.
3. Save a baseline revision. In Unreal, make separately identifiable changes to the map and the Blueprint, then save a second revision. Change something stored in the `.umap` itself. In a One File Per Actor level, changing an actor can update its external package while the map file remains unchanged. If that feature is in use, include at least one external actor package in the test. [Epic Games One File Per Actor documentation](https://dev.epicgames.com/documentation/en-us/unreal-engine/one-file-per-actor-in-unreal-engine)
4. Inspect the committed pointers for both revisions before pushing the test branch. For each file, record the commit ID, the original file size and SHA-256, and the size and object ID in the pointer. Verify that the map and Blueprint each have a different object ID in the second revision.
5. Use an independent fresh clone with an empty LFS cache. Check out the older commit first and confirm that GitHub serves the actual assets. Fetch and check out the newer commit in that clone and repeat the check. For both revisions, compare the downloaded files with the original sizes and SHA-256 values.
6. Start a separate Unreal Editor process for each revision. Open the map, compile the Blueprint, and use Play in Editor to confirm the expected map change and actor state or behavior. Record the commit IDs and results in issue #3. The packaged build for the real project belongs to M0.04.

## Editing binary packages

Assign one person or agent to each binary package or related group of packages at a time. Before editing, record the affected map, actor, or asset and the relevant paths in the issue. For maps with external actor packages, review related additions, edits, moves, and deletions together. Check for overlap with active work before integrating. Release the reservation when the change has been integrated or handed back.

Exercise the recovery procedure locally with two branches that change the same Blueprint. Preserve both versions in separate commits, pick a starting version, and reapply the intended changes in Unreal. Compile the resulting Blueprint and confirm its behavior in Play in Editor.

Treat Git LFS locking as optional. If a second account with write access is available, test a competing lock and a competing push on the same path, then repeat after releasing the lock. Test across branches if the workflow will rely on cross-branch protection. Record whether the client hook or the server rejected the competing push. Use issue reservations as the default until the relevant behavior has been verified. [Git LFS locking specification](https://github.com/git-lfs/git-lfs/blob/main/docs/api/locking.md)

## Cost and acceptance

The budget target is zero new spending. GitHub documents 10 GiB of LFS storage and 10 GiB of download bandwidth for Free and Pro accounts. A changed asset stores another full version, and downloads count against the repository owner. Keep the sample small so it fits the verified allowance. Before adding large source assets or routinely using fresh clones, estimate the total across asset revisions and expected downloads. Removing the test branch leaves uploaded LFS objects on GitHub. [GitHub LFS billing](https://docs.github.com/en/billing/concepts/product-billing/git-lfs) · [Removing files from Git LFS](https://docs.github.com/en/repositories/working-with-files/managing-large-files/removing-files-from-git-large-file-storage)

Issue #3 is ready for acceptance when the GitHub trial has restored both revisions, Unreal has confirmed their expected differences, and the team has a tested procedure for handling overlapping binary edits. The proposal received independent scores of 8/10 for Unreal assets, 9/10 for Git LFS and collaboration, and 9/10 for cost and scope. The plan includes their checks for public redistribution, billing, asset verification, and conflict recovery. The round trip and account limits still need to be verified.
