---
description: '자세히 알아보기: 방법: 조정 규칙을 사용 하 여 표준 시간대 만들기'
title: '방법: 조정 규칙을 사용하여 표준 시간대 만들기'
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], creating
- time zones [.NET], and adjustment rules
- adjustment rule [.NET]
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
ms.openlocfilehash: d581d01d9f9386adf99079f4f8f8e09585b06848
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99702771"
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a>방법: 조정 규칙을 사용하여 표준 시간대 만들기

응용 프로그램에 필요한 정확한 표준 시간대 정보는 다음과 같은 여러 가지 이유로 특정 시스템에 표시 되지 않을 수 있습니다.

- 현지 시스템의 레지스트리에서 표준 시간대가 정의 되지 않았습니다.

- 표준 시간대에 대 한 데이터가 레지스트리에서 수정 되었거나 제거 되었습니다.

- 표준 시간대에 특정 기록 기간의 표준 시간대 조정에 대 한 정확한 정보가 없습니다.

이러한 경우 메서드를 호출 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 하 여 응용 프로그램에 필요한 표준 시간대를 정의할 수 있습니다. 이 메서드의 오버 로드를 사용 하 여 조정 규칙을 사용 하거나 사용 하지 않고 표준 시간대를 만들 수 있습니다. 표준 시간대가 일광 절약 시간을 지 원하는 경우 고정 또는 부동 조정 규칙을 사용 하 여 조정을 정의할 수 있습니다. 이러한 용어에 대 한 정의는 [표준 시간대 개요](time-zone-overview.md)의 "표준 시간대 용어" 섹션을 참조 하세요.

> [!IMPORTANT]
> 메서드를 호출 하 여 만든 사용자 지정 표준 시간대 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 는 레지스트리에 추가 되지 않습니다. 대신 메서드 호출에서 반환 되는 개체 참조를 통해서만 액세스할 수 있습니다 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> .

이 항목에서는 조정 규칙을 사용 하 여 표준 시간대를 만드는 방법을 보여 줍니다. 일광 절약 시간 조정 규칙을 지원 하지 않는 표준 시간대를 만들려면 [방법: 조정 규칙을 사용 하지 않고 표준 시간대 만들기](create-time-zones-without-adjustment-rules.md)를 참조 하세요.

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a>부동 조정 규칙을 사용 하 여 표준 시간대를 만들려면

1. 각 조정에 대해 (즉, 특정 시간 간격 동안 다시 표준 시간으로 전환 하는 경우) 다음을 수행 합니다.

    1. 표준 시간대 조정에 대 한 시작 전환 시간을 정의 합니다.

       메서드를 호출 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> 하 고 전환 <xref:System.DateTime> 시간을 정의 하는 값, 전환 월을 정의 하는 정수 값, 전환이 발생 하는 주를 정의 하는 정수 값 및 전환이 발생 하는 요일을 정의 하는 값을 전달 해야 합니다 <xref:System.DayOfWeek> . 이 메서드 호출은 개체를 인스턴스화합니다 <xref:System.TimeZoneInfo.TransitionTime> .

    2. 표준 시간대 조정의 종료 전환 시간을 정의 합니다. 이렇게 하려면 메서드를 다른 호출 해야 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> 합니다. 이 메서드 호출은 두 번째 개체를 인스턴스화합니다 <xref:System.TimeZoneInfo.TransitionTime> .

    3. 메서드를 호출 <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> 하 고 조정의 유효한 시작 및 종료 날짜, <xref:System.TimeSpan> 전환 시간을 정의 하는 개체 및 <xref:System.TimeZoneInfo.TransitionTime> 일광 절약 시간으로 전환 하는 경우를 정의 하는 두 개의 개체를 전달 합니다. 이 메서드 호출은 개체를 인스턴스화합니다 <xref:System.TimeZoneInfo.AdjustmentRule> .

    4. 개체를 <xref:System.TimeZoneInfo.AdjustmentRule> 개체의 배열에 할당 <xref:System.TimeZoneInfo.AdjustmentRule> 합니다.

2. 표준 시간대의 표시 이름을 정의 합니다. 표시 이름은 표준 시간대의 오프셋 (UTC)을 괄호로 묶고 표준 시간대를 나타내는 문자열, 표준 시간대에서 하나 이상의 도시 또는 표준 시간대의 국가 또는 지역 중 하나 이상에 해당 하는 문자열 뒤에 오는 매우 일반적인 형식입니다.

3. 표준 시간대의 표준 시간 이름을 정의 합니다. 일반적으로이 문자열은 표준 시간대의 식별자로도 사용 됩니다.

4. 표준 시간대의 일광 절약 시간 이름을 정의 합니다.

5. 표준 시간대의 표준 이름과 다른 식별자를 사용 하려면 표준 시간대 식별자를 정의 합니다.

6. <xref:System.TimeSpan>UTC에서 표준 시간대의 오프셋을 정의 하는 개체를 인스턴스화합니다. 시간이 UTC 보다 늦은 표준 시간대에는 양의 오프셋이 있습니다. 시간이 UTC 보다 이전인 표준 시간대에는 음의 오프셋이 있습니다.

7. 메서드를 호출 <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> 하 여 새 표준 시간대를 인스턴스화합니다.

## <a name="example"></a>예제

다음 예제에서는 1918부터 현재 까지의 다양 한 시간 간격에 대 한 조정 규칙을 포함 하는 미국에 대 한 중부 표준 시간대를 정의 합니다.

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

이 예제에서 만든 표준 시간대에는 여러 조정 규칙이 있습니다. 조정 규칙의 유효 시작 및 종료 날짜가 다른 조정 규칙의 날짜와 겹치지 않도록 주의를 기울여야 합니다. 겹치는 부분이 있으면 <xref:System.InvalidTimeZoneException> 이 throw 됩니다.

부동 조정 규칙의 경우 값 5는 `week` 메서드의 매개 변수에 전달 되어 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> 특정 월의 마지막 주에 전환이 발생 함을 표시 합니다.

<xref:System.TimeZoneInfo.AdjustmentRule>메서드 호출에서 사용할 개체의 배열을 만들 <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> 때 코드는 표준 시간대에 대 한 조정 수에 필요한 크기에 맞게 배열을 초기화할 수 있습니다. 대신,이 코드 예제에서는 메서드를 호출 <xref:System.Collections.Generic.List%601.Add%2A> 하 여 각 조정 규칙을 <xref:System.Collections.Generic.List%601> 개체의 제네릭 컬렉션에 추가 <xref:System.TimeZoneInfo.AdjustmentRule> 합니다. 그런 다음 코드는 메서드를 호출 <xref:System.Collections.Generic.List%601.CopyTo%2A> 하 여이 컬렉션의 멤버를 배열에 복사 합니다.

또한이 예제에서는 메서드를 사용 하 여 <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> 고정 날짜 조정을 정의 합니다. 이는 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> 전환 매개 변수의 시간, 월 및 일만 필요 하다는 점을 제외 하 고 메서드를 호출 하는 것과 비슷합니다.

예제는 다음과 같은 코드를 사용 하 여 테스트할 수 있습니다.

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a>코드 컴파일

이 예제에는 다음 사항이 필요합니다.

- 다음 네임 스페이스를 가져옵니다.

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>참고 항목

- [날짜, 시간 및 표준 시간대](index.md)
- [표준 시간대 개요](time-zone-overview.md)
- [방법: 조정 규칙을 사용하지 않고 표준 시간대 만들기](create-time-zones-without-adjustment-rules.md)
