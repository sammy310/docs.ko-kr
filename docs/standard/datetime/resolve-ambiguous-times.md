---
title: '방법: 모호한 시간 확인'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c98f47613479c40804dce254261c560d829d91c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586373"
---
# <a name="how-to-resolve-ambiguous-times"></a>방법: 모호한 시간 확인

모호한 시간은 하나 이상의 UTC(협정 세계시)를 매핑하는 시간입니다. 표준 시간대의 일광 절약 시간에서 표준 시간으로 전환하는 것과 같이 클록 시간을 뒤로 조정하는 경우 발생합니다. 모호한 시간을 처리하는 경우 다음 중 하나를 수행할 수 있습니다.

* 시간을 UTC로 매핑하는 방법에 대해 가정합니다. 예를 들어 있는 모호한 시간을 항상 표준 시간대의 표준 시간으로 표시한다고 가정할 수 있습니다.

* 모호한 시간이 사용자로부터 입력된 데이터 항목인 경우 사용자가 모호성을 해결하도록 맡기면 됩니다.

이 항목에서는 표준 시간대의 표준 시간을 나타낸다고 가정 하 여 모호한 시간을 해결 하는 방법을 보여 줍니다.

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>모호한 시간을 표준 시간대의 표준 시간으로 매핑하려면

1. 호출 된 <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> 시간이 모호한 지를 결정 하는 방법입니다.

2. 시간이 모호한 경우에서 시간을 빼서 합니다 <xref:System.TimeSpan> 표준 시간대에서 반환 된 개체 <xref:System.TimeZoneInfo.BaseUtcOffset%2A> 속성입니다.

3. 호출 된 `static` (`Shared` Visual Basic.net에서) <xref:System.DateTime.SpecifyKind%2A> UTC 날짜 및 시간 값의을 설정 하는 방법 <xref:System.DateTime.Kind%2A> 속성을 <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>입니다.

## <a name="example"></a>예제

다음 예제에서는 현지 표준 시간대의 표준 시간을 나타낸다고 가정 하 여 UTC로 모호한 시간을 변환 하는 방법을 보여 줍니다.

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

예제에서는 라는 메서드로 구성 됩니다 `ResolveAmbiguousTime` 결정 하는 여부를 <xref:System.DateTime> 전달 된 값이 모호 합니다. 메서드는 반환 된 값이 모호한는 <xref:System.DateTime> 해당 UTC 시간을 나타내는 값입니다. 현지 표준 시간대의 값을 빼서이 변환을 처리 <xref:System.TimeZoneInfo.BaseUtcOffset%2A> 현지 시간에서 속성입니다.

모호한 시간을 호출 하 여 처리 되는 일반적으로 <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> 의 배열을 검색 하는 메서드 <xref:System.TimeSpan> 모호한 시간의 가능한 UTC를 포함 하는 개체의 오프셋입니다. 그러나 이 예제에서는 모호한 시간이 표준 시간대의 표준 시간으로 항상 매핑되어야 한다고 임의로 가정합니다. <xref:System.TimeZoneInfo.BaseUtcOffset%2A> 속성 UTC와 표준 시간대의 표준 시간 간에 오프셋을 반환 합니다.

이 예제에서는 현지 표준 시간대에 대 한 모든 참조를 통해 이루어집니다는 <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 속성; 로컬 시간 영역 개체 변수에 할당 되지 않습니다. 때문에이 권장 되는 방법에 대 한 호출을 <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> 현지 표준 시간대에 할당 된 모든 개체를 무효화 하는 메서드.

## <a name="compiling-the-code"></a>코드 컴파일

이 예제에는 다음 사항이 필요합니다.

* 합니다 <xref:System> 네임 스페이스를 사용 하 여 가져와야 합니다 `using` 문 (C# 코드에 필요).

## <a name="see-also"></a>참고자료

- [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
- [방법: 사용자의 모호한 시간 확인 작업 허용](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
