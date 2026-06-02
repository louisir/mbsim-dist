# Versiones de MBSim

Idiomas: [English](README.md) | [简体中文](README.zh_CN.md) |
[繁體中文](README.zh_HK.md) | [Deutsch](README.de.md) | Español |
[Français](README.fr.md) | [Italiano](README.it.md) |
[日本語](README.ja.md) | [한국어](README.ko.md)

MBSim es un simulador de esclavo Modbus RTU/TCP orientado a escenarios de
depuracion e integracion. Permite simular esclavos Modbus cuando no hay
dispositivos reales disponibles, cuando conectarlos no es practico, o cuando se
necesitan construir datos de prueba en lote para validarlos con PLC,
aplicaciones host, gateways, programas de adquisicion de datos y otros maestros
Modbus.

Frente a las herramientas tradicionales de tipo Modbus Slave, MBSim se orienta
mas a una experiencia moderna de integracion de ingenieria: la interfaz encaja
mejor en entornos Windows actuales, los datos simulados pueden organizarse
mediante tablas de registros, y el paquete portable puede usarse directamente
en equipos de prueba, equipos de campo o entornos temporales de integracion.

Este repositorio es el repositorio de releases de MBSim y no contiene codigo
fuente. Proporciona el paquete portable Windows x64, archivos de verificacion
SHA256, terminos de licencia del software y avisos de licencia de componentes
de terceros. MBSim se distribuye como freeware propietario y el codigo fuente
no se publica.

## Ventajas principales

- Basado en tablas Excel: use las hojas `Points`, `Mappings`, `Simulation` y
  `Enums` para describir una tabla completa de puntos del dispositivo sin
  mantener los registros manualmente uno por uno.
- Semantica mas cercana a un dispositivo real: ademas de los valores de
  registro, puede describir nombres de puntos, categorias, unidades, enums,
  valores de ingenieria, valores raw, atributos de lectura/escritura y otra
  informacion.
- Conversion de valores de ingenieria: admite escalado, desplazamiento,
  expresiones, mapeos Raw/Value y casos habituales como valores de 32 bits,
  valores de 64 bits, strings y bit fields.
- Comportamiento de simulacion integrado: los puntos pueden configurarse como
  `manual`, `const`, `rand`, `ramp`, `sine` o `expr`, adecuado para simular
  sensores dinamicos, acumuladores, fluctuaciones periodicas y datos similares.
- Inyeccion de fallos en tiempo de ejecucion: permite devolver codigos de
  excepcion Modbus por esclavo, codigo de funcion, rango de direcciones, numero
  de activaciones o probabilidad para probar la tolerancia a fallos y la logica
  de reintento del maestro.
- Multiples esclavos e instancias: puede simular un rango de Slave ID de una
  vez o iniciar varias instancias, util para probar el sondeo del maestro sobre
  muchos dispositivos.
- Validacion de tablas: al cargar Excel, MBSim revisa encabezados, referencias,
  solapamientos de direcciones, tipos, expresiones y otros problemas para
  detectar errores de la tabla con anticipacion.

## Version mas reciente

- Version mas reciente: https://github.com/louisir/mbsim-dist/releases/latest
- Todas las versiones: https://github.com/louisir/mbsim-dist/releases

## Capturas de pantalla y archivos de ejemplo

![Captura de pantalla de la interfaz de MBSim](https://iamlouis.online/GY21249.jpg)

- Protocolo de ejemplo: [GY21249.pdf](https://www.iamlouis.online/GY21249.pdf)
- Tabla de registros de ejemplo: [XY-MD03_GY21249.xlsx](https://www.iamlouis.online/XY-MD03_GY21249.xlsx)

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
[LICENSE](LICENSE.es.md).

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
