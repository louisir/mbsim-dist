# Hinweise zu Drittanbieter-Lizenzen

Dieses Dokument fasst die wichtigsten Lizenzthemen fuer MBSim-Release-Pakete zusammen. Es ist ein praktischer Hinweis fuer Nutzer und Weiterverteiler und keine Rechtsberatung.

## MBSim

Der eigene Anwendungscode und die Dokumentation von MBSim werden unter der MIT License verteilt. Siehe [LICENSE](LICENSE).

Die MIT License gilt fuer den eigenen MBSim-Code. Sie lizenziert die mitgelieferten Drittanbieter-Laufzeitbibliotheken nicht erneut als MIT.

## Qt Runtime

Das Windows-Portable-Paket enthaelt Qt-Laufzeitbibliotheken und QML-Module. Qt ist unter verschiedenen Lizenzoptionen verfuegbar, darunter kommerzielle Lizenzen und Open-Source-Lizenzen.

Offizielle Qt-Lizenzreferenzen:

- Qt Licensing: https://doc.qt.io/qt-6/licensing.html
- Qt GPL/LGPL obligations: https://www.qt.io/development/open-source-lgpl-obligations

Wichtige Punkte fuer dieses Projekt:

- Open-Source-Qt ist nicht automatisch nur LGPL. Die Qt-Dokumentation erklaert, dass manche Module unter GNU GPL v3 statt LGPLv3 verfuegbar sind.
- MBSim importiert und verwendet Qt Quick 3D. Die Qt-Lizenzseite listet Qt Quick 3D fuer Open-Source-Nutzer als Modul unter GNU GPL v3.
- Die Windows-Bereitstellung kann auch Qt-Virtual-Keyboard-Laufzeitdateien enthalten. Die Qt-Lizenzseite listet auch Qt Virtual Keyboard fuer Open-Source-Nutzer als Modul unter GNU GPL v3.
- Wer ein binaeres Paket mit Open-Source-Qt weiterverteilt, muss sicherstellen, dass die anwendbaren GPL/LGPL-Pflichten eingehalten werden, oder eine passende kommerzielle Qt-Lizenz verwenden.
- Die MIT License von MBSim entfernt oder schwaecht die Qt-Lizenzanforderungen nicht.

Wenn ein Release-Paket mit dem bereitgestellten Skript gebaut wird, werden Qt-Lizenztexte in das Verzeichnis `licenses/` des Pakets kopiert, sofern sie in der lokalen Qt-Installation vorhanden sind.

## OpenXLSX

MBSim verwendet OpenXLSX fuer Excel-Registertabellen.

- Projekt: https://github.com/troldal/OpenXLSX
- Lizenz: BSD 3-Clause License

Das Release-Skript kopiert den OpenXLSX-Copyright-/Lizenztext aus der lokalen vcpkg-Installation in das Verzeichnis `licenses/` des Pakets.

## OpenXLSX-Laufzeitabhaengigkeiten

Das Windows-Paket kann OpenXLSX-Laufzeitabhaengigkeiten enthalten, die ueber vcpkg installiert wurden:

- pugixml: MIT License
- nowide: Boost Software License 1.0

Das Release-Skript kopiert deren vcpkg-Copyright-/Lizenzdateien in das Verzeichnis `licenses/` des Pakets, wenn sie vorhanden sind.

## MinGW/GCC Runtime

Das Windows-Portable-Paket kann MinGW/GCC-Laufzeitbibliotheken wie `libgcc_s_seh-1.dll`, `libstdc++-6.dll` und `libwinpthread-1.dll` enthalten. Diese Komponenten unterliegen ihren eigenen Runtime-Lizenzen und Ausnahmen. Bewahren Sie die relevanten Hinweise auf, wenn Sie das Paket weiterverteilen.

## Checkliste fuer Weiterverteilung

Vor der Weiterverteilung eines Pakets:

1. Behalten Sie die MBSim MIT License im Paket.
2. Behalten Sie die Drittanbieter-Hinweise und Lizenztexte im Paket.
3. Pruefen Sie die aktuelle Qt-Lizenzseite fuer die in Ihrem Build enthaltenen Module.
4. Wenn Sie ein Paket mit Open-Source-Qt und GPL-only-Qt-Modulen verteilen, stellen Sie die Einhaltung von GPLv3 sicher oder verwenden Sie eine kommerzielle Qt-Lizenz.
