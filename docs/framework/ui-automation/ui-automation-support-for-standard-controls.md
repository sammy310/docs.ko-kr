---
title: 표준 컨트롤에 대한 UI 자동화 지원
description: Windows Presentation Foundation (WPF), Win32 및 Windows Forms 용으로 개발 된 응용 프로그램에서 표준 컨트롤에 대 한 UI 자동화 지원에 대 한 정보를 가져옵니다.
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 17916a6978008439e91caae00d8b6f26045f9018
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166119"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="fd566-103">표준 컨트롤에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="fd566-103">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="fd566-104">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fd566-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="fd566-105">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd566-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="fd566-106">이 항목에 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 는 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] , Win32 및 Windows Forms 프레임 워크 용으로 개발 된 응용 프로그램의 표준 컨트롤에 대 한 지원 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd566-106">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="fd566-107">WPF(Windows Presentation Foundation) 컨트롤</span><span class="sxs-lookup"><span data-stu-id="fd566-107">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="fd566-108">사용자 상호 작용 지원 또는 정보를 제공하는 모든 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 요소에는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 전체 기본 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd566-108">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="fd566-109">패널 등과 같은 기타 요소는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd566-109">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a><span data-ttu-id="fd566-110">Win32 컨트롤</span><span class="sxs-lookup"><span data-stu-id="fd566-110">Win32 Controls</span></span>  
 <span data-ttu-id="fd566-111">대부분의 Win32 컨트롤은 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] UIAutomationClientsideProviders.dll의 클라이언트 쪽 공급자를 통해에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd566-111">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="fd566-112">이 어셈블리는 UI 자동화 클라이언트 애플리케이션과 함께 사용할 수 있도록 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd566-112">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="fd566-113">*ComCtrl32.dll*버전 6의 컨트롤에 대해서만 전체 지원이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd566-113">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="fd566-114">다음과 같은 컨트롤이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd566-114">The following controls are supported.</span></span>  
  
