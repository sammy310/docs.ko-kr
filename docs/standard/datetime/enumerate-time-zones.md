---
title: '방법: 컴퓨터에 있는 표준 시간대 열거'
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], enumerating
- enumerating time zones [.NET]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
ms.openlocfilehash: 276c13bb95685e9588e25238f1a6e45cd57a6c91
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817967"
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>방법: 컴퓨터에 있는 표준 시간대 열거

지정한 표준 시간대를 성공적으로 사용하려면 해당 표준 시간대 관련 정보를 시스템에서 사용할 수 있어야 합니다. Windows XP 및 Windows Vista 운영 체제에서는이 정보를 레지스트리에 저장 합니다. 그러나 전세계에 있는 표준 시간대의 전체 수는 상당히 많지만 레지스트리에는 이들 중 일부에 대한 정보만 포함됩니다. 또한 레지스트리 자체도 동적 구조이므로 그 내용이 실수나 고의로 변경될 수 있습니다. 따라서 언제나 애플리케이션에서 특정 표준 시간대가 정의되어 있고 시스템에서 사용할 수 있다고 가정할 수는 없습니다. 표준 시간대 정보 애플리케이션을 사용하는 많은 애플리케이션의 첫 번째 단계는 필요한 표준 시간대를 로컬 시스템에서 사용할 수 있는지를 확인하거나 사용자에게 표준 시간대를 선택할 수 있는 목록을 제공하는 것입니다. 이렇게 하려면 애플리케이션에서 로컬 시스템에 정의되어 있는 표준 시간대를 나열해야 합니다.

> [!NOTE]
> 응용 프로그램에서 로컬 시스템에 정의 되어 있지 않을 수 있는 특정 표준 시간대가 있는 경우 응용 프로그램은 표준 시간대에 대 한 정보를 serialize 하 고 deserialize 하 여 해당 상태를 확인할 수 있습니다. 그러면 응용 프로그램 사용자가 선택할 수 있도록 표준 시간대를 목록 컨트롤에 추가할 수 있습니다. 자세한 내용은 [방법: 포함 리소스에 표준 시간대 저장](save-time-zones-to-an-embedded-resource.md) 및 [방법: 포함 리소스에서 표준 시간대 복원](restore-time-zones-from-an-embedded-resource.md)을 참조 하세요.

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>로컬 시스템에 있는 표준 시간대를 열거하려면

1. <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> 메서드를 호출합니다. 메서드는 개체의 제네릭 컬렉션을 반환 합니다 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> <xref:System.TimeZoneInfo> . 컬렉션의 항목은 해당 속성을 기준으로 정렬 됩니다 <xref:System.TimeZoneInfo.DisplayName%2A> . 예를 들면 다음과 같습니다.

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. <xref:System.TimeZoneInfo> `foreach` 루프 (c #의 경우) 또는 ...를 사용 하 여 컬렉션의 개별 개체를 열거 합니다. `For Each``Next` 루프 (Visual Basic)를 수행 하 고 각 개체에 필요한 처리를 수행 합니다. 예를 들어 다음 코드는 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> <xref:System.TimeZoneInfo> 1 단계에서 반환 된 개체의 컬렉션을 열거 하 고 각 표준 시간대의 표시 이름을 콘솔에 나열 합니다.

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>로컬 시스템에 있는 표준 시간대 목록을 사용자에 게 표시 하려면

1. <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> 메서드를 호출합니다. 메서드는 개체의 제네릭 컬렉션을 반환 합니다 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> <xref:System.TimeZoneInfo> .

2. 1 단계에서 반환 된 컬렉션을 `DataSource` Windows forms 또는 ASP.NET list 컨트롤의 속성에 할당 합니다.

3. 사용자가 <xref:System.TimeZoneInfo> 선택한 개체를 검색 합니다.

이 예에서는 Windows 응용 프로그램에 대 한 설명을 제공 합니다.

## <a name="example"></a>예제

이 예제에서는 목록 상자에 시스템에 정의 된 표준 시간대를 표시 하는 Windows 응용 프로그램을 시작 합니다. 그런 다음 <xref:System.TimeZoneInfo.DisplayName%2A> 사용자가 선택한 표준 시간대 개체의 속성 값을 포함 하는 대화 상자를 표시 합니다.

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

대부분의 목록 컨트롤 (예: <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> 또는 <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> 컨트롤)을 사용 하면 `DataSource` 해당 컬렉션이 인터페이스를 구현 하는 한 개체 변수의 컬렉션을 해당 속성에 할당할 수 있습니다 <xref:System.Collections.IEnumerable> . 제네릭 클래스는 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 이를 수행 합니다. 컬렉션에 개별 개체를 표시 하기 위해 컨트롤은 개체의 메서드를 호출 하 여 `ToString` 개체를 나타내는 데 사용 되는 문자열을 추출 합니다. 개체의 경우 <xref:System.TimeZoneInfo> 메서드는 개체의 `ToString` <xref:System.TimeZoneInfo> 표시 이름 (속성의 값)을 반환 합니다 <xref:System.TimeZoneInfo.DisplayName%2A> .

> [!NOTE]
> 목록 컨트롤은 개체의 메서드를 호출 하기 때문에 `ToString` 개체의 컬렉션을 <xref:System.TimeZoneInfo> 컨트롤에 할당 하 고, 컨트롤에 각 개체에 대 한 의미 있는 이름을 표시 하 고, 사용자가 선택한 개체를 검색할 수 있습니다 <xref:System.TimeZoneInfo> . 이렇게 하면 컬렉션의 각 개체에 대 한 문자열을 추출 하 고, 컨트롤의 속성에 할당 된 컬렉션에 문자열을 할당 하 고 `DataSource` , 사용자가 선택한 문자열을 검색 한 다음,이 문자열을 사용 하 여 설명 하는 개체를 추출할 필요가 없습니다.

## <a name="compiling-the-code"></a>코드 컴파일

이 예제에는 다음 사항이 필요합니다.

- 다음 네임 스페이스를 가져옵니다.

  <xref:System> (c # 코드)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>참고 항목

- [날짜, 시간 및 표준 시간대](index.md)
- [방법: 포함 리소스에 표준 시간대 저장](save-time-zones-to-an-embedded-resource.md)
- [방법: 포함 리소스에서 표준 시간대 복원](restore-time-zones-from-an-embedded-resource.md)
