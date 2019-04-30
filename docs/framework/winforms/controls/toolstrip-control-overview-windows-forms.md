---
title: ToolStrip 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 3e532b040d3c7859220b7f73958b63e7208b988c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009528"
---
# <a name="toolstrip-control-overview-windows-forms"></a><span data-ttu-id="96881-102">ToolStrip 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="96881-102">ToolStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="96881-103">Windows Forms <xref:System.Windows.Forms.ToolStrip> 컨트롤 및 해당 관련된 클래스 도구 모음, 상태 표시줄 및 메뉴를 사용자 인터페이스 요소를 결합 하는 것에 대 한 일반적인 프레임 워크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96881-103">The Windows Forms <xref:System.Windows.Forms.ToolStrip> control and its associated classes provide a common framework for combining user interface elements into toolbars, status bars, and menus.</span></span> <span data-ttu-id="96881-104"><xref:System.Windows.Forms.ToolStrip> 컨트롤 도구 모음의 가로 또는 세로 공간을 공유할 수 있는 내부 활성화와 편집, 사용자 지정 레이아웃 및 래프팅 (rafting)를 비롯 한 다양 한 디자인 타임 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96881-104"><xref:System.Windows.Forms.ToolStrip> controls offer a rich design-time experience that includes in-place activation and editing, custom layout, and rafting, which is the ability of toolbars to share horizontal or vertical space.</span></span>  
  
 <span data-ttu-id="96881-105">하지만 <xref:System.Windows.Forms.ToolStrip> 대체 하 고 이전 버전에서는 컨트롤에 기능 추가 <xref:System.Windows.Forms.ToolBar> 원하는 경우 이전 버전과 호환성 및 향후 사용을 위해 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96881-105">Although <xref:System.Windows.Forms.ToolStrip> replaces and adds functionality to the control in previous versions, <xref:System.Windows.Forms.ToolBar> is retained for both backward compatibility and future use if desired.</span></span>  
  
## <a name="features-of-the-toolstrip-controls"></a><span data-ttu-id="96881-106">ToolStrip 컨트롤의 기능</span><span class="sxs-lookup"><span data-stu-id="96881-106">Features of the ToolStrip Controls</span></span>  
 <span data-ttu-id="96881-107">사용 된 <xref:System.Windows.Forms.ToolStrip> 컨트롤:</span><span class="sxs-lookup"><span data-stu-id="96881-107">Use the <xref:System.Windows.Forms.ToolStrip> control to:</span></span>  
  
- <span data-ttu-id="96881-108">컨테이너 간에 공통 사용자 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96881-108">Present a common user interface across containers.</span></span>  
  
- <span data-ttu-id="96881-109">쉽게 사용자 지정 만들기를 지 원하는 일반적인된 도구 모음 사용자 인터페이스 및 레이아웃 기능, 고급 텍스트 및 이미지, 드롭다운 단추 및 컨트롤을 래프팅, 도킹 단추와 같은 오버플로 단추 및 다시 정렬 런타임 <xref:System.Windows.Forms.ToolStrip> 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="96881-109">Create easily customized, commonly employed toolbars that support advanced user interface and layout features, such as docking, rafting, buttons with text and images, drop-down buttons and controls, overflow buttons, and run-time reordering of <xref:System.Windows.Forms.ToolStrip> items.</span></span>  
  
- <span data-ttu-id="96881-110">오버플로 및 런타임 항목 다시 정렬을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="96881-110">Support overflow and run-time item reordering.</span></span> <span data-ttu-id="96881-111">오버플로 기능 이동 항목 드롭다운 메뉴에 표시할 만큼 충분 한 공간이 없을 때를 <xref:System.Windows.Forms.ToolStrip>입니다.</span><span class="sxs-lookup"><span data-stu-id="96881-111">The overflow feature moves items to a drop-down menu when there is not enough room to display them in a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
- <span data-ttu-id="96881-112">일반적인 모양 및 동작의 일반적인 렌더링 모델을 통해 운영 체제를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="96881-112">Support the typical appearance and behavior of the operating system through a common rendering model.</span></span>  
  
