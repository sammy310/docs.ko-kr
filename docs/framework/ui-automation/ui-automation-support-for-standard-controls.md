---
title: 표준 컨트롤에 대한 UI 자동화 지원
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: ed5e4f6ab23fe9ae77c94616a668da8accb46d4b
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741705"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="a2fc4-102">표준 컨트롤에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="a2fc4-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="a2fc4-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a2fc4-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="a2fc4-105">이 항목에는 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32 및 [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] 프레임 워크 용으로 개발 된 응용 프로그램의 표준 컨트롤에 대 한 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 지원 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="a2fc4-106">WPF(Windows Presentation Foundation) 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a2fc4-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="a2fc4-107">사용자 상호 작용 지원 또는 정보를 제공하는 모든 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 요소에는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 전체 기본 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="a2fc4-108">패널 등과 같은 기타 요소는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="a2fc4-109">Win32 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a2fc4-109">Win32 Controls</span></span>  
 <span data-ttu-id="a2fc4-110">대부분의 Win32 컨트롤은 Uiautomationclientsideproviders.dll의 클라이언트 쪽 공급자를 통해 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-110">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="a2fc4-111">이 어셈블리는 UI 자동화 클라이언트 애플리케이션과 함께 사용할 수 있도록 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="a2fc4-112">*지원은 comctrl32.dll*버전 6의 컨트롤에 대해서만 전체 지원이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="a2fc4-113">다음과 같은 컨트롤이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="a2fc4-114">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="a2fc4-114">Class name</span></span>|<span data-ttu-id="a2fc4-115">컨트롤 종류</span><span class="sxs-lookup"><span data-stu-id="a2fc4-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="a2fc4-116">단추</span><span class="sxs-lookup"><span data-stu-id="a2fc4-116">Button</span></span>|<span data-ttu-id="a2fc4-117">단추</span><span class="sxs-lookup"><span data-stu-id="a2fc4-117">Button</span></span>|  
