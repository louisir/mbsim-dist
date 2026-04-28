# Versions de MBSim

Langues: [English](README.md) | [简体中文](README.zh_CN.md) |
[繁體中文](README.zh_TW.md) | [Deutsch](README.de.md) |
[Español](README.es.md) | Français | [Italiano](README.it.md) |
[日本語](README.ja.md) | [한국어](README.ko.md)

Ce depot heberge les paquets compiles de MBSim, un simulateur esclave Modbus
RTU/TCP.

Le code source est maintenu separement. Telechargez les paquets depuis GitHub
Releases au lieu de cloner ce depot.

## Derniere version

- Derniere version: https://github.com/louisir/mbsim-dist/releases/latest
- Toutes les versions: https://github.com/louisir/mbsim-dist/releases

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

## Licences

Le code applicatif et la documentation propres a MBSim sont distribues sous MIT
License. Voir [LICENSE](LICENSE).

Le paquet portable contient aussi des composants d'execution tiers. Leurs
licences sont distinctes de la MIT License de MBSim et doivent etre respectees
lors de l'utilisation ou de la redistribution du paquet:

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

Ce depot ne fournit pas d'avis juridique. Si vous redistribuez MBSim dans un
produit commercial ou un environnement controle, faites examiner les licences
par un conseil qualifie.

## Fichiers de release

Les fichiers zip dans GitHub Releases sont les artefacts officiels de
distribution. Les fichiers copies dans l'arborescence de travail par le script
de release sont des artefacts de staging pour l'upload et ne doivent pas etre
committes dans git.
