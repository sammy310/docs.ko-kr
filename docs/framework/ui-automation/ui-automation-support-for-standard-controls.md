---
title: 표준 컨트롤에 대한 UI 자동화 지원
description: Windows Presentation Foundation (WPF), Win32 및 Windows Forms 용으로 개발 된 응용 프로그램에서 표준 컨트롤에 대 한 UI 자동화 지원에 대 한 정보를 가져옵니다.
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 0a5a0b61a6492d9efb62799fa610859b247cf26e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261074"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="ff334-103">표준 컨트롤에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="ff334-103">UI Automation Support for Standard Controls</span></span>

> [!NOTE]
> <span data-ttu-id="ff334-104">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ff334-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ff334-105">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff334-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="ff334-106">이 항목에 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 는 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] , Win32 및 Windows Forms 프레임 워크 용으로 개발 된 응용 프로그램의 표준 컨트롤에 대 한 지원 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff334-106">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>

## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="ff334-107">WPF(Windows Presentation Foundation) 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ff334-107">Windows Presentation Foundation Controls</span></span>  

 <span data-ttu-id="ff334-108">사용자 상호 작용 지원 또는 정보를 제공하는 모든 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 요소에는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 전체 기본 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff334-108">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="ff334-109">패널 등과 같은 기타 요소는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff334-109">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>

## <a name="win32-controls"></a><span data-ttu-id="ff334-110">Win32 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ff334-110">Win32 Controls</span></span>  

 <span data-ttu-id="ff334-111">대부분의 Win32 컨트롤은 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] UIAutomationClientsideProviders.dll의 클라이언트 쪽 공급자를 통해에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff334-111">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="ff334-112">이 어셈블리는 UI 자동화 클라이언트 애플리케이션과 함께 사용할 수 있도록 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff334-112">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="ff334-113">*ComCtrl32.dll* 버전 6의 컨트롤에 대해서만 전체 지원이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff334-113">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="ff334-114">다음과 같은 컨트롤이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff334-114">The following controls are supported.</span></span>  
  
