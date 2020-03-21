---
title: 표준 컨트롤에 대한 UI 자동화 지원
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 36028d589e98177f6a0e83092edd656860b1a8d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179858"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="3b0b8-102">표준 컨트롤에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="3b0b8-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="3b0b8-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="3b0b8-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="3b0b8-105">이 항목에는 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]에서 , Win32 및 Windows Forms 프레임워크에 대해 개발된 응용 프로그램의 표준 컨트롤 지원에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="3b0b8-106">WPF(Windows Presentation Foundation) 컨트롤</span><span class="sxs-lookup"><span data-stu-id="3b0b8-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="3b0b8-107">사용자 상호 작용 지원 또는 정보를 제공하는 모든 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 요소에는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 전체 기본 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="3b0b8-108">패널 등과 같은 기타 요소는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a><span data-ttu-id="3b0b8-109">Win32 컨트롤</span><span class="sxs-lookup"><span data-stu-id="3b0b8-109">Win32 Controls</span></span>  
 <span data-ttu-id="3b0b8-110">대부분의 Win32 컨트롤은 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] UIAutomationClientsideProviders.dll의 클라이언트 측 공급자를 통해 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-110">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="3b0b8-111">이 어셈블리는 UI 자동화 클라이언트 애플리케이션과 함께 사용할 수 있도록 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="3b0b8-112">전체 지원은 *ComCtrl32.dll의*버전 6의 컨트롤에 대해서만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="3b0b8-113">다음과 같은 컨트롤이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="3b0b8-114">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="3b0b8-114">Class name</span></span>|<span data-ttu-id="3b0b8-115">컨트롤 종류</span><span class="sxs-lookup"><span data-stu-id="3b0b8-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="3b0b8-116">단추</span><span class="sxs-lookup"><span data-stu-id="3b0b8-116">Button</span></span>|<span data-ttu-id="3b0b8-117">단추</span><span class="sxs-lookup"><span data-stu-id="3b0b8-117">Button</span></span>|  
