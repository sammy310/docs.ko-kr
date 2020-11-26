---
title: UI 자동화 공급자 개요
description: 컨트롤이 UI 자동화 클라이언트 응용 프로그램과 통신할 수 있도록 하는 UI 자동화 공급자의 개요를 참조 하세요. 공급자 유형 및 공급자 개념을 검토 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, providers
- providers, UI Automation
ms.assetid: 859557b8-51e1-4d15-92e8-318d2dcdb2f7
ms.openlocfilehash: 93a80cd35cc23fc0cdfb88620c310397d155b3d9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240370"
---
# <a name="ui-automation-providers-overview"></a><span data-ttu-id="e3b3f-104">UI 자동화 공급자 개요</span><span class="sxs-lookup"><span data-stu-id="e3b3f-104">UI Automation Providers Overview</span></span>

> [!NOTE]
> <span data-ttu-id="e3b3f-105">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e3b3f-106">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="e3b3f-107">UI 자동화 공급자를 통해 컨트롤이 UI 자동화 클라이언트 애플리케이션과 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-107">UI Automation providers enable controls to communicate with UI Automation client applications.</span></span> <span data-ttu-id="e3b3f-108">일반적으로 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 의 각 컨트롤 또는 기타 고유한 요소는 공급자가 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-108">In general, each control or other distinct element in a [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] is represented by a provider.</span></span> <span data-ttu-id="e3b3f-109">공급자는 요소에 대한 정보를 노출하고 클라이언트 애플리케이션이 컨트롤과 상호 작용하도록 하는 컨트롤 패턴을 구현합니다(선택적).</span><span class="sxs-lookup"><span data-stu-id="e3b3f-109">The provider exposes information about the element and optionally implements control patterns that enable the client application to interact with the control.</span></span>  
  
 <span data-ttu-id="e3b3f-110">클라이언트 애플리케이션은 일반적으로 공급자와 직접 작동될 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-110">Client applications do not usually have to work directly with providers.</span></span> <span data-ttu-id="e3b3f-111">Win32, Windows Forms 또는 프레임 워크를 사용 하는 응용 프로그램의 표준 컨트롤 대부분 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 은 시스템에 자동으로 노출 됩니다 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3b3f-111">Most of the standard controls in applications that use the Win32, Windows Forms, or [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] frameworks are automatically exposed to the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] system.</span></span> <span data-ttu-id="e3b3f-112">또한 사용자 지정 컨트롤을 구현하는 애플리케이션은 이러한 컨트롤에 대해 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 공급자를 구현할 수도 있으며, 공급자에 액세스하기 위해 클라이언트 애플리케이션이 수행해야 할 특별한 단계는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-112">Applications that implement custom controls may also implement [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] providers for those controls, and client applications do not have to take any special steps to gain access to them.</span></span>  
  
 <span data-ttu-id="e3b3f-113">이 항목에서는 컨트롤 개발자가 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 특히 Windows Forms 및 Win32 창의 컨트롤에 대 한 공급자를 구현 하는 방법에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-113">This topic provides an overview of how control developers implement [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] providers, particularly for controls in Windows Forms and Win32 windows.</span></span>  
  
<a name="Types_of_Providers"></a>

## <a name="types-of-providers"></a><span data-ttu-id="e3b3f-114">공급자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-114">Types of Providers</span></span>  

 <span data-ttu-id="e3b3f-115">UI 자동화 공급자는 클라이언트 쪽 공급자와 서버 쪽 공급자 두 범주로 나누어집니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-115">UI Automation providers fall into two categories: client-side providers and server-side providers.</span></span>  
  
### <a name="client-side-providers"></a><span data-ttu-id="e3b3f-116">클라이언트 쪽 공급자</span><span class="sxs-lookup"><span data-stu-id="e3b3f-116">Client-side providers</span></span>  

 <span data-ttu-id="e3b3f-117">클라이언트 쪽 공급자는 UI 자동화 클라이언트가 구현하여 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]을 지원하지 않거나 완전하게 지원되지 않는 애플리케이션과 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-117">Client-side providers are implemented by UI Automation clients to communicate with an application that does not support, or does not fully support, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="e3b3f-118">클라이언트 쪽 공급자는 일반적으로 Windows 메시지를 보내고 받아 프로세스 경계를 넘어 서버와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-118">Client-side providers usually communicate with the server across the process boundary by sending and receiving Windows messages.</span></span>  
  
 <span data-ttu-id="e3b3f-119">Win32, Windows Forms 또는 응용 프로그램의 컨트롤에 대 한 UI 자동화 공급자 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 는 운영 체제의 일부로 제공 되므로 클라이언트 응용 프로그램은 자체 공급자를 구현할 필요가 거의 없으며이 개요에서는 더 이상 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-119">Because UI Automation providers for controls in Win32, Windows Forms, or [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] applications are supplied as part of the operating system, client applications seldom have to implement their own providers, and this overview does not cover them further.</span></span>  
  
