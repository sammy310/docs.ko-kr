---
title: '방법: 조정 규칙을 사용하지 않고 표준 시간대 만들기'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb3ffc7b6f1f7baec7ce6beb5a50b706ff78bfa1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026551"
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a>방법: 조정 규칙을 사용하지 않고 표준 시간대 만들기

응용 프로그램에 필요한 정확한 표준 시간대 정보를 여러 가지 이유로 특정 시스템에 존재할 수 있습니다.

* 로컬 시스템 레지스트리에서 표준 시간대를 정의 하지 않았습니다.

* 표준 시간대에 대 한 데이터 수정 되었거나 레지스트리에서 제거 합니다.

* 표준 시간대가 있지만 중요 한 특정 기간에 대 한 표준 시간대 조정에 대 한 정확한 정보가 없습니다.

이러한 경우에 호출할 수 있습니다는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 응용 프로그램에 필요한 표준 시간대를 정의 하는 방법입니다. 표준 시간대를 사용 하 여 만들거나 조정 규칙 없이이 메서드의 오버 로드를 사용할 수 있습니다. 표준 시간대 일광 절약 시간을 지 원하는 경우에 고정 또는 부동 조정 규칙 중 하나를 사용 하 여 조정을 정의할 수 있습니다. (이러한 용어의 정의 "표준 시간대 용어" 섹션을 참조 하세요 [표준 시간대 개요](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> 호출 하 여 만든 사용자 지정 표준 시간대를 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 레지스트리에 추가 되지 않습니다. 대신 반환한 개체 참조를 통해서만 액세스할 수 있습니다는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 호출 합니다.

이 항목에서는 조정 규칙 없이 시간대를 만드는 방법을 보여 줍니다. 일광 절약 시간 조정 규칙을 지 원하는 표준 시간대를 만들려면 참조 [방법: 표준 시간대 조정 규칙을 사용 하 여 만들기](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)합니다.

### <a name="to-create-a-time-zone-without-adjustment-rules"></a>조정 규칙 없이 시간 영역을 만들려면

1. 표준 시간대의 표시 이름을 정의 합니다.

   표시 이름을 시간대의 오프셋이 utc (협정 세계시) 괄호로 묶인 및 시간대 또는 표준 시간대 또는 하나에 있는 도시를 더 이상의 cou를 식별 하는 문자열 뒤에 대개 표준 형식을 따릅니다. ntries 또는 지역 표준 시간대에서입니다.

2. 표준 시간대의 표준 시간 이름을 정의 합니다. 일반적으로이 문자열은 또한 해당 표준 시간대의 식별자로 사용 됩니다.

3. 표준 시간대의 표준 이름 보다 다른 식별자를 사용 하려는 경우 표준 시간대 식별자를 정의 합니다.

4. 인스턴스화하는 <xref:System.TimeSpan> UTC 표준 시간대 오프셋을 정의 하는 개체입니다. UTC 보다 늦은 시간을 사용 하 여 표준 시간대 오프셋은 양수입니다. UTC 보다 이전 시간을 사용 하 여 표준 시간대 오프셋은 음수 경우

5. 호출 된 <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> 새 표준 시간대를 인스턴스화하는 방법입니다.

## <a name="example"></a>예제

다음 예제에서는 모슨에서 남극 대륙, 조정 규칙 없이 대 한 사용자 지정 표준 시간대를 정의 합니다.

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

에 할당 된 문자열을 <xref:System.TimeZoneInfo.DisplayName%2A> 속성에는 UTC 표준 시간대 오프셋 뒤에 설명 된 표준 시간대의 표준 형식을 따릅니다.

## <a name="compiling-the-code"></a>코드 컴파일

이 예제에는 다음 사항이 필요합니다.

* System.Core.dll에 대 한 참조를 프로젝트에 추가할 수 있습니다.

* 다음 네임 스페이스를 가져와야 합니다.

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>참고자료

- [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
- [표준 시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)
- [방법: 표준 시간대 조정 규칙을 사용 하 여 만들기](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)
