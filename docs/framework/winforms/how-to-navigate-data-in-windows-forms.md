---
title: '방법: 데이터 탐색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cursors [Windows Forms], data sources
- data sources [Windows Forms], Windows Forms
- Windows Forms, navigating
- CurrencyManager class [Windows Forms], navigating Windows Forms data
- data [Windows Forms], navigating
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
ms.openlocfilehash: 2dd900b652b0ff21ea0eb0dbc5463b22c869ec7c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739394"
---
# <a name="how-to-navigate-data-in-windows-forms"></a>방법: Windows Forms에서 데이터 탐색
Windows 응용 프로그램에서 데이터 원본의 레코드를 탐색 하는 가장 쉬운 방법은 <xref:System.Windows.Forms.BindingSource> 구성 요소를 데이터 소스에 바인딩한 다음 <xref:System.Windows.Forms.BindingSource>에 컨트롤을 바인딩하는 것입니다. 그런 다음 <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> 및 <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>같은 <xref:System.Windows.Forms.BindingSource>에서 기본 제공 탐색 방법을 사용할 수 있습니다. 이러한 메서드를 사용 하 여 <xref:System.Windows.Forms.BindingSource>의 <xref:System.Windows.Forms.BindingSource.Position%2A> 및 <xref:System.Windows.Forms.BindingSource.Current%2A> 속성을 적절 하 게 조정 합니다. <xref:System.Windows.Forms.BindingSource.Position%2A> 속성을 설정 하 여 항목을 찾고 현재 항목으로 설정할 수도 있습니다.  
  
### <a name="to-increment-the-position-in-a-data-source"></a>데이터 원본에서 위치를 증가 시키려면  
  
1. 바인딩된 데이터의 <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource.Position%2A> 속성을 이동할 레코드 위치로 설정 합니다. 다음 예제에서는 <xref:System.Windows.Forms.BindingSource>의 <xref:System.Windows.Forms.BindingSource.MoveNext%2A> 메서드를 사용 하 여 `nextButton` 클릭 될 때 <xref:System.Windows.Forms.BindingSource.Position%2A> 속성을 늘리는 방법을 보여 줍니다. <xref:System.Windows.Forms.BindingSource>은 `Northwind`데이터 집합의 `Customers` 테이블과 연결 됩니다.  
  
    > [!NOTE]
    > <xref:System.Windows.Forms.BindingSource.Position%2A> 속성을 첫 번째 또는 마지막 레코드 이외의 값으로 설정 하면 .NET Framework에서 위치를 목록 범위 밖의 값으로 설정 하는 것이 허용 되지 않으므로 오류가 발생 하지 않습니다. 응용 프로그램에서 첫 번째 또는 마지막 레코드를 넘어가는 지 여부를 확인 하는 것이 중요 한 경우에는 데이터 요소 수를 초과 하는지 여부를 테스트 하는 논리를 포함 합니다.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>끝을 통과 했는지 여부를 확인 하려면  
  
1. <xref:System.Windows.Forms.BindingSource.PositionChanged> 이벤트에 대한 이벤트 처리기를 만듭니다. 처리기에서 제안 된 위치 값이 실제 데이터 요소 수를 초과 했는지 여부를 테스트할 수 있습니다.  
  
     다음 예제에서는 마지막 데이터 요소에 도달 했는지 여부를 테스트 하는 방법을 보여 줍니다. 예제에서 마지막 요소에 있는 경우 폼의 **다음** 단추를 사용할 수 없습니다.  
  
    > [!NOTE]
    > 코드에서 탐색 하는 목록을 변경 하는 경우 사용자가 새 목록의 전체 길이를 검색할 수 있도록 **다음** 단추를 다시 사용 하도록 설정 해야 합니다. 또한 작업 중인 특정 <xref:System.Windows.Forms.BindingSource>에 대 한 위의 <xref:System.Windows.Forms.BindingSource.PositionChanged> 이벤트를 해당 이벤트 처리 메서드와 연결 해야 합니다. 다음은 <xref:System.Windows.Forms.BindingSource.PositionChanged> 이벤트를 처리 하는 메서드의 예입니다.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>항목을 찾아서 현재 항목으로 설정 하려면  
  
1. 현재 항목으로 설정 하려는 레코드를 찾습니다. 데이터 원본이 <xref:System.ComponentModel.IBindingList>를 구현 하는 경우 <xref:System.Windows.Forms.BindingSource>의 <xref:System.Windows.Forms.BindingSource.Find%2A> 메서드를 사용 하 여이 작업을 수행할 수 있습니다. <xref:System.ComponentModel.IBindingList>를 구현 하는 데이터 원본의 몇 가지 예는 <xref:System.ComponentModel.BindingList%601> 및 <xref:System.Data.DataView>입니다.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>참조

- [Windows Forms에서 지원하는 데이터 소스](data-sources-supported-by-windows-forms.md)
- [Windows Forms 데이터 바인딩의 변경 알림](change-notification-in-windows-forms-data-binding.md)
- [데이터 바인딩 및 Windows Forms](data-binding-and-windows-forms.md)
- [Windows Forms 데이터 바인딩](windows-forms-data-binding.md)