- <span data-ttu-id="96881-113">다른 컨트롤에 대 한 이벤트를 처리 하는 동일한 방식으로 모든 컨테이너 및 포함 된 항목에 대해 일관 되 게 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="96881-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
- <span data-ttu-id="96881-114">항목을 끌어올 <xref:System.Windows.Forms.ToolStrip> 간 또는 한 <xref:System.Windows.Forms.ToolStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="96881-114">Drag items from one <xref:System.Windows.Forms.ToolStrip> to another or within a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
- <span data-ttu-id="96881-115">고급 레이아웃을 사용 하 여 드롭다운 목록 컨트롤 및 사용자 인터페이스 형식 편집기 만들기를 <xref:System.Windows.Forms.ToolStripDropDown>입니다.</span><span class="sxs-lookup"><span data-stu-id="96881-115">Create drop-down controls and user interface type editors with advanced layouts in a <xref:System.Windows.Forms.ToolStripDropDown>.</span></span>  
  
 <span data-ttu-id="96881-116">사용 합니다 <xref:System.Windows.Forms.ToolStripControlHost> 에서 다른 컨트롤을 사용 하는 클래스를 <xref:System.Windows.Forms.ToolStrip> 얻고이 <xref:System.Windows.Forms.ToolStrip> 에 기능.</span><span class="sxs-lookup"><span data-stu-id="96881-116">Use the <xref:System.Windows.Forms.ToolStripControlHost> class to use other controls on a <xref:System.Windows.Forms.ToolStrip> and gain <xref:System.Windows.Forms.ToolStrip> functionality for them.</span></span>  
  
 <span data-ttu-id="96881-117">기능을 확장 하 고 사용 하 여 모양과 동작을 수정할 수는 <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, 및 <xref:System.Windows.Forms.ToolStripManager> 와 함께 합니다 <xref:System.Windows.Forms.ToolStripRenderMode> 및 <xref:System.Windows.Forms.ToolStripManagerRenderMode> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="96881-117">You can extend the functionality and modify the appearance and behavior by using the <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, and <xref:System.Windows.Forms.ToolStripManager> along with the <xref:System.Windows.Forms.ToolStripRenderMode> and <xref:System.Windows.Forms.ToolStripManagerRenderMode> enumerations.</span></span>  
  
 <span data-ttu-id="96881-118"><xref:System.Windows.Forms.ToolStrip> 컨트롤은 항상 구성이 가능 하며 확장 가능 하며 여러 속성, 메서드 및 이벤트 모양 및 동작을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96881-118">The <xref:System.Windows.Forms.ToolStrip> control is highly configurable and extensible, and it provides many properties, methods, and events to customize appearance and behavior.</span></span> <span data-ttu-id="96881-119">몇 가지 중요 한 멤버는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="96881-119">Below are some noteworthy members:</span></span>  
  
### <a name="important-toolstrip-members"></a><span data-ttu-id="96881-120">중요 한 ToolStrip 멤버</span><span class="sxs-lookup"><span data-stu-id="96881-120">Important ToolStrip Members</span></span>  
  
