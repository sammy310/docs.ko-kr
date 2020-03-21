---
title: '방법: ToolStripMenuItems에 향상된 기능 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- commands [Windows Forms], grouping on menus
- check marks [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], displaying access keys
- menus [Windows Forms], grouping commands
- menu items [Windows Forms], displaying shortcut keys
- ToolStripMenuItems
- separators [Windows Forms], displaying on menus
- menu items [Windows Forms], showing separators
- menu items [Windows Forms], adding check marks
- ToolStripMenuItems [Windows Forms], adding check marks
- menu items [Windows Forms], adding images
- ToolStripSeparators [Windows Forms], displaying on MenuStrips
- menu items [Windows Forms], displaying access keys
- ToolStripMenuItems [Windows Forms], displaying shortcut keys
- ToolStripMenuItems [Windows Forms], adding images
- keyboard shortcuts [Windows Forms], displaying on menus
- images [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], showing separator bars
ms.assetid: aa5f19bb-b545-4378-bfa6-36ba592f0d7c
ms.openlocfilehash: 61a79b9bbe101d7bf694240bdffdecee5187adf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182327"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>방법: ToolStripMenuItems에 향상된 기능 추가
다음과 같은 방법으로 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤의 유용성을 향상시킬 수 있습니다.  
  
- 단어 처리 응용 프로그램의 여백을 따라 눈금자가 표시되는지 여부와 같이 피쳐가 켜져 있거나 꺼져 있는지 여부를 지정하거나 **창** 메뉴와 같이 파일 목록에 표시되는 파일을 나타내는 검사 표시를 추가합니다.  
  
- 메뉴 명령을 시각적으로 나타내는 이미지를 추가합니다.  
  
- 바로 가기 키를 표시하여 명령을 수행하기 위한 마우스에 대한 키보드 대안을 제공합니다. 예를 들어 CTRL+C를 누르면 **복사** 명령이 수행됩니다.  
  
- 메뉴 탐색을 위해 마우스에 대한 키보드 대안을 제공하기 위해 액세스 키를 표시합니다. 예를 들어 ALT+F를 누르면 **파일** 메뉴가 선택됩니다.  
  
- 구분 기호 막대를 표시하여 관련 명령을 그룹화하고 메뉴를 더 읽기 쉽게 만듭니다.  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>메뉴 명령에 확인 표시를 표시하려면  
  
- 속성을 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 로 `true`설정합니다.  
  
     이렇게 하면 <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> 속성이 `true`으로 설정됩니다. 메뉴 명령이 선택되었는지 여부에 관계없이 메뉴 명령을 기본적으로 선택된 것으로 표시하려는 경우에만 이 절차를 사용합니다.  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>클릭할 때마다 상태가 변경되는 확인 표시를 표시하려면  
  
- 메뉴 명령의 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 속성을 `true`로 설정합니다.  
  
### <a name="to-add-an-image-to-a-menu-command"></a>메뉴 명령에 이미지를 추가하려면  
  
- 메뉴 명령의 <xref:System.Windows.Forms.ToolStripItem.Image%2A> 속성을 이미지 이름으로 설정합니다. 이 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 메뉴 명령의 속성이 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> 또는 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>로 설정된 경우 이미지를 표시할 수 없습니다.  
  
> [!NOTE]
> 원하는 경우 이미지 여백에 체크 표시가 표시될 수도 있습니다. 또한 이미지의 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 속성을 `true`로 설정할 수 있으며 이미지는 런타임에 이미지 주위에 해치된 테두리로 표시됩니다.  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>메뉴 명령에 대한 바로 가기 키를 표시하려면  
  
- 열기 메뉴 명령에 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> 대 한 CTRL +O와 같은 원하는 **Open** 키보드 조합으로 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> `true`메뉴 명령의 속성을 설정 하 고 속성을 설정 합니다.  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>메뉴 명령에 대한 사용자 지정 바로 가기 키를 표시하려면  
  
- 메뉴 명령의 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> 속성을 SHIFT+CTRL+O가 아닌 CTRL+SHIFT+O와 같은 원하는 키보드 조합으로 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> `true`설정하고 속성을 로 설정합니다.  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>메뉴 명령에 대한 액세스 키를 표시하려면  
  
- 메뉴 명령에 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 대한 속성을 설정할 때 액세스 키로 밑줄을 표시할 문자 앞에 앰퍼샌드(&)를 입력합니다. 예를 들어 메뉴 `&Open` 항목의 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성으로 입력하면 <u>O</u>펜으로 표시되는 메뉴 명령이 생성됩니다.
  
     이 메뉴 명령으로 이동하려면 ALT를 눌러 <xref:System.Windows.Forms.MenuStrip>에 포커스를 지정하고 메뉴 이름의 액세스 키를 누릅니다. 메뉴가 열리고 액세스 키가 있는 항목이 표시되면 액세스 키를 눌러 메뉴 명령을 선택하기만 하면 됩니다.  
  
> [!NOTE]
> 동일한 메뉴 시스템에서 ALT+F를 두 번 정의하는 등 중복 액세스 키를 정의하지 마십시오. 중복 액세스 키의 선택 순서는 보장할 수 없습니다.  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>메뉴 명령 사이에 구분 기호 막대를 표시하려면  
  
- 사용자 <xref:System.Windows.Forms.MenuStrip> 항목과 포함할 항목을 정의한 <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> 후 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 또는 메서드를 사용하여 <xref:System.Windows.Forms.ToolStripSeparator> 메뉴 명령 <xref:System.Windows.Forms.MenuStrip> 및 컨트롤을 원하는 순서대로 추가합니다.  
  
    ```vb  
    ' This code adds a top-level File menu to the MenuStrip.  
    Me.menuStrip1.Items.Add(New ToolStripMenuItem() _  
    {Me.fileToolStripMenuItem})  
  
    ' This code adds the New and Open menu commands, a separator bar,
    ' and the Save and Exit menu commands to the top-level File menu,
    ' in that order.  
    Me.fileToolStripMenuItem.DropDownItems.AddRange(New _  
    ToolStripMenuItem() {Me.newToolStripMenuItem, _  
    Me.openToolStripMenuItem, Me.toolStripSeparator1, _  
    Me.saveToolStripMenuItem, Me.exitToolStripMenuItem})  
    ```  
  
    ```csharp  
    // This code adds a top-level File menu to the MenuStrip.  
    this.menuStrip1.Items.Add(new ToolStripItem[]_  
    {this.fileToolStripMenuItem});  
  
    // This code adds the New and Open menu commands, a separator bar,
    // and the Save and Exit menu commands to the top-level File menu,
    // in that order.  
    this.fileToolStripMenuItem.DropDownItems.AddRange(new _  
    ToolStripItem[] {  
    this.newToolStripMenuItem,  
    this.openToolStripMenuItem,  
    this.toolStripSeparator1,  
    this.saveToolStripMenuItem,  
    this.exitToolStripMenuItem});  
    ```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [MenuStrip 컨트롤 개요](menustrip-control-overview-windows-forms.md)
