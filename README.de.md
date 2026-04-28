# MBSim Releases

Sprachen: [English](README.md) | [简体中文](README.zh_CN.md) |
[繁體中文](README.zh_TW.md) | Deutsch | [Español](README.es.md) |
[Français](README.fr.md) | [Italiano](README.it.md) |
[日本語](README.ja.md) | [한국어](README.ko.md)

Dieses Repository stellt kompilierte Release-Pakete fuer MBSim bereit, einen
Modbus-RTU/TCP-Slave-Simulator.

Der Quellcode wird separat verwaltet. Benutzer sollten Pakete aus GitHub
Releases herunterladen, anstatt dieses Repository zu klonen.

## Aktuelles Release

- Aktuelles Release: https://github.com/louisir/mbsim-dist/releases/latest
- Alle Releases: https://github.com/louisir/mbsim-dist/releases

## Windows-Portable-Paket

Laden Sie das Windows-x64-Portable-Paket aus den Assets des aktuellen Releases:

- `MBSim-v<version>-portable-windows-x64.zip`
- `MBSim-v<version>-portable-windows-x64.zip.sha256`

Entpacken Sie die ZIP-Datei und starten Sie `MBSim.exe`.

## SHA256 Pruefung

In PowerShell:

```powershell
Get-FileHash .\MBSim-v<version>-portable-windows-x64.zip -Algorithm SHA256
Get-Content .\MBSim-v<version>-portable-windows-x64.zip.sha256
```

Der von `Get-FileHash` ausgegebene Hash muss mit dem Wert in der `.sha256`-
Datei uebereinstimmen.

## Lizenzierung

Der eigene MBSim-Anwendungscode und die Dokumentation stehen unter der MIT
License. Siehe [LICENSE](LICENSE).

Das Portable-Paket enthaelt auch Laufzeitkomponenten von Drittanbietern. Deren
Lizenzen sind von der MIT License von MBSim getrennt und muessen bei Nutzung
oder Weiterverteilung beachtet werden:

- Qt ist keine Abhaengigkeit mit nur einer Lizenz. Qt ist unter kommerziellen
  und Open-Source-Lizenzoptionen verfuegbar. Bei Open-Source-Qt sind viele
  Module LGPLv3/GPLv3, einige Module jedoch nur GPLv3.
- MBSim verwendet Qt Quick 3D. Die Qt-Lizenzdokumentation fuehrt Qt Quick 3D
  fuer Open-Source-Nutzer als GNU-GPL-v3-Modul auf. Weiterverteiler muessen die
  passenden GPL/LGPL-Pflichten erfuellen oder eine passende kommerzielle
  Qt-Lizenz verwenden.
- Die Windows-Bereitstellung kann auch Qt-Virtual-Keyboard-Laufzeitdateien
  enthalten. Auch Qt Virtual Keyboard wird in der Qt-Lizenzdokumentation fuer
  Open-Source-Nutzer als GNU-GPL-v3-Modul aufgefuehrt.
- OpenXLSX wird fuer Excel-Registertabellen verwendet und steht unter der
  BSD 3-Clause License.

Details und offizielle Referenzen finden Sie in
[THIRD-PARTY-NOTICES.de.md](THIRD-PARTY-NOTICES.de.md).

Dieses Repository bietet keine Rechtsberatung. Pruefen Sie die relevanten
Lizenzen mit qualifiziertem Rechtsbeistand, wenn Sie MBSim kommerziell oder in
einer kontrollierten Umgebung weiterverteilen.

## Release-Dateien

Die ZIP-Dateien in GitHub Releases sind die offiziellen Distributionsartefakte.
Dateien, die das Release-Skript in diesen Arbeitsbaum kopiert, sind nur
Staging-Artefakte fuer den Upload und sollten nicht in git committet werden.