|<span data-ttu-id="ff334-115">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="ff334-115">Class name</span></span>|<span data-ttu-id="ff334-116">컨트롤 종류</span><span class="sxs-lookup"><span data-stu-id="ff334-116">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="ff334-117">단추</span><span class="sxs-lookup"><span data-stu-id="ff334-117">Button</span></span>|<span data-ttu-id="ff334-118">단추</span><span class="sxs-lookup"><span data-stu-id="ff334-118">Button</span></span>|  
|<span data-ttu-id="ff334-119">단추</span><span class="sxs-lookup"><span data-stu-id="ff334-119">Button</span></span>|<span data-ttu-id="ff334-120">RadioButton</span><span class="sxs-lookup"><span data-stu-id="ff334-120">RadioButton</span></span>|  
|<span data-ttu-id="ff334-121">단추</span><span class="sxs-lookup"><span data-stu-id="ff334-121">Button</span></span>|<span data-ttu-id="ff334-122">그룹</span><span class="sxs-lookup"><span data-stu-id="ff334-122">Group</span></span>|  
|<span data-ttu-id="ff334-123">단추</span><span class="sxs-lookup"><span data-stu-id="ff334-123">Button</span></span>|<span data-ttu-id="ff334-124">CheckBox</span><span class="sxs-lookup"><span data-stu-id="ff334-124">CheckBox</span></span>|  
|<span data-ttu-id="ff334-125">단추</span><span class="sxs-lookup"><span data-stu-id="ff334-125">Button</span></span>|<span data-ttu-id="ff334-126">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="ff334-126">Hyperlink</span></span>|  
|<span data-ttu-id="ff334-127">단추</span><span class="sxs-lookup"><span data-stu-id="ff334-127">Button</span></span>|<span data-ttu-id="ff334-128">SplitButton</span><span class="sxs-lookup"><span data-stu-id="ff334-128">SplitButton</span></span>|  
|<span data-ttu-id="ff334-129">단추</span><span class="sxs-lookup"><span data-stu-id="ff334-129">Button</span></span>|<span data-ttu-id="ff334-130">CheckBox</span><span class="sxs-lookup"><span data-stu-id="ff334-130">CheckBox</span></span>|  
|<span data-ttu-id="ff334-131">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="ff334-131">ComboBoxEx32</span></span>|<span data-ttu-id="ff334-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="ff334-132">ComboBox</span></span>|  
|<span data-ttu-id="ff334-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="ff334-133">ComboBox</span></span>|<span data-ttu-id="ff334-134">ComboBox</span><span class="sxs-lookup"><span data-stu-id="ff334-134">ComboBox</span></span>|  
|<span data-ttu-id="ff334-135">편집</span><span class="sxs-lookup"><span data-stu-id="ff334-135">Edit</span></span>|<span data-ttu-id="ff334-136">문서</span><span class="sxs-lookup"><span data-stu-id="ff334-136">Document</span></span>|  
|<span data-ttu-id="ff334-137">편집</span><span class="sxs-lookup"><span data-stu-id="ff334-137">Edit</span></span>|<span data-ttu-id="ff334-138">편집</span><span class="sxs-lookup"><span data-stu-id="ff334-138">Edit</span></span>|  
|<span data-ttu-id="ff334-139">SysLink</span><span class="sxs-lookup"><span data-stu-id="ff334-139">SysLink</span></span>|<span data-ttu-id="ff334-140">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="ff334-140">Hyperlink</span></span>|  
|<span data-ttu-id="ff334-141">정적</span><span class="sxs-lookup"><span data-stu-id="ff334-141">Static</span></span>|<span data-ttu-id="ff334-142">텍스트</span><span class="sxs-lookup"><span data-stu-id="ff334-142">Text</span></span>|  
|<span data-ttu-id="ff334-143">정적</span><span class="sxs-lookup"><span data-stu-id="ff334-143">Static</span></span>|<span data-ttu-id="ff334-144">이미지</span><span class="sxs-lookup"><span data-stu-id="ff334-144">Image</span></span>|  
|<span data-ttu-id="ff334-145">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="ff334-145">SysIPAddress32</span></span>|<span data-ttu-id="ff334-146">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ff334-146">Custom</span></span>|  
|<span data-ttu-id="ff334-147">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="ff334-147">SysHeader32</span></span>|<span data-ttu-id="ff334-148">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="ff334-148">Header/HeaderItem</span></span>|  
|<span data-ttu-id="ff334-149">SysListView32</span><span class="sxs-lookup"><span data-stu-id="ff334-149">SysListView32</span></span>|<span data-ttu-id="ff334-150">DataGrid</span><span class="sxs-lookup"><span data-stu-id="ff334-150">DataGrid</span></span>|  
|<span data-ttu-id="ff334-151">SysListView32</span><span class="sxs-lookup"><span data-stu-id="ff334-151">SysListView32</span></span>|<span data-ttu-id="ff334-152">목록</span><span class="sxs-lookup"><span data-stu-id="ff334-152">List</span></span>|  
|<span data-ttu-id="ff334-153">ListBox</span><span class="sxs-lookup"><span data-stu-id="ff334-153">ListBox</span></span>|<span data-ttu-id="ff334-154">목록</span><span class="sxs-lookup"><span data-stu-id="ff334-154">List</span></span>|  
|<span data-ttu-id="ff334-155">ListBox</span><span class="sxs-lookup"><span data-stu-id="ff334-155">ListBox</span></span>|<span data-ttu-id="ff334-156">ListItem</span><span class="sxs-lookup"><span data-stu-id="ff334-156">ListItem</span></span>|  
|<span data-ttu-id="ff334-157">#32768</span><span class="sxs-lookup"><span data-stu-id="ff334-157">#32768</span></span>|<span data-ttu-id="ff334-158">메뉴</span><span class="sxs-lookup"><span data-stu-id="ff334-158">Menu</span></span>|  
|<span data-ttu-id="ff334-159">#32768</span><span class="sxs-lookup"><span data-stu-id="ff334-159">#32768</span></span>|<span data-ttu-id="ff334-160">MenuItem</span><span class="sxs-lookup"><span data-stu-id="ff334-160">MenuItem</span></span>|  
|<span data-ttu-id="ff334-161">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="ff334-161">msctls_progress32</span></span>|<span data-ttu-id="ff334-162">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="ff334-162">ProgressBar</span></span>|  
|<span data-ttu-id="ff334-163">RichEdit</span><span class="sxs-lookup"><span data-stu-id="ff334-163">RichEdit</span></span>|<span data-ttu-id="ff334-164">문서입니다.</span><span class="sxs-lookup"><span data-stu-id="ff334-164">Document.</span></span> <span data-ttu-id="ff334-165">참고를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff334-165">See note.</span></span>|  
|<span data-ttu-id="ff334-166">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="ff334-166">RichEdit20A</span></span>|<span data-ttu-id="ff334-167">문서</span><span class="sxs-lookup"><span data-stu-id="ff334-167">Document</span></span>|  
|<span data-ttu-id="ff334-168">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="ff334-168">RichEdit20W</span></span>|<span data-ttu-id="ff334-169">문서</span><span class="sxs-lookup"><span data-stu-id="ff334-169">Document</span></span>|  
|<span data-ttu-id="ff334-170">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="ff334-170">RichEdit50W</span></span>|<span data-ttu-id="ff334-171">문서</span><span class="sxs-lookup"><span data-stu-id="ff334-171">Document</span></span>|  
|<span data-ttu-id="ff334-172">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="ff334-172">ScrollBar</span></span>|<span data-ttu-id="ff334-173">슬라이더</span><span class="sxs-lookup"><span data-stu-id="ff334-173">Slider</span></span>|  
|<span data-ttu-id="ff334-174">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="ff334-174">msctls_trackbar32</span></span>|<span data-ttu-id="ff334-175">슬라이더</span><span class="sxs-lookup"><span data-stu-id="ff334-175">Slider</span></span>|  
|<span data-ttu-id="ff334-176">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="ff334-176">msctls_updown32</span></span>|<span data-ttu-id="ff334-177">Spinner</span><span class="sxs-lookup"><span data-stu-id="ff334-177">Spinner</span></span>|  
|<span data-ttu-id="ff334-178">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="ff334-178">msctls_statusbar32</span></span>|<span data-ttu-id="ff334-179">StatusBar</span><span class="sxs-lookup"><span data-stu-id="ff334-179">StatusBar</span></span>|  
|<span data-ttu-id="ff334-180">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="ff334-180">SysTabControl32</span></span>|<span data-ttu-id="ff334-181">탭</span><span class="sxs-lookup"><span data-stu-id="ff334-181">Tab</span></span>|  
|<span data-ttu-id="ff334-182">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="ff334-182">SysTabControl32</span></span>|<span data-ttu-id="ff334-183">TabItem</span><span class="sxs-lookup"><span data-stu-id="ff334-183">TabItem</span></span>|  
|<span data-ttu-id="ff334-184">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ff334-184">ToolbarWindow32</span></span>|<span data-ttu-id="ff334-185">ToolBar</span><span class="sxs-lookup"><span data-stu-id="ff334-185">ToolBar</span></span>|  
|<span data-ttu-id="ff334-186">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ff334-186">ToolbarWindow32</span></span>|<span data-ttu-id="ff334-187">MenuItem</span><span class="sxs-lookup"><span data-stu-id="ff334-187">MenuItem</span></span>|  
|<span data-ttu-id="ff334-188">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ff334-188">ToolbarWindow32</span></span>|<span data-ttu-id="ff334-189">단추</span><span class="sxs-lookup"><span data-stu-id="ff334-189">Button</span></span>|  
|<span data-ttu-id="ff334-190">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ff334-190">ToolbarWindow32</span></span>|<span data-ttu-id="ff334-191">CheckBox</span><span class="sxs-lookup"><span data-stu-id="ff334-191">CheckBox</span></span>|  
|<span data-ttu-id="ff334-192">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ff334-192">ToolbarWindow32</span></span>|<span data-ttu-id="ff334-193">RadioButton</span><span class="sxs-lookup"><span data-stu-id="ff334-193">RadioButton</span></span>|  
|<span data-ttu-id="ff334-194">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="ff334-194">ToolbarWindow32</span></span>|<span data-ttu-id="ff334-195">구분 기호</span><span class="sxs-lookup"><span data-stu-id="ff334-195">Separator</span></span>|  
|<span data-ttu-id="ff334-196">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="ff334-196">tooltips_class32</span></span>|<span data-ttu-id="ff334-197">ToolTip</span><span class="sxs-lookup"><span data-stu-id="ff334-197">ToolTip</span></span>|  
|<span data-ttu-id="ff334-198">#32774</span><span class="sxs-lookup"><span data-stu-id="ff334-198">#32774</span></span>|<span data-ttu-id="ff334-199">ToolTip</span><span class="sxs-lookup"><span data-stu-id="ff334-199">ToolTip</span></span>|  
|<span data-ttu-id="ff334-200">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="ff334-200">ReBarWindow32</span></span>|<span data-ttu-id="ff334-201">Toolbar</span><span class="sxs-lookup"><span data-stu-id="ff334-201">Toolbar</span></span>|  
|<span data-ttu-id="ff334-202">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="ff334-202">SysTreeView32</span></span>|<span data-ttu-id="ff334-203">트리</span><span class="sxs-lookup"><span data-stu-id="ff334-203">Tree</span></span>|  
|<span data-ttu-id="ff334-204">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="ff334-204">SysTreeView32</span></span>|<span data-ttu-id="ff334-205">TreeItem</span><span class="sxs-lookup"><span data-stu-id="ff334-205">TreeItem</span></span>|  
  
 <span data-ttu-id="ff334-206">**참고** RichEdit 컨트롤은 Windows Vista와 함께 제공 되는 버전 (RichEd20.dll 버전 3.1 이상 및 MsftEdit.dll 버전 4.1 이상)에 대해서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff334-206">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="ff334-207">다음 컨트롤은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff334-207">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="ff334-208">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="ff334-208">Class name</span></span>|<span data-ttu-id="ff334-209">컨트롤 형식</span><span class="sxs-lookup"><span data-stu-id="ff334-209">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="ff334-210">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="ff334-210">SysAnimate32</span></span>|<span data-ttu-id="ff334-211">이미지</span><span class="sxs-lookup"><span data-stu-id="ff334-211">Image</span></span>|  
