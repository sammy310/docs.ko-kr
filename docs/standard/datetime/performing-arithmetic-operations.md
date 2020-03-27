---
title: 날짜 및 시간에 대한 산술 연산 수행
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET Framework], arithmetic operations
- dates [.NET Framework], arithmetic operations
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], comparing
- DateTime structure, arithmetic operations
- DateTimeOffset structure, arithmetic operations
ms.assetid: 87c7ddf2-f15e-48af-8602-b3642237e6d0
ms.openlocfilehash: 0db0331620da8337930bfacf5d1bbd9913647afa
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344179"
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>날짜 및 시간에 대한 산술 연산 수행

구조체와 <xref:System.DateTime> 구조체 <xref:System.DateTimeOffset> 모두 해당 값에 대해 산술 연산을 수행하는 멤버를 제공하지만 산술 연산의 결과는 매우 다릅니다. 이 항목에서는 이러한 차이점을 검사하고 날짜 및 시간 데이터의 표준 시간대 인식 정도와 관련이 있으며 날짜 및 시간 데이터를 사용하여 완전히 표준 시간대 인식 작업을 수행하는 방법에 대해 설명합니다.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>DateTime 값과의 비교 및 산술 연산

속성은 <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> 날짜 <xref:System.DateTimeKind> 및 시간에 값을 할당하여 현지 시간, 조정된 유니버설 타임(UTC) 또는 지정되지 않은 표준 시간대의 시간을 나타내는지 여부를 나타낼 수 있습니다. 그러나 이 제한된 표준 시간대 정보는 값에 대한 <xref:System.DateTimeKind> 날짜 및 시간 산술을 비교하거나 수행할 때 무시됩니다. 현재 UTC 시간을 포함한 현재 현지 시간을 비교하는 다음 예제에서는 이를 보여 줍니다.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

<xref:System.DateTime.CompareTo%28System.DateTime%29> 메서드는 현지 시간이 UTC 시간보다 빠르거나 느리다고 보고하고, 빼기 연산은 미국 태평양 표준 시간대에 있는 시스템의 UTC와 현지 시간 간 차이가 일곱 시간임을 나타냅니다. 그러나 이 두 값은 단일 시점의 서로 다른 표현을 제공하기 때문에 이 경우 시간 간격이 UTC에서 로컬 표준 시간대의 오프셋에 완전히 기인한다는 것이 분명합니다.

일반적으로 속성은 <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> 비교 및 산술 <xref:System.DateTime.Kind> 메서드에 의해 반환된 결과에 영향을 주지 않습니다(두 개의 동일한 점을 시간에서 비교하면 해당 결과의 해석에 영향을 줄 수 있음). 예를 들어:

- <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> 두 날짜 및 시간 값에 대해 수행된 산술 연산 작업의 결과는 두 값 간의 실제 시간 간격을 모두 동일하게 <xref:System.DateTimeKind> 반영합니다. 마찬가지로 이러한 두 개의 날짜 및 시간 값을 비교하면 시간 간의 관계를 정확하게 반영합니다.

- 속성값이 다른 두 날짜 및 시간 값의 <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> 속성이 같거나 <xref:System.DateTimeKind> 두 <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> 값 간의 클럭 시간 차이를 반영하는 두 날짜 및 시간 값에서 수행된 산술 또는 비교 작업의 결과입니다.

- 로컬 날짜 및 시간 값에 대한 산술 또는 비교 작업은 특정 값이 모호하거나 잘못되었는지 여부를 고려하지 않거나 현지 표준 시간대 전환 또는 일광 절약 시간에서 발생하는 모든 조정 규칙의 효과를 고려하지 않습니다.

- UTC와 현지 시간 사이의 차이를 비교하거나 계산하는 작업에는 결과에 있는 UTC에서 현지 표준 시간대 오프셋과 동일한 시간 간격이 포함됩니다.

- 지정되지 않은 시간과 UTC 또는 현지 시간 사이의 차이를 비교하거나 계산하는 작업은 간단한 클록 시간을 반영합니다. 표준 시간대 차이를 고려하지 않으면 결과가 표준 시간대 조정 규칙의 애플리케이션을 반영하지 않습니다.

- 두 개의 지정되지 않은 시간 사이의 차이를 비교하거나 계산하는 작업에는 두 개의 다른 시간대의 시간 사이의 차이를 반영하는 알 수 없는 간격이 포함될 수 있습니다.

표준 시간대 차이가 날짜 및 시간 계산에 영향을 주지 않는 많은 시나리오가 있습니다(이 중 일부에 대한 설명의 경우 [DateTime, DateTimeOffset, TimeSpan 및 TimeZoneInfo 간의 선택](../../../docs/standard/datetime/choosing-between-datetime.md)참조) 또는 날짜 및 시간 데이터의 컨텍스트에서 비교 또는 산술 연산작업의 의미를 정의하는 시나리오가 있습니다.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>DateTimeOffset 값과의 비교 및 산술 연산