|<span data-ttu-id="96881-121">이름</span><span class="sxs-lookup"><span data-stu-id="96881-121">Name</span></span>|<span data-ttu-id="96881-122">설명</span><span class="sxs-lookup"><span data-stu-id="96881-122">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|<span data-ttu-id="96881-123">부모 컨테이너의 가장자리를 가져오거나 설정 합니다.는 <xref:System.Windows.Forms.ToolStrip> 에 도킹 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96881-123">Gets or sets which edge of the parent container a <xref:System.Windows.Forms.ToolStrip> is docked to.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|<span data-ttu-id="96881-124"><xref:System.Windows.Forms.ToolStrip> 클래스를 통해 끌어서 놓기와 항목 다시 정렬을 전용으로 처리할지를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="96881-124">Gets or sets a value indicating whether drag-and-drop and item reordering are handled privately by the <xref:System.Windows.Forms.ToolStrip> class.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|<span data-ttu-id="96881-125">나타내는 값을 가져오거나 하는 방법을 <xref:System.Windows.Forms.ToolStrip> 해당 항목을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="96881-125">Gets or sets a value indicating how the <xref:System.Windows.Forms.ToolStrip> lays out its items.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|<span data-ttu-id="96881-126">가져오거나 설정 여부를 <xref:System.Windows.Forms.ToolStripItem> 에 연결할 때 합니다 <xref:System.Windows.Forms.ToolStrip> 또는 <xref:System.Windows.Forms.ToolStripOverflowButton> 또는 둘 사이의 부동 상태로 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96881-126">Gets or sets whether a <xref:System.Windows.Forms.ToolStripItem> is attached to the <xref:System.Windows.Forms.ToolStrip> or <xref:System.Windows.Forms.ToolStripOverflowButton> or can float between the two.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|<span data-ttu-id="96881-127">나타내는 값을 가져옵니다 여부를 <xref:System.Windows.Forms.ToolStripItem> 드롭다운 목록에서 다른 항목을 표시 때 목록을 <xref:System.Windows.Forms.ToolStripItem> 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96881-127">Gets a value indicating whether a <xref:System.Windows.Forms.ToolStripItem> displays other items in a drop-down list when the <xref:System.Windows.Forms.ToolStripItem> is clicked.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|<span data-ttu-id="96881-128">오버플로가 활성화된 <xref:System.Windows.Forms.ToolStrip>에 대한 오버플로 단추인 <xref:System.Windows.Forms.ToolStripItem>을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="96881-128">Gets the <xref:System.Windows.Forms.ToolStripItem> that is the overflow button for a <xref:System.Windows.Forms.ToolStrip> with overflow enabled.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|<span data-ttu-id="96881-129">가져오거나를 <xref:System.Windows.Forms.ToolStripRenderer> 모양 및 동작 (모양 및 느낌)의 사용자 지정 하는 데는 <xref:System.Windows.Forms.ToolStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="96881-129">Gets or sets a <xref:System.Windows.Forms.ToolStripRenderer> used to customize the appearance and behavior (look and feel) of a <xref:System.Windows.Forms.ToolStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|<span data-ttu-id="96881-130">적용할 것 그리기 스타일을 가져오거나 설정 합니다.는 <xref:System.Windows.Forms.ToolStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="96881-130">Gets or sets the painting styles to be applied to the <xref:System.Windows.Forms.ToolStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|<span data-ttu-id="96881-131"><xref:System.Windows.Forms.ToolStrip.Renderer%2A> 속성이 변경되면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="96881-131">Raised when the <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property changes.</span></span>|  
  
 <span data-ttu-id="96881-132"><xref:System.Windows.Forms.ToolStrip> 컨트롤의 유연성은 다양 한 도우미 클래스를 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96881-132">The <xref:System.Windows.Forms.ToolStrip> control's flexibility is achieved through the use of a number of companion classes.</span></span> <span data-ttu-id="96881-133">다음은 가장 중요 한 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="96881-133">Below are some of the most noteworthy:</span></span>  
  
### <a name="important-toolstrip-companion-classes"></a><span data-ttu-id="96881-134">ToolStrip에 중요 한 역할 클래스</span><span class="sxs-lookup"><span data-stu-id="96881-134">Important ToolStrip Companion Classes</span></span>  
  
