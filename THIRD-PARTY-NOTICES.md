# Third-Party Notices

This document summarizes the main licensing obligations for MBSim release
packages. It is a practical notice for users and redistributors; it is not legal
advice.

## MBSim

MBSim's own application code and documentation are proprietary freeware.
Official MBSim release packages may be installed and used free of charge. MBSim
is not open-source software, and source code is not published. See
[LICENSE](LICENSE).

Donations, when available, are voluntary support for future development. They do
not change license terms or create support, warranty, service, or maintenance
obligations.

The MBSim freeware license applies only to MBSim's own code and documentation.
It does not relicense third-party runtime libraries shipped with the portable
package.

## Qt Runtime

The Windows portable package includes Qt runtime libraries and QML modules.
Qt is available under different licensing options, including commercial licenses
and open-source licenses.

Official Qt licensing references:

- Qt Licensing: https://doc.qt.io/qt-6/licensing.html
- Qt GPL/LGPL obligations: https://www.qt.io/development/open-source-lgpl-obligations

Important points for this project:

- Qt open-source usage is not automatically "LGPL only". Qt's documentation
  states that some modules are available under GNU GPL v3 rather than LGPLv3.
- MBSim imports and uses Qt Quick 3D. Qt's licensing page lists Qt Quick 3D as a
  module available under GNU GPL v3 for open-source users.
- The Windows deployment may also include Qt Virtual Keyboard runtime files.
  Qt's licensing page lists Qt Virtual Keyboard as a module available under GNU
  GPL v3 for open-source users.
- A redistributor of a binary package built with open-source Qt must ensure that
  the applicable GPL/LGPL obligations are satisfied, or use an appropriate
  commercial Qt license.
- The MBSim freeware license does not remove or weaken the Qt license
  requirements.

When a release package is built by the provided script, Qt license texts are
copied into the package's `licenses/` directory when they are available in the
local Qt installation.

## OpenXLSX

MBSim uses OpenXLSX for Excel register-map support.

- Project: https://github.com/troldal/OpenXLSX
- License: BSD 3-Clause License

The provided release script copies the OpenXLSX copyright/license text from the
local vcpkg installation into the package's `licenses/` directory.

## OpenXLSX Runtime Dependencies

The Windows package may include OpenXLSX runtime dependencies installed by
vcpkg:

- pugixml: MIT License
- nowide: Boost Software License 1.0

The provided release script copies their vcpkg copyright/license files into the
package's `licenses/` directory when present.

## MinGW/GCC Runtime

The Windows portable package may include MinGW/GCC runtime libraries such as
`libgcc_s_seh-1.dll`, `libstdc++-6.dll`, and `libwinpthread-1.dll`. These
components are governed by their own runtime licenses and exceptions. Preserve
the relevant notices when redistributing the package.

## Redistribution Checklist

Before redistributing a package:

1. Keep the MBSim license with the package.
2. Keep the third-party notices and license texts with the package.
3. If redistributing or bundling MBSim itself, obtain written permission from
   the copyright holder unless mandatory law provides otherwise.
4. Review Qt's current licensing page for the exact modules included in your
   build.
5. If distributing a package built with open-source Qt and GPL-only Qt modules,
   make sure the distribution complies with GPLv3, or use a commercial Qt
   license.
