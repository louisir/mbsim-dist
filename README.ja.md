# MBSim リリース

言語: [English](README.md) | [简体中文](README.zh_CN.md) |
[繁體中文](README.zh_HK.md) | [Deutsch](README.de.md) |
[Español](README.es.md) | [Français](README.fr.md) |
[Italiano](README.it.md) | 日本語 | [한국어](README.ko.md)

このリポジトリは、Modbus RTU/TCP スレーブシミュレータである MBSim の
コンパイル済みリリースパッケージを配布するためのものです。

MBSim は無料で利用できるプロプライエタリソフトウェアとして配布されます。ソースコード
は公開されていません。利用者はこのリポジトリを clone するのではなく、GitHub
Releases からパッケージをダウンロードしてください。

## 最新リリース

- 最新リリース: https://github.com/louisir/mbsim-dist/releases/latest
- すべてのリリース: https://github.com/louisir/mbsim-dist/releases

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
