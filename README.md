# MBSim Releases

Languages: English | [简体中文](README.zh_CN.md) |
[繁體中文](README.zh_HK.md) | [Deutsch](README.de.md) |
[Español](README.es.md) | [Français](README.fr.md) |
[Italiano](README.it.md) | [日本語](README.ja.md) |
[한국어](README.ko.md)

MBSim is a Modbus RTU/TCP slave simulator for debugging and integration
scenarios. It lets you simulate Modbus slaves when real devices are unavailable,
inconvenient to connect, or when you need to construct test data in bulk for
validation with PLCs, host applications, gateways, data collection programs,
and other Modbus masters.

Compared with traditional Modbus Slave-style tools, MBSim is oriented toward a
more modern engineering integration experience: the interface fits current
Windows environments, simulated data can be organized through register maps,
and the portable package can be used directly on test machines, site computers,
or temporary integration environments.

This repository is the MBSim release repository and does not contain source
code. It provides the Windows x64 portable package, SHA256 checksum files,
software license terms, and third-party component license notices. MBSim is
distributed as proprietary freeware, and source code is not published.

## Key Advantages

- Excel register-map driven: use the `Points`, `Mappings`, `Simulation`, and
  `Enums` sheets to describe a complete device register map without manually
  maintaining registers one by one.
- Closer to real device semantics: in addition to register values, you can
  describe point names, categories, units, enums, engineering values, raw
  values, read/write attributes, and related information.
- Engineering value conversion: supports scaling, offsets, expressions,
  Raw/Value mappings, and common cases such as 32-bit values, 64-bit values,
  strings, and bit fields.
- Built-in simulation behavior: points can be configured as `manual`, `const`,
  `rand`, `ramp`, `sine`, or `expr`, which is useful for simulating dynamic
  sensors, accumulators, periodic fluctuations, and similar data.
- Runtime fault injection: return Modbus exception codes by slave, function
  code, address range, trigger count, or probability to test master-side
  tolerance and retry logic.
- Multiple slaves and instances: simulate a range of Slave IDs at once, or
  launch multiple instances for testing master polling across many devices.
- Register-map validation: when loading Excel files, MBSim checks headers,
  references, address overlaps, types, expressions, and related issues to catch
  register-map errors early.

## Latest Release

- Latest release: https://github.com/louisir/mbsim-dist/releases/latest
- All releases: https://github.com/louisir/mbsim-dist/releases

## Screenshots and Example Files

![MBSim interface screenshot](https://www.iamlouis.online/20210802093110vmwpnx.jpg)

- Sample protocol: [20210802093110vmwpnx.pdf](https://www.iamlouis.online/20210802093110vmwpnx.pdf)
- Sample register map: [20210802093110vmwpnx.xlsx](https://www.iamlouis.online/20210802093110vmwpnx.xlsx)

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
