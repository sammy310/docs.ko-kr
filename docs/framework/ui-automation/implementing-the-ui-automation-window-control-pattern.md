---
title: UI 자동화 Window 컨트롤 패턴 구현
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Window
- UI Automation, Window control pattern
- Window control pattern
ms.assetid: a28cb286-296e-4a62-b4cb-55ad636ebccc
ms.openlocfilehash: 4f11f82b628ac020cbda70d65adf7813291c60a6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645762"
---
# <a name="implementing-the-ui-automation-window-control-pattern"></a><span data-ttu-id="f921e-102">UI 자동화 Window 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="f921e-102">Implementing the UI Automation Window Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="f921e-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f921e-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f921e-104">에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 참조 하세요 [Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)합니다.</span><span class="sxs-lookup"><span data-stu-id="f921e-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="f921e-105">이 항목에서는 <xref:System.Windows.Automation.Provider.IWindowProvider>속성, 메서드 및 이벤트에 대한 정보를 포함하여 <xref:System.Windows.Automation.WindowPattern> 를 구현하기 위한 지침 및 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f921e-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IWindowProvider>, including information about <xref:System.Windows.Automation.WindowPattern> properties, methods, and events.</span></span> <span data-ttu-id="f921e-106">추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f921e-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="f921e-107"><xref:System.Windows.Automation.WindowPattern> 컨트롤 패턴은 기존의 [!INCLUDE[TLA#tla_gui](../../../includes/tlasharptla-gui-md.md)]내에서 창을 기반으로 하는 기본적인 기능을 제공하는 컨트롤을 제공하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f921e-107">The <xref:System.Windows.Automation.WindowPattern> control pattern is used to support controls that provide fundamental window-based functionality within a traditional [!INCLUDE[TLA#tla_gui](../../../includes/tlasharptla-gui-md.md)].</span></span> <span data-ttu-id="f921e-108">이 컨트롤 패턴을 구현해야 하는 컨트롤의 예로는 최상위 애플리케이션 창, [!INCLUDE[TLA#tla_mdi](../../../includes/tlasharptla-mdi-md.md)] 자식 창, 컨트롤 크기 조정 가능한 분할 창 컨트롤, 모달 대화 상자 및 풍선 도움말 창이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f921e-108">Examples of controls that must implement this control pattern include top-level application windows, [!INCLUDE[TLA#tla_mdi](../../../includes/tlasharptla-mdi-md.md)] child windows, resizable split pane controls, modal dialogs and balloon help windows.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="f921e-109">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="f921e-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="f921e-110">Window 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="f921e-110">When implementing the Window control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="f921e-111">UI 자동화를 사용하여 창의 크기와 화면 위치를 수정하는 기능을 지원하려면 컨트롤이 <xref:System.Windows.Automation.Provider.ITransformProvider> 외에 <xref:System.Windows.Automation.Provider.IWindowProvider>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f921e-111">To support the ability to modify both window size and screen position using UI Automation, a control must implement <xref:System.Windows.Automation.Provider.ITransformProvider> in addition to <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="f921e-112">컨트롤을 이동, 크기 조정, 최대화, 최소화 또는 닫을 수 있도록 하는 제목 표시줄 및 제목 표시줄 요소가 포함된 컨트롤은 일반적으로 <xref:System.Windows.Automation.Provider.IWindowProvider>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f921e-112">Controls that contain title bars and title bar elements that enable the control to be moved, resized, maximized, minimized, or closed are typically required to implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="f921e-113">도구 설명 팝업 및 콤보 상자 또는 메뉴 드롭다운 등과 같은 컨트롤을 일반적으로 <xref:System.Windows.Automation.Provider.IWindowProvider>를 구현하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f921e-113">Controls such as tooltip pop-ups and combo box or menu drop-downs do not typically implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="f921e-114">창과 같이 닫기 단추를 제공하는 풍선 도움말 창은 기본적인 도구 설명 팝업과는 구별됩니다.</span><span class="sxs-lookup"><span data-stu-id="f921e-114">Balloon help windows are differentiated from basic tooltip pop-ups by the provision of a window-like Close button.</span></span>  
  
- <span data-ttu-id="f921e-115">전체 화면 모드는 애플리케이션에서 기능별로 다르며 일반적인 창 동작이 아니므로 IWindowProvider에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f921e-115">Full-screen mode is not supported by IWindowProvider as it is feature-specific to an application and is not typical window behavior.</span></span>  
  
<a name="Required_Members_for_IWindowProvider"></a>   
## <a name="required-members-for-iwindowprovider"></a><span data-ttu-id="f921e-116">IWindowProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="f921e-116">Required Members for IWindowProvider</span></span>  
 <span data-ttu-id="f921e-117">IWindowProvider 인터페이스에는 다음과 같은 속성, 메서드 및 이벤트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f921e-117">The following properties, methods, and events are required for the IWindowProvider interface.</span></span>  
  
