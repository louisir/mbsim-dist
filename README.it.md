# Release di MBSim

Lingue: [English](README.md) | [简体中文](README.zh_CN.md) |
[繁體中文](README.zh_HK.md) | [Deutsch](README.de.md) |
[Español](README.es.md) | [Français](README.fr.md) | Italiano |
[日本語](README.ja.md) | [한국어](README.ko.md)

MBSim e un simulatore slave Modbus RTU/TCP per scenari di debug e integrazione.
Permette di simulare slave Modbus quando i dispositivi reali non sono
disponibili, non sono pratici da collegare, o quando e necessario costruire
dati di test in blocco per validarli con PLC, applicazioni host, gateway,
programmi di acquisizione dati e altri master Modbus.

Rispetto agli strumenti tradizionali di tipo Modbus Slave, MBSim e orientato a
un'esperienza di integrazione tecnica piu moderna: l'interfaccia si adatta agli
ambienti Windows attuali, i dati simulati possono essere organizzati tramite
mappe di registri, e il pacchetto portable puo essere usato direttamente su
macchine di test, PC in campo o ambienti temporanei di integrazione.

Questo repository e il repository di release di MBSim e non contiene codice
sorgente. Fornisce il pacchetto portable Windows x64, i file di verifica
SHA256, i termini di licenza del software e gli avvisi di licenza dei componenti
di terze parti. MBSim e distribuito come freeware proprietario e il codice
sorgente non e pubblicato.

## Vantaggi principali

- Basato su mappe Excel: usare i fogli `Points`, `Mappings`, `Simulation` e
  `Enums` per descrivere una mappa punti completa del dispositivo senza
  mantenere i registri manualmente uno per uno.
- Piu vicino alla semantica di un dispositivo reale: oltre ai valori dei
  registri, e possibile descrivere nomi dei punti, categorie, unita, enum,
  valori di engineering, valori raw, attributi di lettura/scrittura e altre
  informazioni.
- Conversione dei valori di engineering: supporta scaling, offset, espressioni,
  mapping Raw/Value e casi comuni come valori a 32 bit, valori a 64 bit,
  stringhe e bit field.
- Comportamenti di simulazione integrati: i punti possono essere configurati
  come `manual`, `const`, `rand`, `ramp`, `sine` o `expr`, adatti a simulare
  sensori dinamici, accumulatori, oscillazioni periodiche e dati simili.
- Iniezione di guasti a runtime: permette di restituire codici di eccezione
  Modbus per slave, codice funzione, intervallo di indirizzi, numero di trigger
  o probabilita, per testare tolleranza agli errori e logica di retry del
  master.
- Piu slave e piu istanze: si puo simulare un intervallo di Slave ID in una
  volta o avviare piu istanze, utile per testare il polling del master su molti
  dispositivi.
- Validazione delle mappe: durante il caricamento di Excel, MBSim controlla
  intestazioni, riferimenti, sovrapposizioni di indirizzi, tipi, espressioni e
  altri problemi per individuare in anticipo gli errori della mappa.

## Ultima release

- Ultima release: https://github.com/louisir/mbsim-dist/releases/latest
- Tutte le release: https://github.com/louisir/mbsim-dist/releases

## Screenshot e file di esempio

![Screenshot dell'interfaccia MBSim](https://iamlouis.online/GY21249.jpg)

- Protocollo di esempio: [GY21249.pdf](https://www.iamlouis.online/GY21249.pdf)
- Mappa registri di esempio: [XY-MD03_GY21249.xlsx](https://www.iamlouis.online/XY-MD03_GY21249.xlsx)

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

## Licenze e donazioni

Il codice applicativo e la documentazione propri di MBSim sono freeware
proprietario. E possibile installare e usare gratuitamente i pacchetti ufficiali
di MBSim. MBSim non e software open-source e il codice sorgente non e
pubblicato. Vedere [LICENSE](LICENSE.it.md).

Le donazioni sono supporto volontario per lo sviluppo futuro. Una donazione non
e un acquisto, non sblocca diritti di licenza o funzioni aggiuntive e non crea
obblighi di supporto, garanzia, servizio o manutenzione.

La ridistribuzione, vendita, modifica, reverse engineering o creazione di opere
derivate da MBSim richiede un permesso scritto separato del titolare dei
diritti, salvo quanto consentito da legge imperativa. I componenti di terze
parti restano regolati dalle proprie licenze.

Il pacchetto portable include anche componenti runtime di terze parti. Le loro
licenze sono separate dalla licenza freeware di MBSim e devono essere rispettate
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

Questo repository non fornisce consulenza legale. Se e necessario ridistribuire
MBSim, includerlo con un altro prodotto o usarlo in un ambiente controllato,
rivedere la licenza MBSim e le licenze di terze parti con un consulente
qualificato.

## File di release

I file zip in GitHub Releases sono gli artefatti ufficiali di distribuzione. I
file copiati nella working tree dallo script di release sono artefatti di
staging per l'upload e non devono essere committati in git.
