---
title: UI 자동화 컨트롤 형식 개요
description: 요소가 나타내는 컨트롤의 종류를 나타내는 데 사용할 수 있는 잘 알려진 식별자 인 UI 자동화 컨트롤 형식에 대 한 개요를 읽습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control types
- control types, UI Automation
ms.assetid: 75159ef8-bd43-4d13-acb7-1f1fe9253160
ms.openlocfilehash: 851d509e719afb658971ea5f6fc2f8fdd6bd2cf7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261347"
---
# <a name="ui-automation-control-types-overview"></a><span data-ttu-id="c40b4-103">UI 자동화 컨트롤 형식 개요</span><span class="sxs-lookup"><span data-stu-id="c40b4-103">UI Automation Control Types Overview</span></span>

> [!NOTE]
> <span data-ttu-id="c40b4-104">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c40b4-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c40b4-105">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c40b4-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] <span data-ttu-id="c40b4-106">컨트롤 형식은 콤보 상자나 단추와 같은 특정 요소가 구현하는 컨트롤의 종류를 나타내기 위해 사용할 수 있는 알려진 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c40b4-106">control types are well-known identifiers that can be used to indicate what kind of control a particular element represents, such as a combo box or a button.</span></span>  
  
 <span data-ttu-id="c40b4-107">알려진 식별자를 사용하면 보조 기술 디바이스가 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 에서 사용 가능한 컨트롤의 형식 및 이 컨트롤을 조작하는 방식을 더 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c40b4-107">Having a well-known identifier makes it easier for assistive technology devices to determine what types of controls are available in the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] and how to interact with the controls.</span></span>  
  
<a name="UI_Automation_Control_Type_Requisites"></a>

## <a name="ui-automation-control-type-requisites"></a><span data-ttu-id="c40b4-108">UI 자동화 컨트롤 형식 필수 요소</span><span class="sxs-lookup"><span data-stu-id="c40b4-108">UI Automation Control Type Requisites</span></span>  

 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] <span data-ttu-id="c40b4-109">컨트롤 형식은 공급자가 충족해야 하는 일련의 조건을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c40b4-109">control types provide a set of conditions that providers must meet.</span></span> <span data-ttu-id="c40b4-110">이러한 조건이 충족되는 경우 컨트롤은 특정 컨트롤 형식 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c40b4-110">When these conditions are met, the control can use the specific control type name.</span></span> <span data-ttu-id="c40b4-111">각 컨트롤 형식에는 다음에 대한 조건이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c40b4-111">Each control type has conditions for the following:</span></span>  
  
