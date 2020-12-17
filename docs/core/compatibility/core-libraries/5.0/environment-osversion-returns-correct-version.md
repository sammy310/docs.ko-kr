---
title: '호환성이 손상되는 변경: Environment.OSVersion에서 올바른 운영 체제 버전이 반환됨'
description: Environment.OSVersion이 애플리케이션 호환성을 위해 선택된 OS 대신 운영 체제의 실제 버전을 반환하는 핵심 .NET 라이브러리의 .NET 5.0 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: c810d9a7a028a0c60c30d69e78a9b9c695d933ef
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009523"
---
# <a name="environmentosversion-returns-the-correct-operating-system-version"></a>Environment.OSVersion에서 올바른 운영 체제 버전이 반환됨

<xref:System.Environment.OSVersion?displayProperty=nameWithType>에서 애플리케이션 호환성을 위해 선택된 OS 등이 아닌 실제 OS(운영 체제) 버전이 반환됩니다.

## <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서는 <xref:System.Environment.OSVersion?displayProperty=nameWithType>이 Windows 호환 모드에서 애플리케이션을 실행할 경우 부정확할 수 있는 OS 버전을 반환합니다. 자세한 내용은 [GetVersionExA 함수 설명](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks)을 참조하세요. macOS에서 <xref:System.Environment.OSVersion?displayProperty=nameWithType>은 기본 Darwin 커널 버전을 반환합니다.

.NET 5.0부터 <xref:System.Environment.OSVersion?displayProperty=nameWithType>은 Windows와 macOS의 실제 운영 체제 버전을 반환합니다.

다음 표에는 동작에서의 차이가 나와 있습니다.

|  | 이전 .NET 버전 | .NET 5 이상 |
|--|------------------------|---------|
| Windows | 6.2.9200.0 | 10.0.19042.0 |
| macOS | 19.6.0.0 | 10.15.7 |

## <a name="reason-for-change"></a>변경 이유

이 속성의 사용자는 실제 운영 체제 버전이 반환될 것으로 예상합니다. 대부분의 .NET 앱은 애플리케이션 매니페스트에서 지원되는 버전을 지정하지 않으므로 dotnet 호스트에서 지원되는 기본 버전을 가져옵니다. 따라서 호환성 shim은 실행 중인 앱에서 거의 의미가 없습니다. Windows에서 새 버전을 릴리스할 때 이전 dotnet 호스트를 아직 사용 중인 경우 해당 앱이 잘못된 OS 버전을 가져올 수 있습니다. 실제 버전을 반환하는 것이 이 API에 대한 개발자의 기대와 좀 더 부합됩니다.

.NET 5.0에서 <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>, <xref:System.OperatingSystem.IsMacOSVersionAtLeast%2A?displayProperty=nameWithType> 및 <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute?displayProperty=nameWithType>이 도입되어 <xref:System.Environment.OSVersion?displayProperty=nameWithType>이 Windows와 macOS에 일관성 있게 변경되었습니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

<xref:System.Environment.OSVersion?displayProperty=nameWithType>을 사용하는 코드를 검토하고 테스트하여 원하는 대로 작동하는지 확인합니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Environment.OSVersion`

-->
