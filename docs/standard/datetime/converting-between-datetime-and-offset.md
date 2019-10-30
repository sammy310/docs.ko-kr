---
title: DateTime과 DateTimeOffset 간 변환
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DateTime structure, converting
- time zones [.NET Framework], conversions
- UTC times, converting
- DateTimeOffset structure, converting
- converting DateTimeOffset and DateTime values
- dates [.NET Framework], converting
- converting times
- Date data type, converting
- local time conversions
ms.assetid: b605ff97-0c45-4c24-833f-4c6a3e8be64c
ms.openlocfilehash: 428553f75db2cca6705ac72873e86e120e94d134
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132589"
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>DateTime과 DateTimeOffset 간 변환

<xref:System.DateTimeOffset> 구조가 <xref:System.DateTime> 구조 보다 더 높은 수준의 표준 시간대 인식을 제공 하지만 <xref:System.DateTime> 매개 변수는 메서드 호출에서 보다 일반적으로 사용 됩니다. 따라서 <xref:System.DateTimeOffset> 값을 <xref:System.DateTime> 값으로 변환 하거나 그 반대로 변환 하는 기능은 매우 중요 합니다. 이 항목에서는 표준 시간대 정보를 최대한 많이 보존 하는 방식으로 이러한 변환을 수행 하는 방법을 보여 줍니다.

> [!NOTE]
> 표준 시간대의 시간을 나타낼 때 <xref:System.DateTime>와 <xref:System.DateTimeOffset> 유형 모두 몇 가지 제한이 있습니다. <xref:System.DateTime.Kind%2A> 속성을 사용 하면 <xref:System.DateTime> UTC (협정 세계시)와 시스템의 현지 표준 시간대만 반영할 수 있습니다. <xref:System.DateTimeOffset>는 UTC에서의 시간 오프셋을 반영 하지만 해당 오프셋이 속한 실제 표준 시간대를 반영 하지는 않습니다. 표준 시간대에 대 한 시간 값 및 지원에 대 한 자세한 내용은 [DateTime, DateTimeOffset, TimeSpan 및 TimeZoneInfo 중에서 선택](../../../docs/standard/datetime/choosing-between-datetime.md)을 참조 하세요.

## <a name="conversions-from-datetime-to-datetimeoffset"></a>DateTime에서 DateTimeOffset으로 변환

<xref:System.DateTimeOffset> 구조에서는 대부분의 변환에 적합 한 <xref:System.DateTimeOffset> 변환에 <xref:System.DateTime>를 수행 하는 두 가지 방법을 제공 합니다.

- <xref:System.DateTimeOffset.%23ctor%2A> 생성자는 <xref:System.DateTime> 값을 기반으로 새 <xref:System.DateTimeOffset> 개체를 만듭니다.

- <xref:System.DateTimeOffset> 개체에 <xref:System.DateTime> 값을 할당할 수 있는 암시적 변환 연산자입니다.

UTC 및 로컬 <xref:System.DateTime> 값의 경우 결과 <xref:System.DateTimeOffset> 값의 <xref:System.DateTimeOffset.Offset%2A> 속성은 UTC 또는 현지 표준 시간대 오프셋을 정확 하 게 반영 합니다. 예를 들어 다음 코드는 UTC 시간을 해당 하는 <xref:System.DateTimeOffset> 값으로 변환 합니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

이 경우 `utcTime2` 변수의 오프셋은 00:00입니다. 마찬가지로 다음 코드에서는 현지 시간을 해당 하는 <xref:System.DateTimeOffset> 값으로 변환 합니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

그러나 <xref:System.DateTime.Kind%2A> 속성을 <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>하는 <xref:System.DateTime> 값의 경우 이러한 두 변환 메서드는 오프셋이 현지 표준 시간대의 오프셋 인 <xref:System.DateTimeOffset> 값을 생성 합니다. 미국 태평양 표준 시간대에 실행되는 다음 예제에서 이를 확인할 수 있습니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