|<span data-ttu-id="fd566-115">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="fd566-115">Class name</span></span>|<span data-ttu-id="fd566-116">컨트롤 종류</span><span class="sxs-lookup"><span data-stu-id="fd566-116">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="fd566-117">단추</span><span class="sxs-lookup"><span data-stu-id="fd566-117">Button</span></span>|<span data-ttu-id="fd566-118">단추</span><span class="sxs-lookup"><span data-stu-id="fd566-118">Button</span></span>|  
|<span data-ttu-id="fd566-119">단추</span><span class="sxs-lookup"><span data-stu-id="fd566-119">Button</span></span>|<span data-ttu-id="fd566-120">RadioButton</span><span class="sxs-lookup"><span data-stu-id="fd566-120">RadioButton</span></span>|  
|<span data-ttu-id="fd566-121">단추</span><span class="sxs-lookup"><span data-stu-id="fd566-121">Button</span></span>|<span data-ttu-id="fd566-122">그룹화</span><span class="sxs-lookup"><span data-stu-id="fd566-122">Group</span></span>|  
|<span data-ttu-id="fd566-123">단추</span><span class="sxs-lookup"><span data-stu-id="fd566-123">Button</span></span>|<span data-ttu-id="fd566-124">CheckBox</span><span class="sxs-lookup"><span data-stu-id="fd566-124">CheckBox</span></span>|  
|<span data-ttu-id="fd566-125">단추</span><span class="sxs-lookup"><span data-stu-id="fd566-125">Button</span></span>|<span data-ttu-id="fd566-126">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="fd566-126">Hyperlink</span></span>|  
|<span data-ttu-id="fd566-127">단추</span><span class="sxs-lookup"><span data-stu-id="fd566-127">Button</span></span>|<span data-ttu-id="fd566-128">SplitButton</span><span class="sxs-lookup"><span data-stu-id="fd566-128">SplitButton</span></span>|  
|<span data-ttu-id="fd566-129">단추</span><span class="sxs-lookup"><span data-stu-id="fd566-129">Button</span></span>|<span data-ttu-id="fd566-130">CheckBox</span><span class="sxs-lookup"><span data-stu-id="fd566-130">CheckBox</span></span>|  
|<span data-ttu-id="fd566-131">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="fd566-131">ComboBoxEx32</span></span>|<span data-ttu-id="fd566-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="fd566-132">ComboBox</span></span>|  
|<span data-ttu-id="fd566-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="fd566-133">ComboBox</span></span>|<span data-ttu-id="fd566-134">ComboBox</span><span class="sxs-lookup"><span data-stu-id="fd566-134">ComboBox</span></span>|  
|<span data-ttu-id="fd566-135">편집</span><span class="sxs-lookup"><span data-stu-id="fd566-135">Edit</span></span>|<span data-ttu-id="fd566-136">문서</span><span class="sxs-lookup"><span data-stu-id="fd566-136">Document</span></span>|  
|<span data-ttu-id="fd566-137">편집</span><span class="sxs-lookup"><span data-stu-id="fd566-137">Edit</span></span>|<span data-ttu-id="fd566-138">편집</span><span class="sxs-lookup"><span data-stu-id="fd566-138">Edit</span></span>|  
|<span data-ttu-id="fd566-139">SysLink</span><span class="sxs-lookup"><span data-stu-id="fd566-139">SysLink</span></span>|<span data-ttu-id="fd566-140">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="fd566-140">Hyperlink</span></span>|  
|<span data-ttu-id="fd566-141">정적</span><span class="sxs-lookup"><span data-stu-id="fd566-141">Static</span></span>|<span data-ttu-id="fd566-142">텍스트</span><span class="sxs-lookup"><span data-stu-id="fd566-142">Text</span></span>|  
|<span data-ttu-id="fd566-143">정적</span><span class="sxs-lookup"><span data-stu-id="fd566-143">Static</span></span>|<span data-ttu-id="fd566-144">이미지</span><span class="sxs-lookup"><span data-stu-id="fd566-144">Image</span></span>|  
|<span data-ttu-id="fd566-145">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="fd566-145">SysIPAddress32</span></span>|<span data-ttu-id="fd566-146">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="fd566-146">Custom</span></span>|  
|<span data-ttu-id="fd566-147">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="fd566-147">SysHeader32</span></span>|<span data-ttu-id="fd566-148">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="fd566-148">Header/HeaderItem</span></span>|  
|<span data-ttu-id="fd566-149">SysListView32</span><span class="sxs-lookup"><span data-stu-id="fd566-149">SysListView32</span></span>|<span data-ttu-id="fd566-150">DataGrid</span><span class="sxs-lookup"><span data-stu-id="fd566-150">DataGrid</span></span>|  
|<span data-ttu-id="fd566-151">SysListView32</span><span class="sxs-lookup"><span data-stu-id="fd566-151">SysListView32</span></span>|<span data-ttu-id="fd566-152">목록</span><span class="sxs-lookup"><span data-stu-id="fd566-152">List</span></span>|  
|<span data-ttu-id="fd566-153">ListBox</span><span class="sxs-lookup"><span data-stu-id="fd566-153">ListBox</span></span>|<span data-ttu-id="fd566-154">목록</span><span class="sxs-lookup"><span data-stu-id="fd566-154">List</span></span>|  
|<span data-ttu-id="fd566-155">ListBox</span><span class="sxs-lookup"><span data-stu-id="fd566-155">ListBox</span></span>|<span data-ttu-id="fd566-156">ListItem</span><span class="sxs-lookup"><span data-stu-id="fd566-156">ListItem</span></span>|  
|<span data-ttu-id="fd566-157">#32768</span><span class="sxs-lookup"><span data-stu-id="fd566-157">#32768</span></span>|<span data-ttu-id="fd566-158">메뉴</span><span class="sxs-lookup"><span data-stu-id="fd566-158">Menu</span></span>|  
|<span data-ttu-id="fd566-159">#32768</span><span class="sxs-lookup"><span data-stu-id="fd566-159">#32768</span></span>|<span data-ttu-id="fd566-160">MenuItem</span><span class="sxs-lookup"><span data-stu-id="fd566-160">MenuItem</span></span>|  
|<span data-ttu-id="fd566-161">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="fd566-161">msctls_progress32</span></span>|<span data-ttu-id="fd566-162">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="fd566-162">ProgressBar</span></span>|  
|<span data-ttu-id="fd566-163">RichEdit</span><span class="sxs-lookup"><span data-stu-id="fd566-163">RichEdit</span></span>|<span data-ttu-id="fd566-164">문서입니다.</span><span class="sxs-lookup"><span data-stu-id="fd566-164">Document.</span></span> <span data-ttu-id="fd566-165">참고를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd566-165">See note.</span></span>|  
|<span data-ttu-id="fd566-166">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="fd566-166">RichEdit20A</span></span>|<span data-ttu-id="fd566-167">문서</span><span class="sxs-lookup"><span data-stu-id="fd566-167">Document</span></span>|  
|<span data-ttu-id="fd566-168">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="fd566-168">RichEdit20W</span></span>|<span data-ttu-id="fd566-169">문서</span><span class="sxs-lookup"><span data-stu-id="fd566-169">Document</span></span>|  
|<span data-ttu-id="fd566-170">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="fd566-170">RichEdit50W</span></span>|<span data-ttu-id="fd566-171">문서</span><span class="sxs-lookup"><span data-stu-id="fd566-171">Document</span></span>|  
|<span data-ttu-id="fd566-172">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="fd566-172">ScrollBar</span></span>|<span data-ttu-id="fd566-173">슬라이더</span><span class="sxs-lookup"><span data-stu-id="fd566-173">Slider</span></span>|  
|<span data-ttu-id="fd566-174">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="fd566-174">msctls_trackbar32</span></span>|<span data-ttu-id="fd566-175">슬라이더</span><span class="sxs-lookup"><span data-stu-id="fd566-175">Slider</span></span>|  
|<span data-ttu-id="fd566-176">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="fd566-176">msctls_updown32</span></span>|<span data-ttu-id="fd566-177">Spinner</span><span class="sxs-lookup"><span data-stu-id="fd566-177">Spinner</span></span>|  
|<span data-ttu-id="fd566-178">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="fd566-178">msctls_statusbar32</span></span>|<span data-ttu-id="fd566-179">StatusBar</span><span class="sxs-lookup"><span data-stu-id="fd566-179">StatusBar</span></span>|  
|<span data-ttu-id="fd566-180">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="fd566-180">SysTabControl32</span></span>|<span data-ttu-id="fd566-181">탭</span><span class="sxs-lookup"><span data-stu-id="fd566-181">Tab</span></span>|  
|<span data-ttu-id="fd566-182">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="fd566-182">SysTabControl32</span></span>|<span data-ttu-id="fd566-183">TabItem</span><span class="sxs-lookup"><span data-stu-id="fd566-183">TabItem</span></span>|  
|<span data-ttu-id="fd566-184">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="fd566-184">ToolbarWindow32</span></span>|<span data-ttu-id="fd566-185">ToolBar</span><span class="sxs-lookup"><span data-stu-id="fd566-185">ToolBar</span></span>|  
|<span data-ttu-id="fd566-186">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="fd566-186">ToolbarWindow32</span></span>|<span data-ttu-id="fd566-187">MenuItem</span><span class="sxs-lookup"><span data-stu-id="fd566-187">MenuItem</span></span>|  
|<span data-ttu-id="fd566-188">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="fd566-188">ToolbarWindow32</span></span>|<span data-ttu-id="fd566-189">단추</span><span class="sxs-lookup"><span data-stu-id="fd566-189">Button</span></span>|  
|<span data-ttu-id="fd566-190">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="fd566-190">ToolbarWindow32</span></span>|<span data-ttu-id="fd566-191">CheckBox</span><span class="sxs-lookup"><span data-stu-id="fd566-191">CheckBox</span></span>|  
|<span data-ttu-id="fd566-192">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="fd566-192">ToolbarWindow32</span></span>|<span data-ttu-id="fd566-193">RadioButton</span><span class="sxs-lookup"><span data-stu-id="fd566-193">RadioButton</span></span>|  
|<span data-ttu-id="fd566-194">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="fd566-194">ToolbarWindow32</span></span>|<span data-ttu-id="fd566-195">구분 기호</span><span class="sxs-lookup"><span data-stu-id="fd566-195">Separator</span></span>|  
|<span data-ttu-id="fd566-196">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="fd566-196">tooltips_class32</span></span>|<span data-ttu-id="fd566-197">도구 설명</span><span class="sxs-lookup"><span data-stu-id="fd566-197">ToolTip</span></span>|  
|<span data-ttu-id="fd566-198">#32774</span><span class="sxs-lookup"><span data-stu-id="fd566-198">#32774</span></span>|<span data-ttu-id="fd566-199">도구 설명</span><span class="sxs-lookup"><span data-stu-id="fd566-199">ToolTip</span></span>|  
|<span data-ttu-id="fd566-200">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="fd566-200">ReBarWindow32</span></span>|<span data-ttu-id="fd566-201">도구 모음</span><span class="sxs-lookup"><span data-stu-id="fd566-201">Toolbar</span></span>|  
|<span data-ttu-id="fd566-202">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="fd566-202">SysTreeView32</span></span>|<span data-ttu-id="fd566-203">트리</span><span class="sxs-lookup"><span data-stu-id="fd566-203">Tree</span></span>|  
|<span data-ttu-id="fd566-204">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="fd566-204">SysTreeView32</span></span>|<span data-ttu-id="fd566-205">TreeItem</span><span class="sxs-lookup"><span data-stu-id="fd566-205">TreeItem</span></span>|  
  
 <span data-ttu-id="fd566-206">**참고** RichEdit 컨트롤은 Windows Vista와 함께 제공 되는 버전 (RichEd20.dll 버전 3.1 이상 및 MsftEdit.dll 버전 4.1 이상)에 대해서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd566-206">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="fd566-207">다음 컨트롤은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd566-207">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="fd566-208">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="fd566-208">Class name</span></span>|<span data-ttu-id="fd566-209">컨트롤 종류</span><span class="sxs-lookup"><span data-stu-id="fd566-209">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="fd566-210">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="fd566-210">SysAnimate32</span></span>|<span data-ttu-id="fd566-211">이미지</span><span class="sxs-lookup"><span data-stu-id="fd566-211">Image</span></span>|  
