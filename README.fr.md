# Versions de MBSim

Langues: [English](README.md) | [简体中文](README.zh_CN.md) |
[繁體中文](README.zh_HK.md) | [Deutsch](README.de.md) |
[Español](README.es.md) | Français | [Italiano](README.it.md) |
[日本語](README.ja.md) | [한국어](README.ko.md)

MBSim est un simulateur esclave Modbus RTU/TCP pour les scenarios de debogage
et d'integration. Il permet de simuler des esclaves Modbus lorsque les appareils
reels ne sont pas disponibles, ne sont pas pratiques a connecter, ou lorsque des
donnees de test doivent etre construites en lot pour validation avec des PLC,
applications hotes, passerelles, programmes d'acquisition de donnees et autres
maitres Modbus.

Par rapport aux outils traditionnels de type Modbus Slave, MBSim vise davantage
une experience moderne d'integration d'ingenierie: l'interface convient aux
environnements Windows actuels, les donnees simulees peuvent etre organisees au
moyen de tables de registres, et le paquet portable peut etre utilise
directement sur des machines de test, des PC de terrain ou des environnements
d'integration temporaires.

Ce depot est le depot de publication de MBSim et ne contient pas le code
source. Il fournit le paquet portable Windows x64, les fichiers de verification
SHA256, les conditions de licence du logiciel et les avis de licence des
composants tiers. MBSim est distribue comme freeware proprietaire, et le code
source n'est pas publie.

## Principaux avantages

- Pilote par des tables Excel: les feuilles `Points`, `Mappings`, `Simulation`
  et `Enums` permettent de decrire une table de points complete sans maintenir
  les registres un par un manuellement.
- Semantique plus proche d'un appareil reel: en plus des valeurs de registre,
  il est possible de decrire les noms de points, categories, unites, enums,
  valeurs d'ingenierie, valeurs raw, attributs lecture/ecriture et autres
  informations.
- Conversion des valeurs d'ingenierie: prise en charge de l'echelle, du decalage,
  des expressions, des mappings Raw/Value, ainsi que des cas courants comme les
  valeurs 32 bits, 64 bits, les strings et les bit fields.
- Comportements de simulation integres: les points peuvent etre configures en
  `manual`, `const`, `rand`, `ramp`, `sine` ou `expr`, ce qui convient aux
  capteurs dynamiques, compteurs, fluctuations periodiques et donnees similaires.
- Injection de defauts a l'execution: retour de codes d'exception Modbus par
  esclave, code fonction, plage d'adresses, nombre de declenchements ou
  probabilite afin de tester la tolerance aux erreurs et la logique de reprise
  du maitre.
- Plusieurs esclaves et instances: simulation d'une plage de Slave ID en une
  fois, ou lancement de plusieurs instances pour tester l'interrogation de
  nombreux appareils par le maitre.
- Validation des tables: au chargement d'Excel, MBSim verifie les en-tetes,
  references, chevauchements d'adresses, types, expressions et autres problemes
  pour detecter les erreurs de table en amont.

## Derniere version

- Derniere version: https://github.com/louisir/mbsim-dist/releases/latest
- Toutes les versions: https://github.com/louisir/mbsim-dist/releases

## Captures d'ecran et fichiers d'exemple

![Capture d'ecran de l'interface MBSim](https://iamlouis.online/GY21249.jpg)

- Protocole d'exemple: [GY21249.pdf](https://www.iamlouis.online/GY21249.pdf)
- Table de registres d'exemple: [XY-MD03_GY21249.xlsx](https://www.iamlouis.online/XY-MD03_GY21249.xlsx)

## Paquet portable Windows

Telechargez le paquet portable Windows x64 depuis les assets de la derniere
version:

- `MBSim-v<version>-portable-windows-x64.zip`
- `MBSim-v<version>-portable-windows-x64.zip.sha256`

Apres le telechargement, decompressez le zip et lancez `MBSim.exe`.

## Verification SHA256

Dans PowerShell:

```powershell
Get-FileHash .\MBSim-v<version>-portable-windows-x64.zip -Algorithm SHA256
Get-Content .\MBSim-v<version>-portable-windows-x64.zip.sha256
```

Le hash affiche par `Get-FileHash` doit correspondre a la valeur du fichier
`.sha256`.

## Licences et dons

Le code applicatif et la documentation propres a MBSim sont un freeware
proprietaire. Vous pouvez installer et utiliser gratuitement les paquets
officiels de MBSim. MBSim n'est pas un logiciel open-source et le code source
n'est pas publie. Voir [LICENSE](LICENSE.fr.md).

Les dons sont un soutien volontaire au developpement futur. Un don n'est pas
un achat, ne debloque aucun droit de licence ni aucune fonction supplementaire,
et ne cree aucune obligation de support, garantie, service ou maintenance.

La redistribution, la vente, la modification, la retro-ingenierie ou la
creation d'oeuvres derivees de MBSim necessite une autorisation ecrite separee
du titulaire des droits, sauf lorsque la loi imperative l'autorise. Les
composants tiers restent regis par leurs propres licences.

Le paquet portable contient aussi des composants d'execution tiers. Leurs
licences sont distinctes de la licence freeware de MBSim et doivent etre
respectees lors de l'utilisation ou de la redistribution du paquet:

- Qt n'est pas une dependance a licence unique. Qt propose des licences
  commerciales et open-source. Dans Qt open-source, de nombreux modules sont
  LGPLv3/GPLv3, mais certains modules sont uniquement GPLv3.
- MBSim utilise Qt Quick 3D. La documentation de licences de Qt liste Qt Quick
  3D comme module GNU GPL v3 pour les utilisateurs open-source. Les
  redistributeurs doivent respecter les obligations GPL/LGPL applicables ou
  utiliser une licence commerciale Qt appropriee.
- Le deploiement Windows peut aussi inclure des fichiers Qt Virtual Keyboard.
  La documentation de Qt liste Qt Virtual Keyboard comme module GNU GPL v3 pour
  les utilisateurs open-source.
- OpenXLSX est utilise pour la prise en charge des fichiers Excel et est sous
  licence BSD 3-Clause.

Voir [THIRD-PARTY-NOTICES.fr.md](THIRD-PARTY-NOTICES.fr.md) pour les details et
les references officielles.

Ce depot ne fournit pas d'avis juridique. Si vous devez redistribuer MBSim,
l'inclure avec un autre produit ou l'utiliser dans un environnement controle,
faites examiner la licence MBSim et les licences tierces par un conseil
qualifie.

## Fichiers de release

Les fichiers zip dans GitHub Releases sont les artefacts officiels de
distribution. Les fichiers copies dans l'arborescence de travail par le script
de release sont des artefacts de staging pour l'upload et ne doivent pas etre
committes dans git.