<xref:System.DateTimeOffset> 값에는 날짜와 시간뿐만 아니라 UTC를 기준으로 해당 날짜와 시간을 명확하게 정의하는 오프셋도 포함됩니다. 이렇게 하면 값과 다소 다르게 같음을 정의할 <xref:System.DateTimeOffset> 수 있습니다. 값이 <xref:System.DateTime> 동일한 날짜 및 시간 값을 가진 <xref:System.DateTimeOffset> 경우 같지만 둘 다 동일한 시점을 참조하는 경우 값은 동일합니다. 이렇게 하면 <xref:System.DateTimeOffset> 비교 및 두 날짜와 시간 사이의 간격을 결정하는 대부분의 산술 연산에서 사용할 때 해석이 필요 하고 더 정확하고 해석이 덜 필요합니다. 로컬 및 UTC <xref:System.DateTimeOffset> <xref:System.DateTimeOffset> 값을 비교한 이전 예제와 동일한 다음 예제에서는 이러한 동작 의 차이를 보여 줍니다.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

이 예제에서 <xref:System.DateTimeOffset.CompareTo%2A> 메서드는 현재 현지 시간과 현재 UTC 시간이 동일하다는 <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> 것을 나타내고 값 빼기는 <xref:System.TimeSpan.Zero?displayProperty=nameWithType>두 시간 간의 차이가 있음을 나타냅니다.

날짜 및 시간 <xref:System.DateTimeOffset> 산술 에서 값을 사용하는 주요 <xref:System.DateTimeOffset> 제한사항은 값에 표준 시간대 인식이 있지만 표준 시간대를 완전히 인식하지 못한다는 것입니다. 변수가 <xref:System.DateTimeOffset> 먼저 값을 할당할 때 <xref:System.DateTimeOffset> 값의 오프셋은 UTC에서 표준 시간대의 오프셋을 반영하지만 그 후 표준 시간대에서 분리됩니다. 더 이상 식별 가능한 시간과 직접 연결되어 있기 때문에 날짜 및 시간 간격의 더하기 및 빼기는 표준 시간대의 조정 규칙을 고려하지 않습니다.

설명하기 위해 미국 중부 표준시간대의 일광 절약 시간제로의 전환은 오전 2:00에 발생합니다. 보고됩니다. 즉, 중부 표준시 2008년 3월 9일 오전 1시 30분에 2시간 30분의 간격을 더하면 날짜와 시간은 보고됩니다. 그러나 다음 예제와 같이 이 더하기 연산의 결과는 보고됩니다. 이 작업의 결과는 우리가 관심있는 표준 시간대의 시간이 아니지만 정확한 시점을 나타냅니다 (즉, 예상 된 표준 시간대 오프셋이 없습니다).

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>표준 시간대의 시간과 연산 작업

클래스에는 <xref:System.TimeZoneInfo> 한 표준 시간대에서 다른 표준 시간대로 시간을 변환할 때 조정을 자동으로 적용하는 여러 변환 방법이 포함되어 있습니다. 여기에는 다음과 같은 옵션이 포함됩니다.

- 두 <xref:System.TimeZoneInfo.ConvertTime%2A> <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> 표준 시간대 간의 시간을 변환하는 및 메서드입니다.

- 및 <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> 메서드는 특정 표준 시간대의 시간을 UTC로 변환하거나 UTC를 특정 표준 시간대의 시간으로 변환합니다.

자세한 내용은 [표준 시간대 간의 시간 변환을](../../../docs/standard/datetime/converting-between-time-zones.md)참조하십시오.

클래스는 <xref:System.TimeZoneInfo> 날짜 및 시간 산술을 수행할 때 조정 규칙을 자동으로 적용하는 메서드를 제공하지 않습니다. 그러나 이렇게 하려면 표준 시간대의 시간을 UTC로 변환하고 산술 연산을 수행하며 UTC에서 표준 시간대의 시간으로 다시 변환해야 합니다. 자세한 내용은 [사용 방법: 날짜 및 시간 산술 연산에서 표준 시간대를 사용합니다.](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)

예를 들어 다음 코드는 2008년 3월 9일 오전 2시에 2시간 30분을 더한 보고됩니다. 그러나 날짜 및 시간 산술 연산을 수행하기 전에 중부 표준시를 UTC로 변환한 다음 UTC의 결과를 중부 표준시로 다시 변환하기 때문에 결과 시간은 일광 절약 시간제로 전환된 중앙 표준 시간대를 반영합니다.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>참조

- [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
- [방법: 날짜 및 시간 산술 연산에서 표준 시간대 사용](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)
