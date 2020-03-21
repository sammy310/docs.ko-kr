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
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="66d2d-102">방법: ToolStripMenuItems에 향상된 기능 추가</span><span class="sxs-lookup"><span data-stu-id="66d2d-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="66d2d-103">다음과 같은 방법으로 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤의 유용성을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
- <span data-ttu-id="66d2d-104">단어 처리 응용 프로그램의 여백을 따라 눈금자가 표시되는지 여부와 같이 피쳐가 켜져 있거나 꺼져 있는지 여부를 지정하거나 **창** 메뉴와 같이 파일 목록에 표시되는 파일을 나타내는 검사 표시를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
- <span data-ttu-id="66d2d-105">메뉴 명령을 시각적으로 나타내는 이미지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-105">Add images that visually represent menu commands.</span></span>  
  
- <span data-ttu-id="66d2d-106">바로 가기 키를 표시하여 명령을 수행하기 위한 마우스에 대한 키보드 대안을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="66d2d-107">예를 들어 CTRL+C를 누르면 **복사** 명령이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
- <span data-ttu-id="66d2d-108">메뉴 탐색을 위해 마우스에 대한 키보드 대안을 제공하기 위해 액세스 키를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="66d2d-109">예를 들어 ALT+F를 누르면 **파일** 메뉴가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
- <span data-ttu-id="66d2d-110">구분 기호 막대를 표시하여 관련 명령을 그룹화하고 메뉴를 더 읽기 쉽게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="66d2d-111">메뉴 명령에 확인 표시를 표시하려면</span><span class="sxs-lookup"><span data-stu-id="66d2d-111">To display a check mark on a menu command</span></span>  
  
- <span data-ttu-id="66d2d-112">속성을 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 로 `true`설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="66d2d-113">이렇게 하면 <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> 속성이 `true`으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="66d2d-114">메뉴 명령이 선택되었는지 여부에 관계없이 메뉴 명령을 기본적으로 선택된 것으로 표시하려는 경우에만 이 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="66d2d-115">클릭할 때마다 상태가 변경되는 확인 표시를 표시하려면</span><span class="sxs-lookup"><span data-stu-id="66d2d-115">To display a check mark that changes state with each click</span></span>  
  
- <span data-ttu-id="66d2d-116">메뉴 명령의 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="66d2d-117">메뉴 명령에 이미지를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="66d2d-117">To add an image to a menu command</span></span>  
  
- <span data-ttu-id="66d2d-118">메뉴 명령의 <xref:System.Windows.Forms.ToolStripItem.Image%2A> 속성을 이미지 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="66d2d-119">이 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 메뉴 명령의 속성이 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> 또는 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>로 설정된 경우 이미지를 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66d2d-120">원하는 경우 이미지 여백에 체크 표시가 표시될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="66d2d-121">또한 이미지의 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 속성을 `true`로 설정할 수 있으며 이미지는 런타임에 이미지 주위에 해치된 테두리로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="66d2d-122">메뉴 명령에 대한 바로 가기 키를 표시하려면</span><span class="sxs-lookup"><span data-stu-id="66d2d-122">To display a shortcut key for a menu command</span></span>  
  
- <span data-ttu-id="66d2d-123">열기 메뉴 명령에 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> 대 한 CTRL +O와 같은 원하는 **Open** 키보드 조합으로 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> `true`메뉴 명령의 속성을 설정 하 고 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="66d2d-124">메뉴 명령에 대한 사용자 지정 바로 가기 키를 표시하려면</span><span class="sxs-lookup"><span data-stu-id="66d2d-124">To display custom shortcut keys for a menu command</span></span>  
  
- <span data-ttu-id="66d2d-125">메뉴 명령의 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> 속성을 SHIFT+CTRL+O가 아닌 CTRL+SHIFT+O와 같은 원하는 키보드 조합으로 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> `true`설정하고 속성을 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="66d2d-126">메뉴 명령에 대한 액세스 키를 표시하려면</span><span class="sxs-lookup"><span data-stu-id="66d2d-126">To display an access key for a menu command</span></span>  
  
- <span data-ttu-id="66d2d-127">메뉴 명령에 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 대한 속성을 설정할 때 액세스 키로 밑줄을 표시할 문자 앞에 앰퍼샌드(&)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="66d2d-128">예를 들어 메뉴 `&Open` 항목의 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성으로 입력하면 <u>O</u>펜으로 표시되는 메뉴 명령이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="66d2d-129">이 메뉴 명령으로 이동하려면 ALT를 눌러 <xref:System.Windows.Forms.MenuStrip>에 포커스를 지정하고 메뉴 이름의 액세스 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="66d2d-130">메뉴가 열리고 액세스 키가 있는 항목이 표시되면 액세스 키를 눌러 메뉴 명령을 선택하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66d2d-131">동일한 메뉴 시스템에서 ALT+F를 두 번 정의하는 등 중복 액세스 키를 정의하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="66d2d-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="66d2d-132">중복 액세스 키의 선택 순서는 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="66d2d-133">메뉴 명령 사이에 구분 기호 막대를 표시하려면</span><span class="sxs-lookup"><span data-stu-id="66d2d-133">To display a separator bar between menu commands</span></span>  
  
- <span data-ttu-id="66d2d-134">사용자 <xref:System.Windows.Forms.MenuStrip> 항목과 포함할 항목을 정의한 <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> 후 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 또는 메서드를 사용하여 <xref:System.Windows.Forms.ToolStripSeparator> 메뉴 명령 <xref:System.Windows.Forms.MenuStrip> 및 컨트롤을 원하는 순서대로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="66d2d-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="66d2d-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66d2d-135">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="66d2d-136">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="66d2d-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
