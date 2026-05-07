# Avis de tiers

Ce document résume les principales obligations de licence des paquets de publication MBSim. Il s'agit d'une notice pratique pour les utilisateurs et les redistributeurs ; ce n'est pas un avis juridique.

## MBSim

Le code applicatif propre à MBSim et sa documentation sont un freeware propriétaire. Les paquets officiels MBSim peuvent être installés et utilisés gratuitement. MBSim n'est pas un logiciel open source et le code source n'est pas publié. Voir [LICENSE](LICENSE).

Les dons, lorsqu'ils sont disponibles, sont un soutien volontaire au développement futur. Ils ne modifient pas les conditions de licence et ne créent aucune obligation de support, garantie, service ou maintenance.

La licence freeware de MBSim s'applique uniquement au code propre et à la documentation de MBSim. Elle ne relicencie pas les bibliothèques d'exécution tierces livrées avec le paquet portable.

## Qt Runtime

Le paquet portable Windows inclut des bibliothèques d'exécution Qt et des modules QML. Qt est disponible sous différentes options de licence, notamment des licences commerciales et des licences open source.

Références officielles Qt :

- Qt Licensing: https://doc.qt.io/qt-6/licensing.html
- Qt GPL/LGPL obligations: https://www.qt.io/development/open-source-lgpl-obligations

Points importants pour ce projet :

- L'utilisation de Qt open source ne signifie pas automatiquement "LGPL uniquement". La documentation Qt indique que certains modules sont disponibles sous GNU GPL v3 plutôt que sous LGPLv3.
- MBSim importe et utilise Qt Quick 3D. La page de licence Qt liste Qt Quick 3D comme module disponible sous GNU GPL v3 pour les utilisateurs open source.
- Le déploiement Windows peut aussi inclure des fichiers d'exécution Qt Virtual Keyboard. La page de licence Qt liste aussi Qt Virtual Keyboard comme module disponible sous GNU GPL v3 pour les utilisateurs open source.
- Le redistributeur d'un paquet binaire construit avec Qt open source doit s'assurer que les obligations GPL/LGPL applicables sont respectées, ou utiliser une licence commerciale Qt appropriée.
- La licence freeware de MBSim ne supprime ni n'affaiblit les exigences de licence de Qt.

Quand un paquet est construit par le script de publication fourni, les textes de licence Qt sont copiés dans le répertoire `licenses/` du paquet lorsqu'ils sont disponibles dans l'installation Qt locale.

## OpenXLSX

MBSim utilise OpenXLSX pour la prise en charge des cartes de registres Excel.

- Projet : https://github.com/troldal/OpenXLSX
- Licence : BSD 3-Clause License

Le script de publication copie le texte de copyright/licence OpenXLSX depuis l'installation vcpkg locale vers le répertoire `licenses/` du paquet.

## Dépendances d'exécution OpenXLSX

Le paquet Windows peut inclure des dépendances d'exécution OpenXLSX installées par vcpkg :

- pugixml: MIT License
- nowide: Boost Software License 1.0

Le script de publication copie leurs fichiers de copyright/licence vcpkg dans le répertoire `licenses/` du paquet lorsqu'ils sont présents.

## Runtime MinGW/GCC

Le paquet portable Windows peut inclure des bibliothèques d'exécution MinGW/GCC comme `libgcc_s_seh-1.dll`, `libstdc++-6.dll` et `libwinpthread-1.dll`. Ces composants sont régis par leurs propres licences runtime et exceptions. Conservez les notices pertinentes lors de la redistribution du paquet.

## Liste de vérification pour redistribution

Avant de redistribuer un paquet :

1. Conservez la licence MBSim avec le paquet.
2. Conservez les avis de tiers et les textes de licence avec le paquet.
3. Si vous redistribuez MBSim ou l'incluez avec un produit, obtenez une autorisation écrite du titulaire des droits, sauf disposition contraire de la loi impérative.
4. Consultez la page de licence Qt actuelle pour les modules exacts inclus dans votre build.
5. Si vous distribuez un paquet construit avec Qt open source et des modules Qt GPL-only, assurez-vous que la distribution respecte GPLv3, ou utilisez une licence commerciale Qt.
