---
title: '방법: TimeZoneInfo 개체 인스턴스화'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET], instantiation
ms.assetid: 8cb620e5-c6a6-4267-a52e-beeb73cd1a34
ms.openlocfilehash: 34606c0e227d7826cd6188f42fc2fb23f17105ca
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063653"
---
# <a name="how-to-instantiate-a-timezoneinfo-object"></a>방법: TimeZoneInfo 개체 인스턴스화

<xref:System.TimeZoneInfo> 개체를 인스턴스화하는 가장 일반적인 방법은 레지스트리에서 해당 정보를 검색하는 것입니다. 이 항목에서는 로컬 시스템 레지스트리에서 <xref:System.TimeZoneInfo> 개체를 인스턴스화하는 방법을 설명합니다.

### <a name="to-instantiate-a-timezoneinfo-object"></a>TimeZoneInfo 개체를 인스턴스화하려면

1. <xref:System.TimeZoneInfo> 개체를 선언합니다.

2. `static` (Visual Basic의 경우`Shared` ) <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> 메서드를 호출합니다.

3. 메서드에서 발생한 예외, 특히 레지스트리에서 표준 시간대가 정의되지 않은 경우 발생하는 <xref:System.TimeZoneNotFoundException> 을 처리합니다.

## <a name="example"></a>예제

다음 코드는 동부 표준시 표준 시간대를 나타내고 현지 시간에 해당하는 동부 표준시를 표시하는 <xref:System.TimeZoneInfo> 개체를 검색합니다.

[!code-csharp[System.TimeZone2.Concepts#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#5)]
[!code-vb[System.TimeZone2.Concepts#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#5)]

<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> 메서드의 단일 매개 변수는 개체의 <xref:System.TimeZoneInfo.Id%2A?displayProperty=nameWithType> 속성에 해당하는, 검색할 표준 시간대의 식별자입니다. 표준 시간대 식별자는 표준 시간대를 고유하게 식별하는 키 필드입니다. 대부분 키는 비교적 짧지만 표준 시간대 식별자는 비교적 깁니다. 대부분의 경우 해당 값은 표준 시간대의 표준 시간 이름을 제공하는 데 사용되는 <xref:System.TimeZoneInfo.StandardName%2A> 개체의 <xref:System.TimeZoneInfo> 속성에 해당합니다. 그러나 예외 사항이 있습니다. 유효한 식별자를 제공하는지 확인하는 가장 좋은 방법은 시스템에서 사용 가능한 표준 시간대를 열거하고 표시된 표준 시간대의 식별자를 확인하는 것입니다. 자세한 내용은 [How to: Enumerate time zones present on a computer](enumerate-time-zones.md)를 참조하세요. [Finding the time zones defined on a local system](finding-the-time-zones-on-local-system.md) 항목에는 선택한 표준 시간대 식별자 목록도 포함되어 있습니다.

표준 시간대가 있는 경우 메서드는 해당 <xref:System.TimeZoneInfo> 개체를 반환합니다. 표준 시간대가 없는 경우 메서드에서 <xref:System.TimeZoneNotFoundException>이 발생합니다. 표준 시간대가 있지만 해당 데이터가 손상되었거나 불완전한 경우 메서드에서 <xref:System.InvalidTimeZoneException>이 발생합니다.

애플리케이션에서 사용하는 표준 시간대가 있어야 하는 경우 먼저 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 메서드를 호출하여 레지스트리에서 표준 시간대 정보를 검색합니다. 메서드 호출이 실패하면 예외 처리기가 표준 시간대의 새 인스턴스를 만들거나 직렬화된 <xref:System.TimeZoneInfo> 개체를 역직렬화하여 다시 만들어야 합니다. 예제는 [방법: 포함 리소스에서 표준 시간대 복원](restore-time-zones-from-an-embedded-resource.md) 을 참조 하세요.

## <a name="see-also"></a>추가 정보

- [날짜, 시간 및 표준 시간대](index.md)
- [로컬 시스템에 정의된 표준 시간대 찾기](finding-the-time-zones-on-local-system.md)
- [방법: 미리 정의된 UTC 및 현지 표준 시간대 개체에 액세스](access-utc-and-local.md)
