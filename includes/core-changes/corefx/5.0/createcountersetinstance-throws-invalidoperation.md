---
ms.openlocfilehash: fabbc9a51f61a703ce97db50ab251e7a13ffe348
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144485"
---
### <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a>CounterSet.CreateCounterSetInstance는 인스턴스가 이미 있는 경우 이제 InvalidOperationException을 throw함

.NET 5.0부터 <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType>은 카운터 집합이 이미 있는 경우 <xref:System.ArgumentException> 대신 <xref:System.InvalidOperationException>을 throw합니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Framework 및 .NET Core 1.0~3.1에서 <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>를 호출하여 카운터 집합의 인스턴스를 만들 수 있습니다. 그러나 카운터 집합이 이미 있는 경우 메서드는 <xref:System.ArgumentException> 예외를 throw합니다.

.NET 5.0 이상 버전에서 <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>를 호출하고 카운터 집합이 있으면 <xref:System.InvalidOperationException> 예외가 throw됩니다.

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 5

#### <a name="recommended-action"></a>권장 조치

<xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>를 호출할 때 앱에서 <xref:System.ArgumentException> 예외를 catch하는 경우 <xref:System.InvalidOperationException> 예외도 catch하는 것이 좋습니다.

> [!NOTE]
> <xref:System.ArgumentException> 예외를 catch하는 것은 권장되지 않습니다.

#### <a name="category"></a>범주

핵심 .NET 라이브러리

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->
