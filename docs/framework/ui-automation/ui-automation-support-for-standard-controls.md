---
title: 표준 컨트롤에 대한 UI 자동화 지원
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 5dbd547378faf885f5d0349ff77d124b0b860591
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57677632"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="ca910-102">표준 컨트롤에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="ca910-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="ca910-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca910-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ca910-104">에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 참조 하세요 [Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca910-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="ca910-105">이 항목에는 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] , [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]및 [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]프레임워크용으로 개발된 애플리케이션에서 표준 컨트롤에 대한 [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] 지원 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca910-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="ca910-106">WPF(Windows Presentation Foundation) 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ca910-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="ca910-107">사용자 상호 작용 지원 또는 정보를 제공하는 모든 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 요소에는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 전체 기본 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca910-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="ca910-108">패널 등과 같은 기타 요소는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca910-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="ca910-109">Win32 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ca910-109">Win32 Controls</span></span>  
 <span data-ttu-id="ca910-110">대부분의 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 컨트롤은 UIAutomationClientsideProviders.dll의 클라이언트쪽 공급자를 통해 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca910-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="ca910-111">이 어셈블리는 UI 자동화 클라이언트 애플리케이션과 함께 사용할 수 있도록 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca910-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="ca910-112">전체 지원은 ComCtrl32.dll 버전 6의 컨트롤에만 제공됩니다( [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] 이상에서 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="ca910-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="ca910-113">다음과 같은 컨트롤이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca910-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="ca910-114">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="ca910-114">Class name</span></span>|<span data-ttu-id="ca910-115">컨트롤 종류</span><span class="sxs-lookup"><span data-stu-id="ca910-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="ca910-116">단추</span><span class="sxs-lookup"><span data-stu-id="ca910-116">Button</span></span>|<span data-ttu-id="ca910-117">단추</span><span class="sxs-lookup"><span data-stu-id="ca910-117">Button</span></span>|  
|<span data-ttu-id="ca910-118">단추</span><span class="sxs-lookup"><span data-stu-id="ca910-118">Button</span></span>|<span data-ttu-id="ca910-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="ca910-119">RadioButton</span></span>|  
|<span data-ttu-id="ca910-120">단추</span><span class="sxs-lookup"><span data-stu-id="ca910-120">Button</span></span>|<span data-ttu-id="ca910-121">그룹화</span><span class="sxs-lookup"><span data-stu-id="ca910-121">Group</span></span>|  
|<span data-ttu-id="ca910-122">단추</span><span class="sxs-lookup"><span data-stu-id="ca910-122">Button</span></span>|<span data-ttu-id="ca910-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="ca910-123">CheckBox</span></span>|  
|<span data-ttu-id="ca910-124">단추</span><span class="sxs-lookup"><span data-stu-id="ca910-124">Button</span></span>|<span data-ttu-id="ca910-125">하이퍼링크</span><span class="sxs-lookup"><span data-stu-id="ca910-125">Hyperlink</span></span>|  
|<span data-ttu-id="ca910-126">단추</span><span class="sxs-lookup"><span data-stu-id="ca910-126">Button</span></span>|<span data-ttu-id="ca910-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="ca910-127">SplitButton</span></span>|  
|<span data-ttu-id="ca910-128">단추</span><span class="sxs-lookup"><span data-stu-id="ca910-128">Button</span></span>|<span data-ttu-id="ca910-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="ca910-129">CheckBox</span></span>|  
|<span data-ttu-id="ca910-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="ca910-130">ComboBoxEx32</span></span>|<span data-ttu-id="ca910-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="ca910-131">ComboBox</span></span>|  
|<span data-ttu-id="ca910-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="ca910-132">ComboBox</span></span>|<span data-ttu-id="ca910-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="ca910-133">ComboBox</span></span>|  
|<span data-ttu-id="ca910-134">편집</span><span class="sxs-lookup"><span data-stu-id="ca910-134">Edit</span></span>|<span data-ttu-id="ca910-135">문서</span><span class="sxs-lookup"><span data-stu-id="ca910-135">Document</span></span>|  
|<span data-ttu-id="ca910-136">편집</span><span class="sxs-lookup"><span data-stu-id="ca910-136">Edit</span></span>|<span data-ttu-id="ca910-137">편집</span><span class="sxs-lookup"><span data-stu-id="ca910-137">Edit</span></span>|  
|<span data-ttu-id="ca910-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="ca910-138">SysLink</span></span>|<span data-ttu-id="ca910-139">하이퍼링크</span><span class="sxs-lookup"><span data-stu-id="ca910-139">Hyperlink</span></span>|  
|<span data-ttu-id="ca910-140">정적</span><span class="sxs-lookup"><span data-stu-id="ca910-140">Static</span></span>|<span data-ttu-id="ca910-141">텍스트</span><span class="sxs-lookup"><span data-stu-id="ca910-141">Text</span></span>|  
|<span data-ttu-id="ca910-142">정적</span><span class="sxs-lookup"><span data-stu-id="ca910-142">Static</span></span>|<span data-ttu-id="ca910-143">이미지</span><span class="sxs-lookup"><span data-stu-id="ca910-143">Image</span></span>|  
|<span data-ttu-id="ca910-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="ca910-144">SysIPAddress32</span></span>|<span data-ttu-id="ca910-145">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ca910-145">Custom</span></span>|  
|<span data-ttu-id="ca910-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="ca910-146">SysHeader32</span></span>|<span data-ttu-id="ca910-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="ca910-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="ca910-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="ca910-148">SysListView32</span></span>|<span data-ttu-id="ca910-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="ca910-149">DataGrid</span></span>|  
|<span data-ttu-id="ca910-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="ca910-150">SysListView32</span></span>|<span data-ttu-id="ca910-151">목록</span><span class="sxs-lookup"><span data-stu-id="ca910-151">List</span></span>|  
|<span data-ttu-id="ca910-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="ca910-152">ListBox</span></span>|<span data-ttu-id="ca910-153">목록</span><span class="sxs-lookup"><span data-stu-id="ca910-153">List</span></span>|  
|<span data-ttu-id="ca910-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="ca910-154">ListBox</span></span>|<span data-ttu-id="ca910-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="ca910-155">ListItem</span></span>|  
|<span data-ttu-id="ca910-156">#32768</span><span class="sxs-lookup"><span data-stu-id="ca910-156">#32768</span></span>|<span data-ttu-id="ca910-157">메뉴</span><span class="sxs-lookup"><span data-stu-id="ca910-157">Menu</span></span>|  
|<span data-ttu-id="ca910-158">#32768</span><span class="sxs-lookup"><span data-stu-id="ca910-158">#32768</span></span>|<span data-ttu-id="ca910-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="ca910-159">MenuItem</span></span>|  
|<span data-ttu-id="ca910-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="ca910-160">msctls_progress32</span></span>|<span data-ttu-id="ca910-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="ca910-161">ProgressBar</span></span>|  
|<span data-ttu-id="ca910-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="ca910-162">RichEdit</span></span>|<span data-ttu-id="ca910-163">문서.</span><span class="sxs-lookup"><span data-stu-id="ca910-163">Document.</span></span> <span data-ttu-id="ca910-164">메모를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca910-164">See note.</span></span>|  
|<span data-ttu-id="ca910-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="ca910-165">RichEdit20A</span></span>|<span data-ttu-id="ca910-166">문서</span><span class="sxs-lookup"><span data-stu-id="ca910-166">Document</span></span>|  
|<span data-ttu-id="ca910-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="ca910-167">RichEdit20W</span></span>|<span data-ttu-id="ca910-168">문서</span><span class="sxs-lookup"><span data-stu-id="ca910-168">Document</span></span>|  
|<span data-ttu-id="ca910-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="ca910-169">RichEdit50W</span></span>|<span data-ttu-id="ca910-170">문서</span><span class="sxs-lookup"><span data-stu-id="ca910-170">Document</span></span>|  
|<span data-ttu-id="ca910-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="ca910-171">ScrollBar</span></span>|<span data-ttu-id="ca910-172">슬라이더</span><span class="sxs-lookup"><span data-stu-id="ca910-172">Slider</span></span>|  
|<span data-ttu-id="ca910-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="ca910-173">msctls_trackbar32</span></span>|<span data-ttu-id="ca910-174">슬라이더</span><span class="sxs-lookup"><span data-stu-id="ca910-174">Slider</span></span>|  
|<span data-ttu-id="ca910-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="ca910-175">msctls_updown32</span></span>|<span data-ttu-id="ca910-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="ca910-176">Spinner</span></span>|  
|<span data-ttu-id="ca910-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="ca910-177">msctls_statusbar32</span></span>|<span data-ttu-id="ca910-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="ca910-178">StatusBar</span></span>|  
|<span data-ttu-id="ca910-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="ca910-179">SysTabControl32</span></span>|<span data-ttu-id="ca910-180">탭</span><span class="sxs-lookup"><span data-stu-id="ca910-180">Tab</span></span>|  
|<span data-ttu-id="ca910-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="ca910-181">SysTabControl32</span></span>|<span data-ttu-id="ca910-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="ca910-182">TabItem</span></span>|  
|<span data-ttu-id="ca910-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ca910-183">ToolbarWindow32</span></span>|<span data-ttu-id="ca910-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="ca910-184">ToolBar</span></span>|  
|<span data-ttu-id="ca910-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ca910-185">ToolbarWindow32</span></span>|<span data-ttu-id="ca910-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="ca910-186">MenuItem</span></span>|  
|<span data-ttu-id="ca910-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ca910-187">ToolbarWindow32</span></span>|<span data-ttu-id="ca910-188">단추</span><span class="sxs-lookup"><span data-stu-id="ca910-188">Button</span></span>|  
|<span data-ttu-id="ca910-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ca910-189">ToolbarWindow32</span></span>|<span data-ttu-id="ca910-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="ca910-190">CheckBox</span></span>|  
|<span data-ttu-id="ca910-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ca910-191">ToolbarWindow32</span></span>|<span data-ttu-id="ca910-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="ca910-192">RadioButton</span></span>|  
|<span data-ttu-id="ca910-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ca910-193">ToolbarWindow32</span></span>|<span data-ttu-id="ca910-194">구분 기호</span><span class="sxs-lookup"><span data-stu-id="ca910-194">Separator</span></span>|  
|<span data-ttu-id="ca910-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="ca910-195">tooltips_class32</span></span>|<span data-ttu-id="ca910-196">도구 설명</span><span class="sxs-lookup"><span data-stu-id="ca910-196">ToolTip</span></span>|  
|<span data-ttu-id="ca910-197">#32774</span><span class="sxs-lookup"><span data-stu-id="ca910-197">#32774</span></span>|<span data-ttu-id="ca910-198">도구 설명</span><span class="sxs-lookup"><span data-stu-id="ca910-198">ToolTip</span></span>|  
|<span data-ttu-id="ca910-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="ca910-199">ReBarWindow32</span></span>|<span data-ttu-id="ca910-200">Toolbar</span><span class="sxs-lookup"><span data-stu-id="ca910-200">Toolbar</span></span>|  
|<span data-ttu-id="ca910-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="ca910-201">SysTreeView32</span></span>|<span data-ttu-id="ca910-202">Tree</span><span class="sxs-lookup"><span data-stu-id="ca910-202">Tree</span></span>|  
|<span data-ttu-id="ca910-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="ca910-203">SysTreeView32</span></span>|<span data-ttu-id="ca910-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="ca910-204">TreeItem</span></span>|  
  
 <span data-ttu-id="ca910-205">**참고** RichEdit 컨트롤은 [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] 와 함께 제공된 버전에서만 지원됩니다(RichEd20.dll 버전 3.1 이상 및 MsftEdit.dll 버전 4.1 이상).</span><span class="sxs-lookup"><span data-stu-id="ca910-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="ca910-206">다음 컨트롤은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca910-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="ca910-207">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="ca910-207">Class name</span></span>|<span data-ttu-id="ca910-208">컨트롤 종류</span><span class="sxs-lookup"><span data-stu-id="ca910-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="ca910-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="ca910-209">SysAnimate32</span></span>|<span data-ttu-id="ca910-210">이미지</span><span class="sxs-lookup"><span data-stu-id="ca910-210">Image</span></span>|  
|<span data-ttu-id="ca910-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="ca910-211">SysPager</span></span>|<span data-ttu-id="ca910-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="ca910-212">Spinner</span></span>|  
|<span data-ttu-id="ca910-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="ca910-213">SysDateTimePick32</span></span>|<span data-ttu-id="ca910-214">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ca910-214">Custom</span></span>|  
|<span data-ttu-id="ca910-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="ca910-215">SysMonthCal32</span></span>|<span data-ttu-id="ca910-216">일정</span><span class="sxs-lookup"><span data-stu-id="ca910-216">Calendar</span></span>|  
|<span data-ttu-id="ca910-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="ca910-217">MS_WINNOTE</span></span>|<span data-ttu-id="ca910-218">도구 설명</span><span class="sxs-lookup"><span data-stu-id="ca910-218">Tooltip</span></span>|  
|<span data-ttu-id="ca910-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="ca910-219">VBBubble</span></span>|<span data-ttu-id="ca910-220">도구 설명</span><span class="sxs-lookup"><span data-stu-id="ca910-220">Tooltip</span></span>|  
|<span data-ttu-id="ca910-221">스크롤 막대(독립 실행형 컨트롤로 사용되는 경우)</span><span class="sxs-lookup"><span data-stu-id="ca910-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="ca910-222">슬라이더</span><span class="sxs-lookup"><span data-stu-id="ca910-222">Slider</span></span>|  
|<span data-ttu-id="ca910-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="ca910-223">SuperGrid</span></span>|<span data-ttu-id="ca910-224">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ca910-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="ca910-225">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ca910-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="ca910-226">Windows Forms 컨트롤에 노출 되어 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] UIAutomationClientsideProviders.dll의 클라이언트쪽 공급자를 통해.</span><span class="sxs-lookup"><span data-stu-id="ca910-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="ca910-227">이 어셈블리는 UI 자동화 클라이언트 애플리케이션과 함께 사용할 수 있도록 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca910-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="ca910-228">Windows Forms 컨트롤에 대 한 래퍼를 관리 하는 일반적으로 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 공용 컨트롤에서 지 원하는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="ca910-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="ca910-229">다음과 같은 컨트롤이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca910-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="ca910-230">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="ca910-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="ca910-231">단추</span><span class="sxs-lookup"><span data-stu-id="ca910-231">Button</span></span>|  
|<span data-ttu-id="ca910-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="ca910-232">CheckBox</span></span>|  
|<span data-ttu-id="ca910-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="ca910-233">CheckedListBox</span></span>|  
|<span data-ttu-id="ca910-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="ca910-234">ColorDialog</span></span>|  
|<span data-ttu-id="ca910-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="ca910-235">ComboBox</span></span>|  
|<span data-ttu-id="ca910-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="ca910-236">FolderBrowser</span></span>|  
|<span data-ttu-id="ca910-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="ca910-237">FontDialog</span></span>|  
|<span data-ttu-id="ca910-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="ca910-238">GroupBox</span></span>|  
|<span data-ttu-id="ca910-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="ca910-239">HscrollBar</span></span>|  
|<span data-ttu-id="ca910-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="ca910-240">ImageList</span></span>|  
|<span data-ttu-id="ca910-241">레이블</span><span class="sxs-lookup"><span data-stu-id="ca910-241">Label</span></span>|  
|<span data-ttu-id="ca910-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="ca910-242">ListBox</span></span>|  
|<span data-ttu-id="ca910-243">ListView</span><span class="sxs-lookup"><span data-stu-id="ca910-243">ListView</span></span>|  
|<span data-ttu-id="ca910-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="ca910-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="ca910-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="ca910-245">MonthCalendar</span></span>|  
|<span data-ttu-id="ca910-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="ca910-246">NotifyIcon</span></span>|  
|<span data-ttu-id="ca910-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="ca910-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="ca910-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="ca910-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="ca910-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="ca910-249">PrintDialog</span></span>|  
|<span data-ttu-id="ca910-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="ca910-250">ProgressBar</span></span>|  
|<span data-ttu-id="ca910-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="ca910-251">RadioButton</span></span>|  
|<span data-ttu-id="ca910-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="ca910-252">RichTextBox</span></span>|  
|<span data-ttu-id="ca910-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="ca910-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="ca910-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="ca910-254">ScrollableControl</span></span>|  
|<span data-ttu-id="ca910-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="ca910-255">SoundPlayer</span></span>|  
|<span data-ttu-id="ca910-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="ca910-256">StatusBar</span></span>|  
|<span data-ttu-id="ca910-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="ca910-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="ca910-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="ca910-258">TextBox</span></span>|  
|<span data-ttu-id="ca910-259">Timer</span><span class="sxs-lookup"><span data-stu-id="ca910-259">Timer</span></span>|  
|<span data-ttu-id="ca910-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="ca910-260">Toolbar</span></span>|  
|<span data-ttu-id="ca910-261">도구 설명</span><span class="sxs-lookup"><span data-stu-id="ca910-261">ToolTip</span></span>|  
|<span data-ttu-id="ca910-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="ca910-262">TrackBar</span></span>|  
|<span data-ttu-id="ca910-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="ca910-263">TreeView</span></span>|  
|<span data-ttu-id="ca910-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="ca910-264">VscrollBar</span></span>|  
|<span data-ttu-id="ca910-265">웹 브라우저</span><span class="sxs-lookup"><span data-stu-id="ca910-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="ca910-266">다음 컨트롤은 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 에 대한 지원을 통해서만 [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)]에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca910-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="ca910-267">일부 기능은 사용하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca910-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="ca910-268">컨트롤 이름</span><span class="sxs-lookup"><span data-stu-id="ca910-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="ca910-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="ca910-269">BindingSource</span></span>|  
|<span data-ttu-id="ca910-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="ca910-270">DataGrid</span></span>|  
|<span data-ttu-id="ca910-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="ca910-271">DataGridView</span></span>|  
|<span data-ttu-id="ca910-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="ca910-272">DataNavigator</span></span>|  
|<span data-ttu-id="ca910-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="ca910-273">DomainUpDown</span></span>|  
|<span data-ttu-id="ca910-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="ca910-274">ErrorProvider</span></span>|  
|<span data-ttu-id="ca910-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ca910-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="ca910-276">Form</span><span class="sxs-lookup"><span data-stu-id="ca910-276">Form</span></span>|  
|<span data-ttu-id="ca910-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="ca910-277">LinkLabel</span></span>|  
|<span data-ttu-id="ca910-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="ca910-278">HelpProvider</span></span>|  
|<span data-ttu-id="ca910-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="ca910-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="ca910-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="ca910-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="ca910-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="ca910-281">NumericUpDown</span></span>|  
|<span data-ttu-id="ca910-282">패널</span><span class="sxs-lookup"><span data-stu-id="ca910-282">Panel</span></span>|  
|<span data-ttu-id="ca910-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="ca910-283">PictureBox</span></span>|  
|<span data-ttu-id="ca910-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="ca910-284">PrintDocument</span></span>|  
|<span data-ttu-id="ca910-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="ca910-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="ca910-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="ca910-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="ca910-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="ca910-287">PropertyGrid</span></span>|  
|<span data-ttu-id="ca910-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="ca910-288">UserControl</span></span>|  
|<span data-ttu-id="ca910-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ca910-289">ToolStrip</span></span>|  
|<span data-ttu-id="ca910-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ca910-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="ca910-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="ca910-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="ca910-292">분할자</span><span class="sxs-lookup"><span data-stu-id="ca910-292">Splitter</span></span>|  
|<span data-ttu-id="ca910-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="ca910-293">RaftingContainer</span></span>|  
|<span data-ttu-id="ca910-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="ca910-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca910-295">참고자료</span><span class="sxs-lookup"><span data-stu-id="ca910-295">See also</span></span>
- [<span data-ttu-id="ca910-296">UI Automation Control Types</span><span class="sxs-lookup"><span data-stu-id="ca910-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
