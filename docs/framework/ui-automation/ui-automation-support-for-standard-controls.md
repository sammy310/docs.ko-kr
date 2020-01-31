---
title: 표준 컨트롤에 대한 UI 자동화 지원
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 49277073706444fd611ae41e762442388ac50b71
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789609"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="8bbb2-102">표준 컨트롤에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="8bbb2-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="8bbb2-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8bbb2-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="8bbb2-105">이 항목에는 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32 및 Windows Forms 프레임 워크 용으로 개발 된 응용 프로그램의 표준 컨트롤에 대 한 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 지원 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="8bbb2-106">WPF(Windows Presentation Foundation) 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8bbb2-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="8bbb2-107">사용자 상호 작용 지원 또는 정보를 제공하는 모든 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 요소에는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 전체 기본 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="8bbb2-108">패널 등과 같은 기타 요소는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="8bbb2-109">Win32 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8bbb2-109">Win32 Controls</span></span>  
 <span data-ttu-id="8bbb2-110">대부분의 Win32 컨트롤은 Uiautomationclientsideproviders.dll의 클라이언트 쪽 공급자를 통해 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-110">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="8bbb2-111">이 어셈블리는 UI 자동화 클라이언트 애플리케이션과 함께 사용할 수 있도록 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="8bbb2-112">*지원은 comctrl32.dll*버전 6의 컨트롤에 대해서만 전체 지원이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="8bbb2-113">다음과 같은 컨트롤이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="8bbb2-114">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="8bbb2-114">Class name</span></span>|<span data-ttu-id="8bbb2-115">컨트롤 종류</span><span class="sxs-lookup"><span data-stu-id="8bbb2-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="8bbb2-116">단추</span><span class="sxs-lookup"><span data-stu-id="8bbb2-116">Button</span></span>|<span data-ttu-id="8bbb2-117">단추</span><span class="sxs-lookup"><span data-stu-id="8bbb2-117">Button</span></span>|  
