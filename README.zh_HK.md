# MBSim 發布包

語言: [English](README.md) | [简体中文](README.zh_CN.md) | 繁體中文 |
[Deutsch](README.de.md) | [Español](README.es.md) |
[Français](README.fr.md) | [Italiano](README.it.md) |
[日本語](README.ja.md) | [한국어](README.ko.md)

MBSim 是一個面向除錯和聯調場景的 Modbus RTU/TCP 從站模擬器。它用於在沒有
真實設備、設備不方便接入，或需要批量建立測試資料時，模擬 Modbus 從站並配合
PLC、上位機、閘道、採集程式等主站系統進行驗證。

和傳統 Modbus Slave 類工具相比，MBSim 更偏向現代化的工程聯調體驗：界面更適合
當前 Windows 環境，支援透過點表組織模擬資料，並以免安裝包形式發布，方便在測試機、
現場電腦或臨時聯調環境中直接使用。

本倉庫是 MBSim 的發布倉庫，不包含原始碼。這裡提供 Windows x64 免安裝包、SHA256
校驗檔案、軟體授權條款和第三方元件授權說明。MBSim 以免費使用但不開源的形式發布，
原始碼不公開。

## 主要優勢

- Excel 點表驅動：可以用 `Points`、`Mappings`、`Simulation`、`Enums` 四張表描述
  完整設備點表，不需要逐個手工維護暫存器。
- 更接近真實設備語義：除了暫存器值，還可以描述點位名稱、分類、單位、枚舉、
  工程值、原始值、讀寫屬性等資訊。
- 支援工程值轉換：支援比例換算、偏移、表達式、Raw/Value 映射，以及 32 位、64 位、
  字串、bit field 等常見場景。
- 內建仿真行為：點位可以配置 `manual`、`const`、`rand`、`ramp`、`sine`、`expr`，
  適合模擬動態感測器、累計量、週期波動等資料。
- 執行時故障注入：可以按從站、功能碼、地址範圍、觸發次數或機率返回 Modbus 異常碼，
  用來測試主站的容錯和重試邏輯。
- 多從站和多實例：可以一次模擬一段 Slave ID，也可以啟動多個實例，適合測試主站輪詢
  多設備的場景。
- 點表校驗：載入 Excel 時會檢查表頭、引用、地址重疊、類型、表達式等問題，提前發現
  點表錯誤。

## 最新版本

- 最新版本: https://github.com/louisir/mbsim-dist/releases/latest
- 全部版本: https://github.com/louisir/mbsim-dist/releases

## 界面截圖和範例檔案

![MBSim 界面截圖](https://iamlouis.online/GY21249.jpg)

- 範例協議: [GY21249.pdf](https://www.iamlouis.online/GY21249.pdf)
- 範例點表: [XY-MD03_GY21249.xlsx](https://www.iamlouis.online/XY-MD03_GY21249.xlsx)

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
發布包。MBSim 不是開源軟體，原始碼不公開。授權條款見 [LICENSE](LICENSE.zh_HK.md)。

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
