# MBSim Releases

This repository hosts compiled release packages for MBSim, a Modbus RTU/TCP
slave simulator.

Source code is maintained separately. Download packages from GitHub Releases
instead of cloning this repository.

## Latest Release

- Latest release: https://github.com/louisir/mbsim-dist/releases/latest
- All releases: https://github.com/louisir/mbsim-dist/releases

## Windows Portable Package

Download the Windows x64 portable package from the latest release assets:

- `MBSim-v<version>-portable-windows-x64.zip`
- `MBSim-v<version>-portable-windows-x64.zip.sha256`

After downloading, unzip the package and run `MBSim.exe`.

## Verify SHA256

In PowerShell, run:

```powershell
Get-FileHash .\MBSim-v<version>-portable-windows-x64.zip -Algorithm SHA256
Get-Content .\MBSim-v<version>-portable-windows-x64.zip.sha256
```

The hash printed by `Get-FileHash` should match the value in the `.sha256`
file.

## Release Assets

The zip files in Releases are the official distribution artifacts. Files copied
into this repository working tree are staging artifacts used by the release
script and are not intended to be committed.