|<span data-ttu-id="8bbb2-118">단추</span><span class="sxs-lookup"><span data-stu-id="8bbb2-118">Button</span></span>|<span data-ttu-id="8bbb2-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="8bbb2-119">RadioButton</span></span>|  
|<span data-ttu-id="8bbb2-120">단추</span><span class="sxs-lookup"><span data-stu-id="8bbb2-120">Button</span></span>|<span data-ttu-id="8bbb2-121">그룹</span><span class="sxs-lookup"><span data-stu-id="8bbb2-121">Group</span></span>|  
|<span data-ttu-id="8bbb2-122">단추</span><span class="sxs-lookup"><span data-stu-id="8bbb2-122">Button</span></span>|<span data-ttu-id="8bbb2-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8bbb2-123">CheckBox</span></span>|  
|<span data-ttu-id="8bbb2-124">단추</span><span class="sxs-lookup"><span data-stu-id="8bbb2-124">Button</span></span>|<span data-ttu-id="8bbb2-125">하이퍼링크</span><span class="sxs-lookup"><span data-stu-id="8bbb2-125">Hyperlink</span></span>|  
|<span data-ttu-id="8bbb2-126">단추</span><span class="sxs-lookup"><span data-stu-id="8bbb2-126">Button</span></span>|<span data-ttu-id="8bbb2-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="8bbb2-127">SplitButton</span></span>|  
|<span data-ttu-id="8bbb2-128">단추</span><span class="sxs-lookup"><span data-stu-id="8bbb2-128">Button</span></span>|<span data-ttu-id="8bbb2-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8bbb2-129">CheckBox</span></span>|  
|<span data-ttu-id="8bbb2-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-130">ComboBoxEx32</span></span>|<span data-ttu-id="8bbb2-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8bbb2-131">ComboBox</span></span>|  
|<span data-ttu-id="8bbb2-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8bbb2-132">ComboBox</span></span>|<span data-ttu-id="8bbb2-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8bbb2-133">ComboBox</span></span>|  
|<span data-ttu-id="8bbb2-134">Edit</span><span class="sxs-lookup"><span data-stu-id="8bbb2-134">Edit</span></span>|<span data-ttu-id="8bbb2-135">문서</span><span class="sxs-lookup"><span data-stu-id="8bbb2-135">Document</span></span>|  
|<span data-ttu-id="8bbb2-136">Edit</span><span class="sxs-lookup"><span data-stu-id="8bbb2-136">Edit</span></span>|<span data-ttu-id="8bbb2-137">Edit</span><span class="sxs-lookup"><span data-stu-id="8bbb2-137">Edit</span></span>|  
|<span data-ttu-id="8bbb2-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="8bbb2-138">SysLink</span></span>|<span data-ttu-id="8bbb2-139">하이퍼링크</span><span class="sxs-lookup"><span data-stu-id="8bbb2-139">Hyperlink</span></span>|  
|<span data-ttu-id="8bbb2-140">Static</span><span class="sxs-lookup"><span data-stu-id="8bbb2-140">Static</span></span>|<span data-ttu-id="8bbb2-141">텍스트</span><span class="sxs-lookup"><span data-stu-id="8bbb2-141">Text</span></span>|  
|<span data-ttu-id="8bbb2-142">Static</span><span class="sxs-lookup"><span data-stu-id="8bbb2-142">Static</span></span>|<span data-ttu-id="8bbb2-143">이미지</span><span class="sxs-lookup"><span data-stu-id="8bbb2-143">Image</span></span>|  
|<span data-ttu-id="8bbb2-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-144">SysIPAddress32</span></span>|<span data-ttu-id="8bbb2-145">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8bbb2-145">Custom</span></span>|  
|<span data-ttu-id="8bbb2-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-146">SysHeader32</span></span>|<span data-ttu-id="8bbb2-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="8bbb2-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="8bbb2-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-148">SysListView32</span></span>|<span data-ttu-id="8bbb2-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="8bbb2-149">DataGrid</span></span>|  
|<span data-ttu-id="8bbb2-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-150">SysListView32</span></span>|<span data-ttu-id="8bbb2-151">목록</span><span class="sxs-lookup"><span data-stu-id="8bbb2-151">List</span></span>|  
|<span data-ttu-id="8bbb2-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="8bbb2-152">ListBox</span></span>|<span data-ttu-id="8bbb2-153">목록</span><span class="sxs-lookup"><span data-stu-id="8bbb2-153">List</span></span>|  
|<span data-ttu-id="8bbb2-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="8bbb2-154">ListBox</span></span>|<span data-ttu-id="8bbb2-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="8bbb2-155">ListItem</span></span>|  
|<span data-ttu-id="8bbb2-156">#32768</span><span class="sxs-lookup"><span data-stu-id="8bbb2-156">#32768</span></span>|<span data-ttu-id="8bbb2-157">메뉴</span><span class="sxs-lookup"><span data-stu-id="8bbb2-157">Menu</span></span>|  
|<span data-ttu-id="8bbb2-158">#32768</span><span class="sxs-lookup"><span data-stu-id="8bbb2-158">#32768</span></span>|<span data-ttu-id="8bbb2-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="8bbb2-159">MenuItem</span></span>|  
|<span data-ttu-id="8bbb2-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-160">msctls_progress32</span></span>|<span data-ttu-id="8bbb2-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="8bbb2-161">ProgressBar</span></span>|  
|<span data-ttu-id="8bbb2-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="8bbb2-162">RichEdit</span></span>|<span data-ttu-id="8bbb2-163">문서.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-163">Document.</span></span> <span data-ttu-id="8bbb2-164">메모를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-164">See note.</span></span>|  
|<span data-ttu-id="8bbb2-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="8bbb2-165">RichEdit20A</span></span>|<span data-ttu-id="8bbb2-166">문서</span><span class="sxs-lookup"><span data-stu-id="8bbb2-166">Document</span></span>|  
|<span data-ttu-id="8bbb2-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="8bbb2-167">RichEdit20W</span></span>|<span data-ttu-id="8bbb2-168">문서</span><span class="sxs-lookup"><span data-stu-id="8bbb2-168">Document</span></span>|  
|<span data-ttu-id="8bbb2-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="8bbb2-169">RichEdit50W</span></span>|<span data-ttu-id="8bbb2-170">문서</span><span class="sxs-lookup"><span data-stu-id="8bbb2-170">Document</span></span>|  
|<span data-ttu-id="8bbb2-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="8bbb2-171">ScrollBar</span></span>|<span data-ttu-id="8bbb2-172">슬라이더</span><span class="sxs-lookup"><span data-stu-id="8bbb2-172">Slider</span></span>|  
|<span data-ttu-id="8bbb2-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-173">msctls_trackbar32</span></span>|<span data-ttu-id="8bbb2-174">슬라이더</span><span class="sxs-lookup"><span data-stu-id="8bbb2-174">Slider</span></span>|  
|<span data-ttu-id="8bbb2-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-175">msctls_updown32</span></span>|<span data-ttu-id="8bbb2-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="8bbb2-176">Spinner</span></span>|  
|<span data-ttu-id="8bbb2-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-177">msctls_statusbar32</span></span>|<span data-ttu-id="8bbb2-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="8bbb2-178">StatusBar</span></span>|  
|<span data-ttu-id="8bbb2-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-179">SysTabControl32</span></span>|<span data-ttu-id="8bbb2-180">탭</span><span class="sxs-lookup"><span data-stu-id="8bbb2-180">Tab</span></span>|  
|<span data-ttu-id="8bbb2-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-181">SysTabControl32</span></span>|<span data-ttu-id="8bbb2-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="8bbb2-182">TabItem</span></span>|  
|<span data-ttu-id="8bbb2-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-183">ToolbarWindow32</span></span>|<span data-ttu-id="8bbb2-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="8bbb2-184">ToolBar</span></span>|  
|<span data-ttu-id="8bbb2-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-185">ToolbarWindow32</span></span>|<span data-ttu-id="8bbb2-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="8bbb2-186">MenuItem</span></span>|  
|<span data-ttu-id="8bbb2-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-187">ToolbarWindow32</span></span>|<span data-ttu-id="8bbb2-188">단추</span><span class="sxs-lookup"><span data-stu-id="8bbb2-188">Button</span></span>|  
|<span data-ttu-id="8bbb2-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-189">ToolbarWindow32</span></span>|<span data-ttu-id="8bbb2-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8bbb2-190">CheckBox</span></span>|  
|<span data-ttu-id="8bbb2-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-191">ToolbarWindow32</span></span>|<span data-ttu-id="8bbb2-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="8bbb2-192">RadioButton</span></span>|  
|<span data-ttu-id="8bbb2-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-193">ToolbarWindow32</span></span>|<span data-ttu-id="8bbb2-194">구분 기호</span><span class="sxs-lookup"><span data-stu-id="8bbb2-194">Separator</span></span>|  
|<span data-ttu-id="8bbb2-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-195">tooltips_class32</span></span>|<span data-ttu-id="8bbb2-196">도구 설명</span><span class="sxs-lookup"><span data-stu-id="8bbb2-196">ToolTip</span></span>|  
|<span data-ttu-id="8bbb2-197">#32774</span><span class="sxs-lookup"><span data-stu-id="8bbb2-197">#32774</span></span>|<span data-ttu-id="8bbb2-198">도구 설명</span><span class="sxs-lookup"><span data-stu-id="8bbb2-198">ToolTip</span></span>|  
|<span data-ttu-id="8bbb2-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-199">ReBarWindow32</span></span>|<span data-ttu-id="8bbb2-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="8bbb2-200">Toolbar</span></span>|  
|<span data-ttu-id="8bbb2-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-201">SysTreeView32</span></span>|<span data-ttu-id="8bbb2-202">Tree</span><span class="sxs-lookup"><span data-stu-id="8bbb2-202">Tree</span></span>|  
|<span data-ttu-id="8bbb2-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-203">SysTreeView32</span></span>|<span data-ttu-id="8bbb2-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="8bbb2-204">TreeItem</span></span>|  
  
 <span data-ttu-id="8bbb2-205">**참고** RichEdit 컨트롤은 Windows Vista와 함께 제공 되는 버전에 대해서만 지원 됩니다 (Riched20.dll 버전 3.1 이상 및 Msftedit.dll 버전 4.1 이상).</span><span class="sxs-lookup"><span data-stu-id="8bbb2-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="8bbb2-206">다음 컨트롤은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="8bbb2-207">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="8bbb2-207">Class name</span></span>|<span data-ttu-id="8bbb2-208">컨트롤 종류</span><span class="sxs-lookup"><span data-stu-id="8bbb2-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="8bbb2-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-209">SysAnimate32</span></span>|<span data-ttu-id="8bbb2-210">이미지</span><span class="sxs-lookup"><span data-stu-id="8bbb2-210">Image</span></span>|  
