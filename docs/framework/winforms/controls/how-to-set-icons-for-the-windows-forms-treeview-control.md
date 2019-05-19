---
title: '방법: Windows Forms TreeView 컨트롤에 대한 아이콘 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
ms.openlocfilehash: eb2d75b7c18aa2e65c5e90749852383eea7985b3
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880674"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>방법: Windows Forms TreeView 컨트롤에 대한 아이콘 설정
Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤 각 노드 옆에 아이콘을 표시할 수 있습니다. 아이콘 노드 텍스트의 바로 왼쪽에 배치 됩니다. 이러한 아이콘을 표시 하려면 트리 뷰에서 사용 하 여 연결 해야 합니다는 <xref:System.Windows.Forms.ImageList> 제어 합니다. 이미지 목록에 대 한 자세한 내용은 참조 하세요. [ImageList 구성 요소](imagelist-component-windows-forms.md) 고 [방법: 제거 이미지는 Windows Forms ImageList 구성 요소 추가 또는](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)합니다.  
  
> [!NOTE]
>  Microsoft.NET Framework 버전 1.1의에서 버그는 이미지에 표시 되지 않도록 방지 <xref:System.Windows.Forms.TreeView> 응용 프로그램 호출 노드 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>합니다. 이 버그를 해결 하려면 호출 <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> 에 사용자 `Main` 메서드를 호출한 후 즉시 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>합니다. 이 버그는에서 수정 [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]합니다.  
  
### <a name="to-display-images-in-a-tree-view"></a>트리 보기에서 이미지를 표시 하려면  
  
1. 설정 합니다 <xref:System.Windows.Forms.TreeView> 컨트롤의 <xref:System.Windows.Forms.TreeView.ImageList%2A> 속성을 기존 <xref:System.Windows.Forms.ImageList> 사용 하려는 컨트롤입니다.  
  
     속성 창 사용 하 여 디자이너에서 또는 코드에서 이러한 속성을 설정할 수 있습니다.  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. 노드를 설정 <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> 고 <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> 속성입니다. <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> 속성 노드의 일반 및 확장 된 상태에 대해 표시할 이미지를 결정 하며 <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> 속성 노드의 선택한 상태에 대 한 표시 되는 이미지를 결정 합니다.  
  
     또는 트리 노드 편집기 내에서 코드에서 이러한 속성을 설정할 수 있습니다. 트리 노드 편집기를 열려면 줄임표 단추를 클릭 합니다. ( ![의 줄임표 단추 (...)의 Visual Studio 속성 창의](./media/visual-studio-ellipsis-button.png)) 옆에 <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성 창에서 속성입니다.  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## <a name="see-also"></a>참고자료

- [TreeView 컨트롤 개요](treeview-control-overview-windows-forms.md)
- [방법: 추가 하 고 Windows Forms TreeView 컨트롤을 사용 하 여 노드를 제거 합니다.](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [방법: Windows Forms TreeView 컨트롤의 노드 전체 반복](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [방법: 클릭 한 TreeView 노드 확인](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [방법: TreeView 또는 ListView 컨트롤 (Windows Forms)에 사용자 지정 정보 추가](add-custom-information-to-a-treeview-or-listview-control-wf.md)
