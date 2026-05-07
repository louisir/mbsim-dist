# Versiones de MBSim

Idiomas: [English](README.md) | [简体中文](README.zh_CN.md) |
[繁體中文](README.zh_HK.md) | [Deutsch](README.de.md) | Español |
[Français](README.fr.md) | [Italiano](README.it.md) |
[日本語](README.ja.md) | [한국어](README.ko.md)

Este repositorio aloja paquetes compilados de MBSim, un simulador de esclavo
Modbus RTU/TCP.

MBSim se distribuye como freeware propietario. El codigo fuente no se publica.
Descargue los paquetes desde GitHub Releases en lugar de clonar este
repositorio.

## Version mas reciente

- Version mas reciente: https://github.com/louisir/mbsim-dist/releases/latest
- Todas las versiones: https://github.com/louisir/mbsim-dist/releases

## Paquete portable para Windows

Descargue el paquete portable Windows x64 desde los assets de la version mas
reciente:

- `MBSim-v<version>-portable-windows-x64.zip`
- `MBSim-v<version>-portable-windows-x64.zip.sha256`

Despues de descargarlo, descomprima el zip y ejecute `MBSim.exe`.

## Verificar SHA256

En PowerShell:

```powershell
Get-FileHash .\MBSim-v<version>-portable-windows-x64.zip -Algorithm SHA256
Get-Content .\MBSim-v<version>-portable-windows-x64.zip.sha256
```

El hash mostrado por `Get-FileHash` debe coincidir con el valor del archivo
`.sha256`.

## Licencias y donaciones

El codigo de la aplicacion MBSim y su documentacion son freeware propietario.
Puede instalar y usar gratuitamente los paquetes oficiales de MBSim. MBSim no
es software de codigo abierto y el codigo fuente no se publica. Consulte
[LICENSE](LICENSE).

Las donaciones son apoyo voluntario para el desarrollo futuro. Una donacion no
es una compra, no desbloquea derechos de licencia ni funciones adicionales, y
no crea obligaciones de soporte, garantia, servicio o mantenimiento.

La redistribucion, venta, modificacion, ingenieria inversa o creacion de obras
derivadas de MBSim requiere permiso escrito separado del titular de derechos,
salvo que la ley obligatoria disponga lo contrario. Los componentes de terceros
siguen sujetos a sus propias licencias.

El paquete portable tambien incluye componentes de terceros. Sus licencias son
independientes de la licencia freeware de MBSim y deben respetarse al usar o
redistribuir el paquete:

- Qt no es una dependencia de licencia unica. Qt ofrece licencias comerciales y
  de codigo abierto. En Qt de codigo abierto, muchos modulos son LGPLv3/GPLv3,
  pero algunos modulos son solo GPLv3.
- MBSim usa Qt Quick 3D. La documentacion de licencias de Qt lista Qt Quick 3D
  como modulo GNU GPL v3 para usuarios de codigo abierto. Los redistribuidores
  deben cumplir las obligaciones GPL/LGPL aplicables o usar una licencia
  comercial de Qt adecuada.
- El despliegue de Windows tambien puede incluir archivos de Qt Virtual
  Keyboard. La documentacion de Qt lista Qt Virtual Keyboard como modulo GNU
  GPL v3 para usuarios de codigo abierto.
- OpenXLSX se usa para soporte de tablas Excel y tiene licencia BSD 3-Clause.

Consulte [THIRD-PARTY-NOTICES.es.md](THIRD-PARTY-NOTICES.es.md) para detalles y
referencias oficiales.

Este repositorio no ofrece asesoramiento legal. Si necesita redistribuir MBSim,
incluirlo con otro producto o usarlo en un entorno controlado, revise la
licencia de MBSim y las licencias de terceros con asesoramiento legal
cualificado.

## Archivos de release

Los archivos zip de GitHub Releases son los artefactos oficiales de
distribucion. Los archivos copiados al arbol de trabajo por el script de release
son artefactos de staging para la subida y no deben confirmarse en git.
