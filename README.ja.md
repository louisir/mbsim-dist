# MBSim リリース

言語: [English](README.md) | [简体中文](README.zh_CN.md) |
[繁體中文](README.zh_HK.md) | [Deutsch](README.de.md) |
[Español](README.es.md) | [Français](README.fr.md) |
[Italiano](README.it.md) | 日本語 | [한국어](README.ko.md)

MBSim は、デバッグや連携テスト向けの Modbus RTU/TCP スレーブシミュレータです。
実機がない場合、機器を接続しにくい場合、またはテストデータをまとめて作成する必要が
ある場合に Modbus スレーブを模擬し、PLC、上位アプリケーション、ゲートウェイ、
データ収集プログラムなどのマスターシステムと組み合わせて検証できます。

従来の Modbus Slave 系ツールと比べて、MBSim はより現代的なエンジニアリング連携
体験を重視しています。現在の Windows 環境に適したインターフェイス、レジスタマップ
によるシミュレーションデータの整理、インストール不要のパッケージにより、テスト機、
現場 PC、一時的な連携テスト環境でそのまま利用できます。

このリポジトリは MBSim のリリース用リポジトリであり、ソースコードは含まれていません。
ここでは Windows x64 ポータブルパッケージ、SHA256 検証ファイル、ソフトウェア
ライセンス条項、サードパーティコンポーネントのライセンス説明を提供します。MBSim は
無料で利用できるプロプライエタリソフトウェアとして配布され、ソースコードは公開されて
いません。

## 主な利点

- Excel 点表駆動: `Points`、`Mappings`、`Simulation`、`Enums` の 4 つのシートで
  完全なデバイス点表を記述でき、レジスタを 1 つずつ手作業で管理する必要がありません。
- 実機の意味により近い表現: レジスタ値だけでなく、点名、分類、単位、列挙値、
  工学値、Raw 値、読み書き属性などの情報を記述できます。
- 工学値変換に対応: スケール変換、オフセット、式、Raw/Value マッピング、32 ビット、
  64 ビット、文字列、bit field などの一般的な場面に対応します。
- 内蔵シミュレーション動作: 点は `manual`、`const`、`rand`、`ramp`、`sine`、`expr`
  として設定でき、動的センサー、積算値、周期的な変動などのデータを模擬するのに適しています。
- 実行時の故障注入: スレーブ、ファンクションコード、アドレス範囲、発生回数、確率に
  応じて Modbus 例外コードを返し、マスター側の耐障害性やリトライ処理をテストできます。
- 複数スレーブと複数インスタンス: 一連の Slave ID を一度に模擬したり、複数インスタンス
  を起動したりでき、多数デバイスをポーリングするマスターのテストに適しています。
- 点表検証: Excel 読み込み時にヘッダー、参照、アドレス重複、型、式などをチェックし、
  点表の誤りを早期に検出します。

## 最新リリース

- 最新リリース: https://github.com/louisir/mbsim-dist/releases/latest
- すべてのリリース: https://github.com/louisir/mbsim-dist/releases

## 画面キャプチャとサンプルファイル

![MBSim インターフェイスの画面キャプチャ](https://iamlouis.online/2026-06-02_17-44-44.jpg)

- サンプルプロトコル: [GY21249.pdf](https://www.iamlouis.online/GY21249.pdf)
- サンプルレジスタマップ: [XY-MD03_GY21249.xlsx](https://www.iamlouis.online/XY-MD03_GY21249.xlsx)

## Windows ポータブルパッケージ

最新リリースの Assets から Windows x64 ポータブルパッケージをダウンロードします。

- `MBSim-v<version>-portable-windows-x64.zip`
- `MBSim-v<version>-portable-windows-x64.zip.sha256`

ダウンロード後、zip を展開して `MBSim.exe` を実行してください。

## SHA256 の確認

PowerShell で実行します。

```powershell
Get-FileHash .\MBSim-v<version>-portable-windows-x64.zip -Algorithm SHA256
Get-Content .\MBSim-v<version>-portable-windows-x64.zip.sha256
```

`Get-FileHash` のハッシュ値が `.sha256` ファイルの値と一致する必要があります。

## ライセンスと寄付

MBSim 独自のアプリケーションコードとドキュメントは、無料で利用できるプロプライエタリ
ソフトウェアとして提供されます。公式 MBSim リリースパッケージは無料でインストール
して使用できます。MBSim はオープンソースソフトウェアではなく、ソースコードは公開されて
いません。[LICENSE](LICENSE.ja.md) を参照してください。

寄付は将来の開発を支援するための任意のものです。寄付は購入ではなく、追加の
ライセンス権や機能を解放するものではなく、サポート、保証、サービス、保守の義務を
発生させるものでもありません。

MBSim 自体の再配布、販売、変更、リバースエンジニアリング、または派生物の作成には、
権利者からの別途の書面許可が必要です。ただし、強行法規が別途認める場合を
除きます。サードパーティコンポーネントはそれぞれのライセンスに従います。

ポータブルパッケージにはサードパーティのランタイムコンポーネントも含まれます。
それらのライセンスは MBSim の freeware ライセンスとは別であり、利用または再配布
する際に遵守する必要があります。

- Qt は単一ライセンスの依存関係ではありません。Qt には商用ライセンスと
  オープンソースライセンスがあります。オープンソース Qt では多くのモジュールが
  LGPLv3/GPLv3 ですが、一部のモジュールは GPLv3 のみです。
- MBSim は Qt Quick 3D を使用します。Qt のライセンス文書では、Qt Quick 3D は
  オープンソース利用者向けの GNU GPL v3 モジュールとして記載されています。
  再配布者は該当する GPL/LGPL の義務を満たすか、適切な Qt 商用ライセンスを
  使用する必要があります。
- Windows 配布物には Qt Virtual Keyboard のランタイムファイルも含まれる場合が
  あります。Qt の文書では Qt Virtual Keyboard も GNU GPL v3 モジュールとして
  記載されています。
- OpenXLSX は Excel レジスタマップ対応に使用され、BSD 3-Clause License です。

詳細と公式参照は [THIRD-PARTY-NOTICES.ja.md](THIRD-PARTY-NOTICES.ja.md) を
参照してください。

このリポジトリは法的助言を提供しません。MBSim を再配布したり、別の製品に同梱
したり、管理された環境で使用したりする必要がある場合は、MBSim ライセンスと
サードパーティライセンスを資格のある専門家に確認してください。

## リリースファイル

GitHub Releases の zip ファイルが正式な配布物です。リリーススクリプトによって
この作業ツリーにコピーされた zip と sha256 ファイルはアップロード用の staging
ファイルであり、git に commit するものではありません。