<xref:System.DateTime> 값이 현지 표준 시간대 또는 UTC와 다른 날짜 및 시간을 반영 하는 경우에는이 값을 <xref:System.DateTimeOffset> 값으로 변환 하 고 오버 로드 된 <xref:System.DateTimeOffset.%23ctor%2A> 생성자를 호출 하 여 해당 표준 시간대 정보를 보존할 수 있습니다. 예를 들어 다음 예제에서는 중부 표준시를 반영 하는 <xref:System.DateTimeOffset> 개체를 인스턴스화합니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

이 생성자 오버 로드에 대 한 두 번째 매개 변수 (UTC에서의 시간 오프셋을 나타내는 <xref:System.TimeSpan> 개체)는 시간의 해당 표준 시간대의 <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> 메서드를 호출 하 여 검색 해야 합니다. 메서드의 단일 매개 변수는 변환할 날짜와 시간을 나타내는 <xref:System.DateTime> 값입니다. 표준 시간대에서 일광 절약 시간제를 지원하는 경우 이 매개 변수를 사용하면 특정 날짜와 시간에 적절한 오프셋을 해당 메서드에서 결정할 수 있습니다.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>DateTimeOffset에서 DateTime으로 변환

<xref:System.DateTimeOffset.DateTime%2A> 속성은 <xref:System.DateTimeOffset>을 수행 하 여 <xref:System.DateTime> 변환을 수행 하는 데 가장 일반적으로 사용 됩니다. 그러나 다음 예제와 같이 <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind.Unspecified>되는 <xref:System.DateTime> 값을 반환 합니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

즉, <xref:System.DateTimeOffset.DateTime%2A> 속성을 사용할 때 변환에서 <xref:System.DateTimeOffset> 값의 UTC와의 관계에 대 한 모든 정보가 손실 됩니다. 이는 <xref:System.DateTimeOffset.DateTime%2A> 구조가 <xref:System.DateTime.Kind%2A> 속성의 두 표준 시간대만 반영 하므로 UTC 시간이 나 시스템의 현지 시간에 해당 하는 <xref:System.DateTimeOffset> 값에 영향을 줍니다.

<xref:System.DateTimeOffset>을 <xref:System.DateTime> 값으로 변환할 때 표준 시간대 정보를 최대한 많이 보존 하려면 <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> 및 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 속성을 사용할 수 있습니다.

### <a name="converting-a-utc-time"></a>UTC 시간 변환

변환 된 <xref:System.DateTimeOffset.DateTime%2A> 값이 UTC 시간 임을 나타내려면 <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> 속성의 값을 검색할 수 있습니다. 다음 두 가지 방법으로 <xref:System.DateTimeOffset.DateTime%2A> 속성과 다릅니다.

- <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind.Utc>되는 <xref:System.DateTime> 값을 반환 합니다.

- <xref:System.DateTimeOffset.Offset%2A> 속성 값이 <xref:System.TimeSpan.Zero?displayProperty=nameWithType>같지 않으면 시간을 UTC로 변환 합니다.

> [!NOTE]
> 응용 프로그램에서 변환 된 <xref:System.DateTime> 값이 특정 시점을 명확 하 게 식별 해야 하는 경우 <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> 속성을 사용 하 여 <xref:System.DateTime> 변환에 대 한 모든 <xref:System.DateTimeOffset>를 처리 하는 것이 좋습니다.

다음 코드는 <xref:System.DateTimeOffset.UtcDateTime%2A> 속성을 사용 하 여 오프셋이 <xref:System.TimeSpan.Zero?displayProperty=nameWithType>는 <xref:System.DateTimeOffset> 값을 <xref:System.DateTime> 값으로 변환 합니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

다음 코드는 <xref:System.DateTimeOffset.UtcDateTime%2A> 속성을 사용 하 여 <xref:System.DateTimeOffset> 값에서 표준 시간대 변환과 형식 변환을 모두 수행 합니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>현지 시간 변환

