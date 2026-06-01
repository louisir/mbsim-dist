# MBSim 发布包

语言: [English](README.md) | 简体中文 | [繁體中文](README.zh_HK.md) |
[Deutsch](README.de.md) | [Español](README.es.md) |
[Français](README.fr.md) | [Italiano](README.it.md) |
[日本語](README.ja.md) | [한국어](README.ko.md)

MBSim 是一个面向调试和联调场景的 Modbus RTU/TCP 从站模拟器。它用于在没有
真实设备、设备不方便接入，或需要批量构造测试数据时，模拟 Modbus 从站并配合
PLC、上位机、网关、采集程序等主站系统进行验证。

和传统 Modbus Slave 类工具相比，MBSim 更偏向现代化的工程联调体验：界面更适合
当前 Windows 环境，支持通过点表组织模拟数据，并以免安装包形式发布，方便在测试机、
现场电脑或临时联调环境中直接使用。

本仓库是 MBSim 的发布仓库，不包含源码。这里提供 Windows x64 免安装包、SHA256
校验文件、软件授权条款和第三方组件授权说明。MBSim 以免费使用但不开源的形式发布，
源码不公开。

## 主要优势

- Excel 点表驱动：可以用 `Points`、`Mappings`、`Simulation`、`Enums` 四张表描述
  完整设备点表，不需要逐个手工维护寄存器。
- 更接近真实设备语义：除了寄存器值，还可以描述点位名称、分类、单位、枚举、
  工程值、原始值、读写属性等信息。
- 支持工程值转换：支持比例换算、偏移、表达式、Raw/Value 映射，以及 32 位、64 位、
  字符串、bit field 等常见场景。
- 内置仿真行为：点位可以配置 `manual`、`const`、`rand`、`ramp`、`sine`、`expr`，
  适合模拟动态传感器、累计量、周期波动等数据。
- 运行时故障注入：可以按从站、功能码、地址范围、触发次数或概率返回 Modbus 异常码，
  用来测试主站的容错和重试逻辑。
- 多从站和多实例：可以一次模拟一段 Slave ID，也可以启动多个实例，适合测试主站轮询
  多设备的场景。
- 点表校验：加载 Excel 时会检查表头、引用、地址重叠、类型、表达式等问题，提前发现
  点表错误。

## 最新版本

- 最新版本: https://github.com/louisir/mbsim-dist/releases/latest
- 全部版本: https://github.com/louisir/mbsim-dist/releases

## 界面截图和示例文件

![MBSim 界面截图](https://www.iamlouis.online/20210802093110vmwpnx.jpg)

- 示例协议: [20210802093110vmwpnx.pdf](https://www.iamlouis.online/20210802093110vmwpnx.pdf)
- 示例点表: [20210802093110vmwpnx.xlsx](https://www.iamlouis.online/20210802093110vmwpnx.xlsx)

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
发布包。MBSim 不是开源软件，源码不公开。授权条款见 [LICENSE](LICENSE.zh_CN.md)。

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
