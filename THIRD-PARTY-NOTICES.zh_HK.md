# 第三方元件授權說明

本文彙總 MBSim 發布包中的主要授權事項，供使用者和再次分發者參考。本文不是法律意見。

## MBSim

MBSim 自身的應用程式碼和文件採用專有免費軟體授權。官方 MBSim 發布包可以免費安裝和
使用。MBSim 不是開源軟體，原始碼不公開。授權條款見 [LICENSE](LICENSE.zh_HK.md)。

打賞是對後續開發的自願支持。打賞不會改變授權條款，也不會形成支援、保固、服務或
維護義務。

MBSim 的專有免費軟體授權只適用於 MBSim 自身程式碼和文件，不會把隨包發布的第三方
執行時函式庫重新授權。

## Qt 執行時

Windows 免安裝包包含 Qt 執行時函式庫和 QML 模組。Qt 同時提供商業授權和開源授權。

Qt 官方授權參考：

- Qt Licensing: https://doc.qt.io/qt-6/licensing.html
- Qt GPL/LGPL obligations: https://www.qt.io/development/open-source-lgpl-obligations

本專案需要特別注意：

- 開源 Qt 不等於全部都是 LGPL。Qt 官方文件說明，部分模組不是 LGPLv3，而是 GNU GPL v3。
- MBSim 引入並使用了 Qt Quick 3D。Qt 官方授權頁面將 Qt Quick 3D 列為開源使用者可用的 GNU GPL v3 模組。
- Windows 部署包也可能包含 Qt Virtual Keyboard 執行時檔案。Qt 官方授權頁面將 Qt Virtual Keyboard 也列為開源使用者可用的 GNU GPL v3 模組。
- 如果使用開源 Qt 建置並分發 MBSim 二進位包，分發方需要確保滿足相應 GPL/LGPL 條款；或者使用合適的 Qt 商業授權。
- MBSim 的專有免費軟體授權不會移除或削弱 Qt 自身的授權要求。

使用本專案發布腳本打包時，如果本機 Qt 安裝目錄中存在 Qt 授權文字，腳本會把它們複製到發布包的 `licenses/` 目錄。

## OpenXLSX

MBSim 使用 OpenXLSX 支援 Excel 點表檔案。

- 專案地址: https://github.com/troldal/OpenXLSX
- 授權: BSD 3-Clause License

發布腳本會從本機 vcpkg 安裝目錄複製 OpenXLSX 的 copyright/license 文字到發布包的 `licenses/` 目錄。

## OpenXLSX 執行時依賴

Windows 發布包中可能包含 vcpkg 安裝的 OpenXLSX 執行時依賴：

- pugixml: MIT License
- nowide: Boost Software License 1.0

發布腳本會在這些授權檔案存在時複製到發布包的 `licenses/` 目錄。

## MinGW/GCC 執行時

Windows 免安裝包中可能包含 MinGW/GCC 執行時函式庫，例如 `libgcc_s_seh-1.dll`、`libstdc++-6.dll` 和 `libwinpthread-1.dll`。這些元件受其自身執行時授權和例外條款約束。再次分發發布包時，應保留相關授權說明。

## 再次分發檢查清單

再次分發發布包前，建議確認：

1. 隨包保留 MBSim 授權檔案。
2. 隨包保留第三方授權說明和授權文字。
3. 如果再次分發或隨產品提供 MBSim 自身程式，需取得著作權持有人的書面許可，法律強制允許的情況除外。
4. 根據實際建置中包含的 Qt 模組，查閱 Qt 目前官方授權頁面。
5. 如果基於開源 Qt 分發且包含 GPL-only 的 Qt 模組，需要確保分發行為符合 GPLv3；如果不能滿足，應使用 Qt 商業授權。
