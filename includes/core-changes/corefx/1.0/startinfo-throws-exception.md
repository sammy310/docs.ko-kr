---
ms.openlocfilehash: 92c03328414410d56a2ff5f445639757367b42c7
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420432"
---
### <a name="processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start"></a>Process.StartInfo는 코드가 시작하지 않은 프로세스에 대해 InvalidOperationException을 throw함

코드가 시작하지 않은 프로세스의 <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> 속성을 읽으면 <xref:System.InvalidOperationException>이 throw됩니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Framework에서는 코드가 시작하지 않은 프로세스의 <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> 속성에 액세스하면 더미 <xref:System.Diagnostics.ProcessStartInfo> 개체가 반환됩니다. 더미 개체는 <xref:System.Diagnostics.ProcessStartInfo.EnvironmentVariables>를 제외하고 모든 속성에 대한 기본값을 포함합니다.

.NET Core 1.0부터 코드가 (<xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>를 호출하여) 시작하지 않은 프로세스의 <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> 속성을 읽는 경우 <xref:System.InvalidOperationException>이 throw됩니다.

#### <a name="version-introduced"></a>도입된 버전

1.0

#### <a name="recommended-action"></a>권장 조치

코드가 시작하지 않은 프로세스의 <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> 속성에 액세스하지 마세요. 예를 들어 <xref:System.Diagnostics.Process.GetProcesses%2A?displayProperty=nameWithType>에서 반환하는 프로세스에 대해서는 이 속성을 읽지 마세요.

#### <a name="category"></a>범주

핵심 .NET 라이브러리

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Diagnostics.Process.StartInfo?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Process.StartInfo`

-->
