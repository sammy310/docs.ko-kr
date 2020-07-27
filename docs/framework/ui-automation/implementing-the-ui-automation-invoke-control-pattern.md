---
title: UI 자동화 Invoke 컨트롤 패턴 구현
description: UI 자동화에서 Invoke 컨트롤 패턴을 구현 하기 위한 지침 및 규칙을 참조 하세요. IInvokeProvider 인터페이스에 필요한 멤버를 참조 하십시오.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Invoke control pattern
- control patterns, Invoke
- Invoke control pattern
ms.assetid: e5b1e239-49f8-468e-bfec-1fba02ec9ac4
ms.openlocfilehash: b464b3ab5cd2b0789798f8b865b946c5eae017eb
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166177"
---
# <a name="implementing-the-ui-automation-invoke-control-pattern"></a><span data-ttu-id="cddb2-104">UI 자동화 Invoke 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="cddb2-104">Implementing the UI Automation Invoke Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="cddb2-105">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="cddb2-106">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cddb2-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>

<span data-ttu-id="cddb2-107">이 항목에서는 이벤트 및 속성에 대한 정보를 포함하여 <xref:System.Windows.Automation.Provider.IInvokeProvider>를 구현하기 위한 지침 및 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IInvokeProvider>, including information about events and properties.</span></span> <span data-ttu-id="cddb2-108">추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-108">Links to additional references are listed at the end of the topic.</span></span>

<span data-ttu-id="cddb2-109"><xref:System.Windows.Automation.InvokePattern> 컨트롤 패턴은 활성화되었을 때 상태를 유지하지 않고 명확한 단일 작업을 시작하거나 수행하는 컨트롤을 지원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-109">The <xref:System.Windows.Automation.InvokePattern> control pattern is used to support controls that do not maintain state when activated but rather initiate or perform a single, unambiguous action.</span></span> <span data-ttu-id="cddb2-110">확인란 및 라디오 단추와 같이 상태를 유지하는 컨트롤은 각각 <xref:System.Windows.Automation.Provider.IToggleProvider> 및 <xref:System.Windows.Automation.Provider.ISelectionItemProvider> 를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-110">Controls that do maintain state, such as check boxes and radio buttons, must instead implement <xref:System.Windows.Automation.Provider.IToggleProvider> and <xref:System.Windows.Automation.Provider.ISelectionItemProvider> respectively.</span></span> <span data-ttu-id="cddb2-111">Invoke 컨트롤 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cddb2-111">For examples of controls that implement the Invoke control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>

<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="cddb2-112">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="cddb2-112">Implementation Guidelines and Conventions</span></span>

<span data-ttu-id="cddb2-113">Invoke 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="cddb2-113">When implementing the Invoke control pattern, note the following guidelines and conventions:</span></span>

- <span data-ttu-id="cddb2-114">동일한 동작이 다른 컨트롤 패턴 공급자를 통해 노출되지 않으면 컨트롤이 <xref:System.Windows.Automation.Provider.IInvokeProvider> 를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-114">Controls implement <xref:System.Windows.Automation.Provider.IInvokeProvider> if the same behavior is not exposed through another control pattern provider.</span></span> <span data-ttu-id="cddb2-115">예를 들어, 컨트롤의 <xref:System.Windows.Automation.InvokePattern.Invoke%2A> 메서드가 <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> 또는 <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> 메서드와 동일한 작업을 수행하는 경우 이 컨트롤은 <xref:System.Windows.Automation.Provider.IInvokeProvider>를 구현하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-115">For example, if the <xref:System.Windows.Automation.InvokePattern.Invoke%2A> method on a control performs the same action as the <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> or <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> method, the control should not implement <xref:System.Windows.Automation.Provider.IInvokeProvider>.</span></span>

- <span data-ttu-id="cddb2-116">일반적으로 컨트롤은 미리 정의된 키보드 바로 가기 또는 몇 가지 키 입력의 조합을 클릭하거나, 두 번 클릭하거나, ENTER 키를 눌러 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-116">Invoking a control is generally performed by clicking or double-clicking or pressing ENTER, a predefined keyboard shortcut, or some alternate combination of keystrokes.</span></span>