|<span data-ttu-id="96881-135">이름</span><span class="sxs-lookup"><span data-stu-id="96881-135">Name</span></span>|<span data-ttu-id="96881-136">설명</span><span class="sxs-lookup"><span data-stu-id="96881-136">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|<span data-ttu-id="96881-137">대체 하 고 기능을 추가 합니다 <xref:System.Windows.Forms.MainMenu> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="96881-137">Replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> class.</span></span>|  
|<xref:System.Windows.Forms.StatusStrip>|<span data-ttu-id="96881-138">대체 하 고 기능을 추가 합니다 <xref:System.Windows.Forms.StatusBar> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="96881-138">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> class.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="96881-139">대체 하 고 기능을 추가 합니다 <xref:System.Windows.Forms.ContextMenu> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="96881-139">Replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> class.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem>|<span data-ttu-id="96881-140">이벤트 및 모든 요소에 대 한 레이아웃을 관리 하는 추상 기본 클래스는를 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>, 또는 <xref:System.Windows.Forms.ToolStripDropDown> 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96881-140">Abstract base class that manages events and layout for all the elements that a <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>, or <xref:System.Windows.Forms.ToolStripDropDown> can contain.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer>|<span data-ttu-id="96881-141">다양 한 방법으로 제어를 정렬할 수 있는 폼의 양쪽 패널을 사용 하 여 컨테이너를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96881-141">Provides a container with a panel on each side of the form in which controls can be arranged in various ways.</span></span>|  
|<xref:System.Windows.Forms.ToolStripRenderer>|<span data-ttu-id="96881-142">에 대 한 그리기 기능을 처리 <xref:System.Windows.Forms.ToolStrip> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="96881-142">Handles the painting functionality for <xref:System.Windows.Forms.ToolStrip> objects.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|<span data-ttu-id="96881-143">Microsoft Office 스타일 모양을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="96881-143">Provides Microsoft Office-style appearance.</span></span>|  
|<xref:System.Windows.Forms.ToolStripManager>|<span data-ttu-id="96881-144">컨트롤 <xref:System.Windows.Forms.ToolStrip> 렌더링 및 래프팅 및 병합 <xref:System.Windows.Forms.MenuStrip>를 <xref:System.Windows.Forms.ToolStripDropDownMenu>, 및 <xref:System.Windows.Forms.ToolStripMenuItem> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="96881-144">Controls <xref:System.Windows.Forms.ToolStrip> rendering and rafting, and the merging of <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, and <xref:System.Windows.Forms.ToolStripMenuItem> objects.</span></span>|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|<span data-ttu-id="96881-145">여러 적용할 그리기 스타일 (사용자 지정 Windows XP 또는 Microsoft Office Professional)을 지정 <xref:System.Windows.Forms.ToolStrip> 폼에 포함 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="96881-145">Specifies the painting style (custom, Windows XP, or Microsoft Office Professional) applied to multiple <xref:System.Windows.Forms.ToolStrip> objects contained in a form.</span></span>|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|<span data-ttu-id="96881-146">하나에 적용 되는 그리기 스타일 (사용자 지정 Windows XP 또는 Microsoft Office Professional) 지정 <xref:System.Windows.Forms.ToolStrip> 폼에 포함 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="96881-146">Specifies the painting style (custom, Windows XP, or Microsoft Office Professional) applied to one <xref:System.Windows.Forms.ToolStrip> object contained in a form.</span></span>|  
|<xref:System.Windows.Forms.ToolStripControlHost>|<span data-ttu-id="96881-147">특히 되지 않는 다른 컨트롤을 호스트 <xref:System.Windows.Forms.ToolStrip> 컨트롤 이지만 하려는 <xref:System.Windows.Forms.ToolStrip> 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="96881-147">Hosts other controls that are not specifically <xref:System.Windows.Forms.ToolStrip> controls but for which you want <xref:System.Windows.Forms.ToolStrip> functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|<span data-ttu-id="96881-148">지정 여부를 <xref:System.Windows.Forms.ToolStripItem> 주에 배치 하는 것 <xref:System.Windows.Forms.ToolStrip>, 오버플로에 <xref:System.Windows.Forms.ToolStrip>, 하거나 사용 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="96881-148">Specifies whether a <xref:System.Windows.Forms.ToolStripItem> is to be laid out on the main <xref:System.Windows.Forms.ToolStrip>, on the overflow <xref:System.Windows.Forms.ToolStrip>, or neither.</span></span>|  
  
 <span data-ttu-id="96881-149">자세한 내용은 [ToolStrip 기술 요약](toolstrip-technology-summary.md) 하 고 [ToolStrip 컨트롤 아키텍처](toolstrip-control-architecture.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="96881-149">For more information, see [ToolStrip Technology Summary](toolstrip-technology-summary.md) and [ToolStrip Control Architecture](toolstrip-control-architecture.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96881-150">참고자료</span><span class="sxs-lookup"><span data-stu-id="96881-150">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
