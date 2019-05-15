---
title: '방법: 컴퓨터에 있는 표준 시간대 열거'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82898e80f5acb2cb0dcab65390701efc8d48115b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586569"
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>방법: 컴퓨터에 있는 표준 시간대 열거

지정한 표준 시간대를 성공적으로 사용하려면 해당 표준 시간대 관련 정보를 시스템에서 사용할 수 있어야 합니다. Windows XP 및 Windows Vista 운영 체제 레지스트리의이 정보를 저장 합니다. 그러나 전세계에 있는 표준 시간대의 전체 수는 상당히 많지만 레지스트리에는 이들 중 일부에 대한 정보만 포함됩니다. 또한 레지스트리 자체도 동적 구조이므로 그 내용이 실수나 고의로 변경될 수 있습니다. 따라서 언제나 애플리케이션에서 특정 표준 시간대가 정의되어 있고 시스템에서 사용할 수 있다고 가정할 수는 없습니다. 표준 시간대 정보 애플리케이션을 사용하는 많은 애플리케이션의 첫 번째 단계는 필요한 표준 시간대를 로컬 시스템에서 사용할 수 있는지를 확인하거나 사용자에게 표준 시간대를 선택할 수 있는 목록을 제공하는 것입니다. 이렇게 하려면 애플리케이션에서 로컬 시스템에 정의되어 있는 표준 시간대를 나열해야 합니다.

> [!NOTE]
> 응용 프로그램 로컬 시스템에 정의 될 수 있는 특정 표준 시간대의 현재 상태에 의존 하는 경우 응용 프로그램 표준 시간대에 대 한 정보의 직렬화 및 역직렬화 하 여 해당 현재 상태를 확인할 수 있습니다. 응용 프로그램 사용자가 선택할 수 있도록 표준 시간대 목록 컨트롤에 추가한 다음 있습니다. 자세한 내용은 [방법: 포함된 리소스에 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) 고 [방법: 포함된 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)합니다.

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>로컬 시스템에 있는 표준 시간대를 열거하려면

1. <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> 메서드를 호출합니다. 메서드는 제네릭 반환 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 모음인 <xref:System.TimeZoneInfo> 개체입니다. 컬렉션의 항목에 따라 정렬 된 해당 <xref:System.TimeZoneInfo.DisplayName%2A> 속성입니다. 예를 들어:

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. 개별 열거 <xref:System.TimeZoneInfo> 를 사용 하 여 컬렉션의 개체를 `foreach` 루프 (C#) 또는 `For Each`...`Next` 루프 (Visual Basic의 경우) 하 고 각 개체에 대해 필요한 처리를 수행 합니다. 예를 들어, 다음 코드를 열거 합니다 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 컬렉션의 <xref:System.TimeZoneInfo> 1 단계에서 반환 된 개체를 콘솔에 각 표준 시간대의 표시 이름을 나열 합니다.

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>사용자를 로컬 시스템에 있는 표준 시간대의 목록을 표시 하려면

1. <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> 메서드를 호출합니다. 메서드는 제네릭 반환 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 모음인 <xref:System.TimeZoneInfo> 개체입니다.

2. 1 단계에서 반환 된 컬렉션에 할당 된 `DataSource` 속성 forms 또는 ASP.NET 목록 컨트롤을 Windows의 합니다.

3. 검색 된 <xref:System.TimeZoneInfo> 사용자가 선택한 개체입니다.

예제는 Windows 응용 프로그램에 대해 설명합니다.

## <a name="example"></a>예제

이 예제에서는 시스템 목록 상자에서 정의 된 표준 시간대를 표시 하는 Windows 응용 프로그램을 시작 합니다. 이 예제에서는 다음의 값이 포함 된 대화 상자를 표시 합니다 <xref:System.TimeZoneInfo.DisplayName%2A> 사용자가 선택한 표준 시간대 개체의 속성입니다.

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

대부분의 목록 컨트롤 (같은 합니다 <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> 또는 <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> 컨트롤) 개체 변수 컬렉션에 할당할 수 있도록 해당 `DataSource` 속성을 구현 하는 컬렉션으로는 <xref:System.Collections.IEnumerable> 인터페이스. (제네릭 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 클래스가 작업을 수행 합니다.) 컨트롤의 해당 개체의 호출 컬렉션의 개별 개체를 표시할 `ToString` 메서드 개체를 나타내는 데 사용 되는 문자열을 추출 합니다. 경우 <xref:System.TimeZoneInfo> 개체를 `ToString` 메서드가 반환 되는 <xref:System.TimeZoneInfo> 개체의 표시 이름 (값 해당 <xref:System.TimeZoneInfo.DisplayName%2A> 속성).

> [!NOTE]
> 목록 컨트롤 개체를 호출 하므로 `ToString` 메서드 컬렉션을 할당할 수 있습니다 <xref:System.TimeZoneInfo> 개체를 컨트롤에 있는 각 개체에 대해 의미 있는 이름을 표시 하 고 검색할 컨트롤의 <xref:System.TimeZoneInfo> 사용자가 선택한 개체입니다. 이 컨트롤에 다시 할당 되는 컬렉션에 문자열 할당을 컬렉션의 각 개체에 대 한 문자열을 추출 하려면 필요가 `DataSource` 속성을 사용자가 선택한 문자열을 검색 하 고 다음이 문자열을 사용 하 여 개체를 추출 하려면 설명합니다. 

## <a name="compiling-the-code"></a>코드 컴파일

이 예제에는 다음 사항이 필요합니다.

* 다음 네임 스페이스를 가져와야 합니다.

  <xref:System> (C# 코드에서)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>참고자료

- [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
- [방법: 포함된 리소스에 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
- [방법: 포함된 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