|<span data-ttu-id="a2fc4-118">단추</span><span class="sxs-lookup"><span data-stu-id="a2fc4-118">Button</span></span>|<span data-ttu-id="a2fc4-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="a2fc4-119">RadioButton</span></span>|  
|<span data-ttu-id="a2fc4-120">단추</span><span class="sxs-lookup"><span data-stu-id="a2fc4-120">Button</span></span>|<span data-ttu-id="a2fc4-121">그룹</span><span class="sxs-lookup"><span data-stu-id="a2fc4-121">Group</span></span>|  
|<span data-ttu-id="a2fc4-122">단추</span><span class="sxs-lookup"><span data-stu-id="a2fc4-122">Button</span></span>|<span data-ttu-id="a2fc4-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a2fc4-123">CheckBox</span></span>|  
|<span data-ttu-id="a2fc4-124">단추</span><span class="sxs-lookup"><span data-stu-id="a2fc4-124">Button</span></span>|<span data-ttu-id="a2fc4-125">하이퍼링크</span><span class="sxs-lookup"><span data-stu-id="a2fc4-125">Hyperlink</span></span>|  
|<span data-ttu-id="a2fc4-126">단추</span><span class="sxs-lookup"><span data-stu-id="a2fc4-126">Button</span></span>|<span data-ttu-id="a2fc4-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="a2fc4-127">SplitButton</span></span>|  
|<span data-ttu-id="a2fc4-128">단추</span><span class="sxs-lookup"><span data-stu-id="a2fc4-128">Button</span></span>|<span data-ttu-id="a2fc4-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a2fc4-129">CheckBox</span></span>|  
|<span data-ttu-id="a2fc4-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-130">ComboBoxEx32</span></span>|<span data-ttu-id="a2fc4-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a2fc4-131">ComboBox</span></span>|  
|<span data-ttu-id="a2fc4-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a2fc4-132">ComboBox</span></span>|<span data-ttu-id="a2fc4-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a2fc4-133">ComboBox</span></span>|  
|<span data-ttu-id="a2fc4-134">Edit</span><span class="sxs-lookup"><span data-stu-id="a2fc4-134">Edit</span></span>|<span data-ttu-id="a2fc4-135">문서</span><span class="sxs-lookup"><span data-stu-id="a2fc4-135">Document</span></span>|  
|<span data-ttu-id="a2fc4-136">Edit</span><span class="sxs-lookup"><span data-stu-id="a2fc4-136">Edit</span></span>|<span data-ttu-id="a2fc4-137">Edit</span><span class="sxs-lookup"><span data-stu-id="a2fc4-137">Edit</span></span>|  
|<span data-ttu-id="a2fc4-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="a2fc4-138">SysLink</span></span>|<span data-ttu-id="a2fc4-139">하이퍼링크</span><span class="sxs-lookup"><span data-stu-id="a2fc4-139">Hyperlink</span></span>|  
|<span data-ttu-id="a2fc4-140">Static</span><span class="sxs-lookup"><span data-stu-id="a2fc4-140">Static</span></span>|<span data-ttu-id="a2fc4-141">텍스트</span><span class="sxs-lookup"><span data-stu-id="a2fc4-141">Text</span></span>|  
|<span data-ttu-id="a2fc4-142">Static</span><span class="sxs-lookup"><span data-stu-id="a2fc4-142">Static</span></span>|<span data-ttu-id="a2fc4-143">이미지</span><span class="sxs-lookup"><span data-stu-id="a2fc4-143">Image</span></span>|  
|<span data-ttu-id="a2fc4-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-144">SysIPAddress32</span></span>|<span data-ttu-id="a2fc4-145">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a2fc4-145">Custom</span></span>|  
|<span data-ttu-id="a2fc4-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-146">SysHeader32</span></span>|<span data-ttu-id="a2fc4-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="a2fc4-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="a2fc4-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-148">SysListView32</span></span>|<span data-ttu-id="a2fc4-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="a2fc4-149">DataGrid</span></span>|  
|<span data-ttu-id="a2fc4-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-150">SysListView32</span></span>|<span data-ttu-id="a2fc4-151">목록</span><span class="sxs-lookup"><span data-stu-id="a2fc4-151">List</span></span>|  
|<span data-ttu-id="a2fc4-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="a2fc4-152">ListBox</span></span>|<span data-ttu-id="a2fc4-153">목록</span><span class="sxs-lookup"><span data-stu-id="a2fc4-153">List</span></span>|  
|<span data-ttu-id="a2fc4-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="a2fc4-154">ListBox</span></span>|<span data-ttu-id="a2fc4-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="a2fc4-155">ListItem</span></span>|  
|<span data-ttu-id="a2fc4-156">#32768</span><span class="sxs-lookup"><span data-stu-id="a2fc4-156">#32768</span></span>|<span data-ttu-id="a2fc4-157">메뉴</span><span class="sxs-lookup"><span data-stu-id="a2fc4-157">Menu</span></span>|  
|<span data-ttu-id="a2fc4-158">#32768</span><span class="sxs-lookup"><span data-stu-id="a2fc4-158">#32768</span></span>|<span data-ttu-id="a2fc4-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="a2fc4-159">MenuItem</span></span>|  
|<span data-ttu-id="a2fc4-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-160">msctls_progress32</span></span>|<span data-ttu-id="a2fc4-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="a2fc4-161">ProgressBar</span></span>|  
|<span data-ttu-id="a2fc4-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="a2fc4-162">RichEdit</span></span>|<span data-ttu-id="a2fc4-163">문서.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-163">Document.</span></span> <span data-ttu-id="a2fc4-164">메모를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-164">See note.</span></span>|  
|<span data-ttu-id="a2fc4-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="a2fc4-165">RichEdit20A</span></span>|<span data-ttu-id="a2fc4-166">문서</span><span class="sxs-lookup"><span data-stu-id="a2fc4-166">Document</span></span>|  
|<span data-ttu-id="a2fc4-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="a2fc4-167">RichEdit20W</span></span>|<span data-ttu-id="a2fc4-168">문서</span><span class="sxs-lookup"><span data-stu-id="a2fc4-168">Document</span></span>|  
|<span data-ttu-id="a2fc4-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="a2fc4-169">RichEdit50W</span></span>|<span data-ttu-id="a2fc4-170">문서</span><span class="sxs-lookup"><span data-stu-id="a2fc4-170">Document</span></span>|  
|<span data-ttu-id="a2fc4-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="a2fc4-171">ScrollBar</span></span>|<span data-ttu-id="a2fc4-172">슬라이더</span><span class="sxs-lookup"><span data-stu-id="a2fc4-172">Slider</span></span>|  
|<span data-ttu-id="a2fc4-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-173">msctls_trackbar32</span></span>|<span data-ttu-id="a2fc4-174">슬라이더</span><span class="sxs-lookup"><span data-stu-id="a2fc4-174">Slider</span></span>|  
|<span data-ttu-id="a2fc4-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-175">msctls_updown32</span></span>|<span data-ttu-id="a2fc4-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="a2fc4-176">Spinner</span></span>|  
|<span data-ttu-id="a2fc4-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-177">msctls_statusbar32</span></span>|<span data-ttu-id="a2fc4-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="a2fc4-178">StatusBar</span></span>|  
|<span data-ttu-id="a2fc4-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-179">SysTabControl32</span></span>|<span data-ttu-id="a2fc4-180">탭</span><span class="sxs-lookup"><span data-stu-id="a2fc4-180">Tab</span></span>|  
|<span data-ttu-id="a2fc4-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-181">SysTabControl32</span></span>|<span data-ttu-id="a2fc4-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="a2fc4-182">TabItem</span></span>|  
|<span data-ttu-id="a2fc4-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-183">ToolbarWindow32</span></span>|<span data-ttu-id="a2fc4-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="a2fc4-184">ToolBar</span></span>|  
|<span data-ttu-id="a2fc4-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-185">ToolbarWindow32</span></span>|<span data-ttu-id="a2fc4-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="a2fc4-186">MenuItem</span></span>|  
|<span data-ttu-id="a2fc4-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-187">ToolbarWindow32</span></span>|<span data-ttu-id="a2fc4-188">단추</span><span class="sxs-lookup"><span data-stu-id="a2fc4-188">Button</span></span>|  
|<span data-ttu-id="a2fc4-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-189">ToolbarWindow32</span></span>|<span data-ttu-id="a2fc4-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a2fc4-190">CheckBox</span></span>|  
|<span data-ttu-id="a2fc4-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-191">ToolbarWindow32</span></span>|<span data-ttu-id="a2fc4-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="a2fc4-192">RadioButton</span></span>|  
|<span data-ttu-id="a2fc4-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-193">ToolbarWindow32</span></span>|<span data-ttu-id="a2fc4-194">구분 기호</span><span class="sxs-lookup"><span data-stu-id="a2fc4-194">Separator</span></span>|  
|<span data-ttu-id="a2fc4-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-195">tooltips_class32</span></span>|<span data-ttu-id="a2fc4-196">도구 설명</span><span class="sxs-lookup"><span data-stu-id="a2fc4-196">ToolTip</span></span>|  
|<span data-ttu-id="a2fc4-197">#32774</span><span class="sxs-lookup"><span data-stu-id="a2fc4-197">#32774</span></span>|<span data-ttu-id="a2fc4-198">도구 설명</span><span class="sxs-lookup"><span data-stu-id="a2fc4-198">ToolTip</span></span>|  
|<span data-ttu-id="a2fc4-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-199">ReBarWindow32</span></span>|<span data-ttu-id="a2fc4-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="a2fc4-200">Toolbar</span></span>|  
|<span data-ttu-id="a2fc4-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-201">SysTreeView32</span></span>|<span data-ttu-id="a2fc4-202">Tree</span><span class="sxs-lookup"><span data-stu-id="a2fc4-202">Tree</span></span>|  
|<span data-ttu-id="a2fc4-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-203">SysTreeView32</span></span>|<span data-ttu-id="a2fc4-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="a2fc4-204">TreeItem</span></span>|  
  
 <span data-ttu-id="a2fc4-205">**참고** RichEdit 컨트롤은 Windows Vista와 함께 제공 되는 버전에 대해서만 지원 됩니다 (Riched20.dll 버전 3.1 이상 및 Msftedit.dll 버전 4.1 이상).</span><span class="sxs-lookup"><span data-stu-id="a2fc4-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="a2fc4-206">다음 컨트롤은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="a2fc4-207">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="a2fc4-207">Class name</span></span>|<span data-ttu-id="a2fc4-208">컨트롤 종류</span><span class="sxs-lookup"><span data-stu-id="a2fc4-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="a2fc4-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-209">SysAnimate32</span></span>|<span data-ttu-id="a2fc4-210">이미지</span><span class="sxs-lookup"><span data-stu-id="a2fc4-210">Image</span></span>|  
