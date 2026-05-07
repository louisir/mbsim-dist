# MBSim 發布包

語言: [English](README.md) | [简体中文](README.zh_CN.md) | 繁體中文 |
[Deutsch](README.de.md) | [Español](README.es.md) |
[Français](README.fr.md) | [Italiano](README.it.md) |
[日本語](README.ja.md) | [한국어](README.ko.md)

本倉庫用於託管 MBSim 的編譯後發布包。MBSim 是一個 Modbus RTU/TCP 從站模擬器。

MBSim 以免費使用但不開源的形式發布，原始碼不公開。一般使用者應從 GitHub Releases
下載發布包，而不是 clone 本倉庫。

## 最新版本

- 最新版本: https://github.com/louisir/mbsim-dist/releases/latest
- 全部版本: https://github.com/louisir/mbsim-dist/releases

## Windows 免安裝包

請從最新 Release 的 Assets 下載 Windows x64 免安裝包：

- `MBSim-v<version>-portable-windows-x64.zip`
- `MBSim-v<version>-portable-windows-x64.zip.sha256`

下載後解壓縮 zip，執行其中的 `MBSim.exe`。

## 校驗 SHA256

在 PowerShell 中執行：

```powershell
Get-FileHash .\MBSim-v<version>-portable-windows-x64.zip -Algorithm SHA256
Get-Content .\MBSim-v<version>-portable-windows-x64.zip.sha256
```

`Get-FileHash` 輸出的雜湊值應與 `.sha256` 檔案中的值一致。

## 軟體授權和打賞

MBSim 自身的應用程式碼和文件採用專有免費軟體授權。你可以免費下載、安裝並使用官方
發布包。MBSim 不是開源軟體，原始碼不公開。授權條款見 [LICENSE](LICENSE)。

打賞是對後續開發的自願支持。打賞不是購買軟體，不會解鎖額外授權或功能，也不會
形成支援、保固、服務或維護義務。

未經著作權持有人另行書面許可，不應再次分發、出售、修改、反編譯或基於 MBSim 自身
程式建立衍生作品；法律強制允許的情況除外。第三方元件仍按各自授權處理。

免安裝包中還包含第三方執行時元件。這些第三方元件的授權獨立於 MBSim 的專有免費
軟體授權，使用或再次分發發布包時需要同時遵守對應授權。尤其需要注意：

- Qt 不是單一授權依賴。Qt 同時提供商業授權和開源授權。開源 Qt 中，許多模組
  使用 LGPLv3/GPLv3，但也有部分模組只按 GPLv3 提供。
- MBSim 使用 Qt Quick 3D。Qt 官方授權文件將 Qt Quick 3D 列在開源使用者可用的
  GNU GPL v3 模組中。因此，如果基於開源 Qt 分發 MBSim 二進位包，分發方需要遵守
  對應的 GPL/LGPL 條款，或使用合適的 Qt 商業授權。
- Windows 部署包也可能包含 Qt Virtual Keyboard 執行時檔案。Qt 官方授權文件將
  Qt Virtual Keyboard 也列為開源使用者可用的 GNU GPL v3 模組。
- OpenXLSX 用於 Excel 點表支援，使用 BSD 3-Clause License。

詳細說明和官方授權連結見
[THIRD-PARTY-NOTICES.zh_HK.md](THIRD-PARTY-NOTICES.zh_HK.md)。

本倉庫不提供法律意見。如果要再次分發 MBSim、把它隨產品一起提供，或在受控環境中
部署，請結合實際使用方式諮詢專業法律意見。

## 發布檔案

GitHub Releases 中的 zip 檔案才是正式發布產物。發布腳本複製到本倉庫工作區中的
zip 和 sha256 檔案只是上傳 Release 用的暫存檔案，不應提交到 git。
