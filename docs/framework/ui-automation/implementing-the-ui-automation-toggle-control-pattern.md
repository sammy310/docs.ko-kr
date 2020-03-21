---
title: UI 자동화 Toggle 컨트롤 패턴 구현
ms.date: 03/30/2017
helpviewer_keywords:
- Toggle control pattern
- control patterns, Toggle
- UI Automation, Toggle control pattern
ms.assetid: 3cfe875f-b0c0-413d-9703-5f14e6a1a30e
ms.openlocfilehash: 5f64842d31d46af3d648b9b570d1cfb210e2910a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180059"
---
# <a name="implementing-the-ui-automation-toggle-control-pattern"></a><span data-ttu-id="d7f97-102">UI 자동화 Toggle 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="d7f97-102">Implementing the UI Automation Toggle Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="d7f97-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d7f97-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d7f97-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7f97-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="d7f97-105">이 항목에서는 메서드 및 속성에 대한 정보를 비롯하여 <xref:System.Windows.Automation.Provider.IToggleProvider>구현을 위한 지침 및 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f97-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>, including information about methods and properties.</span></span> <span data-ttu-id="d7f97-106">추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f97-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="d7f97-107"><xref:System.Windows.Automation.TogglePattern> 컨트롤 패턴은 일련의 상태를 순환할 수 있는 컨트롤을 지원하고 설정된 상태를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f97-107">The <xref:System.Windows.Automation.TogglePattern> control pattern is used to support controls that can cycle through a set of states and maintain a state once set.</span></span> <span data-ttu-id="d7f97-108">이 컨트롤 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7f97-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="d7f97-109">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="d7f97-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="d7f97-110">Toggle 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="d7f97-110">When implementing the Toggle control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="d7f97-111">활성화되면 상태가 유지되지 않는 컨트롤(예: 단추, 도구 모음 단추, 하이퍼링크)은 <xref:System.Windows.Automation.Provider.IInvokeProvider> 를 대신 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f97-111">Controls that do not maintain state when activated, such as buttons, toolbar buttons, and hyperlinks, must implement <xref:System.Windows.Automation.Provider.IInvokeProvider> instead.</span></span>  
  
- <span data-ttu-id="d7f97-112">컨트롤은 다음 순서대로 <xref:System.Windows.Automation.ToggleState> 를 순환해야 합니다. <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> , <xref:System.Windows.Automation.ToggleState.Indeterminate>(지원되는 경우)</span><span class="sxs-lookup"><span data-stu-id="d7f97-112">A control must cycle through its <xref:System.Windows.Automation.ToggleState> in the following order: <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> and, if supported, <xref:System.Windows.Automation.ToggleState.Indeterminate>.</span></span>  
  
- <span data-ttu-id="d7f97-113"><xref:System.Windows.Automation.TogglePattern> 은 적절한 <xref:System.Windows.Automation.ToggleState> 순서로 순환하지 않고 3상 확인란을 직접 설정하는 것과 관련된 문제로 인해 SetState(newState) 메서드를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f97-113"><xref:System.Windows.Automation.TogglePattern> does not provide a SetState(newState) method due to issues surrounding the direct setting of a tri-state CheckBox without cycling through its appropriate <xref:System.Windows.Automation.ToggleState> sequence.</span></span>  
  
- <span data-ttu-id="d7f97-114">RadioButton 컨트롤은 유효한 상태를 순환할 수 없기 때문에 <xref:System.Windows.Automation.Provider.IToggleProvider>를 구현하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f97-114">The RadioButton control does not implement <xref:System.Windows.Automation.Provider.IToggleProvider>, as it is not capable of cycling through its valid states.</span></span>  
  
<a name="Required_Members_for_IToggleProvider"></a>
## <a name="required-members-for-itoggleprovider"></a><span data-ttu-id="d7f97-115">IToggleProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="d7f97-115">Required Members for IToggleProvider</span></span>  
 <span data-ttu-id="d7f97-116"><xref:System.Windows.Automation.Provider.IToggleProvider>를 구현하려면 다음과 같은 속성 및 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f97-116">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>.</span></span>  
  
|<span data-ttu-id="d7f97-117">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="d7f97-117">Required member</span></span>|<span data-ttu-id="d7f97-118">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="d7f97-118">Member type</span></span>|<span data-ttu-id="d7f97-119">메모</span><span class="sxs-lookup"><span data-stu-id="d7f97-119">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.TogglePattern.Toggle%2A>|<span data-ttu-id="d7f97-120">방법</span><span class="sxs-lookup"><span data-stu-id="d7f97-120">Method</span></span>|<span data-ttu-id="d7f97-121">None</span><span class="sxs-lookup"><span data-stu-id="d7f97-121">None</span></span>|  
|<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>|<span data-ttu-id="d7f97-122">속성</span><span class="sxs-lookup"><span data-stu-id="d7f97-122">Property</span></span>|<span data-ttu-id="d7f97-123">None</span><span class="sxs-lookup"><span data-stu-id="d7f97-123">None</span></span>|  
  
 <span data-ttu-id="d7f97-124">이 컨트롤 패턴에 연결된 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f97-124">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="d7f97-125">예외</span><span class="sxs-lookup"><span data-stu-id="d7f97-125">Exceptions</span></span>  
 <span data-ttu-id="d7f97-126">이 컨트롤 패턴에 연결된 예외가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f97-126">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f97-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7f97-127">See also</span></span>

- [<span data-ttu-id="d7f97-128">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="d7f97-128">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="d7f97-129">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="d7f97-129">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="d7f97-130">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="d7f97-130">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="d7f97-131">UI 자동화를 사용하여 확인란의 전환 상태 가져오기</span><span class="sxs-lookup"><span data-stu-id="d7f97-131">Get the Toggle State of a Check Box Using UI Automation</span></span>](get-the-toggle-state-of-a-check-box-using-ui-automation.md)
- [<span data-ttu-id="d7f97-132">UI Automation Tree Overview</span><span class="sxs-lookup"><span data-stu-id="d7f97-132">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="d7f97-133">UI 자동화의 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="d7f97-133">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