|<span data-ttu-id="ff334-212">SysPager</span><span class="sxs-lookup"><span data-stu-id="ff334-212">SysPager</span></span>|<span data-ttu-id="ff334-213">Spinner</span><span class="sxs-lookup"><span data-stu-id="ff334-213">Spinner</span></span>|  
|<span data-ttu-id="ff334-214">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="ff334-214">SysDateTimePick32</span></span>|<span data-ttu-id="ff334-215">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ff334-215">Custom</span></span>|  
|<span data-ttu-id="ff334-216">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="ff334-216">SysMonthCal32</span></span>|<span data-ttu-id="ff334-217">달력</span><span class="sxs-lookup"><span data-stu-id="ff334-217">Calendar</span></span>|  
|<span data-ttu-id="ff334-218">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="ff334-218">MS_WINNOTE</span></span>|<span data-ttu-id="ff334-219">도구 설명</span><span class="sxs-lookup"><span data-stu-id="ff334-219">Tooltip</span></span>|  
|<span data-ttu-id="ff334-220">VBBubble</span><span class="sxs-lookup"><span data-stu-id="ff334-220">VBBubble</span></span>|<span data-ttu-id="ff334-221">도구 설명</span><span class="sxs-lookup"><span data-stu-id="ff334-221">Tooltip</span></span>|  
|<span data-ttu-id="ff334-222">스크롤 막대(독립 실행형 컨트롤로 사용되는 경우)</span><span class="sxs-lookup"><span data-stu-id="ff334-222">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="ff334-223">슬라이더</span><span class="sxs-lookup"><span data-stu-id="ff334-223">Slider</span></span>|  
|<span data-ttu-id="ff334-224">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="ff334-224">SuperGrid</span></span>|<span data-ttu-id="ff334-225">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ff334-225">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>