- <span data-ttu-id="cddb2-117"><xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent> 는 활성화된 컨트롤에서 발생합니다(연결된 작업을 수행하는 컨트롤에 대한 응답으로)</span><span class="sxs-lookup"><span data-stu-id="cddb2-117"><xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent> is raised on a control that has been activated (as a response to a control carrying out its associated action).</span></span> <span data-ttu-id="cddb2-118">가능하면, 컨트롤이 작업을 완료하여 차단하지 않고 반환된 후에 이벤트가 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-118">If possible, the event should be raised after the control has completed the action and returned without blocking.</span></span> <span data-ttu-id="cddb2-119">다음 시나리오에서 호출 요청을 처리하기 전에 Invoked 이벤트가 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-119">The Invoked event should be raised before servicing the Invoke request in the following scenarios:</span></span>

  - <span data-ttu-id="cddb2-120">작업이 완료될 때까지 기다리는 것은 실제로 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-120">It is not possible or practical to wait until the action is complete.</span></span>

  - <span data-ttu-id="cddb2-121">작업에는 사용자 개입이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-121">The action requires user interaction.</span></span>

  - <span data-ttu-id="cddb2-122">작업은 시간이 오래 걸리므로 상당한 시간 동안 호출 클라이언트가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-122">The action is time-consuming and will cause the calling client to block for a significant amount of time.</span></span>

- <span data-ttu-id="cddb2-123">컨트롤 호출로 인해 심각한 부작용이 발생하는 경우, 이러한 부작용은 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A> 속성을 통해 노출되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-123">If invoking the control has significant side-effects, those side-effects should be exposed through the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A> property.</span></span> <span data-ttu-id="cddb2-124">예를 들어, <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> 가 선택 항목과 연결되지 않은 경우에도 <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> 로 인해 다른 컨트롤이 선택될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-124">For example, even though <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> is not associated with selection, <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> may cause another control to become selected.</span></span>

- <span data-ttu-id="cddb2-125">마우스 포인터(또는 마우스를 위에 올려 놓기) 효과는 일반적으로 Invoked 이벤트로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-125">Hover (or mouse-over) effects generally do not constitute an Invoked event.</span></span> <span data-ttu-id="cddb2-126">하지만 가리키기 상태를 기반으로 작업을 수행(시각적 효과를 발생시키는 것과 반대 개념)하는 컨트롤은 <xref:System.Windows.Automation.InvokePattern> 컨트롤 패턴을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-126">However, controls that perform an action (as opposed to cause a visual effect) based on the hover state should support the <xref:System.Windows.Automation.InvokePattern> control pattern.</span></span>

> [!NOTE]
> <span data-ttu-id="cddb2-127">이 구현은 컨트롤을 마우스 관련 부작용의 결과로만 호출할 수 있는 경우 접근성 문제로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-127">This implementation is considered an accessibility issue if the control can be invoked only as a result of a mouse-related side effect.</span></span>

- <span data-ttu-id="cddb2-128">컨트롤을 호출하는 것은 항목을 선택하는 것과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-128">Invoking a control is different from selecting an item.</span></span> <span data-ttu-id="cddb2-129">그러나 컨트롤에 따라, 컨트롤 호출로 인해 항목이 잘못된 방식으로 선택될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-129">However, depending on the control, invoking it may cause the item to become selected as a side-effect.</span></span> <span data-ttu-id="cddb2-130">예를 들어 내 문서 폴더에서 Microsoft Word 문서 목록 항목을 호출 하면 항목이 선택 되 고 문서가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-130">For example, invoking a Microsoft Word document list item in the My Documents folder both selects the item and opens the document.</span></span>

- <span data-ttu-id="cddb2-131">호출하는 즉시 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리에서 요소가 사라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-131">An element can disappear from the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree immediately upon being invoked.</span></span> <span data-ttu-id="cddb2-132">그 결과, 이벤트 콜백에서 제공하는 요소로부터 정보를 요청하는 작업에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-132">Requesting information from the element provided by the event callback may fail as a result.</span></span> <span data-ttu-id="cddb2-133">이러한 문제의 해결 방법으로 캐시된 정보를 프리페치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-133">Pre-fetching cached information is the recommended workaround.</span></span>

