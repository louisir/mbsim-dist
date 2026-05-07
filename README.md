# MBSim Releases

Languages: English | [简体中文](README.zh_CN.md) |
[繁體中文](README.zh_HK.md) | [Deutsch](README.de.md) |
[Español](README.es.md) | [Français](README.fr.md) |
[Italiano](README.it.md) | [日本語](README.ja.md) |
[한국어](README.ko.md)

This repository hosts compiled release packages for MBSim, a Modbus RTU/TCP
slave simulator.

MBSim is distributed as proprietary freeware. Source code is not published.
Download packages from GitHub Releases instead of cloning this repository.

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

## Licensing and Donations

MBSim's own application code and documentation are proprietary freeware. You may
install and use official MBSim release packages free of charge. MBSim is not
open-source software, and source code is not published. See [LICENSE](LICENSE).

Donations are optional support for future development. A donation is not a
purchase, does not unlock additional license rights or features, and does not
create a support, warranty, service, or maintenance obligation.

Redistribution, sale, modification, reverse engineering, or creation of
derivative works of MBSim itself requires separate written permission from the
copyright holder, except where mandatory law provides otherwise. Third-party
components remain governed by their own licenses.

The portable package also includes third-party runtime components. Their
licenses are separate from the MBSim freeware license and must be respected when
using or redistributing the package. In particular:

- Qt is not a single-license dependency. Qt is available under commercial and
  open-source license options. For open-source Qt, many modules are LGPLv3/GPLv3,
  while some modules are GPLv3-only.
- MBSim uses Qt Quick 3D. Qt's own licensing documentation lists Qt Quick 3D
  under modules available under GNU GPL v3 for open-source users. Redistributors
  must either comply with the applicable GPL/LGPL obligations or use an
  appropriate commercial Qt license.
- Windows deployment may also include Qt Virtual Keyboard runtime files. Qt's
  licensing documentation lists Qt Virtual Keyboard under GNU GPL v3 for
  open-source users.
- OpenXLSX is used for Excel register-map support and is licensed under the
  BSD 3-Clause License.

See [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) for details and official
license references.

This repository does not provide legal advice. If you need to redistribute
MBSim, bundle it with another product, or use it in a controlled environment,
review the MBSim license and third-party licenses with qualified counsel.

## Release Assets

The zip files in Releases are the official distribution artifacts. Files copied
into this repository working tree are staging artifacts used by the release
script and are not intended to be committed.