## <a name="windows-forms-controls"></a><span data-ttu-id="ff334-226">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ff334-226">Windows Forms Controls</span></span>  

 <span data-ttu-id="ff334-227">Windows Forms 컨트롤은 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] UIAutomationClientsideProviders.dll 클라이언트 쪽 공급자를 통해에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff334-227">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="ff334-228">이 어셈블리는 UI 자동화 클라이언트 애플리케이션과 함께 사용할 수 있도록 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff334-228">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="ff334-229">일반적으로 Win32 공용 컨트롤에 대 한 관리 되는 래퍼 Windows Forms 컨트롤은에서 지원 됩니다 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ff334-229">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="ff334-230">다음과 같은 컨트롤이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff334-230">The following controls are supported.</span></span>  
  
|<span data-ttu-id="ff334-231">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="ff334-231">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="ff334-232">단추</span><span class="sxs-lookup"><span data-stu-id="ff334-232">Button</span></span>|  
|<span data-ttu-id="ff334-233">CheckBox</span><span class="sxs-lookup"><span data-stu-id="ff334-233">CheckBox</span></span>|  
|<span data-ttu-id="ff334-234">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="ff334-234">CheckedListBox</span></span>|  
|<span data-ttu-id="ff334-235">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="ff334-235">ColorDialog</span></span>|  
|<span data-ttu-id="ff334-236">ComboBox</span><span class="sxs-lookup"><span data-stu-id="ff334-236">ComboBox</span></span>|  
|<span data-ttu-id="ff334-237">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="ff334-237">FolderBrowser</span></span>|  
|<span data-ttu-id="ff334-238">FontDialog</span><span class="sxs-lookup"><span data-stu-id="ff334-238">FontDialog</span></span>|  
|<span data-ttu-id="ff334-239">GroupBox</span><span class="sxs-lookup"><span data-stu-id="ff334-239">GroupBox</span></span>|  
|<span data-ttu-id="ff334-240">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="ff334-240">HscrollBar</span></span>|  
|<span data-ttu-id="ff334-241">ImageList</span><span class="sxs-lookup"><span data-stu-id="ff334-241">ImageList</span></span>|  
|<span data-ttu-id="ff334-242">레이블</span><span class="sxs-lookup"><span data-stu-id="ff334-242">Label</span></span>|  
|<span data-ttu-id="ff334-243">ListBox</span><span class="sxs-lookup"><span data-stu-id="ff334-243">ListBox</span></span>|  
|<span data-ttu-id="ff334-244">ListView</span><span class="sxs-lookup"><span data-stu-id="ff334-244">ListView</span></span>|  
|<span data-ttu-id="ff334-245">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="ff334-245">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="ff334-246">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="ff334-246">MonthCalendar</span></span>|  
|<span data-ttu-id="ff334-247">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="ff334-247">NotifyIcon</span></span>|  
|<span data-ttu-id="ff334-248">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="ff334-248">OpenFileDialog</span></span>|  
|<span data-ttu-id="ff334-249">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="ff334-249">PageSetupDialog</span></span>|  
|<span data-ttu-id="ff334-250">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="ff334-250">PrintDialog</span></span>|  
|<span data-ttu-id="ff334-251">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="ff334-251">ProgressBar</span></span>|  
|<span data-ttu-id="ff334-252">RadioButton</span><span class="sxs-lookup"><span data-stu-id="ff334-252">RadioButton</span></span>|  
|<span data-ttu-id="ff334-253">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="ff334-253">RichTextBox</span></span>|  
|<span data-ttu-id="ff334-254">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="ff334-254">SaveFileDialog</span></span>|  
|<span data-ttu-id="ff334-255">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="ff334-255">ScrollableControl</span></span>|  
|<span data-ttu-id="ff334-256">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="ff334-256">SoundPlayer</span></span>|  
|<span data-ttu-id="ff334-257">StatusBar</span><span class="sxs-lookup"><span data-stu-id="ff334-257">StatusBar</span></span>|  
|<span data-ttu-id="ff334-258">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="ff334-258">TabControl/TabPage</span></span>|  
|<span data-ttu-id="ff334-259">TextBox</span><span class="sxs-lookup"><span data-stu-id="ff334-259">TextBox</span></span>|  
|<span data-ttu-id="ff334-260">타이머</span><span class="sxs-lookup"><span data-stu-id="ff334-260">Timer</span></span>|  
|<span data-ttu-id="ff334-261">Toolbar</span><span class="sxs-lookup"><span data-stu-id="ff334-261">Toolbar</span></span>|  
|<span data-ttu-id="ff334-262">ToolTip</span><span class="sxs-lookup"><span data-stu-id="ff334-262">ToolTip</span></span>|  
|<span data-ttu-id="ff334-263">TrackBar</span><span class="sxs-lookup"><span data-stu-id="ff334-263">TrackBar</span></span>|  
|<span data-ttu-id="ff334-264">TreeView</span><span class="sxs-lookup"><span data-stu-id="ff334-264">TreeView</span></span>|  
|<span data-ttu-id="ff334-265">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="ff334-265">VscrollBar</span></span>|  
|<span data-ttu-id="ff334-266">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="ff334-266">WebBrowser</span></span>|  
  
 <span data-ttu-id="ff334-267">다음 컨트롤은 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Microsoft Active Accessibility에 대 한 지원을 통해서만에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff334-267">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="ff334-268">일부 기능은 사용하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff334-268">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="ff334-269">컨트롤 이름</span><span class="sxs-lookup"><span data-stu-id="ff334-269">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="ff334-270">BindingSource</span><span class="sxs-lookup"><span data-stu-id="ff334-270">BindingSource</span></span>|  
