---
title: '방법: 디자이너를 사용하여 TreeNode에 바로 가기 메뉴 연결'
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: 1cc90ed9a103c41dbf85e39a43d307b1c0422603
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191448"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a>방법: 디자이너를 사용하여 TreeNode에 바로 가기 메뉴 연결
Windows Forms <xref:System.Windows.Forms.TreeView> 제어 노드, 파일 및 Windows 운영 체제에서 Windows 탐색기 기능의 왼쪽된 창에서 표시 폴더와 유사한 계층 구조를 표시 합니다. 설정 하 여 합니다 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 제공할 수 있습니다 상황에 맞는 작업 사용자에 게는 마우스 오른쪽 단추로 클릭는 <xref:System.Windows.Forms.TreeView> 제어 합니다. 연결 하 여는 <xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 개별 <xref:System.Windows.Forms.TreeNode> 항목을 사용자 지정된 된 바로 가기 메뉴 기능 수준을 추가할 수 있습니다 프로그램 <xref:System.Windows.Forms.TreeView> 컨트롤입니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a>디자인 타임에는 트리 노드를 사용 하 여 바로 가기 메뉴를 연결 하려면  
  
1.  추가 된 <xref:System.Windows.Forms.TreeView> 폼에 컨트롤을 추가한 다음 노드를는 <xref:System.Windows.Forms.TreeView> 필요에 따라 합니다. 자세한 내용은 [방법: 추가 및 제거는 Windows 노드 Forms TreeView 컨트롤](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)합니다.  
  
2.  추가 된 <xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 폼에 다음 런타임에 사용할 수 있도록 하려는 노드 수준의 작업을 나타내는 바로 가기 메뉴에 메뉴 항목을 추가 합니다. 자세한 내용은 [방법: ContextMenuStrip에 메뉴 항목 추가](how-to-add-menu-items-to-a-contextmenustrip.md)합니다.  
  
3.  다시를 **TreeNodeEditor** 대화 상자를 <xref:System.Windows.Forms.TreeView> 컨트롤을 편집 하 고 설정 하려면 노드를 선택 해당 <xref:System.Windows.Forms.ContextMenuStrip> 추가한 바로 가기 메뉴에는 속성입니다.  
  
4.  이 속성을 설정 하는 경우 바로 가기 메뉴에서 노드를 마우스 오른쪽 단추로 클릭할 때 표시 됩니다.  
  
     처리할 코드를 작성 하려고 또한는 <xref:System.Windows.Forms.ToolStripItem.Click> 이러한 메뉴 항목에 대 한 이벤트입니다.  
  
## <a name="see-also"></a>참고자료

- [TreeView 컨트롤](treeview-control-windows-forms.md)
- [TreeView 컨트롤 개요](treeview-control-overview-windows-forms.md)
- [ContextMenuStrip 컨트롤](contextmenustrip-control.md)
