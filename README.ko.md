# MBSim 릴리스

언어: [English](README.md) | [简体中文](README.zh_CN.md) |
[繁體中文](README.zh_HK.md) | [Deutsch](README.de.md) |
[Español](README.es.md) | [Français](README.fr.md) |
[Italiano](README.it.md) | [日本語](README.ja.md) | 한국어

MBSim은 디버깅과 연동 테스트 상황을 위한 Modbus RTU/TCP 슬레이브 시뮬레이터입니다.
실제 장비가 없거나 장비 연결이 어렵거나, 테스트 데이터를 대량으로 구성해야 할 때
Modbus 슬레이브를 시뮬레이션하고 PLC, 상위 애플리케이션, 게이트웨이, 데이터 수집
프로그램 등 마스터 시스템과 함께 검증할 수 있습니다.

기존 Modbus Slave 계열 도구와 비교해 MBSim은 더 현대적인 엔지니어링 연동 경험에
초점을 둡니다. 현재 Windows 환경에 맞는 인터페이스, 레지스터 맵을 통한 시뮬레이션
데이터 구성, 설치가 필요 없는 패키지를 통해 테스트 장비, 현장 PC 또는 임시 연동
환경에서 바로 사용할 수 있습니다.

이 저장소는 MBSim의 릴리스 저장소이며 소스 코드를 포함하지 않습니다. 여기에는 Windows
x64 포터블 패키지, SHA256 확인 파일, 소프트웨어 라이선스 조건, 타사 구성 요소 라이선스
고지가 제공됩니다. MBSim은 무료로 사용할 수 있는 독점 소프트웨어로 배포되며 소스 코드는
공개되지 않습니다.

## 주요 장점

- Excel 점표 기반: `Points`, `Mappings`, `Simulation`, `Enums` 네 개 시트로 전체 장비
  점표를 설명할 수 있어 레지스터를 하나씩 수동으로 관리할 필요가 없습니다.
- 실제 장비 의미에 더 가까움: 레지스터 값뿐 아니라 포인트 이름, 분류, 단위, 열거값,
  엔지니어링 값, raw 값, 읽기/쓰기 속성 등의 정보를 설명할 수 있습니다.
- 엔지니어링 값 변환 지원: 비율 변환, 오프셋, 표현식, Raw/Value 매핑, 32비트, 64비트,
  문자열, bit field 등 일반적인 상황을 지원합니다.
- 내장 시뮬레이션 동작: 포인트를 `manual`, `const`, `rand`, `ramp`, `sine`, `expr`로
  설정할 수 있어 동적 센서, 누적값, 주기적 변동 등의 데이터를 시뮬레이션하기에 적합합니다.
- 런타임 오류 주입: 슬레이브, 기능 코드, 주소 범위, 트리거 횟수 또는 확률에 따라 Modbus
  예외 코드를 반환하여 마스터의 내결함성과 재시도 로직을 테스트할 수 있습니다.
- 다중 슬레이브와 다중 인스턴스: Slave ID 범위를 한 번에 시뮬레이션하거나 여러 인스턴스를
  실행할 수 있어 여러 장비를 폴링하는 마스터 테스트에 적합합니다.
- 점표 검증: Excel을 로드할 때 헤더, 참조, 주소 중복, 타입, 표현식 등의 문제를 검사해
  점표 오류를 미리 발견합니다.

## 최신 릴리스

- 최신 릴리스: https://github.com/louisir/mbsim-dist/releases/latest
- 모든 릴리스: https://github.com/louisir/mbsim-dist/releases

## 화면 캡처와 예제 파일

![MBSim 인터페이스 화면 캡처](https://iamlouis.online/2026-06-02_17-44-44.jpg)

- 예제 프로토콜: [GY21249.pdf](https://www.iamlouis.online/GY21249.pdf)
- 예제 레지스터 맵: [XY-MD03_GY21249.xlsx](https://www.iamlouis.online/XY-MD03_GY21249.xlsx)

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