### <a name="server-side-providers"></a><span data-ttu-id="e3b3f-120">서버 쪽 공급자</span><span class="sxs-lookup"><span data-stu-id="e3b3f-120">Server-side providers</span></span>  

 <span data-ttu-id="e3b3f-121">서버 쪽 공급자는 사용자 지정 컨트롤이 나 Win32, Windows Forms 또는 이외의 UI 프레임 워크를 기반으로 하는 응용 프로그램에 의해 구현 됩니다 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3b3f-121">Server-side providers are implemented by custom controls or by applications that are based on a UI framework other than Win32, Windows Forms, or [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="e3b3f-122">서버 쪽 공급자는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 핵심 시스템에 인터페이스를 노출하여 프로세스 경계를 넘어 클라이언트 애플리케이션과 통신하고, 클라이언트의 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-122">Server-side providers communicate with client applications across the process boundary by exposing interfaces to the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] core system, which in turn serves requests from clients.</span></span>  
  
<a name="AutomationProviderConcepts"></a>

## <a name="ui-automation-provider-concepts"></a><span data-ttu-id="e3b3f-123">UI 자동화 공급자 개념</span><span class="sxs-lookup"><span data-stu-id="e3b3f-123">UI Automation Provider Concepts</span></span>  

 <span data-ttu-id="e3b3f-124">이 섹션에서는 UI 자동화 공급자를 구현하기 위해 이해해야 할 주요 개념 중 일부에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-124">This section provides brief explanations of some of the key concepts you need to understand in order to implement UI Automation providers.</span></span>  
  
### <a name="elements"></a><span data-ttu-id="e3b3f-125">요소</span><span class="sxs-lookup"><span data-stu-id="e3b3f-125">Elements</span></span>  

 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="e3b3f-126">요소는 UI 자동화 클라이언트에 표시되는 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-126">elements are pieces of [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] that are visible to UI Automation clients.</span></span> <span data-ttu-id="e3b3f-127">애플리케이션 창, 창, 단추, 도구 설명, 목록 상자 및 목록 항목을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-127">Examples include application windows, panes, buttons, tooltips, list boxes, and list items.</span></span>  
  
