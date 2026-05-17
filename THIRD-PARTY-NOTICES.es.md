# Avisos de terceros

Este documento resume las principales obligaciones de licencia de los paquetes de MBSim. Es un aviso práctico para usuarios y redistribuidores; no es asesoramiento legal.

## MBSim

El código propio de la aplicación MBSim y su documentación son freeware propietario. Los paquetes oficiales de MBSim pueden instalarse y usarse gratuitamente. MBSim no es software de código abierto y el código fuente no se publica. Consulte [LICENSE](LICENSE.es.md).

Las donaciones, cuando estén disponibles, son apoyo voluntario para el desarrollo futuro. No cambian los términos de licencia ni crean obligaciones de soporte, garantía, servicio o mantenimiento.

La licencia freeware de MBSim se aplica solo al código propio y la documentación de MBSim. No vuelve a licenciar las bibliotecas de terceros incluidas en el paquete portable.

## Qt Runtime

El paquete portable de Windows incluye bibliotecas de ejecución de Qt y módulos QML. Qt está disponible bajo distintas opciones de licencia, incluidas licencias comerciales y licencias de código abierto.

Referencias oficiales de licencia de Qt:

- Qt Licensing: https://doc.qt.io/qt-6/licensing.html
- Qt GPL/LGPL obligations: https://www.qt.io/development/open-source-lgpl-obligations

Puntos importantes para este proyecto:

- Usar Qt de código abierto no significa que todo sea únicamente LGPL. La documentación de Qt indica que algunos módulos están disponibles bajo GNU GPL v3 en lugar de LGPLv3.
- MBSim importa y usa Qt Quick 3D. La página de licencias de Qt lista Qt Quick 3D como un módulo disponible bajo GNU GPL v3 para usuarios de código abierto.
- El despliegue de Windows también puede incluir archivos de ejecución de Qt Virtual Keyboard. La página de licencias de Qt lista Qt Virtual Keyboard como un módulo disponible bajo GNU GPL v3 para usuarios de código abierto.
- Quien redistribuya un paquete binario creado con Qt de código abierto debe asegurarse de cumplir las obligaciones GPL/LGPL aplicables, o usar una licencia comercial de Qt adecuada.
- La licencia freeware de MBSim no elimina ni reduce los requisitos de licencia de Qt.

Cuando un paquete se crea con el script de publicación proporcionado, los textos de licencia de Qt se copian en el directorio `licenses/` del paquete si están disponibles en la instalación local de Qt.

## OpenXLSX

MBSim usa OpenXLSX para la compatibilidad con mapas de registros en Excel.

- Proyecto: https://github.com/troldal/OpenXLSX
- Licencia: BSD 3-Clause License

El script de publicación copia el texto de copyright/licencia de OpenXLSX desde la instalación local de vcpkg al directorio `licenses/` del paquete.

## Dependencias de ejecución de OpenXLSX

El paquete de Windows puede incluir dependencias de ejecución de OpenXLSX instaladas por vcpkg:

- pugixml: MIT License
- nowide: Boost Software License 1.0

El script de publicación copia sus archivos de copyright/licencia de vcpkg al directorio `licenses/` del paquete cuando están presentes.

## Runtime de MinGW/GCC

El paquete portable de Windows puede incluir bibliotecas de ejecución de MinGW/GCC como `libgcc_s_seh-1.dll`, `libstdc++-6.dll` y `libwinpthread-1.dll`. Estos componentes se rigen por sus propias licencias y excepciones de runtime. Conserve los avisos correspondientes al redistribuir el paquete.

## Lista de comprobación para redistribución

Antes de redistribuir un paquete:

1. Mantenga la licencia de MBSim con el paquete.
2. Mantenga los avisos de terceros y los textos de licencia con el paquete.
3. Si redistribuye MBSim o lo incluye con un producto, obtenga permiso escrito del titular de derechos, salvo que la ley obligatoria disponga lo contrario.
4. Revise la página actual de licencias de Qt para los módulos incluidos en su compilación.
5. Si distribuye un paquete creado con Qt de código abierto y módulos de Qt solo GPL, asegúrese de que la distribución cumpla GPLv3, o use una licencia comercial de Qt.
