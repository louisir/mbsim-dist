# 타사 고지

이 문서는 MBSim 릴리스 패키지의 주요 라이선스 의무를 요약합니다. 사용자와 재배포자를 위한 실무적 안내이며 법률 자문이 아닙니다.

## MBSim

MBSim 자체 애플리케이션 코드와 문서는 MIT License로 배포됩니다. [LICENSE](LICENSE)를 참조하십시오.

MIT License는 MBSim 자체 코드에 적용됩니다. 포터블 패키지에 포함된 타사 런타임 라이브러리를 MIT로 재라이선스하지 않습니다.

## Qt Runtime

Windows 포터블 패키지에는 Qt 런타임 라이브러리와 QML 모듈이 포함됩니다. Qt는 상용 라이선스와 오픈소스 라이선스를 포함한 여러 라이선스 옵션으로 제공됩니다.

Qt 공식 라이선스 참고 자료:

- Qt Licensing: https://doc.qt.io/qt-6/licensing.html
- Qt GPL/LGPL obligations: https://www.qt.io/development/open-source-lgpl-obligations

이 프로젝트에서 중요한 사항:

- 오픈소스 Qt 사용이 자동으로 "LGPL only"를 의미하지는 않습니다. Qt 문서는 일부 모듈이 LGPLv3가 아니라 GNU GPL v3로 제공된다고 설명합니다.
- MBSim은 Qt Quick 3D를 import하고 사용합니다. Qt 라이선스 페이지는 Qt Quick 3D를 오픈소스 사용자에게 GNU GPL v3로 제공되는 모듈로 나열합니다.
- Windows 배포에는 Qt Virtual Keyboard 런타임 파일도 포함될 수 있습니다. Qt 라이선스 페이지는 Qt Virtual Keyboard도 오픈소스 사용자에게 GNU GPL v3로 제공되는 모듈로 나열합니다.
- 오픈소스 Qt로 빌드된 바이너리 패키지를 재배포하는 경우, 적용되는 GPL/LGPL 의무를 충족하거나 적절한 Qt 상용 라이선스를 사용해야 합니다.
- MBSim의 MIT License는 Qt 라이선스 요구 사항을 제거하거나 약화하지 않습니다.

제공된 릴리스 스크립트로 패키지를 빌드할 때, 로컬 Qt 설치에 Qt 라이선스 텍스트가 있으면 패키지의 `licenses/` 디렉터리에 복사됩니다.

## OpenXLSX

MBSim은 Excel 레지스터 맵 지원을 위해 OpenXLSX를 사용합니다.

- Project: https://github.com/troldal/OpenXLSX
- License: BSD 3-Clause License

릴리스 스크립트는 로컬 vcpkg 설치에서 OpenXLSX copyright/license 텍스트를 패키지의 `licenses/` 디렉터리로 복사합니다.

## OpenXLSX 런타임 의존성

Windows 패키지에는 vcpkg로 설치된 OpenXLSX 런타임 의존성이 포함될 수 있습니다.

- pugixml: MIT License
- nowide: Boost Software License 1.0

해당 vcpkg copyright/license 파일이 있으면 릴리스 스크립트가 패키지의 `licenses/` 디렉터리로 복사합니다.

## MinGW/GCC Runtime

Windows 포터블 패키지에는 `libgcc_s_seh-1.dll`, `libstdc++-6.dll`, `libwinpthread-1.dll` 같은 MinGW/GCC 런타임 라이브러리가 포함될 수 있습니다. 이러한 구성 요소에는 자체 런타임 라이선스와 예외가 적용됩니다. 패키지를 재배포할 때 관련 고지를 보존하십시오.

## 재배포 체크리스트

패키지를 재배포하기 전에:

1. MBSim MIT License를 패키지에 포함하십시오.
2. 타사 고지와 라이선스 텍스트를 패키지에 포함하십시오.
3. 빌드에 포함된 정확한 Qt 모듈에 대해 현재 Qt 라이선스 페이지를 확인하십시오.
4. 오픈소스 Qt와 GPL-only Qt 모듈로 빌드된 패키지를 배포하는 경우, 배포가 GPLv3를 준수하는지 확인하거나 Qt 상용 라이선스를 사용하십시오.
