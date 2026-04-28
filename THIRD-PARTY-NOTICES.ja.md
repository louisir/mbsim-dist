# サードパーティ通知

この文書は、MBSim リリースパッケージに関する主なライセンス上の注意点をまとめたものです。利用者および再配布者向けの実務的な通知であり、法的助言ではありません。

## MBSim

MBSim 自身のアプリケーションコードとドキュメントは MIT License で配布されます。[LICENSE](LICENSE) を参照してください。

MIT License は MBSim 自身のコードに適用されます。ポータブルパッケージに同梱されるサードパーティのランタイムライブラリを MIT として再ライセンスするものではありません。

## Qt Runtime

Windows ポータブルパッケージには Qt ランタイムライブラリと QML モジュールが含まれます。Qt には商用ライセンスとオープンソースライセンスを含む複数のライセンス形態があります。

Qt 公式ライセンス参照：

- Qt Licensing: https://doc.qt.io/qt-6/licensing.html
- Qt GPL/LGPL obligations: https://www.qt.io/development/open-source-lgpl-obligations

このプロジェクトで重要な点：

- オープンソース Qt の利用は、自動的に「LGPL のみ」を意味しません。Qt のドキュメントでは、一部のモジュールが LGPLv3 ではなく GNU GPL v3 で提供されることが示されています。
- MBSim は Qt Quick 3D を import して使用します。Qt のライセンスページでは、Qt Quick 3D はオープンソース利用者向けに GNU GPL v3 で提供されるモジュールとして記載されています。
- Windows 配布物には Qt Virtual Keyboard のランタイムファイルが含まれる場合もあります。Qt のライセンスページでは、Qt Virtual Keyboard もオープンソース利用者向けに GNU GPL v3 で提供されるモジュールとして記載されています。
- オープンソース Qt でビルドしたバイナリパッケージを再配布する場合、適用される GPL/LGPL の義務を満たすか、適切な Qt 商用ライセンスを使用する必要があります。
- MBSim の MIT License は、Qt のライセンス要件を削除または弱めるものではありません。

提供されているリリーススクリプトでパッケージを作成する場合、ローカルの Qt インストールに Qt ライセンステキストが存在すれば、パッケージ内の `licenses/` ディレクトリにコピーされます。

## OpenXLSX

MBSim は Excel レジスタマップ対応のために OpenXLSX を使用します。

- Project: https://github.com/troldal/OpenXLSX
- License: BSD 3-Clause License

リリーススクリプトは、ローカルの vcpkg インストールから OpenXLSX の copyright/license テキストをパッケージ内の `licenses/` ディレクトリにコピーします。

## OpenXLSX ランタイム依存関係

Windows パッケージには、vcpkg によりインストールされた OpenXLSX ランタイム依存関係が含まれる場合があります。

- pugixml: MIT License
- nowide: Boost Software License 1.0

これらの vcpkg copyright/license ファイルが存在する場合、リリーススクリプトはパッケージ内の `licenses/` ディレクトリにコピーします。

## MinGW/GCC Runtime

Windows ポータブルパッケージには、`libgcc_s_seh-1.dll`、`libstdc++-6.dll`、`libwinpthread-1.dll` などの MinGW/GCC ランタイムライブラリが含まれる場合があります。これらのコンポーネントには、それぞれのランタイムライセンスと例外条項が適用されます。パッケージを再配布する場合は、関連する通知を保持してください。

## 再配布チェックリスト

パッケージを再配布する前に：

1. MBSim の MIT License をパッケージに同梱してください。
2. サードパーティ通知とライセンステキストをパッケージに同梱してください。
3. ビルドに含まれる正確な Qt モジュールについて、Qt の最新ライセンスページを確認してください。
4. オープンソース Qt と GPL-only の Qt モジュールを含むパッケージを配布する場合は、配布が GPLv3 に準拠していることを確認するか、Qt 商用ライセンスを使用してください。