|<span data-ttu-id="fd566-212">SysPager</span><span class="sxs-lookup"><span data-stu-id="fd566-212">SysPager</span></span>|<span data-ttu-id="fd566-213">Spinner</span><span class="sxs-lookup"><span data-stu-id="fd566-213">Spinner</span></span>|  
|<span data-ttu-id="fd566-214">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="fd566-214">SysDateTimePick32</span></span>|<span data-ttu-id="fd566-215">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="fd566-215">Custom</span></span>|  
|<span data-ttu-id="fd566-216">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="fd566-216">SysMonthCal32</span></span>|<span data-ttu-id="fd566-217">일정</span><span class="sxs-lookup"><span data-stu-id="fd566-217">Calendar</span></span>|  
|<span data-ttu-id="fd566-218">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="fd566-218">MS_WINNOTE</span></span>|<span data-ttu-id="fd566-219">Tooltip</span><span class="sxs-lookup"><span data-stu-id="fd566-219">Tooltip</span></span>|  
|<span data-ttu-id="fd566-220">VBBubble</span><span class="sxs-lookup"><span data-stu-id="fd566-220">VBBubble</span></span>|<span data-ttu-id="fd566-221">Tooltip</span><span class="sxs-lookup"><span data-stu-id="fd566-221">Tooltip</span></span>|  
|<span data-ttu-id="fd566-222">스크롤 막대(독립 실행형 컨트롤로 사용되는 경우)</span><span class="sxs-lookup"><span data-stu-id="fd566-222">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="fd566-223">슬라이더</span><span class="sxs-lookup"><span data-stu-id="fd566-223">Slider</span></span>|  
|<span data-ttu-id="fd566-224">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="fd566-224">SuperGrid</span></span>|<span data-ttu-id="fd566-225">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="fd566-225">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a><span data-ttu-id="fd566-226">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="fd566-226">Windows Forms Controls</span></span>  
 <span data-ttu-id="fd566-227">Windows Forms 컨트롤은 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] UIAutomationClientsideProviders.dll 클라이언트 쪽 공급자를 통해에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd566-227">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="fd566-228">이 어셈블리는 UI 자동화 클라이언트 애플리케이션과 함께 사용할 수 있도록 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd566-228">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="fd566-229">일반적으로 Win32 공용 컨트롤에 대 한 관리 되는 래퍼 Windows Forms 컨트롤은에서 지원 됩니다 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fd566-229">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="fd566-230">다음과 같은 컨트롤이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd566-230">The following controls are supported.</span></span>  
  
