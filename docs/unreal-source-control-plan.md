# Unreal Engine source control plan

This is the workflow for [M0.03](https://github.com/Hagrid862/GrandTheftAgent/issues/3). It covers the files to track, a GitHub LFS trial, and coordination of edits to binary assets. The local trial used the Unreal Engine 5.9.0 build recorded in the [macOS verification report](unreal-macos-verification.md).

## What goes into the repository

| Where | Files |
| --- | --- |
| Git | C++ source, the `.uproject` descriptor, shared settings in `Config/`, scripts, documentation, plugin source and descriptors, and project-owned inputs in `Build/`. |
| Git LFS | All `.uasset` and `.umap` files, including packages in Unreal's external actor and object directories. Add other large binary sources individually when the project needs them and their license permits storage in this repository. |
| Outside Git | Generated `Intermediate/`, `Saved/`, `DerivedDataCache/`, and `Binaries/` directories, local IDE state, and packaged builds. If a plugin requires a prebuilt binary, explicitly include the required files after checking how they can be distributed and recovered. |

The repository's [`.gitattributes`](../.gitattributes) and [`.gitignore`](../.gitignore) implement these rules. Check that the test assets are absent from the existing GitHub history and that a staged asset produces an LFS pointer. Keep the sample assets on a dedicated test branch.

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

Issue #3 is ready for acceptance when the GitHub trial has restored both revisions, Unreal has confirmed their expected differences, and the team has a tested procedure for handling overlapping binary edits. The proposal received independent scores of 8/10 for Unreal assets, 9/10 for Git LFS and collaboration, and 9/10 for cost and scope. The plan includes their checks for public redistribution, billing, asset verification, and conflict recovery.

## Local verification on November 22, 2026

Git LFS 3.8.1 was installed on the Mac Studio and initialized in the repository. The test pushed the two revisions to a local bare repository over `file://`. A fresh clone with an empty LFS cache downloaded the baseline using `git lfs pull`, then took the second revision with `git pull --ff-only` and `git lfs pull`. `git lfs fsck` passed on both revisions. The downloaded files matched the source files and the committed pointers. The four distinct objects total 69,519 bytes.

| Test commit | File | Size in bytes | LFS object ID and file SHA-256 |
| --- | --- | ---: | --- |
| `9249d219b54e272ee61cb06391eb82b67694f32a` | `BP_Verification.uasset` | 23,931 | `49c617bb3cfb4ccaa1446ffe34820ea63a97857228cb47e6451a0be3d496ed42` |
| `9249d219b54e272ee61cb06391eb82b67694f32a` | `Map_Verification.umap` | 10,707 | `6da0aab3d7cf99393241fd0831360706acf8e0d3e1d7aa12eb54b0e5763646b8` |
| `58a7ebba71584b28d70d7ee0ef2ed1f6cb312820` | `BP_Verification.uasset` | 23,984 | `beabc48f05320e89db2188c38cd1d5773b1ff9c87a3aad9a4e2c0be0e1775a40` |
| `58a7ebba71584b28d70d7ee0ef2ed1f6cb312820` | `Map_Verification.umap` | 10,897 | `8bb674addb846cc4948098f65f454a3f4ca9a44a80d5579514c2965854fc28de` |

A separate Unreal Editor process compiled the Blueprint and ran Play in Editor for each revision. The baseline actor was at X=0 with the default lifespan of 0 seconds. The second actor was at X=350 with a lifespan of 600 seconds.

An independent edit (`283c582`) disabled damage on the same Blueprint. Git reported a conflict when it merged that edit with revision two. Both source commits were preserved. The recovery took revision two as its starting point, reapplied the damage setting in Unreal, and compiled and ran the result in Play in Editor. The actor retained X=350, a 600-second lifespan, and the disabled damage setting. Use issue reservations and this recovery procedure for overlapping edits.

The remaining acceptance check is the GitHub round trip. The available GitHub login could read the repository and issue, but it could not read the owner's billing usage. Confirm the available LFS allowance and the control that stops paid overages before uploading the sample. Until then, keep issue #3 open.