|<span data-ttu-id="3b0b8-118">단추</span><span class="sxs-lookup"><span data-stu-id="3b0b8-118">Button</span></span>|<span data-ttu-id="3b0b8-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="3b0b8-119">RadioButton</span></span>|  
|<span data-ttu-id="3b0b8-120">단추</span><span class="sxs-lookup"><span data-stu-id="3b0b8-120">Button</span></span>|<span data-ttu-id="3b0b8-121">그룹</span><span class="sxs-lookup"><span data-stu-id="3b0b8-121">Group</span></span>|  
|<span data-ttu-id="3b0b8-122">단추</span><span class="sxs-lookup"><span data-stu-id="3b0b8-122">Button</span></span>|<span data-ttu-id="3b0b8-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="3b0b8-123">CheckBox</span></span>|  
|<span data-ttu-id="3b0b8-124">단추</span><span class="sxs-lookup"><span data-stu-id="3b0b8-124">Button</span></span>|<span data-ttu-id="3b0b8-125">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="3b0b8-125">Hyperlink</span></span>|  
|<span data-ttu-id="3b0b8-126">단추</span><span class="sxs-lookup"><span data-stu-id="3b0b8-126">Button</span></span>|<span data-ttu-id="3b0b8-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="3b0b8-127">SplitButton</span></span>|  
|<span data-ttu-id="3b0b8-128">단추</span><span class="sxs-lookup"><span data-stu-id="3b0b8-128">Button</span></span>|<span data-ttu-id="3b0b8-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="3b0b8-129">CheckBox</span></span>|  
|<span data-ttu-id="3b0b8-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-130">ComboBoxEx32</span></span>|<span data-ttu-id="3b0b8-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="3b0b8-131">ComboBox</span></span>|  
|<span data-ttu-id="3b0b8-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="3b0b8-132">ComboBox</span></span>|<span data-ttu-id="3b0b8-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="3b0b8-133">ComboBox</span></span>|  
|<span data-ttu-id="3b0b8-134">편집</span><span class="sxs-lookup"><span data-stu-id="3b0b8-134">Edit</span></span>|<span data-ttu-id="3b0b8-135">문서</span><span class="sxs-lookup"><span data-stu-id="3b0b8-135">Document</span></span>|  
|<span data-ttu-id="3b0b8-136">편집</span><span class="sxs-lookup"><span data-stu-id="3b0b8-136">Edit</span></span>|<span data-ttu-id="3b0b8-137">편집</span><span class="sxs-lookup"><span data-stu-id="3b0b8-137">Edit</span></span>|  
|<span data-ttu-id="3b0b8-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="3b0b8-138">SysLink</span></span>|<span data-ttu-id="3b0b8-139">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="3b0b8-139">Hyperlink</span></span>|  
|<span data-ttu-id="3b0b8-140">정적</span><span class="sxs-lookup"><span data-stu-id="3b0b8-140">Static</span></span>|<span data-ttu-id="3b0b8-141">텍스트</span><span class="sxs-lookup"><span data-stu-id="3b0b8-141">Text</span></span>|  
|<span data-ttu-id="3b0b8-142">정적</span><span class="sxs-lookup"><span data-stu-id="3b0b8-142">Static</span></span>|<span data-ttu-id="3b0b8-143">이미지</span><span class="sxs-lookup"><span data-stu-id="3b0b8-143">Image</span></span>|  
|<span data-ttu-id="3b0b8-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-144">SysIPAddress32</span></span>|<span data-ttu-id="3b0b8-145">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3b0b8-145">Custom</span></span>|  
|<span data-ttu-id="3b0b8-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-146">SysHeader32</span></span>|<span data-ttu-id="3b0b8-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="3b0b8-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="3b0b8-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-148">SysListView32</span></span>|<span data-ttu-id="3b0b8-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="3b0b8-149">DataGrid</span></span>|  
|<span data-ttu-id="3b0b8-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-150">SysListView32</span></span>|<span data-ttu-id="3b0b8-151">목록</span><span class="sxs-lookup"><span data-stu-id="3b0b8-151">List</span></span>|  
|<span data-ttu-id="3b0b8-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="3b0b8-152">ListBox</span></span>|<span data-ttu-id="3b0b8-153">목록</span><span class="sxs-lookup"><span data-stu-id="3b0b8-153">List</span></span>|  
|<span data-ttu-id="3b0b8-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="3b0b8-154">ListBox</span></span>|<span data-ttu-id="3b0b8-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="3b0b8-155">ListItem</span></span>|  
|<span data-ttu-id="3b0b8-156">#32768</span><span class="sxs-lookup"><span data-stu-id="3b0b8-156">#32768</span></span>|<span data-ttu-id="3b0b8-157">메뉴</span><span class="sxs-lookup"><span data-stu-id="3b0b8-157">Menu</span></span>|  
|<span data-ttu-id="3b0b8-158">#32768</span><span class="sxs-lookup"><span data-stu-id="3b0b8-158">#32768</span></span>|<span data-ttu-id="3b0b8-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="3b0b8-159">MenuItem</span></span>|  
|<span data-ttu-id="3b0b8-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-160">msctls_progress32</span></span>|<span data-ttu-id="3b0b8-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="3b0b8-161">ProgressBar</span></span>|  
|<span data-ttu-id="3b0b8-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="3b0b8-162">RichEdit</span></span>|<span data-ttu-id="3b0b8-163">문서입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-163">Document.</span></span> <span data-ttu-id="3b0b8-164">메모를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-164">See note.</span></span>|  
|<span data-ttu-id="3b0b8-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="3b0b8-165">RichEdit20A</span></span>|<span data-ttu-id="3b0b8-166">문서</span><span class="sxs-lookup"><span data-stu-id="3b0b8-166">Document</span></span>|  
|<span data-ttu-id="3b0b8-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="3b0b8-167">RichEdit20W</span></span>|<span data-ttu-id="3b0b8-168">문서</span><span class="sxs-lookup"><span data-stu-id="3b0b8-168">Document</span></span>|  
|<span data-ttu-id="3b0b8-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="3b0b8-169">RichEdit50W</span></span>|<span data-ttu-id="3b0b8-170">문서</span><span class="sxs-lookup"><span data-stu-id="3b0b8-170">Document</span></span>|  
|<span data-ttu-id="3b0b8-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="3b0b8-171">ScrollBar</span></span>|<span data-ttu-id="3b0b8-172">슬라이더</span><span class="sxs-lookup"><span data-stu-id="3b0b8-172">Slider</span></span>|  
|<span data-ttu-id="3b0b8-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-173">msctls_trackbar32</span></span>|<span data-ttu-id="3b0b8-174">슬라이더</span><span class="sxs-lookup"><span data-stu-id="3b0b8-174">Slider</span></span>|  
|<span data-ttu-id="3b0b8-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-175">msctls_updown32</span></span>|<span data-ttu-id="3b0b8-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="3b0b8-176">Spinner</span></span>|  
|<span data-ttu-id="3b0b8-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-177">msctls_statusbar32</span></span>|<span data-ttu-id="3b0b8-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="3b0b8-178">StatusBar</span></span>|  
|<span data-ttu-id="3b0b8-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-179">SysTabControl32</span></span>|<span data-ttu-id="3b0b8-180">탭</span><span class="sxs-lookup"><span data-stu-id="3b0b8-180">Tab</span></span>|  
|<span data-ttu-id="3b0b8-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-181">SysTabControl32</span></span>|<span data-ttu-id="3b0b8-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="3b0b8-182">TabItem</span></span>|  
|<span data-ttu-id="3b0b8-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-183">ToolbarWindow32</span></span>|<span data-ttu-id="3b0b8-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="3b0b8-184">ToolBar</span></span>|  
|<span data-ttu-id="3b0b8-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-185">ToolbarWindow32</span></span>|<span data-ttu-id="3b0b8-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="3b0b8-186">MenuItem</span></span>|  
|<span data-ttu-id="3b0b8-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-187">ToolbarWindow32</span></span>|<span data-ttu-id="3b0b8-188">단추</span><span class="sxs-lookup"><span data-stu-id="3b0b8-188">Button</span></span>|  
|<span data-ttu-id="3b0b8-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-189">ToolbarWindow32</span></span>|<span data-ttu-id="3b0b8-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="3b0b8-190">CheckBox</span></span>|  
|<span data-ttu-id="3b0b8-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-191">ToolbarWindow32</span></span>|<span data-ttu-id="3b0b8-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="3b0b8-192">RadioButton</span></span>|  
|<span data-ttu-id="3b0b8-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-193">ToolbarWindow32</span></span>|<span data-ttu-id="3b0b8-194">구분 기호</span><span class="sxs-lookup"><span data-stu-id="3b0b8-194">Separator</span></span>|  
|<span data-ttu-id="3b0b8-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-195">tooltips_class32</span></span>|<span data-ttu-id="3b0b8-196">도구 설명</span><span class="sxs-lookup"><span data-stu-id="3b0b8-196">ToolTip</span></span>|  
|<span data-ttu-id="3b0b8-197">#32774</span><span class="sxs-lookup"><span data-stu-id="3b0b8-197">#32774</span></span>|<span data-ttu-id="3b0b8-198">도구 설명</span><span class="sxs-lookup"><span data-stu-id="3b0b8-198">ToolTip</span></span>|  
|<span data-ttu-id="3b0b8-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-199">ReBarWindow32</span></span>|<span data-ttu-id="3b0b8-200">도구 모음</span><span class="sxs-lookup"><span data-stu-id="3b0b8-200">Toolbar</span></span>|  
|<span data-ttu-id="3b0b8-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-201">SysTreeView32</span></span>|<span data-ttu-id="3b0b8-202">트리</span><span class="sxs-lookup"><span data-stu-id="3b0b8-202">Tree</span></span>|  
|<span data-ttu-id="3b0b8-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-203">SysTreeView32</span></span>|<span data-ttu-id="3b0b8-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="3b0b8-204">TreeItem</span></span>|  
  
 <span data-ttu-id="3b0b8-205">**참고 사항** RichEdit 컨트롤은 Windows Vista와 함께 제공된 버전(RichEd20.dll 버전 3.1 이상 및 MsftEdit.dll 버전 4.1 이상)에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="3b0b8-206">다음 컨트롤은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="3b0b8-207">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="3b0b8-207">Class name</span></span>|<span data-ttu-id="3b0b8-208">컨트롤 종류</span><span class="sxs-lookup"><span data-stu-id="3b0b8-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="3b0b8-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-209">SysAnimate32</span></span>|<span data-ttu-id="3b0b8-210">이미지</span><span class="sxs-lookup"><span data-stu-id="3b0b8-210">Image</span></span>|  
