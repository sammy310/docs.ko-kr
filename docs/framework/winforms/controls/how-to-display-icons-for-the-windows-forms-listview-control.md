---
title: ListView 컨트롤의 아이콘 표시
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
ms.openlocfilehash: 5fc54c448dae95cab50cdafa8403769fb421dffa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744510"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a>방법: Windows Forms ListView 컨트롤의 아이콘 표시
Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤은 세 가지 이미지 목록에서 아이콘을 표시할 수 있습니다. 목록, 세부 정보 및 SmallIcon 보기는 <xref:System.Windows.Forms.ListView.SmallImageList%2A> 속성에 지정 된 이미지 목록의 이미지를 표시 합니다. LargeIcon view는 <xref:System.Windows.Forms.ListView.LargeImageList%2A> 속성에 지정 된 이미지 목록의 이미지를 표시 합니다. 목록 뷰에는 <xref:System.Windows.Forms.ListView.StateImageList%2A> 속성에서 크거나 작은 아이콘 옆에 설정 된 추가 아이콘 집합이 표시 될 수도 있습니다. 이미지 목록에 대 한 자세한 내용은 [Imagelist 구성 요소](imagelist-component-windows-forms.md) 및 [방법: Windows Forms imagelist 구성 요소를 사용 하 여 이미지 추가 또는 제거](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)를 참조 하세요.  
  
### <a name="to-display-images-in-a-list-view"></a>목록 뷰에서 이미지를 표시 하려면  
  
1. <xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>또는 <xref:System.Windows.Forms.ListView.StateImageList%2A>등의 적절 한 속성을 사용 하려는 기존 <xref:System.Windows.Forms.ImageList> 구성 요소로 설정 합니다.  
  
     이러한 속성은 디자이너에서 속성 창 또는 코드를 사용 하 여 설정할 수 있습니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. 연결 된 아이콘이 있는 각 목록 항목에 대해 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 또는 <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> 속성을 설정 합니다.  
  
     이러한 속성은 코드 또는 **ListViewItem 컬렉션 편집기**내에서 설정할 수 있습니다. **ListViewItem 컬렉션 편집기**를 열려면 **속성** 창의 <xref:System.Windows.Forms.ListView.Items%2A> 속성 옆에 있는 줄임표 단추 (...)를 클릭 하 여 줄임표 단추 (속성 창)를![클릭 합니다](./media/visual-studio-ellipsis-button.png).  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a>참조

- [ListView 컨트롤 개요](listview-control-overview-windows-forms.md)
- [방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [방법: Windows Forms ListView 컨트롤에 열 추가](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [ImageList 구성 요소](imagelist-component-windows-forms.md)
