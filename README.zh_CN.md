# MBSim 发布包

语言: [English](README.md) | 简体中文 | [繁體中文](README.zh_TW.md) |
[Deutsch](README.de.md) | [Español](README.es.md) |
[Français](README.fr.md) | [Italiano](README.it.md) |
[日本語](README.ja.md) | [한국어](README.ko.md)

本仓库用于托管 MBSim 的编译后发布包。MBSim 是一个 Modbus RTU/TCP 从站模拟器。

MBSim 以免费使用但不开源的形式发布，源码不公开。普通用户应从 GitHub Releases
下载发布包，而不是 clone 本仓库。

## 最新版本

- 最新版本: https://github.com/louisir/mbsim-dist/releases/latest
- 全部版本: https://github.com/louisir/mbsim-dist/releases

## Windows 免安装包

请从最新 Release 的 Assets 中下载 Windows x64 免安装包：

- `MBSim-v<version>-portable-windows-x64.zip`
- `MBSim-v<version>-portable-windows-x64.zip.sha256`

下载后解压 zip，运行其中的 `MBSim.exe`。

## 校验 SHA256

在 PowerShell 中执行：

```powershell
Get-FileHash .\MBSim-v<version>-portable-windows-x64.zip -Algorithm SHA256
Get-Content .\MBSim-v<version>-portable-windows-x64.zip.sha256
```

`Get-FileHash` 输出的哈希值应与 `.sha256` 文件中的值一致。

## 软件授权和打赏

MBSim 自身的应用代码和文档采用专有免费软件授权。你可以免费下载安装并使用官方
发布包。MBSim 不是开源软件，源码不公开。授权条款见 [LICENSE](LICENSE)。

打赏是对后续开发的自愿支持。打赏不是购买软件，不会解锁额外授权或功能，也不会
形成支持、保修、服务或维护义务。

未经版权持有人另行书面许可，不应再次分发、出售、修改、反编译或基于 MBSim 自身
程序创建衍生作品；法律强制允许的情况除外。第三方组件仍按各自许可证处理。

免安装包中还包含第三方运行库。这些第三方组件的许可证独立于 MBSim 的专有免费软件
授权，使用或再次分发发布包时需要同时遵守对应许可证。尤其需要注意：

- Qt 不是单一许可证依赖。Qt 同时提供商业授权和开源授权。开源 Qt 中，很多模块
  使用 LGPLv3/GPLv3，但也有部分模块只按 GPLv3 提供。
- MBSim 使用了 Qt Quick 3D。Qt 官方授权文档将 Qt Quick 3D 列在开源用户可用的
  GNU GPL v3 模块中。因此，如果基于开源 Qt 分发 MBSim 二进制包，分发方需要遵守
  对应的 GPL/LGPL 条款，或者使用合适的 Qt 商业授权。
- Windows 部署包也可能包含 Qt Virtual Keyboard 运行时文件。Qt 官方授权文档将
  Qt Virtual Keyboard 也列为开源用户可用的 GNU GPL v3 模块。
- OpenXLSX 用于 Excel 点表支持，使用 BSD 3-Clause License。

详细说明和官方授权链接见
[THIRD-PARTY-NOTICES.zh_CN.md](THIRD-PARTY-NOTICES.zh_CN.md)。

本仓库不提供法律意见。如果要再次分发 MBSim、把它随产品一起提供，或在受控环境中
部署，请结合实际使用方式咨询专业法律意见。

## 发布文件

GitHub Releases 中的 zip 文件才是正式发布产物。发布脚本复制到本仓库工作区中的
zip 和 sha256 文件只是上传 Release 用的临时 staging 文件，不应提交到 git。