|<span data-ttu-id="fd566-231">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="fd566-231">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="fd566-232">단추</span><span class="sxs-lookup"><span data-stu-id="fd566-232">Button</span></span>|  
|<span data-ttu-id="fd566-233">CheckBox</span><span class="sxs-lookup"><span data-stu-id="fd566-233">CheckBox</span></span>|  
|<span data-ttu-id="fd566-234">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="fd566-234">CheckedListBox</span></span>|  
|<span data-ttu-id="fd566-235">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="fd566-235">ColorDialog</span></span>|  
|<span data-ttu-id="fd566-236">ComboBox</span><span class="sxs-lookup"><span data-stu-id="fd566-236">ComboBox</span></span>|  
|<span data-ttu-id="fd566-237">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="fd566-237">FolderBrowser</span></span>|  
|<span data-ttu-id="fd566-238">FontDialog</span><span class="sxs-lookup"><span data-stu-id="fd566-238">FontDialog</span></span>|  
|<span data-ttu-id="fd566-239">GroupBox</span><span class="sxs-lookup"><span data-stu-id="fd566-239">GroupBox</span></span>|  
|<span data-ttu-id="fd566-240">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="fd566-240">HscrollBar</span></span>|  
|<span data-ttu-id="fd566-241">ImageList</span><span class="sxs-lookup"><span data-stu-id="fd566-241">ImageList</span></span>|  
|<span data-ttu-id="fd566-242">레이블</span><span class="sxs-lookup"><span data-stu-id="fd566-242">Label</span></span>|  
|<span data-ttu-id="fd566-243">ListBox</span><span class="sxs-lookup"><span data-stu-id="fd566-243">ListBox</span></span>|  
|<span data-ttu-id="fd566-244">ListView</span><span class="sxs-lookup"><span data-stu-id="fd566-244">ListView</span></span>|  
|<span data-ttu-id="fd566-245">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="fd566-245">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="fd566-246">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="fd566-246">MonthCalendar</span></span>|  
|<span data-ttu-id="fd566-247">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="fd566-247">NotifyIcon</span></span>|  
|<span data-ttu-id="fd566-248">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="fd566-248">OpenFileDialog</span></span>|  
|<span data-ttu-id="fd566-249">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="fd566-249">PageSetupDialog</span></span>|  
|<span data-ttu-id="fd566-250">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="fd566-250">PrintDialog</span></span>|  
|<span data-ttu-id="fd566-251">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="fd566-251">ProgressBar</span></span>|  
|<span data-ttu-id="fd566-252">RadioButton</span><span class="sxs-lookup"><span data-stu-id="fd566-252">RadioButton</span></span>|  
|<span data-ttu-id="fd566-253">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="fd566-253">RichTextBox</span></span>|  
|<span data-ttu-id="fd566-254">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="fd566-254">SaveFileDialog</span></span>|  
|<span data-ttu-id="fd566-255">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="fd566-255">ScrollableControl</span></span>|  
|<span data-ttu-id="fd566-256">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="fd566-256">SoundPlayer</span></span>|  
|<span data-ttu-id="fd566-257">StatusBar</span><span class="sxs-lookup"><span data-stu-id="fd566-257">StatusBar</span></span>|  
|<span data-ttu-id="fd566-258">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="fd566-258">TabControl/TabPage</span></span>|  
|<span data-ttu-id="fd566-259">TextBox</span><span class="sxs-lookup"><span data-stu-id="fd566-259">TextBox</span></span>|  
|<span data-ttu-id="fd566-260">Timer</span><span class="sxs-lookup"><span data-stu-id="fd566-260">Timer</span></span>|  
|<span data-ttu-id="fd566-261">도구 모음</span><span class="sxs-lookup"><span data-stu-id="fd566-261">Toolbar</span></span>|  
|<span data-ttu-id="fd566-262">도구 설명</span><span class="sxs-lookup"><span data-stu-id="fd566-262">ToolTip</span></span>|  
|<span data-ttu-id="fd566-263">TrackBar</span><span class="sxs-lookup"><span data-stu-id="fd566-263">TrackBar</span></span>|  
|<span data-ttu-id="fd566-264">TreeView</span><span class="sxs-lookup"><span data-stu-id="fd566-264">TreeView</span></span>|  
|<span data-ttu-id="fd566-265">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="fd566-265">VscrollBar</span></span>|  
|<span data-ttu-id="fd566-266">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="fd566-266">WebBrowser</span></span>|  
  
 <span data-ttu-id="fd566-267">다음 컨트롤은 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Microsoft Active Accessibility에 대 한 지원을 통해서만에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd566-267">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="fd566-268">일부 기능은 사용하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd566-268">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="fd566-269">컨트롤 이름</span><span class="sxs-lookup"><span data-stu-id="fd566-269">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="fd566-270">BindingSource</span><span class="sxs-lookup"><span data-stu-id="fd566-270">BindingSource</span></span>|  
