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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d5f807481468b61365c8b4d8412f12a4741ebb9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912758"
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>날짜 및 시간에 대한 산술 연산 수행

하지만 모두를 <xref:System.DateTime> 하며 <xref:System.DateTimeOffset> 값에 산술 연산을 수행 하는 멤버를 제공 하는 구조, 산술 연산의 결과 매우 다릅니다. 이 항목에서는 이러한 차이점을 검사 하 고, 날짜 및 시간 데이터의 표준 시간대 인식이 관련이 하, 완벽 하 게 날짜 및 시간 데이터를 사용 하 여 표준 시간대 인식 작업을 수행 하는 방법에 설명 합니다.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>비교 및 날짜/시간 값을 사용 하 여 산술 연산

<xref:System.DateTime.Kind%2A?displayProperty=nameWithType> 속성을 사용 하면 한 <xref:System.DateTimeKind> 를 현지 시간을 utc (협정 세계시) 또는 미지정된 표준 시간대의 시간을 나타내는지 여부를 나타내는 날짜 및 시간에 할당할 값입니다. 그러나 비교 또는 날짜 및 시간 산술 연산을 수행 하는 경우이 제한 된 표준 시간대 정보는 무시 됩니다 <xref:System.DateTimeKind> 값입니다. 현재 UTC 시간을 포함한 현재 현지 시간을 비교하는 다음 예제에서는 이를 보여 줍니다.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

<xref:System.DateTime.CompareTo%28System.DateTime%29> 메서드는 현지 시간 보다 이전 인지 보고 (또는 미만)는 UTC 시간과 빼기 연산을 나타내는 미국의 UTC와 시스템의 현지 시간 사이의 차이 태평양 표준 시간대는 7시간입니다. 하지만 이러한 두 개의 값은 시간에서 단일 지점의 다양한 표현을 제공하기 때문에 이 경우에 이 시간 간격이 UTC에서 현지 표준 시간대 오프셋을 발생시키는 것이 명확합니다.

보다 일반적으로 <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> 속성에서 반환 된 결과 영향을 주지 않습니다 <xref:System.DateTime.Kind> 비교 및 산술 연산 메서드에서 (두 개의 동일한 지점 시간에서 비교를 나타냄)으로 하지만 해당 결과의 해석에 영향을 줄 수 있습니다. 예를 들어:

* 갖는 두 개의 날짜 및 시간 값에서 모든 산술 연산의 결과 수행 <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> 속성이 둘 다 <xref:System.DateTimeKind> 두 값 사이의 실제 시간 간격을 반영 합니다. 마찬가지로 이러한 두 개의 날짜 및 시간 값을 비교하면 시간 간의 관계를 정확하게 반영합니다.

* 갖는 두 개의 날짜 및 시간 값에 산술 또는 비교 작업의 결과 수행 <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> 속성이 둘 다 <xref:System.DateTimeKind> 또는 다른 두 날짜 및 시간 값에 대해 <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> 시계 시간 차이 반영 하는 속성 값 두 값 사이.

* 로컬 날짜 및 시간 값에 대한 산술 또는 비교 작업은 특정 값이 모호하거나 잘못되었는지 여부를 고려하지 않거나 현지 표준 시간대 전환 또는 일광 절약 시간에서 발생하는 모든 조정 규칙의 효과를 고려하지 않습니다.

* UTC와 현지 시간 사이의 차이를 비교하거나 계산하는 작업에는 결과에 있는 UTC에서 현지 표준 시간대 오프셋과 동일한 시간 간격이 포함됩니다.

* 지정되지 않은 시간과 UTC 또는 현지 시간 사이의 차이를 비교하거나 계산하는 작업은 간단한 클록 시간을 반영합니다. 표준 시간대 차이를 고려하지 않으면 결과가 표준 시간대 조정 규칙의 애플리케이션을 반영하지 않습니다.

* 두 개의 지정되지 않은 시간 사이의 차이를 비교하거나 계산하는 작업에는 두 개의 다른 시간대의 시간 사이의 차이를 반영하는 알 수 없는 간격이 포함될 수 있습니다.

여러 시나리오가 있는 표준 시간대의 차이점을 미치치지 않습니다 날짜 및 시간 계산 (그 중 일부 설명은 참조 하세요. [DateTime, DateTimeOffset, TimeSpan 및 TimeZoneInfo 중 선택](../../../docs/standard/datetime/choosing-between-datetime.md)) 또는는 컨텍스트 날짜 및 시간 데이터 비교 또는 산술 연산 작업의 의미를 정의합니다.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>비교 및 산술 연산 DateTimeOffset 값을 사용 하 여

