---
title: '호환성이 손상되는 변경: OSPlatform 특성이 제거되었거나 특성 이름이 바뀜'
description: 미리 보기 버전에 도입된 OS 플랫폼 특성이 제거되었거나 이름이 바뀐 핵심 .NET 라이브러리의 .NET 5.0 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: be2ddd4909bef70f531ca48246f091923d6435ec
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739492"
---
# <a name="osplatform-attributes-renamed-or-removed"></a>OSPlatform 특성이 제거되었거나 특성 이름이 바뀜

.NET 5.0 미리 보기 8에 도입된 `MinimumOSPlatformAttribute`, `RemovedInOSPlatformAttribute`, `ObsoletedInOSPlatformAttribute` 특성은 제거되었거나 그 이름이 바뀌었습니다.

## <a name="change-description"></a>변경 내용 설명

.NET 5.0 미리 보기 8에서는 <xref:System.Runtime.Versioning> 네임스페이스에 다음과 같은 특성을 도입했습니다.

- `MinimumOSPlatformAttribute`
- `RemovedInOSPlatformAttribute`
- `ObsoletedInOSPlatformAttribute`

.NET 5.0 미리 보기 8에서 프로젝트가 `net5.0-windows` 같은 [대상 프레임워크 모니커](../../../../standard/frameworks.md)를 사용하여 OS별 .NET 5 버전을 대상으로 하는 경우 빌드는 어셈블리 수준 `System.Runtime.Versioning.MinimumOSPlatformAttribute` 특성을 추가합니다.

.NET 5.0 RC1에서는 `ObsoletedInOSPlatformAttribute`가 제거되었고 `MinimumOSPlatformAttribute` 및 `RemovedInOSPlatformAttribute`의 이름이 다음과 같이 바뀌었습니다.

| 미리 보기 8 이름 | RC1 이상 이름 |
| - | - |
| `MinimumOSPlatformAttribute` | <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> |
| `RemovedInOSPlatformAttribute` | <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> |

.NET 5.0 RC1 이상에서 프로젝트가 `net5.0-windows` 같은 [대상 프레임워크 모니커](../../../../standard/frameworks.md)를 사용하여 OS별 .NET 5 버전을 대상으로 하는 경우 빌드는 어셈블리 수준 <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> 특성을 추가합니다.

## <a name="reason-for-change"></a>변경 이유

.NET 5.0 미리 보기 8에는 API에 지원되는 플랫폼을 지정하는 특성이 <xref:System.Runtime.Versioning>에 도입되었습니다. 이 특성은 이러한 API를 지원하지 않는 플랫폼에서 플랫폼별 API가 사용되는 경우 [플랫폼 호환성 분석기](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md)에서 빌드 경고를 생성하는 데 사용됩니다.

.NET 5.0 RC1의 경우 플랫폼을 제외하는 기능이 플랫폼 호환성 분석기에 더 추가되었습니다. 이 기능을 통해 API가 OS 플랫폼에서 완전히 지원되지 않는 것으로 표시될 수 있습니다. 이 기능으로 인해 더 적절한 이름을 사용하는 등 특성을 변경하게 되었습니다. `ObsoletedInOSPlatformAttribute`는 더 이상 필요하지 않아 제거되었습니다.

## <a name="version-introduced"></a>도입된 버전

5.0 RC1

## <a name="recommended-action"></a>권장 조치

이러한 변경으로 인해 프로젝트 대상을 .NET 5.0 미리 보기 8에서 .NET 5.0 RC1로 바꿀 때 빌드 오류나 런타임 오류가 발생할 수도 있습니다. 예를 들어 `MinimumOSPlatformAttribute`의 이름을 바꾸면 오류가 발생할 수 있습니다. 빌드 시 특성이 플랫폼별 어셈블리에 적용되지만, 이전 빌드 아티팩트가 여전히 이전 API 이름을 참조하기 때문입니다.

빌드 시 오류 예:

- **오류 CS0246: 형식 또는 네임스페이스 이름 ‘MinimumOSPlatformAttribute’를 찾을 수 없습니다. (사용 중인 지시문 또는 어셈블리 참조가 없습니까?)**
- **오류 CS0246: 형식 또는 네임스페이스 이름 ‘RemovedInOSPlatformAttribute’를 찾을 수 없습니다. (사용 중인 지시문 또는 어셈블리 참조가 없습니까?)**
- **오류 CS0246: 형식 또는 네임스페이스 이름 ‘ObsoletedInOSPlatformAttribute’를 찾을 수 없습니다. (사용 중인 지시문 또는 어셈블리 참조가 없습니까?)**

런타임 오류 예:

**처리되지 않은 예외: System.TypeLoadException: 어셈블리 ‘System.Runtime, Version=5.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a’에서 형식 ‘System.Runtime.Versioning.MinimumOSPlatformAttribute’를 로드할 수 없습니다.**

이러한 오류를 해결하려면 다음을 수행합니다.

- `MinimumOSPlatformAttribute`의 모든 참조를 <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute>로 업데이트합니다.
- `RemovedInOSPlatformAttribute`의 모든 참조를 <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>로 업데이트합니다.
- `ObsoletedInOSPlatformAttribute`에 대한 모든 참조를 제거합니다.
- 이전 빌드 아티팩트를 삭제하려면 프로젝트를 다시 빌드합니다(또는 정리 + 빌드 수행).

## <a name="affected-apis"></a>영향을 받는 API

- `System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `System.Runtime.Versioning.RemovedInOSPlatformAttribute`

<!--

### Category

Core .NET libraries

### Affected APIs

- `T:System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `T:System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `T:System.Runtime.Versioning.RemovedInOSPlatformAttribute`

-->