|<span data-ttu-id="8bbb2-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="8bbb2-211">SysPager</span></span>|<span data-ttu-id="8bbb2-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="8bbb2-212">Spinner</span></span>|  
|<span data-ttu-id="8bbb2-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-213">SysDateTimePick32</span></span>|<span data-ttu-id="8bbb2-214">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8bbb2-214">Custom</span></span>|  
|<span data-ttu-id="8bbb2-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="8bbb2-215">SysMonthCal32</span></span>|<span data-ttu-id="8bbb2-216">일정</span><span class="sxs-lookup"><span data-stu-id="8bbb2-216">Calendar</span></span>|  
|<span data-ttu-id="8bbb2-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="8bbb2-217">MS_WINNOTE</span></span>|<span data-ttu-id="8bbb2-218">도구 설명</span><span class="sxs-lookup"><span data-stu-id="8bbb2-218">Tooltip</span></span>|  
|<span data-ttu-id="8bbb2-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="8bbb2-219">VBBubble</span></span>|<span data-ttu-id="8bbb2-220">도구 설명</span><span class="sxs-lookup"><span data-stu-id="8bbb2-220">Tooltip</span></span>|  
|<span data-ttu-id="8bbb2-221">스크롤 막대(독립 실행형 컨트롤로 사용되는 경우)</span><span class="sxs-lookup"><span data-stu-id="8bbb2-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="8bbb2-222">슬라이더</span><span class="sxs-lookup"><span data-stu-id="8bbb2-222">Slider</span></span>|  
|<span data-ttu-id="8bbb2-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="8bbb2-223">SuperGrid</span></span>|<span data-ttu-id="8bbb2-224">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8bbb2-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="8bbb2-225">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8bbb2-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="8bbb2-226">Windows Forms 컨트롤은 Uiautomationclientsideproviders.dll의 클라이언트 쪽 공급자를 통해 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="8bbb2-227">이 어셈블리는 UI 자동화 클라이언트 애플리케이션과 함께 사용할 수 있도록 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="8bbb2-228">일반적으로 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서 Win32 공용 컨트롤에 대 한 관리 되는 래퍼로 Windows Forms 컨트롤을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-228">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="8bbb2-229">다음과 같은 컨트롤이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="8bbb2-230">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="8bbb2-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="8bbb2-231">단추</span><span class="sxs-lookup"><span data-stu-id="8bbb2-231">Button</span></span>|  
|<span data-ttu-id="8bbb2-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8bbb2-232">CheckBox</span></span>|  
|<span data-ttu-id="8bbb2-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="8bbb2-233">CheckedListBox</span></span>|  
|<span data-ttu-id="8bbb2-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="8bbb2-234">ColorDialog</span></span>|  
|<span data-ttu-id="8bbb2-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8bbb2-235">ComboBox</span></span>|  
|<span data-ttu-id="8bbb2-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="8bbb2-236">FolderBrowser</span></span>|  
|<span data-ttu-id="8bbb2-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="8bbb2-237">FontDialog</span></span>|  
|<span data-ttu-id="8bbb2-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="8bbb2-238">GroupBox</span></span>|  
|<span data-ttu-id="8bbb2-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="8bbb2-239">HscrollBar</span></span>|  
|<span data-ttu-id="8bbb2-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="8bbb2-240">ImageList</span></span>|  
|<span data-ttu-id="8bbb2-241">레이블</span><span class="sxs-lookup"><span data-stu-id="8bbb2-241">Label</span></span>|  
|<span data-ttu-id="8bbb2-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="8bbb2-242">ListBox</span></span>|  
|<span data-ttu-id="8bbb2-243">ListView</span><span class="sxs-lookup"><span data-stu-id="8bbb2-243">ListView</span></span>|  
|<span data-ttu-id="8bbb2-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="8bbb2-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="8bbb2-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="8bbb2-245">MonthCalendar</span></span>|  
|<span data-ttu-id="8bbb2-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="8bbb2-246">NotifyIcon</span></span>|  
|<span data-ttu-id="8bbb2-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="8bbb2-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="8bbb2-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="8bbb2-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="8bbb2-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="8bbb2-249">PrintDialog</span></span>|  
|<span data-ttu-id="8bbb2-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="8bbb2-250">ProgressBar</span></span>|  
|<span data-ttu-id="8bbb2-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="8bbb2-251">RadioButton</span></span>|  
|<span data-ttu-id="8bbb2-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="8bbb2-252">RichTextBox</span></span>|  
|<span data-ttu-id="8bbb2-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="8bbb2-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="8bbb2-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="8bbb2-254">ScrollableControl</span></span>|  
|<span data-ttu-id="8bbb2-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="8bbb2-255">SoundPlayer</span></span>|  
|<span data-ttu-id="8bbb2-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="8bbb2-256">StatusBar</span></span>|  
|<span data-ttu-id="8bbb2-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="8bbb2-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="8bbb2-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="8bbb2-258">TextBox</span></span>|  
|<span data-ttu-id="8bbb2-259">타이머</span><span class="sxs-lookup"><span data-stu-id="8bbb2-259">Timer</span></span>|  
|<span data-ttu-id="8bbb2-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="8bbb2-260">Toolbar</span></span>|  
|<span data-ttu-id="8bbb2-261">도구 설명</span><span class="sxs-lookup"><span data-stu-id="8bbb2-261">ToolTip</span></span>|  
|<span data-ttu-id="8bbb2-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="8bbb2-262">TrackBar</span></span>|  
|<span data-ttu-id="8bbb2-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="8bbb2-263">TreeView</span></span>|  
|<span data-ttu-id="8bbb2-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="8bbb2-264">VscrollBar</span></span>|  
|<span data-ttu-id="8bbb2-265">웹 브라우저</span><span class="sxs-lookup"><span data-stu-id="8bbb2-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="8bbb2-266">다음 컨트롤은 Microsoft Active Accessibility에 대 한 지원을 통해서만 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="8bbb2-267">일부 기능은 사용하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb2-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="8bbb2-268">컨트롤 이름</span><span class="sxs-lookup"><span data-stu-id="8bbb2-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="8bbb2-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="8bbb2-269">BindingSource</span></span>|  
|<span data-ttu-id="8bbb2-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="8bbb2-270">DataGrid</span></span>|  
|<span data-ttu-id="8bbb2-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="8bbb2-271">DataGridView</span></span>|  
|<span data-ttu-id="8bbb2-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="8bbb2-272">DataNavigator</span></span>|  
|<span data-ttu-id="8bbb2-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="8bbb2-273">DomainUpDown</span></span>|  
|<span data-ttu-id="8bbb2-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="8bbb2-274">ErrorProvider</span></span>|  
|<span data-ttu-id="8bbb2-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8bbb2-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="8bbb2-276">Form</span><span class="sxs-lookup"><span data-stu-id="8bbb2-276">Form</span></span>|  
|<span data-ttu-id="8bbb2-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="8bbb2-277">LinkLabel</span></span>|  
|<span data-ttu-id="8bbb2-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="8bbb2-278">HelpProvider</span></span>|  
|<span data-ttu-id="8bbb2-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="8bbb2-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="8bbb2-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="8bbb2-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="8bbb2-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="8bbb2-281">NumericUpDown</span></span>|  
|<span data-ttu-id="8bbb2-282">패널</span><span class="sxs-lookup"><span data-stu-id="8bbb2-282">Panel</span></span>|  
|<span data-ttu-id="8bbb2-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="8bbb2-283">PictureBox</span></span>|  
|<span data-ttu-id="8bbb2-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="8bbb2-284">PrintDocument</span></span>|  
|<span data-ttu-id="8bbb2-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="8bbb2-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="8bbb2-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="8bbb2-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="8bbb2-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="8bbb2-287">PropertyGrid</span></span>|  
|<span data-ttu-id="8bbb2-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="8bbb2-288">UserControl</span></span>|  
|<span data-ttu-id="8bbb2-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="8bbb2-289">ToolStrip</span></span>|  
|<span data-ttu-id="8bbb2-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8bbb2-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="8bbb2-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="8bbb2-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="8bbb2-292">분할자</span><span class="sxs-lookup"><span data-stu-id="8bbb2-292">Splitter</span></span>|  
|<span data-ttu-id="8bbb2-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="8bbb2-293">RaftingContainer</span></span>|  
|<span data-ttu-id="8bbb2-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="8bbb2-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8bbb2-295">참조</span><span class="sxs-lookup"><span data-stu-id="8bbb2-295">See also</span></span>

- [<span data-ttu-id="8bbb2-296">UI 자동화 컨트롤 형식</span><span class="sxs-lookup"><span data-stu-id="8bbb2-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
