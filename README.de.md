# MBSim Releases

Sprachen: [English](README.md) | [简体中文](README.zh_CN.md) |
[繁體中文](README.zh_HK.md) | Deutsch | [Español](README.es.md) |
[Français](README.fr.md) | [Italiano](README.it.md) |
[日本語](README.ja.md) | [한국어](README.ko.md)

MBSim ist ein Modbus-RTU/TCP-Slave-Simulator fuer Debugging- und
Integrationsszenarien. Er kann Modbus-Slaves simulieren, wenn reale Geraete
nicht verfuegbar oder schwer anzuschliessen sind, oder wenn Testdaten in groesserem
Umfang fuer die Validierung mit PLCs, Host-Anwendungen, Gateways,
Datenerfassungsprogrammen und anderen Modbus-Mastern aufgebaut werden muessen.

Im Vergleich zu klassischen Modbus-Slave-Werkzeugen ist MBSim staerker auf eine
moderne Engineering-Integrationserfahrung ausgerichtet: Die Oberflaeche passt
zu aktuellen Windows-Umgebungen, simulierte Daten lassen sich ueber
Registertabellen organisieren, und das Portable-Paket kann direkt auf
Testrechnern, Vor-Ort-PCs oder in temporaeren Integrationsumgebungen genutzt
werden.

Dieses Repository ist das MBSim-Release-Repository und enthaelt keinen
Quellcode. Es stellt das Windows-x64-Portable-Paket, SHA256-Pruefsummendateien,
Software-Lizenzbedingungen und Lizenzhinweise zu Drittanbieterkomponenten
bereit. MBSim wird als proprietaere Freeware verteilt, und der Quellcode wird
nicht veroeffentlicht.

## Hauptvorteile

- Excel-Registertabellen: Mit den vier Tabellen `Points`, `Mappings`,
  `Simulation` und `Enums` kann eine vollstaendige Geraete-Registertabelle
  beschrieben werden, ohne Register einzeln manuell zu pflegen.
- Naeher an realer Geraetesemantik: Neben Registerwerten koennen auch
  Punktnamen, Kategorien, Einheiten, Enumerationen, Engineering-Werte,
  Rohwerte, Lese-/Schreibattribute und weitere Informationen beschrieben
  werden.
- Unterstuetzung fuer Engineering-Wertumrechnung: Skalierung, Offset,
  Ausdruecke, Raw/Value-Zuordnung sowie typische Faelle wie 32-Bit-Werte,
  64-Bit-Werte, Strings und Bitfelder werden unterstuetzt.
- Eingebautes Simulationsverhalten: Punkte koennen als `manual`, `const`,
  `rand`, `ramp`, `sine` oder `expr` konfiguriert werden, geeignet fuer
  dynamische Sensoren, Zaehlerstaende, periodische Schwankungen und aehnliche
  Daten.
- Laufzeit-Fehlerinjektion: Modbus-Ausnahmecodes koennen nach Slave,
  Funktionscode, Adressbereich, Ausloeseanzahl oder Wahrscheinlichkeit
  zurueckgegeben werden, um Fehlertoleranz und Wiederholungslogik des Masters
  zu testen.
- Mehrere Slaves und Instanzen: Ein Bereich von Slave IDs kann auf einmal
  simuliert werden, oder mehrere Instanzen koennen fuer Tests mit Master-Polling
  ueber viele Geraete gestartet werden.
- Registertabellen-Validierung: Beim Laden von Excel-Dateien prueft MBSim
  Kopfzeilen, Referenzen, Adressueberlappungen, Typen, Ausdruecke und weitere
  Probleme, um Fehler in Registertabellen frueh zu erkennen.

## Aktuelles Release

- Aktuelles Release: https://github.com/louisir/mbsim-dist/releases/latest
- Alle Releases: https://github.com/louisir/mbsim-dist/releases

## Screenshots und Beispieldateien

![Screenshot der MBSim-Oberflaeche](https://iamlouis.online/2026-06-02_17-44-44.jpg)

- Beispielprotokoll: [GY21249.pdf](https://www.iamlouis.online/GY21249.pdf)
- Beispiel-Registertabelle: [XY-MD03_GY21249.xlsx](https://www.iamlouis.online/XY-MD03_GY21249.xlsx)

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

## Lizenzierung und Spenden

Der eigene MBSim-Anwendungscode und die Dokumentation sind proprietaere
Freeware. Sie duerfen offizielle MBSim-Release-Pakete kostenlos installieren
und nutzen. MBSim ist keine Open-Source-Software, und der Quellcode wird nicht
veroeffentlicht. Siehe [LICENSE](LICENSE.de.md).

Spenden sind freiwillige Unterstuetzung fuer die weitere Entwicklung. Eine
Spende ist kein Kauf, schaltet keine zusaetzlichen Lizenzrechte oder Funktionen
frei und begruendet keine Support-, Garantie-, Service- oder Wartungspflicht.

Weiterverteilung, Verkauf, Aenderung, Reverse Engineering oder Erstellung
abgeleiteter Werke von MBSim selbst erfordern eine separate schriftliche
Genehmigung des Rechteinhabers, soweit zwingendes Recht nichts anderes erlaubt.
Drittanbieterkomponenten bleiben ihren eigenen Lizenzen unterworfen.

Das Portable-Paket enthaelt auch Laufzeitkomponenten von Drittanbietern. Deren
Lizenzen sind von der MBSim-Freeware-Lizenz getrennt und muessen bei Nutzung
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

Dieses Repository bietet keine Rechtsberatung. Wenn Sie MBSim weiterverteilen,
mit einem anderen Produkt buendeln oder in einer kontrollierten Umgebung
nutzen wollen, pruefen Sie die MBSim-Lizenz und die Drittanbieter-Lizenzen mit
qualifiziertem Rechtsbeistand.

## Release-Dateien

Die ZIP-Dateien in GitHub Releases sind die offiziellen Distributionsartefakte.
Dateien, die das Release-Skript in diesen Arbeitsbaum kopiert, sind nur
Staging-Artefakte fuer den Upload und sollten nicht in git committet werden.