|<span data-ttu-id="ff334-271">DataGrid</span><span class="sxs-lookup"><span data-stu-id="ff334-271">DataGrid</span></span>|  
|<span data-ttu-id="ff334-272">DataGridView</span><span class="sxs-lookup"><span data-stu-id="ff334-272">DataGridView</span></span>|  
|<span data-ttu-id="ff334-273">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="ff334-273">DataNavigator</span></span>|  
|<span data-ttu-id="ff334-274">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="ff334-274">DomainUpDown</span></span>|  
|<span data-ttu-id="ff334-275">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="ff334-275">ErrorProvider</span></span>|  
|<span data-ttu-id="ff334-276">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ff334-276">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="ff334-277">Form</span><span class="sxs-lookup"><span data-stu-id="ff334-277">Form</span></span>|  
|<span data-ttu-id="ff334-278">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="ff334-278">LinkLabel</span></span>|  
|<span data-ttu-id="ff334-279">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="ff334-279">HelpProvider</span></span>|  
|<span data-ttu-id="ff334-280">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="ff334-280">MaskedTextBox</span></span>|  
|<span data-ttu-id="ff334-281">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="ff334-281">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="ff334-282">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="ff334-282">NumericUpDown</span></span>|  
|<span data-ttu-id="ff334-283">패널</span><span class="sxs-lookup"><span data-stu-id="ff334-283">Panel</span></span>|  
|<span data-ttu-id="ff334-284">PictureBox</span><span class="sxs-lookup"><span data-stu-id="ff334-284">PictureBox</span></span>|  
|<span data-ttu-id="ff334-285">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="ff334-285">PrintDocument</span></span>|  
|<span data-ttu-id="ff334-286">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="ff334-286">PrintPreview-Control</span></span>|  
|<span data-ttu-id="ff334-287">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="ff334-287">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="ff334-288">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="ff334-288">PropertyGrid</span></span>|  
|<span data-ttu-id="ff334-289">UserControl</span><span class="sxs-lookup"><span data-stu-id="ff334-289">UserControl</span></span>|  
|<span data-ttu-id="ff334-290">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ff334-290">ToolStrip</span></span>|  
|<span data-ttu-id="ff334-291">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ff334-291">TableLayoutPanel</span></span>|  
|<span data-ttu-id="ff334-292">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="ff334-292">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="ff334-293">분할자</span><span class="sxs-lookup"><span data-stu-id="ff334-293">Splitter</span></span>|  
|<span data-ttu-id="ff334-294">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="ff334-294">RaftingContainer</span></span>|  
|<span data-ttu-id="ff334-295">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="ff334-295">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ff334-296">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff334-296">See also</span></span>

- [<span data-ttu-id="ff334-297">UI 자동화 컨트롤 형식</span><span class="sxs-lookup"><span data-stu-id="ff334-297">UI Automation Control Types</span></span>](ui-automation-control-types.md)
