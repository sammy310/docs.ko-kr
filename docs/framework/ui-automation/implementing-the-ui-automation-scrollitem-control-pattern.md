---
title: UI 자동화 ScrollItem 컨트롤 패턴 구현
description: UI 자동화에서 ScrollItem 컨트롤 패턴을 구현 하기 위한 지침 및 규칙을 검토 합니다. IScrollItemProvider 인터페이스에 필요한 멤버를 참조 하십시오.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
ms.openlocfilehash: 3274f75af0ca055547a75fd8db6384ddb0f59483
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239239"
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a><span data-ttu-id="b434b-104">UI 자동화 ScrollItem 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="b434b-104">Implementing the UI Automation ScrollItem Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="b434b-105">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b434b-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="b434b-106">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b434b-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="b434b-107">이 항목에서는 속성, 메서드 및 이벤트에 대한 정보를 포함하여 <xref:System.Windows.Automation.Provider.IScrollItemProvider>를 구현하기 위한 지침 및 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b434b-107">This topic introduces guidelines and conventions for implementing the <xref:System.Windows.Automation.Provider.IScrollItemProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="b434b-108">추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b434b-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="b434b-109"><xref:System.Windows.Automation.ScrollItemPattern> 컨트롤 패턴은 <xref:System.Windows.Automation.Provider.IScrollProvider>를 구현하는 컨테이너의 개별 자식 컨트롤을 지원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b434b-109">The <xref:System.Windows.Automation.ScrollItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IScrollProvider>.</span></span> <span data-ttu-id="b434b-110">이 컨트롤 패턴은 자식 컨트롤과 해당 컨테이너 간에 통신 채널 역할을 하여 컨테이너가 자식 컨트롤이 표시되도록 뷰포트 내에 현재 표시된 콘텐츠(또는 영역)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b434b-110">This control pattern acts as a communication channel between a child control and its container to ensure that the container can change the currently visible content (or region) within its viewport to display the child control.</span></span> <span data-ttu-id="b434b-111">이 컨트롤 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b434b-111">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="b434b-112">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="b434b-112">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="b434b-113">Scroll Item 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="b434b-113">When implementing the Scroll Item control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="b434b-114">창 또는 캔버스 컨트롤 내에 포함된 항목은 IScrollItemProvider 인터페이스를 구현하는 데 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b434b-114">Items contained within a Window or Canvas control are not required to implement the IScrollItemProvider interface.</span></span> <span data-ttu-id="b434b-115">그 대신, <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>에 대해 유효한 위치를 노출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b434b-115">As an alternative, however, they must expose a valid location for the <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span></span> <span data-ttu-id="b434b-116">이렇게 하면 UI 자동화 클라이언트 애플리케이션이 컨테이너의 <xref:System.Windows.Automation.ScrollPattern> 컨트롤 패턴 메서드를 사용하여 자식 항목을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b434b-116">This will allow a UI Automation client application to use the <xref:System.Windows.Automation.ScrollPattern> control pattern methods on the container to display the child item.</span></span>  
  
<a name="Required_Members_for_IScrollItemProvider"></a>

## <a name="required-members-for-iscrollitemprovider"></a><span data-ttu-id="b434b-117">IScrollItemProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="b434b-117">Required Members for IScrollItemProvider</span></span>  

 <span data-ttu-id="b434b-118">다음 메서드는 IScrollProvider 인터페이스를 구현하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b434b-118">The following method is required for implementing the IScrollProvider interface.</span></span>  
  
|<span data-ttu-id="b434b-119">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="b434b-119">Required members</span></span>|<span data-ttu-id="b434b-120">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="b434b-120">Member type</span></span>|<span data-ttu-id="b434b-121">참고</span><span class="sxs-lookup"><span data-stu-id="b434b-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|<span data-ttu-id="b434b-122">-메서드</span><span class="sxs-lookup"><span data-stu-id="b434b-122">-   Method</span></span>|<span data-ttu-id="b434b-123">없음</span><span class="sxs-lookup"><span data-stu-id="b434b-123">None</span></span>|  
  
 <span data-ttu-id="b434b-124">이 컨트롤 패턴에는 연결된 속성 또는 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b434b-124">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="b434b-125">예외</span><span class="sxs-lookup"><span data-stu-id="b434b-125">Exceptions</span></span>  

 <span data-ttu-id="b434b-126">공급자는 다음과 같은 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b434b-126">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="b434b-127">예외 유형</span><span class="sxs-lookup"><span data-stu-id="b434b-127">Exception Type</span></span>|<span data-ttu-id="b434b-128">조건</span><span class="sxs-lookup"><span data-stu-id="b434b-128">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="b434b-129">항목을 스크롤하여 볼 수 없는 경우:</span><span class="sxs-lookup"><span data-stu-id="b434b-129">If an item cannot be scrolled into view:</span></span><br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="b434b-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b434b-130">See also</span></span>

- [<span data-ttu-id="b434b-131">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="b434b-131">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="b434b-132">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="b434b-132">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="b434b-133">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="b434b-133">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="b434b-134">UI 자동화 트리 개요</span><span class="sxs-lookup"><span data-stu-id="b434b-134">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="b434b-135">UI 자동화에서 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="b434b-135">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
