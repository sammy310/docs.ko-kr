---
title: .NET 런타임 및 SDK의 버전 관리 방법
description: 이 문서에서는 .NET SDK 및 런타임의 버전 관리 방법을 설명합니다(유의적 버전과 유사함).
ms.date: 12/07/2020
ms.openlocfilehash: 2fe0b162b52f1e4500ec87f7d5d92054cd569552
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009308"
---
# <a name="overview-of-how-net-is-versioned"></a>.NET의 버전 관리 방법 개요

[.NET 런타임과 .NET SDK](../introduction.md#sdk-and-runtimes)는 다른 빈도로 새 기능을 추가합니다. 일반적으로 SDK는 런타임보다 더 자주 업데이트됩니다. 이 문서에서는 런타임 및 SDK 버전 번호를 설명합니다.

## <a name="versioning-details"></a>버전 관리 정보

.NET 런타임에는 [유의적 버전](#semantic-versioning)을 따르는 버전 관리에 대한 주/부/패치 접근 방식이 있습니다.

.NET SDK는 유의적 버전을 따르지 않습니다. .NET SDK는 더 빠르게 릴리스되며 해당 버전 번호는 정렬된 런타임과 SDK의 자체 부 릴리스 및 패치 릴리스를 모두 전달해야 합니다.

.NET SDK 버전 번호의 처음 두 위치는 릴리스된 .NET 런타임에 고정되어 있습니다. SDK의 각 버전은 이 런타임 또는 다른 하위 버전에 대한 애플리케이션을 만들 수 있습니다.

SDK 버전 번호의 세 번째 위치는 보조 및 패치 번호를 모두 전달합니다. 부 버전에는 100이 곱해집니다. 부 버전 1, 패치 버전 2는 102로 표시됩니다. 마지막 두 자리는 패치 번호를 나타냅니다. 예를 들어 다음과 같은 런타임 및 SDK 버전 번호 시퀀스를 사용할 수 있습니다.

| 변경                | .NET 런타임      | .NET SDK(\*)     |
|-----------------------|-------------------|-------------------|
| 초기 릴리스       | 2.2.0             | 2.2.100           |
| SDK 패치             | 2.2.0             | 2.2.101           |
| 런타임 및 SDK 패치 | 2.2.1             | 2.2.102           |
| SDK 기능 변경    | 2.2.1             | 2.2.200           |

참고:

- 런타임 기능 업데이트 전에 SDK에 10개의 기능 업데이트가 있는 경우 버전 번호는 2.2.900 이후의 기능 릴리스로 2.2.1000과 같은 숫자를 가진 1000 시리즈로 롤링됩니다. 이 상황은 발생할 것으로 예상되지 않습니다.
- 기능 릴리스가 없는 99 패치 릴리스는 발생하지 않습니다. 릴리스가 이 숫자에 가까워지면 기능 릴리스가 강제 실행됩니다.

[dotnet/designs](https://github.com/dotnet/designs/pull/29) 리포지토리에서 초기 제안서에 자세한 내용을 확인할 수 있습니다.

## <a name="semantic-versioning"></a>유의적 버전

.NET *런타임* 은 [유의적 버전(SemVer)](https://semver.org/)을 대략적으로 준수하며, `MAJOR.MINOR.PATCH` 버전 관리를 사용하고, 버전 번호의 다양한 부분으로 변경의 수준 및 종류를 설명합니다.

```
MAJOR.MINOR.PATCH[-PRERELEASE-BUILDNUMBER]
```

선택 사항인 `PRERELEASE` 및 `BUILDNUMBER` 부분은 지원되는 릴리스에 포함되지 않으며, 야간 빌드, 소스 대상에서의 로컬 빌드 및 지원되지 않는 미리 보기 릴리스에만 존재합니다.

### <a name="understand-runtime-version-number-changes"></a>런타임 버전 번호 변경 이해

다음 경우에는 `MAJOR`가 증가합니다.

- 제품 또는 새 제품 방향에 중대한 변경이 발생합니다.
- 주요 변경 내용이 있었습니다. 주요 변경 내용을 받아들이는 데는 높은 장벽이 있습니다.
- 이전 버전이 더 이상 지원되지 않는 경우
- 기존 종속성의 최신 `MAJOR` 버전이 채택된 경우

다음 경우에는 `MINOR`가 증가합니다.

- 공용 API 노출 영역이 추가된 경우
- 새 동작이 추가된 경우
- 기존 종속성의 최신 `MINOR` 버전이 채택된 경우
- 새 종속성이 도입된 경우

다음 경우에는 `PATCH`가 증가합니다.

- 버그 수정이 이루어진 경우
- 최신 플랫폼에 대한 지원이 추가된 경우
- 기존 종속성의 최신 `PATCH` 버전이 채택된 경우
- 위 경우 중 하나에 해당하지 않는 다른 변경 내용이 있는 경우

여러 가지 변경이 이루어진 경우에는 개별 변경의 영향을 받는 가장 높은 요소가 증가되고 다음은 0으로 다시 설정됩니다. 예를 들어 `MAJOR`가 증가하면 `MINOR` 및 `PATCH`는 0으로 다시 설정됩니다. `MINOR`가 증가하면 `PATCH`는 0으로 다시 설정되지만 `MAJOR`는 변경되지 않습니다.

## <a name="version-numbers-in-file-names"></a>파일 이름의 버전 번호

.NET용으로 다운로드한 파일에는 버전(예: `dotnet-sdk-2.1.300-win10-x64.exe`)이 들어 있습니다.

### <a name="preview-versions"></a>미리 보기 버전

미리 보기 버전에는 버전 번호에 `-preview[number]-([build]|"final")`이 추가됩니다. 예: `2.0.0-preview1-final`.

### <a name="servicing-versions"></a>서비스 버전

릴리스가 출시된 후에 릴리스 분기는 일반적으로 매일 빌드 만들기를 중지하고 대신 서비스 빌드를 만들기 시작합니다. 서비스 버전에는 `-servicing-[number]`이 추가됩니다. 예: `2.0.1-servicing-006924`.

## <a name="relationship-to-net-standard-versions"></a>.NET Standard 버전과의 관계

.NET Standard는 .NET 참조 어셈블리로 구성됩니다. 각 플랫폼마다 여러 구현이 있습니다. 참조 어셈블리에는 지정된 .NET Standard 버전의 일부인 .NET API의 정의가 포함되어 있습니다. 각 구현은 특정 플랫폼의 .NET Standard 계약을 충족합니다.

.NET Standard 참조 어셈블리는 `MAJOR.MINOR` 버전 관리 체계를 사용합니다. `PATCH` 수준은 .NET Standard에서 유용하지 않습니다. 이는 API 사양(구현 없음)만 노출하고 정의에 따라 API를 변경하면 기능 집합의 변경 내용을 나타내며, 따라서 새 `MINOR` 버전이 변경되기 때문입니다.

각 플랫폼의 구현은 일반적으로 플랫폼 릴리스의 일부로 업데이트될 수 있으므로, 해당 플랫폼에서 .NET Standard를 사용하는 프로그래머에게는 분명하지 않습니다.

자세한 내용은 [.NET 표준](../../standard/net-standard.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [대상 프레임워크](../../standard/frameworks.md)
- [.NET 배포 패키징](../distribution-packaging.md)
- [.NET 지원 수명 주기 팩트 시트](https://dotnet.microsoft.com/platform/support/policy)
- [.NET용 Docker 이미지](https://hub.docker.com/_/microsoft-dotnet/)
