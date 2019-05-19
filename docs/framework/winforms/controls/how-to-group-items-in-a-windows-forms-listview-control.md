---
title: '방법: Windows Forms ListView 컨트롤에서 항목 그룹화'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
ms.openlocfilehash: bbca1d76f747f53103095c916605ce7335207f51
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882369"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>방법: Windows Forms ListView 컨트롤에서 항목 그룹화
그룹화 기능을 사용 하 여는 <xref:System.Windows.Forms.ListView> 컨트롤 그룹의 관련된 항목 집합을 표시할 수 있습니다. 이러한 그룹은 화면에서 그룹 제목을 포함 하는 행 그룹 머리글에 의해 구분 됩니다. 사용할 수 있습니다 <xref:System.Windows.Forms.ListView> 그룹 날짜 또는 기타 논리 그룹으로 항목을 사전순으로 그룹화 하 여 보다 쉽게 긴 목록 이동 되도록 합니다. 다음 이미지에서는 일부 그룹화 된 항목을 보여 줍니다.  
  
 ![홀수와 짝수 ListView 그룹의 스크린샷입니다.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  
   
 그룹화를 사용 하려면 먼저 디자이너에서 또는 프로그래밍 방식으로 하나 이상의 그룹을 만들어야 합니다. 그룹을 정의한 후 할당할 수 있습니다 <xref:System.Windows.Forms.ListView> 그룹 항목입니다. 이동할 수도 있습니다 항목이 하나의 그룹에서 다른 프로그래밍 방식으로 합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView> 그룹에만 사용할 수 있습니다 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] 응용 프로그램 호출 하는 경우는 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 메서드. 이전 버전의 운영 체제 그룹 관련 모든 코드가 미치지 않으며 그룹 표시 되지 않습니다. 자세한 내용은 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>을 참조하세요.  
  
### <a name="to-add-groups"></a>그룹을 추가 하려면  
  
1. <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> 컬렉션의 <xref:System.Windows.Forms.ListView.Groups%2A> 메서드를 사용합니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>그룹을 제거 하려면  
  
1. 사용 된 <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> 또는 <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> 메서드의 <xref:System.Windows.Forms.ListView.Groups%2A> 컬렉션입니다.  
  
     합니다 <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> 메서드는 단일 그룹을 제거, <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> 메서드 목록에서 모든 그룹을 제거 합니다.  
  
    > [!NOTE]
    >  그룹을 제거 하는 경우에 해당 그룹 내의 항목은 제거 되지 않습니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>항목 그룹을 할당 하거나 항목 그룹 사이 이동  
  
1. 설정 된 <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> 개별 항목의 속성입니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView 컨트롤](listview-control-windows-forms.md)
- [ListView 컨트롤 개요](listview-control-overview-windows-forms.md)
- [방법: Windows Forms ListView 컨트롤을 사용 하 여 항목 추가 및 제거](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