<xref:System.DateTimeOffset> 값이 현지 시간을 나타내도록 나타내려면 <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> 속성에 의해 반환 된 <xref:System.DateTime> 값을 `static` (`Shared`의 Visual Basic) <xref:System.DateTime.SpecifyKind%2A> 메서드에 전달할 수 있습니다. 메서드는 전달 된 날짜와 시간을 첫 번째 매개 변수로 반환 하지만 <xref:System.DateTime.Kind%2A> 속성을 두 번째 매개 변수로 지정 된 값으로 설정 합니다. 다음 코드에서는 현지 표준 시간대의 오프셋에 해당 하는 <xref:System.DateTimeOffset> 값을 변환할 때 <xref:System.DateTime.SpecifyKind%2A> 메서드를 사용 합니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

<xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 속성을 사용 하 여 <xref:System.DateTimeOffset> 값을 로컬 <xref:System.DateTime> 값으로 변환할 수도 있습니다. 반환 된 <xref:System.DateTime> 값의 <xref:System.DateTime.Kind%2A> 속성은 <xref:System.DateTimeKind.Local>입니다. 다음 코드에서는 현지 표준 시간대의 오프셋에 해당 하는 <xref:System.DateTimeOffset> 값을 변환할 때 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 속성을 사용 합니다. 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

<xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 속성을 사용 하 여 <xref:System.DateTime> 값을 검색 하는 경우 속성의 `get` 접근자는 먼저 <xref:System.DateTimeOffset> 값을 UTC로 변환한 다음 <xref:System.DateTimeOffset.ToLocalTime%2A> 메서드를 호출 하 여 현지 시간으로 변환 합니다. 즉, <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 속성에서 값을 검색 하 여 형식 변환을 수행할 때 표준 시간대 변환을 수행할 수 있습니다. 또한 변환을 수행할 때 현지 표준 시간대의 조정 규칙도 적용됩니다. 다음 코드에서는 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 속성을 사용 하 여 형식과 표준 시간대 변환을 모두 수행 하는 방법을 보여 줍니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>범용 변환 메서드

다음 예제에서는 <xref:System.DateTimeOffset> 값을 <xref:System.DateTime> 값으로 변환 하는 `ConvertFromDateTimeOffset` 이라는 메서드를 정의 합니다. 오프셋을 기반으로 하는 <xref:System.DateTimeOffset> 값이 UTC 시간, 현지 시간 또는 다른 시간 인지 여부를 확인 하 고 그에 따라 반환 된 날짜 및 시간 값의 <xref:System.DateTime.Kind%2A> 속성을 정의 합니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

다음 예제에서는 `ConvertFromDateTimeOffset` 메서드를 호출하여 UTC 시간, 현지 시간 및 미국 중부 표준 시간대를 나타내는 <xref:System.DateTimeOffset> 값을 변환합니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

이 코드에서는 다음 두 가지를 가정합니다. 이러한 가정은 애플리케이션과 애플리케이션에서 사용하는 날짜 및 시간 값의 소스에 따라 맞지 않을 수도 있습니다.

- 오프셋이 <xref:System.TimeSpan.Zero?displayProperty=nameWithType> UTC를 나타내는 날짜 및 시간 값이 있다고 가정 합니다. 실제로 UTC는 특정 표준 시간대의 시간이 아니라 표준화된 전세계 표준 시간대의 시간입니다. 표준 시간대의 오프셋은 <xref:System.TimeSpan.Zero>수도 있습니다.

- 현지 표준 시간대 오프셋과 동일한 오프셋의 날짜와 시간이 현지 표준 시간대를 나타낸다고 가정합니다. 그러나 날짜 및 시간 값이 원래 표준 시간대와 관련이 없기 때문에 이와 다른 경우가 있을 수 있습니다. 날짜와 시간은 동일한 오프셋을 사용하는 다른 표준 시간대에서 가져올 수 있습니다.

## <a name="see-also"></a>참조

- [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