- <span data-ttu-id="cddb2-134">컨트롤은 여러 개의 컨트롤 패턴을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-134">Controls can implement multiple control patterns.</span></span> <span data-ttu-id="cddb2-135">예를 들어 Microsoft Excel 도구 모음의 채우기 색 컨트롤은 <xref:System.Windows.Automation.InvokePattern> 및 컨트롤 패턴을 모두 구현 합니다 <xref:System.Windows.Automation.ExpandCollapsePattern> .</span><span class="sxs-lookup"><span data-stu-id="cddb2-135">For example, the Fill Color control on the Microsoft Excel toolbar implements both the <xref:System.Windows.Automation.InvokePattern> and the <xref:System.Windows.Automation.ExpandCollapsePattern> control patterns.</span></span> <span data-ttu-id="cddb2-136"><xref:System.Windows.Automation.ExpandCollapsePattern> 은 메뉴를 노출하고 <xref:System.Windows.Automation.InvokePattern> 은 선택된 색으로 활성 상태의 선택 항목을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-136"><xref:System.Windows.Automation.ExpandCollapsePattern> exposes the menu and the <xref:System.Windows.Automation.InvokePattern> fills the active selection with the chosen color.</span></span>

<a name="Required_Members_for_the_IValueProvider_Interface"></a>

## <a name="required-members-for-iinvokeprovider"></a><span data-ttu-id="cddb2-137">IInvokeProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="cddb2-137">Required Members for IInvokeProvider</span></span>

<span data-ttu-id="cddb2-138"><xref:System.Windows.Automation.Provider.IInvokeProvider>를 구현하려면 다음과 같은 속성 및 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-138">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IInvokeProvider>.</span></span>

|<span data-ttu-id="cddb2-139">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="cddb2-139">Required members</span></span>|<span data-ttu-id="cddb2-140">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="cddb2-140">Member type</span></span>|<span data-ttu-id="cddb2-141">참고</span><span class="sxs-lookup"><span data-stu-id="cddb2-141">Notes</span></span>|
|----------------------|-----------------|-----------|
|<xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A>|<span data-ttu-id="cddb2-142">method</span><span class="sxs-lookup"><span data-stu-id="cddb2-142">method</span></span>|<span data-ttu-id="cddb2-143"><xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> 는 비동기 호출이며 차단하지 않고 즉시 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-143"><xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> is an asynchronous call and must return immediately without blocking.</span></span><br /><br /> <span data-ttu-id="cddb2-144">이 동작은 호출될 때 직접 또는 간접적으로 모달 대화 상자를 시작하는 컨트롤에 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-144">This behavior is particularly critical for controls that, directly or indirectly, launch a modal dialog when invoked.</span></span> <span data-ttu-id="cddb2-145">이벤트를 발생시킨 모든 UI 자동화 클라이언트는 모달 대화 상자가 닫힐 때까지 차단된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-145">Any UI Automation client that instigated the event will remain blocked until the modal dialog is closed.</span></span>|

<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="cddb2-146">예외</span><span class="sxs-lookup"><span data-stu-id="cddb2-146">Exceptions</span></span>

<span data-ttu-id="cddb2-147">공급자는 다음과 같은 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddb2-147">Providers must throw the following exceptions.</span></span>

|<span data-ttu-id="cddb2-148">예외 유형</span><span class="sxs-lookup"><span data-stu-id="cddb2-148">Exception Type</span></span>|<span data-ttu-id="cddb2-149">조건</span><span class="sxs-lookup"><span data-stu-id="cddb2-149">Condition</span></span>|
|--------------------|---------------|
|<xref:System.Windows.Automation.ElementNotEnabledException>|<span data-ttu-id="cddb2-150">컨트롤이 사용 설정되지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="cddb2-150">If the control is not enabled.</span></span>|

## <a name="see-also"></a><span data-ttu-id="cddb2-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cddb2-151">See also</span></span>

- [<span data-ttu-id="cddb2-152">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="cddb2-152">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="cddb2-153">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="cddb2-153">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="cddb2-154">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="cddb2-154">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="cddb2-155">UI 자동화를 사용하여 컨트롤 호출</span><span class="sxs-lookup"><span data-stu-id="cddb2-155">Invoke a Control Using UI Automation</span></span>](invoke-a-control-using-ui-automation.md)
- [<span data-ttu-id="cddb2-156">UI 자동화 트리 개요</span><span class="sxs-lookup"><span data-stu-id="cddb2-156">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="cddb2-157">UI 자동화에서 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="cddb2-157">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
