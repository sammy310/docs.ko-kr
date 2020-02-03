---
title: ListView 컨트롤을 사용 하 여 열에 하위 항목 표시
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
ms.openlocfilehash: 5c6d807410ad4ee0198d6334844bd65b148edff4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745550"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a>방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시
Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤은 자세히 보기의 각 항목에 대 한 추가 텍스트 또는 하위 항목을 표시할 수 있습니다. 첫 번째 열은 직원 번호와 같은 항목 텍스트를 표시 합니다. 두 번째, 세 번째 및 다음 열에는 첫 번째, 두 번째 및 다음에 연결 된 하위 항목이 표시 됩니다.  
  
### <a name="to-add-subitems-to-a-list-item"></a>목록 항목에 하위 항목을 추가 하려면  
  
1. 필요한 열을 추가 합니다. 첫 번째 열에는 항목의 <xref:System.Windows.Forms.ListView.Text%2A> 속성이 표시 되므로 하위 항목 보다 하나 이상의 열이 필요 합니다. 열 추가에 대 한 자세한 내용은 [방법: Windows Forms ListView 컨트롤에 열 추가](how-to-add-columns-to-the-windows-forms-listview-control.md)를 참조 하세요.  
  
2. 항목의 <xref:System.Windows.Forms.ListViewItem.SubItems%2A> 속성에서 반환 된 컬렉션의 <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> 메서드를 호출 합니다. 아래 코드 예제에서는 목록 항목의 직원 이름과 부서를 설정 합니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>참고 항목

- [ListView 컨트롤 개요](listview-control-overview-windows-forms.md)
- [방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [방법: Windows Forms ListView 컨트롤에 열 추가](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [방법: Windows Forms ListView 컨트롤의 아이콘 표시](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
