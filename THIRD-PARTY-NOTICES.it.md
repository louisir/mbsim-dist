# Note sui componenti di terze parti

Questo documento riassume i principali obblighi di licenza per i pacchetti di rilascio di MBSim. È una nota pratica per utenti e ridistributori; non è consulenza legale.

## MBSim

Il codice applicativo di MBSim e la documentazione sono freeware proprietario. I pacchetti ufficiali di MBSim possono essere installati e usati gratuitamente. MBSim non e software open-source e il codice sorgente non e pubblicato. Vedere [LICENSE](LICENSE.it.md).

Le donazioni, quando disponibili, sono supporto volontario per lo sviluppo futuro. Non cambiano i termini di licenza e non creano obblighi di supporto, garanzia, servizio o manutenzione.

La licenza freeware di MBSim si applica solo al codice proprio e alla documentazione di MBSim. Non rilicenzia le librerie runtime di terze parti incluse nel pacchetto portable.

## Qt Runtime

Il pacchetto portable Windows include librerie runtime Qt e moduli QML. Qt è disponibile con diverse opzioni di licenza, incluse licenze commerciali e licenze open source.

Riferimenti ufficiali Qt:

- Qt Licensing: https://doc.qt.io/qt-6/licensing.html
- Qt GPL/LGPL obligations: https://www.qt.io/development/open-source-lgpl-obligations

Punti importanti per questo progetto:

- L'uso di Qt open source non significa automaticamente "solo LGPL". La documentazione Qt indica che alcuni moduli sono disponibili sotto GNU GPL v3 invece che LGPLv3.
- MBSim importa e usa Qt Quick 3D. La pagina delle licenze Qt elenca Qt Quick 3D come modulo disponibile sotto GNU GPL v3 per gli utenti open source.
- La distribuzione Windows può includere anche file runtime di Qt Virtual Keyboard. La pagina delle licenze Qt elenca anche Qt Virtual Keyboard come modulo disponibile sotto GNU GPL v3 per gli utenti open source.
- Chi ridistribuisce un pacchetto binario creato con Qt open source deve assicurarsi che gli obblighi GPL/LGPL applicabili siano rispettati, oppure usare una licenza commerciale Qt appropriata.
- La licenza freeware di MBSim non rimuove né indebolisce i requisiti di licenza di Qt.

Quando un pacchetto viene creato con lo script di rilascio fornito, i testi di licenza Qt vengono copiati nella directory `licenses/` del pacchetto se sono disponibili nell'installazione Qt locale.

## OpenXLSX

MBSim usa OpenXLSX per il supporto ai registri in formato Excel.

- Progetto: https://github.com/troldal/OpenXLSX
- Licenza: BSD 3-Clause License

Lo script di rilascio copia il testo di copyright/licenza di OpenXLSX dall'installazione vcpkg locale nella directory `licenses/` del pacchetto.

## Dipendenze runtime di OpenXLSX

Il pacchetto Windows può includere dipendenze runtime di OpenXLSX installate da vcpkg:

- pugixml: MIT License
- nowide: Boost Software License 1.0

Lo script di rilascio copia i relativi file di copyright/licenza vcpkg nella directory `licenses/` del pacchetto quando presenti.

## Runtime MinGW/GCC

Il pacchetto portable Windows può includere librerie runtime MinGW/GCC come `libgcc_s_seh-1.dll`, `libstdc++-6.dll` e `libwinpthread-1.dll`. Questi componenti sono regolati dalle proprie licenze runtime ed eccezioni. Conservare le note pertinenti quando si ridistribuisce il pacchetto.

## Checklist per la ridistribuzione

Prima di ridistribuire un pacchetto:

1. Mantenere la licenza MBSim nel pacchetto.
2. Mantenere le note di terze parti e i testi di licenza nel pacchetto.
3. Se si ridistribuisce MBSim o lo si include con un prodotto, ottenere il permesso scritto del titolare dei diritti, salvo diversa disposizione di legge imperativa.
4. Controllare la pagina corrente delle licenze Qt per i moduli esatti inclusi nel proprio build.
5. Se si distribuisce un pacchetto creato con Qt open source e moduli Qt GPL-only, assicurarsi che la distribuzione rispetti GPLv3, oppure usare una licenza commerciale Qt.
