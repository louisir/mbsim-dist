# MBSim Releases

中文说明: [README.zh_CN.md](README.zh_CN.md)

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

## Licensing

MBSim's own application code and documentation are distributed under the MIT
License. See [LICENSE](LICENSE).

The portable package also includes third-party runtime components. Their
licenses are separate from the MBSim MIT License and must be respected when
using or redistributing the package. In particular:

- Qt is not a single-license dependency. Qt is available under commercial and
  open-source license options. For open-source Qt, many modules are LGPLv3/GPLv3,
  while some modules are GPLv3-only.
- MBSim uses Qt Quick 3D. Qt's own licensing documentation lists Qt Quick 3D
  under modules available under GNU GPL v3 for open-source users. Redistributors
  must either comply with the applicable GPL/LGPL obligations or use an
  appropriate commercial Qt license.
- OpenXLSX is used for Excel register-map support and is licensed under the
  BSD 3-Clause License.

See [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) for details and official
license references.

This repository does not provide legal advice. If you distribute MBSim in a
commercial product or controlled environment, review the relevant licenses with
qualified counsel.

## Release Assets

The zip files in Releases are the official distribution artifacts. Files copied
into this repository working tree are staging artifacts used by the release
script and are not intended to be committed.