|<span data-ttu-id="3b0b8-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="3b0b8-211">SysPager</span></span>|<span data-ttu-id="3b0b8-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="3b0b8-212">Spinner</span></span>|  
|<span data-ttu-id="3b0b8-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-213">SysDateTimePick32</span></span>|<span data-ttu-id="3b0b8-214">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3b0b8-214">Custom</span></span>|  
|<span data-ttu-id="3b0b8-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="3b0b8-215">SysMonthCal32</span></span>|<span data-ttu-id="3b0b8-216">달력</span><span class="sxs-lookup"><span data-stu-id="3b0b8-216">Calendar</span></span>|  
|<span data-ttu-id="3b0b8-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="3b0b8-217">MS_WINNOTE</span></span>|<span data-ttu-id="3b0b8-218">도구 설명</span><span class="sxs-lookup"><span data-stu-id="3b0b8-218">Tooltip</span></span>|  
|<span data-ttu-id="3b0b8-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="3b0b8-219">VBBubble</span></span>|<span data-ttu-id="3b0b8-220">도구 설명</span><span class="sxs-lookup"><span data-stu-id="3b0b8-220">Tooltip</span></span>|  
|<span data-ttu-id="3b0b8-221">스크롤 막대(독립 실행형 컨트롤로 사용되는 경우)</span><span class="sxs-lookup"><span data-stu-id="3b0b8-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="3b0b8-222">슬라이더</span><span class="sxs-lookup"><span data-stu-id="3b0b8-222">Slider</span></span>|  
|<span data-ttu-id="3b0b8-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="3b0b8-223">SuperGrid</span></span>|<span data-ttu-id="3b0b8-224">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3b0b8-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a><span data-ttu-id="3b0b8-225">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="3b0b8-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="3b0b8-226">Windows 양식 컨트롤은 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] UIAutomationClientsideProviders.dll의 클라이언트 쪽 공급자를 통해 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="3b0b8-227">이 어셈블리는 UI 자동화 클라이언트 애플리케이션과 함께 사용할 수 있도록 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="3b0b8-228">일반적으로 Win32 일반 컨트롤에 대해 관리되는 래퍼가 관리되는 Windows Forms 컨트롤은 에서 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-228">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="3b0b8-229">다음과 같은 컨트롤이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="3b0b8-230">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="3b0b8-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="3b0b8-231">단추</span><span class="sxs-lookup"><span data-stu-id="3b0b8-231">Button</span></span>|  
|<span data-ttu-id="3b0b8-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="3b0b8-232">CheckBox</span></span>|  
|<span data-ttu-id="3b0b8-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="3b0b8-233">CheckedListBox</span></span>|  
|<span data-ttu-id="3b0b8-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="3b0b8-234">ColorDialog</span></span>|  
|<span data-ttu-id="3b0b8-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="3b0b8-235">ComboBox</span></span>|  
|<span data-ttu-id="3b0b8-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="3b0b8-236">FolderBrowser</span></span>|  
|<span data-ttu-id="3b0b8-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="3b0b8-237">FontDialog</span></span>|  
|<span data-ttu-id="3b0b8-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="3b0b8-238">GroupBox</span></span>|  
|<span data-ttu-id="3b0b8-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="3b0b8-239">HscrollBar</span></span>|  
|<span data-ttu-id="3b0b8-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="3b0b8-240">ImageList</span></span>|  
|<span data-ttu-id="3b0b8-241">레이블</span><span class="sxs-lookup"><span data-stu-id="3b0b8-241">Label</span></span>|  
|<span data-ttu-id="3b0b8-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="3b0b8-242">ListBox</span></span>|  
|<span data-ttu-id="3b0b8-243">ListView</span><span class="sxs-lookup"><span data-stu-id="3b0b8-243">ListView</span></span>|  
|<span data-ttu-id="3b0b8-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="3b0b8-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="3b0b8-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="3b0b8-245">MonthCalendar</span></span>|  
|<span data-ttu-id="3b0b8-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="3b0b8-246">NotifyIcon</span></span>|  
|<span data-ttu-id="3b0b8-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="3b0b8-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="3b0b8-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="3b0b8-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="3b0b8-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="3b0b8-249">PrintDialog</span></span>|  
|<span data-ttu-id="3b0b8-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="3b0b8-250">ProgressBar</span></span>|  
|<span data-ttu-id="3b0b8-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="3b0b8-251">RadioButton</span></span>|  
|<span data-ttu-id="3b0b8-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="3b0b8-252">RichTextBox</span></span>|  
|<span data-ttu-id="3b0b8-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="3b0b8-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="3b0b8-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="3b0b8-254">ScrollableControl</span></span>|  
|<span data-ttu-id="3b0b8-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="3b0b8-255">SoundPlayer</span></span>|  
|<span data-ttu-id="3b0b8-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="3b0b8-256">StatusBar</span></span>|  
|<span data-ttu-id="3b0b8-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="3b0b8-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="3b0b8-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="3b0b8-258">TextBox</span></span>|  
|<span data-ttu-id="3b0b8-259">Timer</span><span class="sxs-lookup"><span data-stu-id="3b0b8-259">Timer</span></span>|  
|<span data-ttu-id="3b0b8-260">도구 모음</span><span class="sxs-lookup"><span data-stu-id="3b0b8-260">Toolbar</span></span>|  
|<span data-ttu-id="3b0b8-261">도구 설명</span><span class="sxs-lookup"><span data-stu-id="3b0b8-261">ToolTip</span></span>|  
|<span data-ttu-id="3b0b8-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="3b0b8-262">TrackBar</span></span>|  
|<span data-ttu-id="3b0b8-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="3b0b8-263">TreeView</span></span>|  
|<span data-ttu-id="3b0b8-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="3b0b8-264">VscrollBar</span></span>|  
|<span data-ttu-id="3b0b8-265">웹 브라우저</span><span class="sxs-lookup"><span data-stu-id="3b0b8-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="3b0b8-266">다음 컨트롤은 Microsoft [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 활성 접근성에 대한 지원을 통해서만 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="3b0b8-267">일부 기능은 사용하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0b8-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="3b0b8-268">컨트롤 이름</span><span class="sxs-lookup"><span data-stu-id="3b0b8-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="3b0b8-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="3b0b8-269">BindingSource</span></span>|  
|<span data-ttu-id="3b0b8-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="3b0b8-270">DataGrid</span></span>|  
|<span data-ttu-id="3b0b8-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="3b0b8-271">DataGridView</span></span>|  
|<span data-ttu-id="3b0b8-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="3b0b8-272">DataNavigator</span></span>|  
|<span data-ttu-id="3b0b8-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="3b0b8-273">DomainUpDown</span></span>|  
|<span data-ttu-id="3b0b8-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="3b0b8-274">ErrorProvider</span></span>|  
|<span data-ttu-id="3b0b8-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="3b0b8-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="3b0b8-276">Form</span><span class="sxs-lookup"><span data-stu-id="3b0b8-276">Form</span></span>|  
|<span data-ttu-id="3b0b8-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="3b0b8-277">LinkLabel</span></span>|  
|<span data-ttu-id="3b0b8-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="3b0b8-278">HelpProvider</span></span>|  
|<span data-ttu-id="3b0b8-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="3b0b8-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="3b0b8-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="3b0b8-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="3b0b8-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="3b0b8-281">NumericUpDown</span></span>|  
|<span data-ttu-id="3b0b8-282">패널</span><span class="sxs-lookup"><span data-stu-id="3b0b8-282">Panel</span></span>|  
|<span data-ttu-id="3b0b8-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="3b0b8-283">PictureBox</span></span>|  
|<span data-ttu-id="3b0b8-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="3b0b8-284">PrintDocument</span></span>|  
|<span data-ttu-id="3b0b8-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="3b0b8-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="3b0b8-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="3b0b8-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="3b0b8-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="3b0b8-287">PropertyGrid</span></span>|  
|<span data-ttu-id="3b0b8-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="3b0b8-288">UserControl</span></span>|  
|<span data-ttu-id="3b0b8-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="3b0b8-289">ToolStrip</span></span>|  
|<span data-ttu-id="3b0b8-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="3b0b8-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="3b0b8-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="3b0b8-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="3b0b8-292">분할자</span><span class="sxs-lookup"><span data-stu-id="3b0b8-292">Splitter</span></span>|  
|<span data-ttu-id="3b0b8-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="3b0b8-293">RaftingContainer</span></span>|  
|<span data-ttu-id="3b0b8-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="3b0b8-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3b0b8-295">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b0b8-295">See also</span></span>

- [<span data-ttu-id="3b0b8-296">UI 자동화 컨트롤 형식</span><span class="sxs-lookup"><span data-stu-id="3b0b8-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