|<span data-ttu-id="f921e-118">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="f921e-118">Required member</span></span>|<span data-ttu-id="f921e-119">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="f921e-119">Member type</span></span>|<span data-ttu-id="f921e-120">노트</span><span class="sxs-lookup"><span data-stu-id="f921e-120">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.InteractionState%2A>|<span data-ttu-id="f921e-121">속성</span><span class="sxs-lookup"><span data-stu-id="f921e-121">Property</span></span>|<span data-ttu-id="f921e-122">없음</span><span class="sxs-lookup"><span data-stu-id="f921e-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsModal%2A>|<span data-ttu-id="f921e-123">속성</span><span class="sxs-lookup"><span data-stu-id="f921e-123">Property</span></span>|<span data-ttu-id="f921e-124">없음</span><span class="sxs-lookup"><span data-stu-id="f921e-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsTopmost%2A>|<span data-ttu-id="f921e-125">속성</span><span class="sxs-lookup"><span data-stu-id="f921e-125">Property</span></span>|<span data-ttu-id="f921e-126">없음</span><span class="sxs-lookup"><span data-stu-id="f921e-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Maximizable%2A>|<span data-ttu-id="f921e-127">속성</span><span class="sxs-lookup"><span data-stu-id="f921e-127">Property</span></span>|<span data-ttu-id="f921e-128">없음</span><span class="sxs-lookup"><span data-stu-id="f921e-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Minimizable%2A>|<span data-ttu-id="f921e-129">속성</span><span class="sxs-lookup"><span data-stu-id="f921e-129">Property</span></span>|<span data-ttu-id="f921e-130">없음</span><span class="sxs-lookup"><span data-stu-id="f921e-130">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.VisualState%2A>|<span data-ttu-id="f921e-131">속성</span><span class="sxs-lookup"><span data-stu-id="f921e-131">Property</span></span>|<span data-ttu-id="f921e-132">없음</span><span class="sxs-lookup"><span data-stu-id="f921e-132">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Close%2A>|<span data-ttu-id="f921e-133">메서드</span><span class="sxs-lookup"><span data-stu-id="f921e-133">Method</span></span>|<span data-ttu-id="f921e-134">없음</span><span class="sxs-lookup"><span data-stu-id="f921e-134">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A>|<span data-ttu-id="f921e-135">메서드</span><span class="sxs-lookup"><span data-stu-id="f921e-135">Method</span></span>|<span data-ttu-id="f921e-136">없음</span><span class="sxs-lookup"><span data-stu-id="f921e-136">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A>|<span data-ttu-id="f921e-137">메서드</span><span class="sxs-lookup"><span data-stu-id="f921e-137">Method</span></span>|<span data-ttu-id="f921e-138">없음</span><span class="sxs-lookup"><span data-stu-id="f921e-138">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|<span data-ttu-id="f921e-139">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="f921e-139">Event</span></span>|<span data-ttu-id="f921e-140">없음</span><span class="sxs-lookup"><span data-stu-id="f921e-140">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|<span data-ttu-id="f921e-141">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="f921e-141">Event</span></span>|<span data-ttu-id="f921e-142">없음</span><span class="sxs-lookup"><span data-stu-id="f921e-142">None</span></span>|  
|<xref:System.Windows.Automation.WindowInteractionState>|<span data-ttu-id="f921e-143">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="f921e-143">Event</span></span>|<span data-ttu-id="f921e-144"> <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span><span class="sxs-lookup"><span data-stu-id="f921e-144">Is not guaranteed to be <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span></span>|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="f921e-145">예외</span><span class="sxs-lookup"><span data-stu-id="f921e-145">Exceptions</span></span>  
 <span data-ttu-id="f921e-146">공급자는 다음과 같은 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f921e-146">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="f921e-147">예외 형식</span><span class="sxs-lookup"><span data-stu-id="f921e-147">Exception type</span></span>|<span data-ttu-id="f921e-148">조건</span><span class="sxs-lookup"><span data-stu-id="f921e-148">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A><br /><br /> <span data-ttu-id="f921e-149">-컨트롤을 요청 된 동작을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f921e-149">-   When a control does not support a requested behavior.</span></span>|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A><br /><br /> <span data-ttu-id="f921e-150">-매개 변수가 유효한 숫자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f921e-150">-   When the parameter is not a valid number.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f921e-151">참고자료</span><span class="sxs-lookup"><span data-stu-id="f921e-151">See also</span></span>

- [<span data-ttu-id="f921e-152">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="f921e-152">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="f921e-153">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="f921e-153">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="f921e-154">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="f921e-154">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="f921e-155">UI 자동화 트리 개요</span><span class="sxs-lookup"><span data-stu-id="f921e-155">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [<span data-ttu-id="f921e-156">UI 자동화의 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="f921e-156">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
