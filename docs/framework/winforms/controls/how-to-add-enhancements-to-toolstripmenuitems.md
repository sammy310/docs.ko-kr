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
ms.openlocfilehash: 458347df7e17aabc1e9e21d66ad1b5a96200fe28
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198558"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>방법: ToolStripMenuItems에 향상된 기능 추가
사용 편의성을 향상 시킬 수 있습니다 <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ContextMenuStrip> 다음과 같은 방법으로 제어 합니다.  
  
-   눈금자는 워드 프로세싱 응용 프로그램의 여백 표시 되는지 여부와 같은 기능을 켜 지거나 해제 여부를 지정 하거나 중임을 나타내는 파일 목록의 파일 표시 등에서 확인 표시를 추가 된 **창을** 메뉴입니다.  
  
-   메뉴 명령에 시각적으로 나타내는 이미지를 추가 합니다.  
  
-   명령을 수행 하는 것에 대 한 마우스 바로 대안을 제공 하려면 바로 가기 키를 표시 합니다. 예를 들어, CTRL + C를 수행 합니다 **복사** 명령입니다.  
  
-   액세스 키 표시 메뉴 탐색을 위한 마우스 바로 대안을 제공 합니다. 예를 들어, ALT + F를 누르면 선택 된 **파일** 메뉴.  
  
-   관련된 명령을 그룹화 하 여 메뉴를 더 읽기 쉽게 구분 기호 막대를 표시 합니다.  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>메뉴 명령에 확인 표시를 표시 하려면  
  
-   설정 해당 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 속성을 `true`입니다.  
  
     이 설정 된 <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> 속성을 `true`입니다. 메뉴 명령을 선택 되었는지 여부에 관계 없이 기본적으로 선택 된 상태로 표시 하려는 경우에이 절차를 따르십시오.  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>클릭할 때마다 상태를 변경 하는 확인란을 표시 하려면  
  
-   설정 메뉴 명령의 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 속성을 `true`입니다.  
  
### <a name="to-add-an-image-to-a-menu-command"></a>메뉴 명령에 이미지를 추가 하려면  
  
-   설정 메뉴 명령의 <xref:System.Windows.Forms.ToolStripItem.Image%2A> 속성을 이미지의 이름입니다. 경우는 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 이 메뉴 명령의 속성 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> 또는 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, 이미지를 표시할 수 없습니다.  
  
> [!NOTE]
>  이미지 여백이 표시할 수도 확인 표시가 필요한 경우. 또한 설정할 수 있습니다 합니다 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 이미지의 속성 `true`, 런타임 시 이미지 주위 빗금 테두리로 표시 됩니다.  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>메뉴 명령에 대 한 바로 가기 키를 표시 하려면  
  
-   설정 메뉴 명령의 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> CTRL + O 등에서 원하는 키보드 조합 속성 합니다 **열기** 메뉴 명령 및 집합을 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> 속성을 `true`.  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>메뉴 명령에 대 한 사용자 지정 바로 가기 키를 표시 하려면  
  
-   설정 메뉴 명령의 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> 에서 원하는 키보드 조합 집합 및 SHIFT + CTRL + O를 사용 하는 대신 CTRL + SHIFT + O와 같은 속성을 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> 속성을 `true`.  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>메뉴 명령에 대 한 액세스 키를 표시 하려면  
  
-   설정 하는 경우는 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 앰퍼샌드를 입력 하는 메뉴 명령에 대 한 속성 액세스 키와 밑줄을 표시 하려면 문자 앞에 (&). 예를 들어 입력 `&Open` 으로 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 메뉴 항목의 속성으로 표시 되는 메뉴 명령을 발생 <u>O</u>펜입니다.
  
     이 메뉴 명령으로 이동 하려면 alt 키를 포커스를 <xref:System.Windows.Forms.MenuStrip>, 메뉴 이름에 대 한 액세스 키를 누릅니다. 메뉴 선택 키를 사용 하 여 항목을 보여 줍니다.을 열고, 액세스 키를 눌러 메뉴 명령이 선택 해야 합니다.  
  
> [!NOTE]
>  ALT + F를 동일한 메뉴 시스템에서 두 번 정의 하는 등의 중복 된 액세스 키를 정의 하지 마세요. 중복 된 액세스 키의 선택 순서를 보장할 수 없습니다.  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>메뉴 명령 사이 구분줄 표시 하려면  
  
-   정의한 후에 <xref:System.Windows.Forms.MenuStrip> 및 여기에 포함 될 항목 사용 합니다 <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> 또는 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 메뉴 명령을 추가 하는 방법 및 <xref:System.Windows.Forms.ToolStripSeparator> 컨트롤을 <xref:System.Windows.Forms.MenuStrip> 원하는 순서로 합니다.  
  
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
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [MenuStrip 컨트롤 개요](menustrip-control-overview-windows-forms.md)
