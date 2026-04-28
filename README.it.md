# Release di MBSim

Lingue: [English](README.md) | [简体中文](README.zh_CN.md) |
[繁體中文](README.zh_TW.md) | [Deutsch](README.de.md) |
[Español](README.es.md) | [Français](README.fr.md) | Italiano |
[日本語](README.ja.md) | [한국어](README.ko.md)

Questo repository ospita i pacchetti compilati di MBSim, un simulatore slave
Modbus RTU/TCP.

Il codice sorgente e mantenuto separatamente. Scaricare i pacchetti da GitHub
Releases invece di clonare questo repository.

## Ultima release

- Ultima release: https://github.com/louisir/mbsim-dist/releases/latest
- Tutte le release: https://github.com/louisir/mbsim-dist/releases

## Pacchetto portable per Windows

Scaricare il pacchetto portable Windows x64 dagli asset dell'ultima release:

- `MBSim-v<version>-portable-windows-x64.zip`
- `MBSim-v<version>-portable-windows-x64.zip.sha256`

Dopo il download, decomprimere il file zip ed eseguire `MBSim.exe`.

## Verifica SHA256

In PowerShell:

```powershell
Get-FileHash .\MBSim-v<version>-portable-windows-x64.zip -Algorithm SHA256
Get-Content .\MBSim-v<version>-portable-windows-x64.zip.sha256
```

L'hash stampato da `Get-FileHash` deve corrispondere al valore nel file
`.sha256`.

## Licenze

Il codice applicativo e la documentazione propri di MBSim sono distribuiti con
MIT License. Vedere [LICENSE](LICENSE).

Il pacchetto portable include anche componenti runtime di terze parti. Le loro
licenze sono separate dalla MIT License di MBSim e devono essere rispettate
quando si usa o si redistribuisce il pacchetto:

- Qt non e una dipendenza con una sola licenza. Qt offre opzioni commerciali e
  open-source. In Qt open-source molti moduli sono LGPLv3/GPLv3, mentre alcuni
  moduli sono solo GPLv3.
- MBSim usa Qt Quick 3D. La documentazione Qt elenca Qt Quick 3D come modulo
  GNU GPL v3 per gli utenti open-source. Chi redistribuisce deve rispettare gli
  obblighi GPL/LGPL applicabili oppure usare una licenza commerciale Qt adatta.
- Il deployment Windows puo includere anche file runtime di Qt Virtual Keyboard.
  La documentazione Qt elenca Qt Virtual Keyboard come modulo GNU GPL v3 per
  gli utenti open-source.
- OpenXLSX e usato per il supporto delle mappe Excel ed e distribuito con
  licenza BSD 3-Clause.

Vedere [THIRD-PARTY-NOTICES.it.md](THIRD-PARTY-NOTICES.it.md) per dettagli e
riferimenti ufficiali.

Questo repository non fornisce consulenza legale. Se si redistribuisce MBSim in
un prodotto commerciale o in un ambiente controllato, rivedere le licenze con
un consulente qualificato.

## File di release

I file zip in GitHub Releases sono gli artefatti ufficiali di distribuzione. I
file copiati nella working tree dallo script di release sono artefatti di
staging per l'upload e non devono essere committati in git.