|<span data-ttu-id="a2fc4-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="a2fc4-211">SysPager</span></span>|<span data-ttu-id="a2fc4-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="a2fc4-212">Spinner</span></span>|  
|<span data-ttu-id="a2fc4-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-213">SysDateTimePick32</span></span>|<span data-ttu-id="a2fc4-214">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a2fc4-214">Custom</span></span>|  
|<span data-ttu-id="a2fc4-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="a2fc4-215">SysMonthCal32</span></span>|<span data-ttu-id="a2fc4-216">일정</span><span class="sxs-lookup"><span data-stu-id="a2fc4-216">Calendar</span></span>|  
|<span data-ttu-id="a2fc4-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="a2fc4-217">MS_WINNOTE</span></span>|<span data-ttu-id="a2fc4-218">도구 설명</span><span class="sxs-lookup"><span data-stu-id="a2fc4-218">Tooltip</span></span>|  
|<span data-ttu-id="a2fc4-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="a2fc4-219">VBBubble</span></span>|<span data-ttu-id="a2fc4-220">도구 설명</span><span class="sxs-lookup"><span data-stu-id="a2fc4-220">Tooltip</span></span>|  
|<span data-ttu-id="a2fc4-221">스크롤 막대(독립 실행형 컨트롤로 사용되는 경우)</span><span class="sxs-lookup"><span data-stu-id="a2fc4-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="a2fc4-222">슬라이더</span><span class="sxs-lookup"><span data-stu-id="a2fc4-222">Slider</span></span>|  
|<span data-ttu-id="a2fc4-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="a2fc4-223">SuperGrid</span></span>|<span data-ttu-id="a2fc4-224">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a2fc4-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="a2fc4-225">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a2fc4-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="a2fc4-226">Windows Forms 컨트롤은 Uiautomationclientsideproviders.dll의 클라이언트 쪽 공급자를 통해 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="a2fc4-227">이 어셈블리는 UI 자동화 클라이언트 애플리케이션과 함께 사용할 수 있도록 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="a2fc4-228">일반적으로 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서 Win32 공용 컨트롤에 대 한 관리 되는 래퍼로 Windows Forms 컨트롤을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-228">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="a2fc4-229">다음과 같은 컨트롤이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="a2fc4-230">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="a2fc4-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="a2fc4-231">단추</span><span class="sxs-lookup"><span data-stu-id="a2fc4-231">Button</span></span>|  
|<span data-ttu-id="a2fc4-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a2fc4-232">CheckBox</span></span>|  
|<span data-ttu-id="a2fc4-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="a2fc4-233">CheckedListBox</span></span>|  
|<span data-ttu-id="a2fc4-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="a2fc4-234">ColorDialog</span></span>|  
|<span data-ttu-id="a2fc4-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a2fc4-235">ComboBox</span></span>|  
|<span data-ttu-id="a2fc4-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="a2fc4-236">FolderBrowser</span></span>|  
|<span data-ttu-id="a2fc4-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="a2fc4-237">FontDialog</span></span>|  
|<span data-ttu-id="a2fc4-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="a2fc4-238">GroupBox</span></span>|  
|<span data-ttu-id="a2fc4-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="a2fc4-239">HscrollBar</span></span>|  
|<span data-ttu-id="a2fc4-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="a2fc4-240">ImageList</span></span>|  
|<span data-ttu-id="a2fc4-241">레이블</span><span class="sxs-lookup"><span data-stu-id="a2fc4-241">Label</span></span>|  
|<span data-ttu-id="a2fc4-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="a2fc4-242">ListBox</span></span>|  
|<span data-ttu-id="a2fc4-243">ListView</span><span class="sxs-lookup"><span data-stu-id="a2fc4-243">ListView</span></span>|  
|<span data-ttu-id="a2fc4-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="a2fc4-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="a2fc4-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="a2fc4-245">MonthCalendar</span></span>|  
|<span data-ttu-id="a2fc4-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="a2fc4-246">NotifyIcon</span></span>|  
|<span data-ttu-id="a2fc4-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="a2fc4-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="a2fc4-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="a2fc4-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="a2fc4-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="a2fc4-249">PrintDialog</span></span>|  
|<span data-ttu-id="a2fc4-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="a2fc4-250">ProgressBar</span></span>|  
|<span data-ttu-id="a2fc4-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="a2fc4-251">RadioButton</span></span>|  
|<span data-ttu-id="a2fc4-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="a2fc4-252">RichTextBox</span></span>|  
|<span data-ttu-id="a2fc4-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="a2fc4-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="a2fc4-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="a2fc4-254">ScrollableControl</span></span>|  
|<span data-ttu-id="a2fc4-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="a2fc4-255">SoundPlayer</span></span>|  
|<span data-ttu-id="a2fc4-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="a2fc4-256">StatusBar</span></span>|  
|<span data-ttu-id="a2fc4-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="a2fc4-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="a2fc4-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="a2fc4-258">TextBox</span></span>|  
|<span data-ttu-id="a2fc4-259">타이머</span><span class="sxs-lookup"><span data-stu-id="a2fc4-259">Timer</span></span>|  
|<span data-ttu-id="a2fc4-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="a2fc4-260">Toolbar</span></span>|  
|<span data-ttu-id="a2fc4-261">도구 설명</span><span class="sxs-lookup"><span data-stu-id="a2fc4-261">ToolTip</span></span>|  
|<span data-ttu-id="a2fc4-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="a2fc4-262">TrackBar</span></span>|  
|<span data-ttu-id="a2fc4-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="a2fc4-263">TreeView</span></span>|  
|<span data-ttu-id="a2fc4-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="a2fc4-264">VscrollBar</span></span>|  
|<span data-ttu-id="a2fc4-265">웹 브라우저</span><span class="sxs-lookup"><span data-stu-id="a2fc4-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="a2fc4-266">다음 컨트롤은 Microsoft Active Accessibility에 대 한 지원을 통해서만 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="a2fc4-267">일부 기능은 사용하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2fc4-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="a2fc4-268">컨트롤 이름</span><span class="sxs-lookup"><span data-stu-id="a2fc4-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="a2fc4-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="a2fc4-269">BindingSource</span></span>|  
|<span data-ttu-id="a2fc4-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="a2fc4-270">DataGrid</span></span>|  
|<span data-ttu-id="a2fc4-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="a2fc4-271">DataGridView</span></span>|  
|<span data-ttu-id="a2fc4-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="a2fc4-272">DataNavigator</span></span>|  
|<span data-ttu-id="a2fc4-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="a2fc4-273">DomainUpDown</span></span>|  
|<span data-ttu-id="a2fc4-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="a2fc4-274">ErrorProvider</span></span>|  
|<span data-ttu-id="a2fc4-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a2fc4-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="a2fc4-276">Form</span><span class="sxs-lookup"><span data-stu-id="a2fc4-276">Form</span></span>|  
|<span data-ttu-id="a2fc4-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="a2fc4-277">LinkLabel</span></span>|  
|<span data-ttu-id="a2fc4-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="a2fc4-278">HelpProvider</span></span>|  
|<span data-ttu-id="a2fc4-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="a2fc4-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="a2fc4-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="a2fc4-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="a2fc4-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="a2fc4-281">NumericUpDown</span></span>|  
|<span data-ttu-id="a2fc4-282">패널</span><span class="sxs-lookup"><span data-stu-id="a2fc4-282">Panel</span></span>|  
|<span data-ttu-id="a2fc4-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="a2fc4-283">PictureBox</span></span>|  
|<span data-ttu-id="a2fc4-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="a2fc4-284">PrintDocument</span></span>|  
|<span data-ttu-id="a2fc4-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="a2fc4-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="a2fc4-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="a2fc4-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="a2fc4-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="a2fc4-287">PropertyGrid</span></span>|  
|<span data-ttu-id="a2fc4-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="a2fc4-288">UserControl</span></span>|  
|<span data-ttu-id="a2fc4-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="a2fc4-289">ToolStrip</span></span>|  
|<span data-ttu-id="a2fc4-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a2fc4-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="a2fc4-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="a2fc4-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="a2fc4-292">분할자</span><span class="sxs-lookup"><span data-stu-id="a2fc4-292">Splitter</span></span>|  
|<span data-ttu-id="a2fc4-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="a2fc4-293">RaftingContainer</span></span>|  
|<span data-ttu-id="a2fc4-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="a2fc4-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2fc4-295">참조</span><span class="sxs-lookup"><span data-stu-id="a2fc4-295">See also</span></span>

- [<span data-ttu-id="a2fc4-296">UI Automation Control Types</span><span class="sxs-lookup"><span data-stu-id="a2fc4-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
