---
title: '방법: Windows Forms에서 데이터 탐색'
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
ms.openlocfilehash: 920f6d6206a8f33a912d8a7d1b46a3047ed874bc
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725339"
---
# <a name="how-to-navigate-data-in-windows-forms"></a>방법: Windows Forms에서 데이터 탐색
Windows 응용 프로그램에서 데이터 원본에서 레코드를 탐색 하는 가장 쉬운 방법은에 바인딩하는 것을 <xref:System.Windows.Forms.BindingSource> 데이터 원본 및 다음 바인딩 컨트롤을 구성 요소는 <xref:System.Windows.Forms.BindingSource>합니다. 기본 제공 탐색 메서드를 사용 합니다는 <xref:System.Windows.Forms.BindingSource> 이러한를 <xref:System.Windows.Forms.BindingSource.MoveNext%2A>를 <xref:System.Windows.Forms.BindingSource.MoveLast%2A>를 <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> 및 <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>합니다. 이러한 메서드를 사용 하 여 조정 됩니다 합니다 <xref:System.Windows.Forms.BindingSource.Position%2A> 및 <xref:System.Windows.Forms.BindingSource.Current%2A> 의 속성을 <xref:System.Windows.Forms.BindingSource> 적절 하 게 합니다. 또한 항목을 찾을 설정 하 여 현재 항목으로 설정 된 <xref:System.Windows.Forms.BindingSource.Position%2A> 속성입니다.  
  
### <a name="to-increment-the-position-in-a-data-source"></a>데이터 원본의 위치를 증가 시키기  
  
1.  설정 합니다 <xref:System.Windows.Forms.BindingSource.Position%2A> 의 속성을 <xref:System.Windows.Forms.BindingSource> 이동할 레코드 위치에 바인딩된 데이터에 대 한 합니다. 다음 예제를 사용 하 여를 <xref:System.Windows.Forms.BindingSource.MoveNext%2A> 메서드의 <xref:System.Windows.Forms.BindingSource> 증가 시 키를 <xref:System.Windows.Forms.BindingSource.Position%2A> 속성 때는 `nextButton` 를 클릭 합니다. 합니다 <xref:System.Windows.Forms.BindingSource> 연관 된 합니다 `Customers` 데이터 집합의 테이블 `Northwind`합니다.  
  
    > [!NOTE]
    >  설정 합니다 <xref:System.Windows.Forms.BindingSource.Position%2A> 속성의 첫 번째 또는 마지막 레코드 보다 큰 값을 얻지 오류가로 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 목록의 범위를 벗어난 값으로 위치를 설정 하는 데 하면 합니다. 첫 번째 또는 마지막 레코드를 지난를 벗어났는지 여부를 알아야 응용 프로그램에서 중요 한 경우에 데이터 요소 수를 초과 했는지 여부를 테스트 하는 논리가 포함 됩니다.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>시작 또는 끝 전달한 여부를 확인 하려면  
  
1.  <xref:System.Windows.Forms.BindingSource.PositionChanged> 이벤트에 대한 이벤트 처리기를 만듭니다. 처리기에서 제안 된 위치 값을 실제 데이터 요소 수를 초과 하는지 여부를 테스트할 수 있습니다.  
  
     다음 예제에서는 마지막 데이터 요소에 도달한 있는지 여부를 테스트 하는 방법을 보여 줍니다. 예제에서는 마지막 요소에 있는 경우는 **다음** 폼에 단추를 사용 하지 않도록 설정 합니다.  
  
    > [!NOTE]
    >  를 코드에서 탐색 중인 목록을 변경 하는 다시 사용할 수 있도록 주의 합니다 **다음** 단추를 새 목록 전체 길이 탐색할 수 있도록 합니다. 또한는 위의 <xref:System.Windows.Forms.BindingSource.PositionChanged> 는 특정 이벤트 <xref:System.Windows.Forms.BindingSource> 작업할 해당 이벤트 처리 메서드를 사용 하 여 연결된 되어야 합니다. 다음은 처리 하는 방법의 예로 <xref:System.Windows.Forms.BindingSource.PositionChanged> 이벤트:  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>항목을 찾아 현재 항목으로 설정  
  
1.  현재 항목으로 설정 하려는 레코드를 찾습니다. 사용 하 여 수행할 수 있습니다 합니다 <xref:System.Windows.Forms.BindingSource.Find%2A> 메서드를 <xref:System.Windows.Forms.BindingSource>데이터 원본을 구현 하는 경우 <xref:System.ComponentModel.IBindingList>합니다. 데이터의 예로 구현 하는 소스 <xref:System.ComponentModel.IBindingList> 됩니다 <xref:System.ComponentModel.BindingList%601> 고 <xref:System.Data.DataView>입니다.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>참고자료
- [Windows Forms에서 지원하는 데이터 소스](data-sources-supported-by-windows-forms.md)
- [Windows Forms 데이터 바인딩의 변경 알림](change-notification-in-windows-forms-data-binding.md)
- [데이터 바인딩 및 Windows Forms](data-binding-and-windows-forms.md)
- [Windows Forms 데이터 바인딩](windows-forms-data-binding.md)
