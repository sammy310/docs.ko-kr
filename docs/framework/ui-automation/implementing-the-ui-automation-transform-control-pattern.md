---
title: UI 자동화 Transform 컨트롤 패턴 구현
description: UI 자동화에서 Transform 컨트롤 패턴을 구현 하기 위한 지침 및 규칙을 검토 합니다. ITransformProvider 인터페이스의 필수 멤버를 알고 있어야 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Transform
- Transform control pattern
- UI Automation, Transform control pattern
ms.assetid: 5f49d843-5845-4800-9d9c-56ce0d146844
ms.openlocfilehash: fc47170a08ff08f6cd8f67996ef8fbf19c40f819
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265650"
---
# <a name="implementing-the-ui-automation-transform-control-pattern"></a><span data-ttu-id="cbbd8-104">UI 자동화 Transform 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="cbbd8-104">Implementing the UI Automation Transform Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="cbbd8-105">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="cbbd8-106">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="cbbd8-107">이 항목에서는 속성, 메서드 및 이벤트에 대한 정보를 포함하여 <xref:System.Windows.Automation.Provider.ITransformProvider>를 구현하기 위한 지침 및 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="cbbd8-108">추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="cbbd8-109"><xref:System.Windows.Automation.TransformPattern> 컨트롤 패턴은 2차원 공간 내에서 이동, 크기 조정 또는 회전할 수 있는 컨트롤을 지원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-109">The <xref:System.Windows.Automation.TransformPattern> control pattern is used to support controls that can be moved, resized, or rotated within a two-dimensional space.</span></span> <span data-ttu-id="cbbd8-110">이 컨트롤 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="cbbd8-111">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="cbbd8-111">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="cbbd8-112">Transform 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-112">When implementing the Transform control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="cbbd8-113">이 컨트롤 패턴에 대한 지원은 데스크톱의 개체로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-113">Support for this control pattern is not limited to objects on the desktop.</span></span> <span data-ttu-id="cbbd8-114">컨테이너 경계 내에서 자식 항목을 자유롭게 이동, 크기 조정 또는 회전할 수 있는 경우 이 컨트롤 패턴은 컨테이너 개체의 자식 항목에서도 지원되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-114">This control pattern must also be supported by the children of a container object if the children can be moved, resized, or rotated freely within the boundaries of the container.</span></span>  
  
