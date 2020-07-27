---
title: UI 자동화 MultipleView 컨트롤 패턴 구현
description: UI 자동화에서 MultipleView 컨트롤 패턴을 구현 하기 위한 지침 및 규칙을 검토 합니다. IMultipleViewProvider 인터페이스에 필요한 멤버를 참조 하십시오.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
ms.openlocfilehash: 0d65d57637891fcb1307f5ee83a417941ff323fb
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168230"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a><span data-ttu-id="17db2-104">UI 자동화 MultipleView 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="17db2-104">Implementing the UI Automation MultipleView Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="17db2-105">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="17db2-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="17db2-106">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="17db2-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="17db2-107">이 항목에서는 이벤트 및 속성에 대한 정보를 포함하여 <xref:System.Windows.Automation.Provider.IMultipleViewProvider>를 구현하기 위한 지침 및 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="17db2-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, including information about events and properties.</span></span> <span data-ttu-id="17db2-108">추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17db2-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="17db2-109"><xref:System.Windows.Automation.MultipleViewPattern> 컨트롤 패턴은 동일한 정보 또는 자식 컨트롤 집합의 여러 표현 간을 전환할 수 있는 컨트롤을 지원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="17db2-109">The <xref:System.Windows.Automation.MultipleViewPattern> control pattern is used to support controls that provide, and are able to switch between, multiple representations of the same set of information or child controls.</span></span>  
  
 <span data-ttu-id="17db2-110">여러 뷰를 표시할 수 있는 컨트롤의 예로는 목록 뷰가 있습니다. 여기에는 해당 내용이 축소판 그림으로 표시 될 수 있습니다. 타일, 아이콘 또는 세부 정보), Microsoft Excel 차트 (원형, 꺾은선형, 가로 막대형, 수식이 있는 셀 값), Microsoft Word 문서 (보통, 웹 레이아웃, 인쇄 레이아웃, 읽기 레이아웃, 개요), Microsoft Outlook 일정 (연도, 월, 주, 일) 및 Microsoft Windows Media Player 스킨이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17db2-110">Examples of controls that can present multiple views include the list view (which can show its contents as thumbnails, tiles, icons, or details), Microsoft Excel charts (pie, line, bar, cell value with a formula), Microsoft Word documents (normal, Web layout, print layout, reading layout, outline), Microsoft Outlook calendar (year, month, week, day), and Microsoft Windows Media Player skins.</span></span> <span data-ttu-id="17db2-111">지원되는 뷰는 컨트롤 개발자가 결정하며 컨트롤마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="17db2-111">The supported views are determined by the control developer and are specific to each control.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="17db2-112">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="17db2-112">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="17db2-113">Multiple View 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="17db2-113">When implementing the Multiple View control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="17db2-114"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> 가 현재 보기를 제공하는 컨트롤과 다를 경우 현재 보기를 관리하는 컨테이너에도 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17db2-114"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> should also be implemented on a container that manages the current view if it is different from a control that provides the current view.</span></span> <span data-ttu-id="17db2-115">예를 들어, 컨트롤의 뷰가 Windows 탐색기 애플리케이션에서 관리되는 동안 Windows 탐색기에는 현재 폴더 내용에 대한 목록 컨트롤이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="17db2-115">For example, Windows Explorer contains a List control for the current folder content while the view for the control is managed from the Windows Explorer application.</span></span>  
  
- <span data-ttu-id="17db2-116">콘텐츠를 정렬할 수 있는 컨트롤은 여러 뷰를 지원한다고 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17db2-116">A control that is able to sort its content is not considered to support multiple views.</span></span>  
  
- <span data-ttu-id="17db2-117">뷰 컬렉션은 인스턴스 간에 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17db2-117">The collection of views must be identical across instances.</span></span>  
  
- <span data-ttu-id="17db2-118">뷰 이름은 텍스트 읽어주기, 브라유 점자 및 기타 사람이 읽을 수 있는 애플리케이션에서 사용하기 적합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17db2-118">View names must be suitable for use in Text to Speech, Braille, and other human-readable applications.</span></span>  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>
## <a name="required-members-for-imultipleviewprovider"></a><span data-ttu-id="17db2-119">IMultipleViewProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="17db2-119">Required Members for IMultipleViewProvider</span></span>  
 <span data-ttu-id="17db2-120">IMultipleViewProvider를 구현하려면 다음과 같은 속성 및 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="17db2-120">The following properties and methods are required for implementing IMultipleViewProvider.</span></span>  
  
|<span data-ttu-id="17db2-121">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="17db2-121">Required members</span></span>|<span data-ttu-id="17db2-122">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="17db2-122">Member type</span></span>|<span data-ttu-id="17db2-123">참고</span><span class="sxs-lookup"><span data-stu-id="17db2-123">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|<span data-ttu-id="17db2-124">속성</span><span class="sxs-lookup"><span data-stu-id="17db2-124">Property</span></span>|<span data-ttu-id="17db2-125">없음</span><span class="sxs-lookup"><span data-stu-id="17db2-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|<span data-ttu-id="17db2-126">메서드</span><span class="sxs-lookup"><span data-stu-id="17db2-126">Method</span></span>|<span data-ttu-id="17db2-127">없음</span><span class="sxs-lookup"><span data-stu-id="17db2-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|<span data-ttu-id="17db2-128">메서드</span><span class="sxs-lookup"><span data-stu-id="17db2-128">Method</span></span>|<span data-ttu-id="17db2-129">없음</span><span class="sxs-lookup"><span data-stu-id="17db2-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|<span data-ttu-id="17db2-130">메서드</span><span class="sxs-lookup"><span data-stu-id="17db2-130">Method</span></span>|<span data-ttu-id="17db2-131">없음</span><span class="sxs-lookup"><span data-stu-id="17db2-131">None</span></span>|  
  
 <span data-ttu-id="17db2-132">이 컨트롤 패턴과 관련된 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17db2-132">There are no events associated with this control pattern.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="17db2-133">예외</span><span class="sxs-lookup"><span data-stu-id="17db2-133">Exceptions</span></span>  
 <span data-ttu-id="17db2-134">공급자는 다음과 같은 예외를 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17db2-134">Provider must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="17db2-135">예외 종류</span><span class="sxs-lookup"><span data-stu-id="17db2-135">Exception type</span></span>|<span data-ttu-id="17db2-136">조건</span><span class="sxs-lookup"><span data-stu-id="17db2-136">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="17db2-137">지원되는 뷰 컬렉션 멤버가 아닌 매개 변수로 <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> 또는 <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> 이 호출되는 경우.</span><span class="sxs-lookup"><span data-stu-id="17db2-137">When either <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> or <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> is called with a parameter that is not a member of the supported views collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="17db2-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17db2-138">See also</span></span>

- [<span data-ttu-id="17db2-139">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="17db2-139">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="17db2-140">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="17db2-140">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="17db2-141">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="17db2-141">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="17db2-142">UI 자동화 트리 개요</span><span class="sxs-lookup"><span data-stu-id="17db2-142">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="17db2-143">UI 자동화에서 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="17db2-143">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
