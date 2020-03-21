---
title: UI 자동화 MultipleView 컨트롤 패턴 구현
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
ms.openlocfilehash: 9decb617e30a340d3e73e911f7848110de5599e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180163"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a><span data-ttu-id="ffdde-102">UI 자동화 MultipleView 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="ffdde-102">Implementing the UI Automation MultipleView Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="ffdde-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ffdde-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ffdde-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ffdde-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="ffdde-105">이 항목에서는 이벤트 및 속성에 대한 정보를 포함하여 <xref:System.Windows.Automation.Provider.IMultipleViewProvider>를 구현하기 위한 지침 및 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdde-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, including information about events and properties.</span></span> <span data-ttu-id="ffdde-106">추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdde-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="ffdde-107"><xref:System.Windows.Automation.MultipleViewPattern> 컨트롤 패턴은 동일한 정보 또는 자식 컨트롤 집합의 여러 표현 간을 전환할 수 있는 컨트롤을 지원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdde-107">The <xref:System.Windows.Automation.MultipleViewPattern> control pattern is used to support controls that provide, and are able to switch between, multiple representations of the same set of information or child controls.</span></span>  
  
 <span data-ttu-id="ffdde-108">여러 뷰를 표시할 수 있는 컨트롤의 예로는 목록 보기(해당 내용을 축소판, 타일, 아이콘 또는 세부 정보로 표시할 수 있음), Microsoft Excel 차트(수식이 있는 원형, 선, 막대, 셀 값), Microsoft Word 문서(일반, 웹 레이아웃, 인쇄) 등이 있습니다. 레이아웃, 읽기 레이아웃, 개요), 마이크로 소프트 아웃룩 달력 (년, 월, 주, 일), 마이크로 소프트 윈도우 미디어 플레이어 스킨.</span><span class="sxs-lookup"><span data-stu-id="ffdde-108">Examples of controls that can present multiple views include the list view (which can show its contents as thumbnails, tiles, icons, or details), Microsoft Excel charts (pie, line, bar, cell value with a formula), Microsoft Word documents (normal, Web layout, print layout, reading layout, outline), Microsoft Outlook calendar (year, month, week, day), and Microsoft Windows Media Player skins.</span></span> <span data-ttu-id="ffdde-109">지원되는 뷰는 컨트롤 개발자가 결정하며 컨트롤마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffdde-109">The supported views are determined by the control developer and are specific to each control.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="ffdde-110">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="ffdde-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="ffdde-111">Multiple View 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="ffdde-111">When implementing the Multiple View control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="ffdde-112"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> 가 현재 보기를 제공하는 컨트롤과 다를 경우 현재 보기를 관리하는 컨테이너에도 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdde-112"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> should also be implemented on a container that manages the current view if it is different from a control that provides the current view.</span></span> <span data-ttu-id="ffdde-113">예를 들어, 컨트롤의 뷰가 Windows 탐색기 애플리케이션에서 관리되는 동안 Windows 탐색기에는 현재 폴더 내용에 대한 목록 컨트롤이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdde-113">For example, Windows Explorer contains a List control for the current folder content while the view for the control is managed from the Windows Explorer application.</span></span>  
  
- <span data-ttu-id="ffdde-114">콘텐츠를 정렬할 수 있는 컨트롤은 여러 뷰를 지원한다고 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdde-114">A control that is able to sort its content is not considered to support multiple views.</span></span>  
  
- <span data-ttu-id="ffdde-115">뷰 컬렉션은 인스턴스 간에 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdde-115">The collection of views must be identical across instances.</span></span>  
  
- <span data-ttu-id="ffdde-116">뷰 이름은 텍스트 읽어주기, 브라유 점자 및 기타 사람이 읽을 수 있는 애플리케이션에서 사용하기 적합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdde-116">View names must be suitable for use in Text to Speech, Braille, and other human-readable applications.</span></span>  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>
## <a name="required-members-for-imultipleviewprovider"></a><span data-ttu-id="ffdde-117">IMultipleViewProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="ffdde-117">Required Members for IMultipleViewProvider</span></span>  
 <span data-ttu-id="ffdde-118">IMultipleViewProvider를 구현하려면 다음과 같은 속성 및 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdde-118">The following properties and methods are required for implementing IMultipleViewProvider.</span></span>  
  
|<span data-ttu-id="ffdde-119">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="ffdde-119">Required members</span></span>|<span data-ttu-id="ffdde-120">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="ffdde-120">Member type</span></span>|<span data-ttu-id="ffdde-121">메모</span><span class="sxs-lookup"><span data-stu-id="ffdde-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|<span data-ttu-id="ffdde-122">속성</span><span class="sxs-lookup"><span data-stu-id="ffdde-122">Property</span></span>|<span data-ttu-id="ffdde-123">None</span><span class="sxs-lookup"><span data-stu-id="ffdde-123">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|<span data-ttu-id="ffdde-124">방법</span><span class="sxs-lookup"><span data-stu-id="ffdde-124">Method</span></span>|<span data-ttu-id="ffdde-125">None</span><span class="sxs-lookup"><span data-stu-id="ffdde-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|<span data-ttu-id="ffdde-126">방법</span><span class="sxs-lookup"><span data-stu-id="ffdde-126">Method</span></span>|<span data-ttu-id="ffdde-127">None</span><span class="sxs-lookup"><span data-stu-id="ffdde-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|<span data-ttu-id="ffdde-128">방법</span><span class="sxs-lookup"><span data-stu-id="ffdde-128">Method</span></span>|<span data-ttu-id="ffdde-129">None</span><span class="sxs-lookup"><span data-stu-id="ffdde-129">None</span></span>|  
  
 <span data-ttu-id="ffdde-130">이 컨트롤 패턴과 관련된 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdde-130">There are no events associated with this control pattern.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="ffdde-131">예외</span><span class="sxs-lookup"><span data-stu-id="ffdde-131">Exceptions</span></span>  
 <span data-ttu-id="ffdde-132">공급자는 다음과 같은 예외를 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdde-132">Provider must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="ffdde-133">예외 형식</span><span class="sxs-lookup"><span data-stu-id="ffdde-133">Exception type</span></span>|<span data-ttu-id="ffdde-134">조건</span><span class="sxs-lookup"><span data-stu-id="ffdde-134">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="ffdde-135">지원되는 뷰 컬렉션 멤버가 아닌 매개 변수로 <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> 또는 <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> 이 호출되는 경우.</span><span class="sxs-lookup"><span data-stu-id="ffdde-135">When either <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> or <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> is called with a parameter that is not a member of the supported views collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ffdde-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ffdde-136">See also</span></span>

- [<span data-ttu-id="ffdde-137">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="ffdde-137">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="ffdde-138">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="ffdde-138">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="ffdde-139">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="ffdde-139">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="ffdde-140">UI Automation Tree Overview</span><span class="sxs-lookup"><span data-stu-id="ffdde-140">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="ffdde-141">UI 자동화의 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="ffdde-141">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
