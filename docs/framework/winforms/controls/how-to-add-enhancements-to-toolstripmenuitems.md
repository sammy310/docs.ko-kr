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
ms.openlocfilehash: 9e95c3623bf9bad8395f586392a0557ad1cde880
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912578"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="38462-102">방법: ToolStripMenuItems에 향상된 기능 추가</span><span class="sxs-lookup"><span data-stu-id="38462-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="38462-103">다음과 같은 방법으로 및 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤의 유용성을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38462-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
- <span data-ttu-id="38462-104">선택 표시를 추가 하 여 기능이 설정 되었는지 여부를 지정 합니다. 예를 들어, 워드 프로세싱 응용 프로그램의 여백에 눈금자가 표시 되는지 여부와 같은 **창** 메뉴에 표시 되는 파일 목록에서 파일을 표시할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38462-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
- <span data-ttu-id="38462-105">시각적으로 표시 되는 메뉴 명령을 표시 하는 이미지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="38462-105">Add images that visually represent menu commands.</span></span>  
  
- <span data-ttu-id="38462-106">바로 가기 키를 표시 하 여 명령을 수행할 때 마우스에 대 한 키보드 대체를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38462-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="38462-107">예를 들어 CTRL + C를 누르면 **Copy** 명령이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38462-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
- <span data-ttu-id="38462-108">메뉴 탐색에 마우스에 대 한 키보드 대체를 제공 하는 액세스 키를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="38462-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="38462-109">예를 들어 ALT + F를 누르면 **파일** 메뉴가 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38462-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
- <span data-ttu-id="38462-110">구분 기호를 표시 하 여 관련 명령을 그룹화 하 고 메뉴를 더 읽기 쉽게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38462-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="38462-111">메뉴 명령에 확인 표시를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="38462-111">To display a check mark on a menu command</span></span>  
  
- <span data-ttu-id="38462-112">해당 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 속성을로 `true`설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38462-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="38462-113">또한 <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> 속성을로 `true`설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38462-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="38462-114">이 절차는 선택 여부에 관계 없이 메뉴 명령을 기본적으로 선택 된 것으로 표시 하려는 경우에만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38462-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="38462-115">각 클릭의 상태를 변경 하는 확인 표시를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="38462-115">To display a check mark that changes state with each click</span></span>  
  
- <span data-ttu-id="38462-116">메뉴 명령의 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 속성을로 `true`설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38462-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="38462-117">메뉴 명령에 이미지를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="38462-117">To add an image to a menu command</span></span>  
  
- <span data-ttu-id="38462-118">메뉴 명령의 <xref:System.Windows.Forms.ToolStripItem.Image%2A> 속성을 이미지 이름으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38462-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="38462-119">이 메뉴 명령의 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 속성을 또는로 설정 하면 이미지를 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38462-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="38462-120">이미지 여백은 선택 하는 경우 확인 표시를 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38462-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="38462-121">또한 이미지의 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 속성을로 `true`설정할 수 있으며, 이미지는 런타임에 빗금 테두리와 함께 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38462-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="38462-122">메뉴 명령에 대 한 바로 가기 키를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="38462-122">To display a shortcut key for a menu command</span></span>  
  
- <span data-ttu-id="38462-123">메뉴 명령의 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> 속성을 **열기** 메뉴 명령에 대 한 CTRL + O와 같이 원하는 키보드 조합으로 설정 하 고 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> 속성을로 `true`설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38462-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="38462-124">메뉴 명령에 대 한 사용자 지정 바로 가기 키를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="38462-124">To display custom shortcut keys for a menu command</span></span>  
  
- <span data-ttu-id="38462-125">메뉴 명령의 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> 속성을 shift + ctrl + o 대신 CTRL + shift + o와 같이 원하는 키보드 조합으로 설정 하 고 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> 속성을로 `true`설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38462-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="38462-126">메뉴 명령에 대 한 선택 키를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="38462-126">To display an access key for a menu command</span></span>  
  
- <span data-ttu-id="38462-127">메뉴 명령에 대 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 한 속성을 설정할 때 선택 키로 밑줄이 표시 될 문자 앞에 앰퍼샌드 (&)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="38462-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="38462-128">예를 들어를 `&Open` 메뉴 항목 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 의 속성으로 입력 하면 메뉴 명령이 <u>O</u>펜으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38462-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="38462-129">이 메뉴 명령으로 이동 하려면 ALT 키를 눌러에 포커스 <xref:System.Windows.Forms.MenuStrip>를 이동 하 고 메뉴 이름의 선택 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="38462-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="38462-130">메뉴가 열리고 액세스 키가 포함 된 항목이 표시 되 면 액세스 키를 눌러 메뉴 명령을 선택 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38462-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="38462-131">동일한 메뉴 시스템에서 ALT + F를 두 번 정의 하는 것과 같이 중복 된 액세스 키를 정의 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="38462-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="38462-132">중복 된 액세스 키의 선택 순서는 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38462-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="38462-133">메뉴 명령 사이에 구분 기호를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="38462-133">To display a separator bar between menu commands</span></span>  
  
- <span data-ttu-id="38462-134"><xref:System.Windows.Forms.MenuStrip> 및 여기에 포함 될 항목을 정의한 후에는 <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> 또는 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 메서드를 사용 하 여 메뉴 명령과 <xref:System.Windows.Forms.ToolStripSeparator> 컨트롤 <xref:System.Windows.Forms.MenuStrip> 을 원하는 순서 대로에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="38462-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="38462-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="38462-135">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="38462-136">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="38462-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
