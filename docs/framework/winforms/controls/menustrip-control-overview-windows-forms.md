---
title: MenuStrip 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: a536d13cb7be3f4e4e4a085e1a4da1b0899b3a0c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734474"
---
# <a name="menustrip-control-overview-windows-forms"></a><span data-ttu-id="a087d-102">MenuStrip 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="a087d-102">MenuStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="a087d-103">메뉴는 공통 테마에 따라 그룹화 된 명령을 포함 하 여 사용자에 게 기능을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-103">Menus expose functionality to your users by holding commands that are grouped by a common theme.</span></span>  
  
 <span data-ttu-id="a087d-104"><xref:System.Windows.Forms.MenuStrip> 컨트롤은 .NET Framework 버전 2.0에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-104">The <xref:System.Windows.Forms.MenuStrip> control was introduced in version 2.0 of the .NET Framework.</span></span> <span data-ttu-id="a087d-105"><xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용 하면 Microsoft Office에 있는 것과 같은 메뉴를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-105">With the <xref:System.Windows.Forms.MenuStrip> control, you can easily create menus like those found in Microsoft Office.</span></span>  
  
 <span data-ttu-id="a087d-106"><xref:System.Windows.Forms.MenuStrip> 컨트롤은 MDI (다중 문서 인터페이스) 및 메뉴 병합, 도구 설명 및 오버플로를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-106">The <xref:System.Windows.Forms.MenuStrip> control supports the multiple-document interface (MDI) and menu merging, tool tips, and overflow.</span></span> <span data-ttu-id="a087d-107">액세스 키, 바로 가기 키, 확인 표시, 이미지 및 구분 기호를 추가 하 여 메뉴의 유용성 및 가독성을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-107">You can enhance the usability and readability of your menus by adding access keys, shortcut keys, check marks, images, and separator bars.</span></span>  
  
 <span data-ttu-id="a087d-108"><xref:System.Windows.Forms.MenuStrip> 컨트롤은 기능을 대체 하 고 <xref:System.Windows.Forms.MainMenu> 컨트롤에 기능을 추가 합니다. 그러나 <xref:System.Windows.Forms.MainMenu> 컨트롤은 이전 버전과의 호환성 및 향후 사용을 위해 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-108">The <xref:System.Windows.Forms.MenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> control; however, the <xref:System.Windows.Forms.MainMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
## <a name="ways-to-use-the-menustrip-control"></a><span data-ttu-id="a087d-109">MenuStrip 컨트롤을 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="a087d-109">Ways to Use the MenuStrip Control</span></span>  
 <span data-ttu-id="a087d-110"><xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용 하 여 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-110">Use the <xref:System.Windows.Forms.MenuStrip> control to:</span></span>  
  
- <span data-ttu-id="a087d-111">텍스트 및 이미지 정렬 및 맞춤, 끌어서 놓기 작업, MDI, 오버플로 및 메뉴 명령 액세스의 대체 모드와 같은 고급 사용자 인터페이스 및 레이아웃 기능을 지 원하는, 일반적으로 사용 되는 사용자 지정 된 메뉴를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-111">Create easily customized, commonly employed menus that support advanced user interface and layout features, such as text and image ordering and alignment, drag-and-drop operations, MDI, overflow, and alternate modes of accessing menu commands.</span></span>  
  
- <span data-ttu-id="a087d-112">운영 체제의 일반적인 모양과 동작을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-112">Support the typical appearance and behavior of the operating system.</span></span>  
  
- <span data-ttu-id="a087d-113">다른 컨트롤에 대 한 이벤트를 처리 하는 것과 동일한 방식으로 모든 컨테이너 및 포함 된 항목에 대해 이벤트를 일관 되 게 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
 <span data-ttu-id="a087d-114">다음 표에서는 <xref:System.Windows.Forms.MenuStrip> 및 관련 클래스의 일부 특히 중요 한 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-114">The following table shows some particularly important properties of <xref:System.Windows.Forms.MenuStrip> and associated classes.</span></span>  
  
|<span data-ttu-id="a087d-115">속성</span><span class="sxs-lookup"><span data-stu-id="a087d-115">Property</span></span>|<span data-ttu-id="a087d-116">Description</span><span class="sxs-lookup"><span data-stu-id="a087d-116">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|<span data-ttu-id="a087d-117">MDI 자식 폼의 목록을 표시 하는 데 사용 되는 <xref:System.Windows.Forms.ToolStripMenuItem>를 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-117">Gets or sets the <xref:System.Windows.Forms.ToolStripMenuItem> that is used to display a list of MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|<span data-ttu-id="a087d-118">자식 메뉴를 MDI 응용 프로그램의 부모 메뉴와 병합 하는 방법을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-118">Gets or sets how child menus are merged with parent menus in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|<span data-ttu-id="a087d-119">MDI 응용 프로그램의 메뉴 내에서 병합 된 항목의 위치를 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-119">Gets or sets the position of a merged item within a menu in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|<span data-ttu-id="a087d-120">폼이 MDI 자식 폼의 컨테이너 인지 여부를 나타내는 값을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-120">Gets or sets a value indicating whether the form is a container for MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|<span data-ttu-id="a087d-121"><xref:System.Windows.Forms.MenuStrip>에 대 한 도구 설명이 표시 되는지 여부를 나타내는 값을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-121">Gets or sets a value indicating whether tool tips are shown for the <xref:System.Windows.Forms.MenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<span data-ttu-id="a087d-122"><xref:System.Windows.Forms.MenuStrip>에서 오버플로 기능을 지원하는지 여부를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-122">Gets or sets a value indicating whether the <xref:System.Windows.Forms.MenuStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|<span data-ttu-id="a087d-123"><xref:System.Windows.Forms.ToolStripMenuItem>에 연결된 바로 가기 키를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-123">Gets or sets the shortcut keys associated with the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|<span data-ttu-id="a087d-124"><xref:System.Windows.Forms.ToolStripMenuItem>에 연결된 바로 가기 키가 <xref:System.Windows.Forms.ToolStripMenuItem> 옆에 표시되는지 여부를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-124">Gets or sets a value indicating whether the shortcut keys that are associated with the <xref:System.Windows.Forms.ToolStripMenuItem> are displayed next to the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
  
 <span data-ttu-id="a087d-125">다음 표에서는 중요 한 <xref:System.Windows.Forms.MenuStrip> 동반 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-125">The following table shows the important <xref:System.Windows.Forms.MenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="a087d-126">클래스</span><span class="sxs-lookup"><span data-stu-id="a087d-126">Class</span></span>|<span data-ttu-id="a087d-127">Description</span><span class="sxs-lookup"><span data-stu-id="a087d-127">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="a087d-128"><xref:System.Windows.Forms.MenuStrip> 또는 <xref:System.Windows.Forms.ContextMenuStrip>에 표시된 선택 가능한 옵션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-128">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="a087d-129">바로 가기 메뉴를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-129">Represents a shortcut menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="a087d-130">사용자가 <xref:System.Windows.Forms.ToolStripDropDownButton> 또는 더 높은 수준의 메뉴 항목을 클릭할 때 표시 되는 목록에서 단일 항목을 선택할 수 있도록 하는 컨트롤을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-130">Represents a control that allows the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="a087d-131">클릭 하면 드롭다운 항목을 표시 하는 <xref:System.Windows.Forms.ToolStripItem>에서 파생 되는 컨트롤에 대 한 기본 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a087d-131">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a087d-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a087d-132">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
