# Windows Portable Build

This repository includes a GitHub Actions workflow that builds a Windows portable zip for Bambu Studio.

Workflow:

- `.github/workflows/windows_portable.yml`
- Runs automatically on `master` when application source/build files change.
- Can also be started manually from GitHub Actions with `Run workflow`.
- Produces an artifact named like `BambuStudio_Windows_V*_portable.zip`.
- Caches the Windows dependency install directory with a manually versioned cache key. If dependency definitions under `deps/` change, bump the cache version in `.github/workflows/windows_portable.yml`.

How to use it on another Windows computer:

1. Open the repository on GitHub.
2. Go to `Actions`.
3. Open the latest successful `Windows Portable Build` run.
4. Download the `BambuStudio_Windows_V*_portable.zip` artifact.
5. Unzip it and run `bambu-studio.exe` from the extracted folder.

Hardware-only imports under `hardware-projects/` do not trigger this build because they do not change the Bambu Studio app binary.
