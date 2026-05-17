# MBSim 릴리스

언어: [English](README.md) | [简体中文](README.zh_CN.md) |
[繁體中文](README.zh_HK.md) | [Deutsch](README.de.md) |
[Español](README.es.md) | [Français](README.fr.md) |
[Italiano](README.it.md) | [日本語](README.ja.md) | 한국어

이 저장소는 Modbus RTU/TCP 슬레이브 시뮬레이터인 MBSim의 컴파일된 릴리스
패키지를 배포합니다.

MBSim은 무료로 사용할 수 있는 독점 소프트웨어로 배포됩니다. 소스 코드는 공개되지
않습니다. 이 저장소를 clone하지 말고 GitHub Releases에서 패키지를 다운로드하십시오.

## 최신 릴리스

- 최신 릴리스: https://github.com/louisir/mbsim-dist/releases/latest
- 모든 릴리스: https://github.com/louisir/mbsim-dist/releases

## Windows 포터블 패키지

최신 릴리스 Assets에서 Windows x64 포터블 패키지를 다운로드하십시오.

- `MBSim-v<version>-portable-windows-x64.zip`
- `MBSim-v<version>-portable-windows-x64.zip.sha256`

다운로드 후 zip을 풀고 `MBSim.exe`를 실행하십시오.

## SHA256 확인

PowerShell에서 실행합니다.

```powershell
Get-FileHash .\MBSim-v<version>-portable-windows-x64.zip -Algorithm SHA256
Get-Content .\MBSim-v<version>-portable-windows-x64.zip.sha256
```

`Get-FileHash`가 출력한 해시가 `.sha256` 파일의 값과 일치해야 합니다.

## 라이선스와 후원

MBSim 자체 애플리케이션 코드와 문서는 무료로 사용할 수 있는 독점 소프트웨어로
제공됩니다. 공식 MBSim 릴리스 패키지는 무료로 설치하고 사용할 수 있습니다. MBSim은
오픈소스 소프트웨어가 아니며 소스 코드는 공개되지 않습니다. [LICENSE](LICENSE.ko.md)를
참조하십시오.

후원은 향후 개발을 위한 자발적 지원입니다. 후원은 구매가 아니며 추가 라이선스 권리나
기능을 해제하지 않고, 지원, 보증, 서비스 또는 유지보수 의무를 만들지 않습니다.

MBSim 자체의 재배포, 판매, 수정, 리버스 엔지니어링 또는 파생물 작성에는 권리자의
별도 서면 허가가 필요합니다. 단, 강행 법규가 달리 정하는 경우는 예외입니다. 타사 구성
요소에는 각각의 라이선스가 적용됩니다.

포터블 패키지에는 타사 런타임 구성 요소도 포함됩니다. 이러한 라이선스는 MBSim의
freeware 라이선스와 별개이며, 패키지를 사용하거나 재배포할 때 준수해야 합니다.

- Qt는 단일 라이선스 의존성이 아닙니다. Qt는 상용 라이선스와 오픈소스 라이선스를
  제공합니다. 오픈소스 Qt에서 많은 모듈은 LGPLv3/GPLv3이지만 일부 모듈은 GPLv3
  전용입니다.
- MBSim은 Qt Quick 3D를 사용합니다. Qt 라이선스 문서는 Qt Quick 3D를 오픈소스
  사용자용 GNU GPL v3 모듈로 나열합니다. 재배포자는 적용 가능한 GPL/LGPL 의무를
  충족하거나 적절한 Qt 상용 라이선스를 사용해야 합니다.
- Windows 배포물에는 Qt Virtual Keyboard 런타임 파일도 포함될 수 있습니다. Qt
  문서는 Qt Virtual Keyboard도 오픈소스 사용자용 GNU GPL v3 모듈로 나열합니다.
- OpenXLSX는 Excel 레지스터 맵 지원에 사용되며 BSD 3-Clause License입니다.

자세한 내용과 공식 참조는 [THIRD-PARTY-NOTICES.ko.md](THIRD-PARTY-NOTICES.ko.md)를
참조하십시오.

이 저장소는 법률 자문을 제공하지 않습니다. MBSim을 재배포하거나 다른 제품에 포함하거나
통제된 환경에서 사용해야 하는 경우, 자격 있는 전문가와 MBSim 라이선스 및 타사
라이선스를 검토하십시오.

## 릴리스 파일

GitHub Releases의 zip 파일이 공식 배포 산출물입니다. 릴리스 스크립트가 이 작업
트리에 복사한 zip 및 sha256 파일은 업로드용 staging 파일이며 git에 commit하지
않아야 합니다.
