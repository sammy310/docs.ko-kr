---
title: 디자이너를 사용 하 여 TreeView 컨트롤을 사용 하 여 노드 추가 및 제거
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 7edf09539719ec76fa3f650254c5c84ff0bc3af7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732247"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms TreeView 컨트롤에서 노드 추가 및 제거

Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤은 노드를 계층적 방식으로 표시 하기 때문에 노드를 추가 하는 경우 해당 부모 노드에 대해 주의를 기울여야 합니다.

다음 절차에는 <xref:System.Windows.Forms.TreeView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다. 이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 및 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요.

### <a name="to-add-or-remove-nodes-in-the-designer"></a>디자이너에서 노드를 추가 하거나 제거 하려면

1. <xref:System.Windows.Forms.TreeView> 컨트롤을 선택합니다.

2. **속성** 창에서 <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성 옆의 속성 창 Visual Studio.](./media/visual-studio-ellipsis-button.png)) 단추에 **있는 줄임표 단추** (...)를![클릭 합니다.

     **TreeNode 편집기** 가 나타납니다.

3. 노드를 추가 하려면 루트 노드가 있어야 합니다. 이 항목이 없으면 **루트 추가** 단추를 클릭 하 여 루트를 먼저 추가 해야 합니다. 그런 다음 루트 또는 다른 노드를 선택 하 고 **자식 추가** 단추를 클릭 하 여 자식 노드를 추가할 수 있습니다.

4. 노드를 삭제 하려면 삭제할 노드를 선택 하 고 **삭제** 단추를 클릭 합니다.

## <a name="see-also"></a>참조

- [TreeView 컨트롤](treeview-control-windows-forms.md)
- [TreeView 컨트롤 개요](treeview-control-overview-windows-forms.md)
- [방법: Windows Forms TreeView 컨트롤의 아이콘 설정](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [방법: Windows Forms TreeView 컨트롤의 노드 전체 반복](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [방법: 클릭한 TreeView 노드 확인](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
