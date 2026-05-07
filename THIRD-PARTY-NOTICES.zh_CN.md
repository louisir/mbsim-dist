# 第三方组件授权说明

本文汇总 MBSim 发布包中的主要授权事项，供用户和再分发者参考。本文不是法律意见。

## MBSim

MBSim 自身的应用代码和文档采用专有免费软件授权。官方 MBSim 发布包可以免费安装和
使用。MBSim 不是开源软件，源码不公开。授权条款见 [LICENSE](LICENSE)。

打赏是对后续开发的自愿支持。打赏不会改变授权条款，也不会形成支持、保修、服务或
维护义务。

MBSim 的专有免费软件授权只适用于 MBSim 自身代码和文档，不会把随包发布的第三方
运行库重新授权。

## Qt 运行库

Windows 免安装包包含 Qt 运行库和 QML 模块。Qt 同时提供商业授权和开源授权。

Qt 官方授权参考：

- Qt Licensing: https://doc.qt.io/qt-6/licensing.html
- Qt GPL/LGPL obligations: https://www.qt.io/development/open-source-lgpl-obligations

本项目需要特别注意：

- 开源 Qt 并不等于全部都是 LGPL。Qt 官方文档说明，部分模块不是 LGPLv3，而是
  GNU GPL v3。
- MBSim 引入并使用了 Qt Quick 3D。Qt 官方授权页面将 Qt Quick 3D 列为开源用户
  可用的 GNU GPL v3 模块。
- Windows 部署包也可能包含 Qt Virtual Keyboard 运行时文件。Qt 官方授权页面将
  Qt Virtual Keyboard 也列为开源用户可用的 GNU GPL v3 模块。
- 如果使用开源 Qt 构建并分发 MBSim 二进制包，分发方需要确保满足相应 GPL/LGPL
  条款；或者使用合适的 Qt 商业授权。
- MBSim 的专有免费软件授权不会移除或削弱 Qt 自身的授权要求。

使用本项目发布脚本打包时，如果本机 Qt 安装目录中存在 Qt 许可证文本，脚本会把它们
复制到发布包的 `licenses/` 目录。

## OpenXLSX

MBSim 使用 OpenXLSX 支持 Excel 点表文件。

- 项目地址: https://github.com/troldal/OpenXLSX
- 许可证: BSD 3-Clause License

发布脚本会从本机 vcpkg 安装目录复制 OpenXLSX 的 copyright/license 文本到发布包的
`licenses/` 目录。

## OpenXLSX 运行时依赖

Windows 发布包中可能包含 vcpkg 安装的 OpenXLSX 运行时依赖：

- pugixml: MIT License
- nowide: Boost Software License 1.0

发布脚本会在这些许可证文件存在时复制到发布包的 `licenses/` 目录。

## MinGW/GCC 运行库

Windows 免安装包中可能包含 MinGW/GCC 运行库，例如 `libgcc_s_seh-1.dll`、
`libstdc++-6.dll` 和 `libwinpthread-1.dll`。这些组件受其自身运行库许可证和例外条款
约束。再次分发发布包时，应保留相关授权说明。

## 再分发检查清单

再次分发发布包前，建议确认：

1. 随包保留 MBSim 授权文件。
2. 随包保留第三方授权说明和许可证文本。
3. 如果再次分发或随产品提供 MBSim 自身程序，需取得版权持有人的书面许可，法律强制
   允许的情况除外。
4. 根据实际构建中包含的 Qt 模块，查阅 Qt 当前官方授权页面。
5. 如果基于开源 Qt 分发且包含 GPL-only 的 Qt 模块，需要确保分发行为符合 GPLv3；
   如果不能满足，应使用 Qt 商业授权。