- <span data-ttu-id="cbbd8-115">개체를 이동하거나, 크기를 조정하거나, 회전할 수 없습니다. 이렇게 하면 결과로 표시되는 화면 위치가 컨테이너의 좌표를 완전히 벗어나므로 키보드 또는 마우스에 액세스할 수 없습니다(예: 최상위 창이 화면을 벗어나거나 자식 개체가 컨테이너의 뷰포트 경계 밖으로 이동되는 경우).</span><span class="sxs-lookup"><span data-stu-id="cbbd8-115">An object cannot be moved, resized, or rotated such that its resulting screen location would be completely outside the coordinates of its container and therefore inaccessible to the keyboard or mouse (for example, when a top-level window is moved off-screen or a child object is moved outside the boundaries of the container's viewport).</span></span> <span data-ttu-id="cbbd8-116">이러한 경우에는, 개체가 컨테이너 경계 내에 있도록 재정의되어 상단 또는 왼쪽 좌표로 가능하면 요청된 화면 좌표와 최대한 가깝게 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-116">In these cases, the object is placed as close to the requested screen coordinates as possible with the top or left coordinates overridden to be within the container boundaries.</span></span>  
  
- <span data-ttu-id="cbbd8-117">다중 모니터 시스템의 경우 개체가 이동, 크기 조정 또는 회전되어 조합된 데스크톱 화면 좌표를 완전히 벗어나면 이 개체는 요청된 좌표에 최대한 가깝게 기본 모니터에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-117">For multi-monitor systems, if an object is moved, resized, or rotated completely outside the combined desktop screen coordinates, the object is placed on the primary monitor as close to the requested coordinates as possible.</span></span>  
  
- <span data-ttu-id="cbbd8-118">모든 매개 변수 및 속성 값은 절대 값이며 로캘과 무관합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-118">All parameters and property values are absolute and independent of locale.</span></span>  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>

## <a name="required-members-for-itransformprovider"></a><span data-ttu-id="cbbd8-119">ITransformProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="cbbd8-119">Required Members for ITransformProvider</span></span>  

 <span data-ttu-id="cbbd8-120"><xref:System.Windows.Automation.Provider.ITransformProvider>를 구현하려면 다음과 같은 속성 및 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-120">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>.</span></span>  
  
|<span data-ttu-id="cbbd8-121">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="cbbd8-121">Required members</span></span>|<span data-ttu-id="cbbd8-122">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="cbbd8-122">Member type</span></span>|<span data-ttu-id="cbbd8-123">참고</span><span class="sxs-lookup"><span data-stu-id="cbbd8-123">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanMove%2A>|<span data-ttu-id="cbbd8-124">속성</span><span class="sxs-lookup"><span data-stu-id="cbbd8-124">Property</span></span>|<span data-ttu-id="cbbd8-125">없음</span><span class="sxs-lookup"><span data-stu-id="cbbd8-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanResize%2A>|<span data-ttu-id="cbbd8-126">속성</span><span class="sxs-lookup"><span data-stu-id="cbbd8-126">Property</span></span>|<span data-ttu-id="cbbd8-127">없음</span><span class="sxs-lookup"><span data-stu-id="cbbd8-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanRotate%2A>|<span data-ttu-id="cbbd8-128">속성</span><span class="sxs-lookup"><span data-stu-id="cbbd8-128">Property</span></span>|<span data-ttu-id="cbbd8-129">없음</span><span class="sxs-lookup"><span data-stu-id="cbbd8-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A>|<span data-ttu-id="cbbd8-130">메서드</span><span class="sxs-lookup"><span data-stu-id="cbbd8-130">Method</span></span>|<span data-ttu-id="cbbd8-131">없음</span><span class="sxs-lookup"><span data-stu-id="cbbd8-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A>|<span data-ttu-id="cbbd8-132">메서드</span><span class="sxs-lookup"><span data-stu-id="cbbd8-132">Method</span></span>|<span data-ttu-id="cbbd8-133">없음</span><span class="sxs-lookup"><span data-stu-id="cbbd8-133">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A>|<span data-ttu-id="cbbd8-134">메서드</span><span class="sxs-lookup"><span data-stu-id="cbbd8-134">Method</span></span>|<span data-ttu-id="cbbd8-135">없음</span><span class="sxs-lookup"><span data-stu-id="cbbd8-135">None</span></span>|  
  
 <span data-ttu-id="cbbd8-136">이 컨트롤 패턴에 연결된 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-136">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="cbbd8-137">예외</span><span class="sxs-lookup"><span data-stu-id="cbbd8-137">Exceptions</span></span>  

 <span data-ttu-id="cbbd8-138">공급자는 다음과 같은 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-138">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="cbbd8-139">예외 유형</span><span class="sxs-lookup"><span data-stu-id="cbbd8-139">Exception Type</span></span>|<span data-ttu-id="cbbd8-140">조건</span><span class="sxs-lookup"><span data-stu-id="cbbd8-140">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A><br /><br /> <span data-ttu-id="cbbd8-141">- <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> 이 false 인 경우</span><span class="sxs-lookup"><span data-stu-id="cbbd8-141">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A><br /><br /> <span data-ttu-id="cbbd8-142">- <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> 이 false 인 경우</span><span class="sxs-lookup"><span data-stu-id="cbbd8-142">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A><br /><br /> <span data-ttu-id="cbbd8-143">- <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> 이 false 인 경우</span><span class="sxs-lookup"><span data-stu-id="cbbd8-143">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> is false.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cbbd8-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbbd8-144">See also</span></span>

- [<span data-ttu-id="cbbd8-145">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="cbbd8-145">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="cbbd8-146">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="cbbd8-146">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="cbbd8-147">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="cbbd8-147">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="cbbd8-148">UI 자동화 트리 개요</span><span class="sxs-lookup"><span data-stu-id="cbbd8-148">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="cbbd8-149">UI 자동화에서 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="cbbd8-149">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