- [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="c40b4-112">컨트롤 패턴 - 지원해야 하는 컨트롤 패턴, 선택 사항인 컨트롤 패턴, 컨트롤에서 지원해서는 안 되는 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="c40b4-112">control patterns—which control patterns must be supported, which control patterns are optional, and which control patterns must not be supported by the control.</span></span>  
  
- [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="c40b4-113">속성 값 - 지원되는 속성 값</span><span class="sxs-lookup"><span data-stu-id="c40b4-113">property values—which property values are supported.</span></span>  
  
- [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="c40b4-114">트리 구조 - 컨트롤에 필요한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리 구조</span><span class="sxs-lookup"><span data-stu-id="c40b4-114">tree structure—the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure for the control.</span></span>  
  
 <span data-ttu-id="c40b4-115">컨트롤이 특정 컨트롤 형식에 대한 조건을 충족한다면 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> 속성 값이 해당 컨트롤 형식을 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c40b4-115">When a control meets the conditions for a particular control type, the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> property value will indicate that control type.</span></span>  
  
<a name="Current_UI_Automation_Control_Types"></a>

## <a name="current-ui-automation-control-types"></a><span data-ttu-id="c40b4-116">현재 UI 자동화 컨트롤 형식</span><span class="sxs-lookup"><span data-stu-id="c40b4-116">Current UI Automation Control Types</span></span>  

 <span data-ttu-id="c40b4-117">다음 목록에는 현재 제공되는 일련의 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 컨트롤 형식이 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="c40b4-117">The following list contains the current set of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] control types:</span></span>  
  
- [<span data-ttu-id="c40b4-118">Button 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-118">UI Automation Support for the Button Control Type</span></span>](ui-automation-support-for-the-button-control-type.md)  
  
- [<span data-ttu-id="c40b4-119">Calendar 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-119">UI Automation Support for the Calendar Control Type</span></span>](ui-automation-support-for-the-calendar-control-type.md)  
  
- [<span data-ttu-id="c40b4-120">CheckBox 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-120">UI Automation Support for the CheckBox Control Type</span></span>](ui-automation-support-for-the-checkbox-control-type.md)  
  
- [<span data-ttu-id="c40b4-121">ComboBox 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-121">UI Automation Support for the ComboBox Control Type</span></span>](ui-automation-support-for-the-combobox-control-type.md)  
  
- [<span data-ttu-id="c40b4-122">DataGrid 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-122">UI Automation Support for the DataGrid Control Type</span></span>](ui-automation-support-for-the-datagrid-control-type.md)  
  
- [<span data-ttu-id="c40b4-123">DataItem 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-123">UI Automation Support for the DataItem Control Type</span></span>](ui-automation-support-for-the-dataitem-control-type.md)  
  
- [<span data-ttu-id="c40b4-124">Document 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-124">UI Automation Support for the Document Control Type</span></span>](ui-automation-support-for-the-document-control-type.md)  
  
- [<span data-ttu-id="c40b4-125">Edit 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-125">UI Automation Support for the Edit Control Type</span></span>](ui-automation-support-for-the-edit-control-type.md)  
  
- [<span data-ttu-id="c40b4-126">Group 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-126">UI Automation Support for the Group Control Type</span></span>](ui-automation-support-for-the-group-control-type.md)  
  
- [<span data-ttu-id="c40b4-127">Header 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-127">UI Automation Support for the Header Control Type</span></span>](ui-automation-support-for-the-header-control-type.md)  
  
- [<span data-ttu-id="c40b4-128">HeaderItem 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-128">UI Automation Support for the HeaderItem Control Type</span></span>](ui-automation-support-for-the-headeritem-control-type.md)  
  
- [<span data-ttu-id="c40b4-129">Hyperlink 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-129">UI Automation Support for the Hyperlink Control Type</span></span>](ui-automation-support-for-the-hyperlink-control-type.md)  
  
- [<span data-ttu-id="c40b4-130">Image 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-130">UI Automation Support for the Image Control Type</span></span>](ui-automation-support-for-the-image-control-type.md)  
  
- [<span data-ttu-id="c40b4-131">List 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-131">UI Automation Support for the List Control Type</span></span>](ui-automation-support-for-the-list-control-type.md)  
  
- [<span data-ttu-id="c40b4-132">ListItem 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-132">UI Automation Support for the ListItem Control Type</span></span>](ui-automation-support-for-the-listitem-control-type.md)  
  
- [<span data-ttu-id="c40b4-133">Menu 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-133">UI Automation Support for the Menu Control Type</span></span>](ui-automation-support-for-the-menu-control-type.md)  
  
- [<span data-ttu-id="c40b4-134">MenuBar 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-134">UI Automation Support for the MenuBar Control Type</span></span>](ui-automation-support-for-the-menubar-control-type.md)  
  
- [<span data-ttu-id="c40b4-135">MenuItem 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-135">UI Automation Support for the MenuItem Control Type</span></span>](ui-automation-support-for-the-menuitem-control-type.md)  
  
- [<span data-ttu-id="c40b4-136">Pane 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-136">UI Automation Support for the Pane Control Type</span></span>](ui-automation-support-for-the-pane-control-type.md)  
  
- [<span data-ttu-id="c40b4-137">ProgressBar 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-137">UI Automation Support for the ProgressBar Control Type</span></span>](ui-automation-support-for-the-progressbar-control-type.md)  
  
- [<span data-ttu-id="c40b4-138">RadioButton 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-138">UI Automation Support for the RadioButton Control Type</span></span>](ui-automation-support-for-the-radiobutton-control-type.md)  
  
- [<span data-ttu-id="c40b4-139">ScrollBar 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-139">UI Automation Support for the ScrollBar Control Type</span></span>](ui-automation-support-for-the-scrollbar-control-type.md)  
  
- [<span data-ttu-id="c40b4-140">Separator 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-140">UI Automation Support for the Separator Control Type</span></span>](ui-automation-support-for-the-separator-control-type.md)  
  
- [<span data-ttu-id="c40b4-141">Slider 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-141">UI Automation Support for the Slider Control Type</span></span>](ui-automation-support-for-the-slider-control-type.md)  
  
- [<span data-ttu-id="c40b4-142">Spinner 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-142">UI Automation Support for the Spinner Control Type</span></span>](ui-automation-support-for-the-spinner-control-type.md)  
  
- [<span data-ttu-id="c40b4-143">SplitButton 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-143">UI Automation Support for the SplitButton Control Type</span></span>](ui-automation-support-for-the-splitbutton-control-type.md)  
  
- [<span data-ttu-id="c40b4-144">StatusBar 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-144">UI Automation Support for the StatusBar Control Type</span></span>](ui-automation-support-for-the-statusbar-control-type.md)  
  
- [<span data-ttu-id="c40b4-145">Tab 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-145">UI Automation Support for the Tab Control Type</span></span>](ui-automation-support-for-the-tab-control-type.md)  
  
- [<span data-ttu-id="c40b4-146">TabItem 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-146">UI Automation Support for the TabItem Control Type</span></span>](ui-automation-support-for-the-tabitem-control-type.md)  
  
- [<span data-ttu-id="c40b4-147">Table 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-147">UI Automation Support for the Table Control Type</span></span>](ui-automation-support-for-the-table-control-type.md)  
  
- [<span data-ttu-id="c40b4-148">Text 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-148">UI Automation Support for the Text Control Type</span></span>](ui-automation-support-for-the-text-control-type.md)  
  
- [<span data-ttu-id="c40b4-149">Thumb 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-149">UI Automation Support for the Thumb Control Type</span></span>](ui-automation-support-for-the-thumb-control-type.md)  
  
- [<span data-ttu-id="c40b4-150">TitleBar 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-150">UI Automation Support for the TitleBar Control Type</span></span>](ui-automation-support-for-the-titlebar-control-type.md)  
  
- [<span data-ttu-id="c40b4-151">ToolBar 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-151">UI Automation Support for the ToolBar Control Type</span></span>](ui-automation-support-for-the-toolbar-control-type.md)  
  
- [<span data-ttu-id="c40b4-152">ToolTip 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-152">UI Automation Support for the ToolTip Control Type</span></span>](ui-automation-support-for-the-tooltip-control-type.md)  
  
- [<span data-ttu-id="c40b4-153">Tree 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-153">UI Automation Support for the Tree Control Type</span></span>](ui-automation-support-for-the-tree-control-type.md)  
  
- [<span data-ttu-id="c40b4-154">TreeItem 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-154">UI Automation Support for the TreeItem Control Type</span></span>](ui-automation-support-for-the-treeitem-control-type.md)  
  
- [<span data-ttu-id="c40b4-155">Window 컨트롤 형식에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="c40b4-155">UI Automation Support for the Window Control Type</span></span>](ui-automation-support-for-the-window-control-type.md)  
  
## <a name="see-also"></a><span data-ttu-id="c40b4-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c40b4-156">See also</span></span>

- <xref:System.Windows.Automation.ControlType>