### <a name="navigation"></a><span data-ttu-id="e3b3f-128">탐색</span><span class="sxs-lookup"><span data-stu-id="e3b3f-128">Navigation</span></span>  

 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="e3b3f-129">요소는 클라이언트에 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-129">elements are exposed to clients as a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree.</span></span> [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="e3b3f-130">은 요소를 탐색하여 트리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-130">constructs the tree by navigating from one element to another.</span></span> <span data-ttu-id="e3b3f-131">탐색은 부모, 형제, 자식을 나타낼 수 있는 각 요소의 공급자를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-131">Navigation is enabled by the providers for each element, each of which may point to a parent, siblings, and children.</span></span>  
  
 <span data-ttu-id="e3b3f-132">트리의 클라이언트 뷰에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] [UI 자동화 트리 개요](ui-automation-tree-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-132">For more information on the client view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree, see [UI Automation Tree Overview](ui-automation-tree-overview.md).</span></span>  
  
### <a name="views"></a><span data-ttu-id="e3b3f-133">보기</span><span class="sxs-lookup"><span data-stu-id="e3b3f-133">Views</span></span>  

 <span data-ttu-id="e3b3f-134">다음 표에서와 같이 클라이언트에서는 3개의 주요 뷰로 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-134">A client can see the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree in three principal views, as shown in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e3b3f-135">Raw 뷰</span><span class="sxs-lookup"><span data-stu-id="e3b3f-135">Raw view</span></span>|<span data-ttu-id="e3b3f-136">모든 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-136">Contains all elements.</span></span>|  
|<span data-ttu-id="e3b3f-137">컨트롤 뷰</span><span class="sxs-lookup"><span data-stu-id="e3b3f-137">Control view</span></span>|<span data-ttu-id="e3b3f-138">컨트롤인 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-138">Contains elements that are controls.</span></span>|  
|<span data-ttu-id="e3b3f-139">콘텐츠 뷰</span><span class="sxs-lookup"><span data-stu-id="e3b3f-139">Content view</span></span>|<span data-ttu-id="e3b3f-140">콘텐츠가 있는 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-140">Contains elements that have content.</span></span>|  
  
 <span data-ttu-id="e3b3f-141">트리의 클라이언트 뷰에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] [UI 자동화 트리 개요](ui-automation-tree-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-141">For more information on client views of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree, see [UI Automation Tree Overview](ui-automation-tree-overview.md).</span></span>  
  
 <span data-ttu-id="e3b3f-142">콘텐츠 요소 또는 컨트롤 요소로 요소를 정의하는 것은 공급자 구현에서 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-142">It is the responsibility of the provider implementation to define an element as a content element or a control element.</span></span> <span data-ttu-id="e3b3f-143">컨트롤 요소가 콘텐츠 요소일 수도 있고 그렇지 않을 수도 있지만, 모든 콘텐츠 요소는 컨트롤 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-143">Control elements may or may not also be content elements, but all content elements are control elements.</span></span>  
  
### <a name="frameworks"></a><span data-ttu-id="e3b3f-144">프레임워크</span><span class="sxs-lookup"><span data-stu-id="e3b3f-144">Frameworks</span></span>  

 <span data-ttu-id="e3b3f-145">프레임워크는 화면 영역에서 하위 컨트롤, 적중 테스트, 렌더링을 관리하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-145">A framework is a component that manages child controls, hit-testing, and rendering in an area of the screen.</span></span> <span data-ttu-id="e3b3f-146">예를 들어, HWND 라고도 하는 Win32 창은 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 메뉴 모음, 상태 표시줄 및 단추와 같은 여러 요소를 포함 하는 프레임 워크 역할을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-146">For example, a Win32 window, often referred to as an HWND, can serve as a framework that contains multiple [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements such as a menu bar, a status bar, and buttons.</span></span>  
  
 <span data-ttu-id="e3b3f-147">목록 상자 및 트리 뷰와 같은 Win32 컨테이너 컨트롤은 자식 항목을 렌더링 하 고 적중 테스트를 수행 하는 고유한 코드를 포함 하기 때문에 프레임 워크로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-147">Win32 container controls such as list boxes and tree views are considered to be frameworks, because they contain their own code for rendering child items and performing hit-testing on them.</span></span> <span data-ttu-id="e3b3f-148">한편, [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 목록 상자는 렌더링 및 적중 테스트가 포함된 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 창에서 처리되기 때문에 프레임워크가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-148">By contrast, a [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] list box is not a framework, because the rendering and hit-testing is being handled by the containing [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] window.</span></span>  
  
 <span data-ttu-id="e3b3f-149">애플리케이션에서 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 는 다양한 프레임워크로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-149">The [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] in an application can be made up of different frameworks.</span></span> <span data-ttu-id="e3b3f-150">예를 들어, HWND 응용 프로그램 창에는 DHTML의 콤보 상자와 같은 구성 요소를 포함 하는 DHTML (동적 HTML)이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-150">For example, an HWND application window might contain Dynamic HTML (DHTML) which in turn contains a component such as a combo box in an HWND.</span></span>  
  
### <a name="fragments"></a><span data-ttu-id="e3b3f-151">조각</span><span class="sxs-lookup"><span data-stu-id="e3b3f-151">Fragments</span></span>  

 <span data-ttu-id="e3b3f-152">조각은 특정 프레임워크에서 요소의 전체 하위 트리입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-152">A fragment is a complete subtree of elements from a particular framework.</span></span> <span data-ttu-id="e3b3f-153">하위 트리의 루트 노드에 있는 요소를 조각 루트라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-153">The element at the root node of the subtree is called a fragment root.</span></span> <span data-ttu-id="e3b3f-154">조각 루트에는 부모는 없지만 다른 프레임 워크 내에서 호스트 됩니다. 일반적으로 Win32 창 (HWND)입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-154">A fragment root does not have a parent, but is hosted within some other framework, usually a Win32 window (HWND).</span></span>  
  
### <a name="hosts"></a><span data-ttu-id="e3b3f-155">호스트</span><span class="sxs-lookup"><span data-stu-id="e3b3f-155">Hosts</span></span>  

 <span data-ttu-id="e3b3f-156">모든 조각의 루트 노드는 요소, 일반적으로 Win32 창 (HWND)에서 호스팅되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-156">The root node of every fragment must be hosted in an element, usually a Win32 window (HWND).</span></span> <span data-ttu-id="e3b3f-157">다른 요소에서 호스트되지 않는 데스크톱은 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-157">The exception is the desktop, which is not hosted in any other element.</span></span> <span data-ttu-id="e3b3f-158">사용자 지정의 호스트는 애플리케이션 창 또는 최상위 컨트롤 그룹이 있을 수 있는 다른 창이 아닌 컨트롤 자체의 HWND입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-158">The host of a custom control is the HWND of the control itself, not the application window or any other window that might contain groups of top-level controls.</span></span>  
  
 <span data-ttu-id="e3b3f-159">조각의 호스트는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 서비스를 제공하는 중요한 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-159">The host of a fragment plays an important role in providing [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] services.</span></span> <span data-ttu-id="e3b3f-160">이 호스트를 통해 조각 루트를 탐색할 수 있으며, 몇 가지 기본 속성을 제공하므로 사용자 지정 공급자가 속성을 구현할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3f-160">It enables navigation to the fragment root, and supplies some default properties so that the custom provider does not have to implement them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3b3f-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3b3f-161">See also</span></span>

- [<span data-ttu-id="e3b3f-162">서버 쪽 UI 자동화 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="e3b3f-162">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)