<xref:System.DateTimeOffset> 날짜 및 시간 뿐만 아니라 UTC에 상대적인 해당 시간과 날짜를 명확 하 게 정의 하는 오프셋 값이 포함 되어 있습니다. 이렇게 하면에 대 한 경우와 다르게 같음을 정의할 수 <xref:System.DateTimeOffset> 값입니다. 반면 <xref:System.DateTime> 값은 동일한 날짜 및 시간 값을 가질 경우 동일 <xref:System.DateTimeOffset> 값이 같으면 두 참조 하는 경우 동일한 지점을 시간에서입니다. 이렇게 하면를 <xref:System.DateTimeOffset> 값 더 정확 해지고 해석 두 날짜 및 시간 사이의 간격을 결정 하는 대부분의 산술 연산 및 비교에 사용 될 때 적어집니다. 다음 예제에서는 합니다 <xref:System.DateTimeOffset> 로컬 비교 하는 이전 예제 및 UTC에 해당 <xref:System.DateTimeOffset> 값, 동작의이 차이 보여 줍니다.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

이 예는 <xref:System.DateTimeOffset.CompareTo%2A> 메서드는 현재 현지 시간과 현재 UTC 시간가 서로 같으면 빼기 나타냅니다 <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> 값은 두 시간 사이의 차이가 임을 나타냅니다 <xref:System.TimeSpan.Zero?displayProperty=nameWithType>합니다.

사용 하는 주요 제한 사항은 <xref:System.DateTimeOffset> 날짜 및 시간 산술 연산의 값은 있지만 <xref:System.DateTimeOffset> 값 시간대 인식이 없는 완벽 하 게 표준 시간대 인식 합니다. 하지만 합니다 <xref:System.DateTimeOffset> UTC 표준 시간대의 오프셋을 반영 하는 값의 오프셋 때는 <xref:System.DateTimeOffset> 변수에 값 할당, 이후에 표준 시간대에서와 분리 됩니다. 더 이상 식별 가능한 시간과 직접 연결되어 있기 때문에 날짜 및 시간 간격의 더하기 및 빼기는 표준 시간대의 조정 규칙을 고려하지 않습니다.

예를 들어 미국 중부 표준시에서는 2008년 3월 9일 오전 2시에 표준 시간대가 일광 절약 시간제로 전환됩니다. 즉, 중부 표준시 2008년 3월 9일 오전 1시 30분에 2시간 30분의 간격을 더하면 날짜와 시간은 2008년 3월 9일 오전 5시가 됩니다. 그러나 다음 예제와 같이 이 더하기 연산의 결과는 2008년 3월 9일 오전 4시가 됩니다. 관심 있는 표준 시간대의 시간이 아니지만(즉, 예상된 표준 시간대 오프셋이 아님) 이 작업의 결과는 올바른 특정 시점을 나타냅니다.

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>시간대의 시간으로 산술 연산

<xref:System.TimeZoneInfo> 클래스는 다양 한 다른 시간대의 시간을 변환할 때 자동으로 조정을 적용 하는 변환 메서드를 포함 합니다. 이러한 요구 사항은 다음과 같습니다.

* 합니다 <xref:System.TimeZoneInfo.ConvertTime%2A> 고 <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> 두 표준 시간대 간에 시간 변환 하는 메서드.

* 합니다 <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> 고 <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> 특정 표준 시간대의 시간을 UTC로 변환 하거나 특정 표준 시간대의 시간을 UTC로 변환 하는 메서드.

자세한 내용은 참조 하세요 [표준 시간대 간에 시간 변환](../../../docs/standard/datetime/converting-between-time-zones.md)합니다.

<xref:System.TimeZoneInfo.ConvertTimeToUtc(System.DateTime)> 클래스 날짜 및 시간 산술 연산을 수행할 때 자동으로 조정 규칙을 적용 하는 메서드를 제공 하지 않습니다. 그러나 이렇게 하려면 표준 시간대의 시간을 UTC로 변환하고 산술 연산을 수행하며 UTC에서 표준 시간대의 시간으로 다시 변환해야 합니다. 자세한 내용은 [방법: 날짜 및 시간 산술 연산의 표준 시간대 사용](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)합니다.

예를 들어 다음 코드는 2008년 3월 9일 오전 2시에 2시간 30분을 더한 이전 코드와 유사합니다. 그러나 날짜 및 시간 산술 연산을 수행하기 전에 중부 표준시를 UTC로 변환한 다음 UTC의 결과를 중부 표준시로 다시 변환하기 때문에 결과 시간은 일광 절약 시간제로 전환된 중앙 표준 시간대를 반영합니다.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>참고자료

- [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
- [방법: 날짜 및 시간 산술 연산의 표준 시간대 사용](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)