|<span data-ttu-id="fd566-271">DataGrid</span><span class="sxs-lookup"><span data-stu-id="fd566-271">DataGrid</span></span>|  
|<span data-ttu-id="fd566-272">DataGridView</span><span class="sxs-lookup"><span data-stu-id="fd566-272">DataGridView</span></span>|  
|<span data-ttu-id="fd566-273">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="fd566-273">DataNavigator</span></span>|  
|<span data-ttu-id="fd566-274">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="fd566-274">DomainUpDown</span></span>|  
|<span data-ttu-id="fd566-275">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="fd566-275">ErrorProvider</span></span>|  
|<span data-ttu-id="fd566-276">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="fd566-276">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="fd566-277">Form</span><span class="sxs-lookup"><span data-stu-id="fd566-277">Form</span></span>|  
|<span data-ttu-id="fd566-278">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="fd566-278">LinkLabel</span></span>|  
|<span data-ttu-id="fd566-279">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="fd566-279">HelpProvider</span></span>|  
|<span data-ttu-id="fd566-280">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="fd566-280">MaskedTextBox</span></span>|  
|<span data-ttu-id="fd566-281">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="fd566-281">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="fd566-282">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="fd566-282">NumericUpDown</span></span>|  
|<span data-ttu-id="fd566-283">패널</span><span class="sxs-lookup"><span data-stu-id="fd566-283">Panel</span></span>|  
|<span data-ttu-id="fd566-284">PictureBox</span><span class="sxs-lookup"><span data-stu-id="fd566-284">PictureBox</span></span>|  
|<span data-ttu-id="fd566-285">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="fd566-285">PrintDocument</span></span>|  
|<span data-ttu-id="fd566-286">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="fd566-286">PrintPreview-Control</span></span>|  
|<span data-ttu-id="fd566-287">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="fd566-287">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="fd566-288">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="fd566-288">PropertyGrid</span></span>|  
|<span data-ttu-id="fd566-289">UserControl</span><span class="sxs-lookup"><span data-stu-id="fd566-289">UserControl</span></span>|  
|<span data-ttu-id="fd566-290">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="fd566-290">ToolStrip</span></span>|  
|<span data-ttu-id="fd566-291">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="fd566-291">TableLayoutPanel</span></span>|  
|<span data-ttu-id="fd566-292">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="fd566-292">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="fd566-293">분할자</span><span class="sxs-lookup"><span data-stu-id="fd566-293">Splitter</span></span>|  
|<span data-ttu-id="fd566-294">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="fd566-294">RaftingContainer</span></span>|  
|<span data-ttu-id="fd566-295">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="fd566-295">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd566-296">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd566-296">See also</span></span>

- [<span data-ttu-id="fd566-297">UI 자동화 컨트롤 형식</span><span class="sxs-lookup"><span data-stu-id="fd566-297">UI Automation Control Types</span></span>](ui-automation-control-types.md)
