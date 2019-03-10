---
title: ListView 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ListView
helpviewer_keywords:
- lists
- ListView control [Windows Forms], about ListView control
- list views
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
ms.openlocfilehash: d62c0081c128693861a9fd21360f09f65d485a79
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709794"
---
# <a name="listview-control-overview-windows-forms"></a>ListView 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤은 아이콘이 포함된 항목 목록을 표시합니다. 목록 뷰를 사용하여 Windows 탐색기의 오른쪽 창과 같은 사용자 인터페이스를 만들 수 있습니다. 컨트롤에는 네 가지 보기 모드에 있습니다. 큰 아이콘, 작은 아이콘, 목록 및 세부 정보입니다.  
  
## <a name="what-you-can-do-with-the-listview-control"></a>ListView 컨트롤을 사용 하 여 수행할 수 있는 작업  
  
> [!NOTE]
>  타일 추가 뷰 모드를만 Windows XP 및 Windows Server 2003 운영 체제에서 제공 됩니다. 자세한 내용은 [방법: Forms ListView 컨트롤을 Windows의 Tile 보기 사용](how-to-enable-tile-view-in-a-windows-forms-listview-control.md)합니다.  
  
 큰 아이콘 모드를 표시 된 항목 텍스트 옆에 있는 큰 아이콘 항목이는 컨트롤 충분히 큰 경우 여러 열에 나타납니다. SmallIcon 모드를 작은 아이콘을 표시 하는 점을 제외 하면 동일 합니다. 목록 모드를 작은 아이콘을 표시 하지만 항상 단일 열입니다. 자세히 모드는 여러 열에서 항목을 표시합니다. 자세한 내용은 [방법: 열에는 Windows Forms ListView 컨트롤 추가](how-to-add-columns-to-the-windows-forms-listview-control.md)합니다. 보기 모드에서 결정 됩니다는 <xref:System.Windows.Forms.ListView.View%2A> 속성입니다. 보기 모드의 모든 이미지 목록에서 이미지를 표시할 수 있습니다. 자세한 내용은 [방법: Windows Forms ListView 컨트롤에 대 한 아이콘을 표시](how-to-display-icons-for-the-windows-forms-listview-control.md)합니다.  
  
 다음 표에서 몇 가지를 <xref:System.Windows.Forms.ListView> 멤버와는 사용할 수 있는 보기입니다.  
  
|ListView 구성원|보기|  
|---------------------|----------|  
|<xref:System.Windows.Forms.ListView.Alignment%2A> 속성|<xref:System.Windows.Forms.View.SmallIcon> 또는 <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.AutoArrange%2A> 속성|<xref:System.Windows.Forms.View.SmallIcon> 또는 <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.AutoResizeColumn%2A> 메서드|<xref:System.Windows.Forms.View.Details>|  
|<xref:System.Windows.Forms.ListView.Columns%2A> 속성|<xref:System.Windows.Forms.View.Details> 또는 <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.DrawSubItem> 이벤트|<xref:System.Windows.Forms.View.Details>|  
|<xref:System.Windows.Forms.ListView.FindItemWithText%2A> 메서드|<xref:System.Windows.Forms.View.Details>, <xref:System.Windows.Forms.View.List>또는 <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.FindNearestItem%2A> 메서드|<xref:System.Windows.Forms.View.SmallIcon> 또는 <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.GetItemAt%2A> 메서드|<xref:System.Windows.Forms.View.Details> 또는 <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.Groups%2A> 속성|제외한 모든 보기 <xref:System.Windows.Forms.View.List>|  
|<xref:System.Windows.Forms.ListView.HeaderStyle%2A> 속성|<xref:System.Windows.Forms.View.Details>.|  
|<xref:System.Windows.Forms.ListView.InsertionMark%2A> 속성|<xref:System.Windows.Forms.View.LargeIcon>, <xref:System.Windows.Forms.View.SmallIcon>또는 <xref:System.Windows.Forms.View.Tile>|  
  
 키 속성을 <xref:System.Windows.Forms.ListView> 컨트롤은 <xref:System.Windows.Forms.ListView.Items%2A>, 컨트롤에서 표시 된 항목을 포함 하는 합니다. <xref:System.Windows.Forms.ListView.SelectedItems%2A> 속성 컨트롤에서 현재 선택 된 항목의 컬렉션을 포함 합니다. 사용자가 끌어서 경우 다른 컨트롤을 한 번에 여러 항목을 삭제 하는 예제에 대 한 여러 항목을 선택할 수는 <xref:System.Windows.Forms.ListView.MultiSelect%2A> 속성이 `true`합니다. <xref:System.Windows.Forms.ListView> 제어 하는 경우 항목 옆의 확인란을 표시할 수 있습니다 합니다 <xref:System.Windows.Forms.ListView.CheckBoxes%2A> 속성이 `true`합니다.  
  
 <xref:System.Windows.Forms.ListView.Activation%2A> 속성 동작 유형을 목록에서 항목을 활성화 하기 위해 사용자를 수행 해야 결정: 옵션은 <xref:System.Windows.Forms.ItemActivation.Standard>를 <xref:System.Windows.Forms.ItemActivation.OneClick>, 및 <xref:System.Windows.Forms.ItemActivation.TwoClick>합니다. <xref:System.Windows.Forms.ItemActivation.OneClick> 활성화 항목을 활성화 하려면 한 번의 클릭을 해야 합니다. <xref:System.Windows.Forms.ItemActivation.TwoClick> 활성화의 경우 항목을 활성화 하려면 두 번 클릭 항목 텍스트의 색을 변경 하는 한 번의 클릭 합니다. <xref:System.Windows.Forms.ItemActivation.Standard> 활성화의 경우 항목을 활성화 하려면 두 번 클릭 하지만 항목 모양은 변경 되지 않습니다.  
  
 <xref:System.Windows.Forms.ListView> 그룹화, 바둑판식 뷰 및 삽입 표시를 포함 하 여 Windows XP 플랫폼에서도 지 원하는 시각적 스타일 및 기타 기능을 사용할 수 있는 컨트롤입니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.ListView>
- [ListView 컨트롤](listview-control-windows-forms.md)
- [방법: Windows Forms ListView 컨트롤을 사용 하 여 항목 추가 및 제거](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [방법: Windows Forms ListView 컨트롤에 열 추가](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [방법: Windows Forms ListView 컨트롤에 대 한 아이콘을 표시 합니다.](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [방법: Windows Forms ListView 컨트롤을 사용 하 여 열에 하위 항목 표시](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [방법: Windows Forms ListView 컨트롤에서 항목을 선택 합니다.](how-to-select-an-item-in-the-windows-forms-listview-control.md)
- [방법: Windows Forms ListView 컨트롤에서 항목 그룹화](how-to-group-items-in-a-windows-forms-listview-control.md)
- [방법: Windows Forms ListView 컨트롤에 삽입 표시](how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)
- [방법: ListView 컨트롤에 검색 기능 추가](how-to-add-search-capabilities-to-a-listview-control.md)
- [방법: TreeView 또는 ListView 컨트롤 (Windows Forms)에 사용자 지정 정보 추가](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [방법: Windows Forms로 다중 창 사용자 인터페이스 만들기](how-to-create-a-multipane-user-interface-with-windows-forms.md)
