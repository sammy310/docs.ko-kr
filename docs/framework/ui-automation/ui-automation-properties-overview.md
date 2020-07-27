---
title: UI 자동화 속성 개요
description: Microsoft UI 자동화 속성의 광범위 한 개요를 참조 하세요. 속성 식별자, 범주별 속성, 지역화 및 속성 및 이벤트에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, properties
- properties, UI Automation
ms.assetid: a6c31d7b-b33e-49b3-b5c1-31a345f9b7c8
ms.openlocfilehash: 17d780c059530be8c91890302ea4066de2d4aa73
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163205"
---
# <a name="ui-automation-properties-overview"></a><span data-ttu-id="38dfc-104">UI 자동화 속성 개요</span><span class="sxs-lookup"><span data-stu-id="38dfc-104">UI Automation Properties Overview</span></span>
> [!NOTE]
> <span data-ttu-id="38dfc-105">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="38dfc-106">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38dfc-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="38dfc-107">UI 자동화 공급자는 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 요소에 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-107">UI Automation providers expose properties on [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements.</span></span> <span data-ttu-id="38dfc-108">이러한 속성을 통해 UI 자동화 클라이언트 애플리케이션은 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)]항목에 대한 정보(특히 정적 및 동적 데이터를 포함한 컨트롤)를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-108">These properties enable UI Automation client applications to discover information about pieces of the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], especially controls, including both static and dynamic data.</span></span>  
  
 <span data-ttu-id="38dfc-109">이 섹션에서는 광범위한 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 속성 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-109">This section gives a broad overview of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] properties.</span></span> <span data-ttu-id="38dfc-110">보다 구체적인 정보는 다음 항목에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-110">More specific information is given in the following topics:</span></span>  
  
- [<span data-ttu-id="38dfc-111">클라이언트에 대한 UI 자동화 속성</span><span class="sxs-lookup"><span data-stu-id="38dfc-111">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)  
  
- [<span data-ttu-id="38dfc-112">서버 쪽 UI 자동화 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="38dfc-112">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)  
  
<a name="Property_Identifiers"></a>
## <a name="property-identifiers"></a><span data-ttu-id="38dfc-113">속성 식별자</span><span class="sxs-lookup"><span data-stu-id="38dfc-113">Property Identifiers</span></span>  
 <span data-ttu-id="38dfc-114">모든 속성은 숫자 및 이름으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-114">Every property is identified by a number and a name.</span></span> <span data-ttu-id="38dfc-115">속성의 이름은 디버깅 및 진단용으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-115">The names of properties are used only for debugging and diagnosis.</span></span> <span data-ttu-id="38dfc-116">공급자는 숫자 Id를 사용 하 여 들어오는 속성 요청을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-116">Providers use the numeric IDs to identify incoming property requests.</span></span> <span data-ttu-id="38dfc-117">그러나 클라이언트 애플리케이션은 숫자 및 이름 캡슐화하는 <xref:System.Windows.Automation.AutomationProperty>만 사용하여 검색하려는 속성을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-117">Client applications, however, only use <xref:System.Windows.Automation.AutomationProperty>, which encapsulates the number and name, to identify properties they wish to retrieve.</span></span>  
  
 <span data-ttu-id="38dfc-118">특정 속성을 나타내는<xref:System.Windows.Automation.AutomationProperty> 개체는 다양한 클래스에 필드로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-118"><xref:System.Windows.Automation.AutomationProperty> objects representing particular properties are available as fields in various classes.</span></span> <span data-ttu-id="38dfc-119">보안상의 이유로, UI 자동화 공급자는 Uiautomationtypes.dll에 포함된 별도의 클래스 집합에서 이러한 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-119">For security reasons, UI Automation providers obtain these objects from a separate set of classes that are contained in Uiautomationtypes.dll.</span></span>  
  
 <span data-ttu-id="38dfc-120">다음 표에서는 id를 포함 하는 클래스로 속성을 분류 합니다 <xref:System.Windows.Automation.AutomationProperty> .</span><span class="sxs-lookup"><span data-stu-id="38dfc-120">The following table categorizes properties by the classes that contain the <xref:System.Windows.Automation.AutomationProperty>IDs.</span></span>  
  
|<span data-ttu-id="38dfc-121">속성의 종류</span><span class="sxs-lookup"><span data-stu-id="38dfc-121">Kinds of properties</span></span>|<span data-ttu-id="38dfc-122">클라이언트가 ID를 가져오는 위치</span><span class="sxs-lookup"><span data-stu-id="38dfc-122">Clients get IDs from</span></span>|<span data-ttu-id="38dfc-123">공급자 ID를 가져오는 위치</span><span class="sxs-lookup"><span data-stu-id="38dfc-123">Providers get IDs from</span></span>|  
|-------------------------|--------------------------|----------------------------|  
|<span data-ttu-id="38dfc-124">모든 요소에 공통된 속성(다음 표 참조)</span><span class="sxs-lookup"><span data-stu-id="38dfc-124">Properties common to all elements (see following tables)</span></span>|<xref:System.Windows.Automation.AutomationElement>|<xref:System.Windows.Automation.AutomationElementIdentifiers>|  
|<span data-ttu-id="38dfc-125">도킹 창의 위치</span><span class="sxs-lookup"><span data-stu-id="38dfc-125">Position of a docking window</span></span>|<xref:System.Windows.Automation.DockPattern>|<xref:System.Windows.Automation.DockPatternIdentifiers>|  
|<span data-ttu-id="38dfc-126">확장 및 축소할 수 있는 요소의 상태</span><span class="sxs-lookup"><span data-stu-id="38dfc-126">State of an element that can expand and collapse</span></span>|<xref:System.Windows.Automation.ExpandCollapsePattern>|<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers>|  
|<span data-ttu-id="38dfc-127">표에 있는 항목의 속성</span><span class="sxs-lookup"><span data-stu-id="38dfc-127">Properties of an item in a grid</span></span>|<xref:System.Windows.Automation.GridItemPattern>|<xref:System.Windows.Automation.GridItemPatternIdentifiers>|  
|<span data-ttu-id="38dfc-128">표의 속성</span><span class="sxs-lookup"><span data-stu-id="38dfc-128">Properties of a grid</span></span>|<xref:System.Windows.Automation.GridPattern>|<xref:System.Windows.Automation.GridPatternIdentifiers>|  
|<span data-ttu-id="38dfc-129">여러 뷰가 있는 요소의 현재 및 지원되는 뷰</span><span class="sxs-lookup"><span data-stu-id="38dfc-129">Current and supported view of an element that has multiple views</span></span>|<xref:System.Windows.Automation.MultipleViewPattern>|<xref:System.Windows.Automation.MultipleViewPatternIdentifiers>|  
|<span data-ttu-id="38dfc-130">값 범위 내에서 이동하는 요소의 속성(예: 슬라이더)</span><span class="sxs-lookup"><span data-stu-id="38dfc-130">Properties of an element that moves over a range of values, such as a slider</span></span>|<xref:System.Windows.Automation.RangeValuePattern>|<xref:System.Windows.Automation.RangeValuePatternIdentifiers>|  
|<span data-ttu-id="38dfc-131">스크롤 창의 속성</span><span class="sxs-lookup"><span data-stu-id="38dfc-131">Properties of a scrolling window</span></span>|<xref:System.Windows.Automation.ScrollPattern>|<xref:System.Windows.Automation.ScrollPatternIdentifiers>|  
|<span data-ttu-id="38dfc-132">선택할 수 있는 항목의 상태 및 컨테이너(예: 목록 내부)</span><span class="sxs-lookup"><span data-stu-id="38dfc-132">Status and container of an item that can be selected, as in a list</span></span>|<xref:System.Windows.Automation.SelectionItemPattern>|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers>|  
|<span data-ttu-id="38dfc-133">선택 항목을 포함하는 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="38dfc-133">Properties of a control that contains selection items</span></span>|<xref:System.Windows.Automation.SelectionPattern>|<xref:System.Windows.Automation.SelectionPatternIdentifiers>|  
|<span data-ttu-id="38dfc-134">테이블에 있는 항목의 열 및 행 헤더</span><span class="sxs-lookup"><span data-stu-id="38dfc-134">Column and row headers of an item in a table</span></span>|<xref:System.Windows.Automation.TableItemPattern>|<xref:System.Windows.Automation.TableItemPatternIdentifiers>|  
|<span data-ttu-id="38dfc-135">테이블의 열 및 행 헤더와 방향</span><span class="sxs-lookup"><span data-stu-id="38dfc-135">Column and row headers, and orientation, of a table</span></span>|<xref:System.Windows.Automation.TablePattern>|<xref:System.Windows.Automation.TablePatternIdentifiers>|  
|<span data-ttu-id="38dfc-136">토글 컨트롤의 상태</span><span class="sxs-lookup"><span data-stu-id="38dfc-136">State of a toggle control</span></span>|<xref:System.Windows.Automation.TogglePattern>|<xref:System.Windows.Automation.TogglePatternIdentifiers>|  
|<span data-ttu-id="38dfc-137">이동, 회전, 크기 조정할 수 있는 요소의 기능</span><span class="sxs-lookup"><span data-stu-id="38dfc-137">Capabilities of an element that can be moved, rotated, or resized</span></span>|<xref:System.Windows.Automation.TransformPattern>|<xref:System.Windows.Automation.TransformPatternIdentifiers>|  
|<span data-ttu-id="38dfc-138">값이 있는 요소의 값과 읽기/쓰기 기능</span><span class="sxs-lookup"><span data-stu-id="38dfc-138">Value and read/write capabilities of an element that has a value</span></span>|<xref:System.Windows.Automation.ValuePattern>|<xref:System.Windows.Automation.ValuePatternIdentifiers>|  
|<span data-ttu-id="38dfc-139">창의 기능 및 상태</span><span class="sxs-lookup"><span data-stu-id="38dfc-139">Capabilities and state of a window</span></span>|<xref:System.Windows.Automation.WindowPattern>|<xref:System.Windows.Automation.WindowPatternIdentifiers>|  
  
<a name="Properties_by_Category"></a>
## <a name="properties-by-category"></a><span data-ttu-id="38dfc-140">항목별 속성</span><span class="sxs-lookup"><span data-stu-id="38dfc-140">Properties by Category</span></span>  
 <span data-ttu-id="38dfc-141">다음 표에서는 및에서 Id를 찾을 수 있는 속성을 분류 합니다 <xref:System.Windows.Automation.AutomationElement> <xref:System.Windows.Automation.AutomationElementIdentifiers> .</span><span class="sxs-lookup"><span data-stu-id="38dfc-141">The following tables categorize the properties whose IDs are found in <xref:System.Windows.Automation.AutomationElement> and <xref:System.Windows.Automation.AutomationElementIdentifiers>.</span></span> <span data-ttu-id="38dfc-142">이러한 속성은 모든 컨트롤에 공통됩니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-142">These properties are common to all controls.</span></span> <span data-ttu-id="38dfc-143">일부를 제외한 모든 속성은 공급자 애플리케이션의 수명 동안 정적일 가능성이 높습니다. 대부분의 동적 속성은 컨트롤 패턴과 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-143">All but a few of them are likely to be static over the lifetime of the provider application; most dynamic properties are associated with control patterns.</span></span>  
  
 <span data-ttu-id="38dfc-144">**속성 액세스** 열에는 <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> 및 <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>외에도 각 속성에 대한 기타 접근자가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-144">The **Property Access** column lists any other accessors for each property, in addition to <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> and <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>.</span></span> <span data-ttu-id="38dfc-145">클라이언트 애플리케이션에서 속성을 가져오는 방법에 대한 자세한 내용은 [UI Automation Properties for Clients](ui-automation-properties-for-clients.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38dfc-145">For more information on getting properties in a client application, see [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="38dfc-146">각 속성에 대한 특정 정보를 보려면 **속성 액세스** 열에 있는 링크를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="38dfc-146">For specific information about each property, follow the link in the **Property Access** column.</span></span>  
  
### <a name="display-characteristics"></a><span data-ttu-id="38dfc-147">특성 표시</span><span class="sxs-lookup"><span data-stu-id="38dfc-147">Display Characteristics</span></span>  
  
|<span data-ttu-id="38dfc-148">속성 식별자</span><span class="sxs-lookup"><span data-stu-id="38dfc-148">Property identifier</span></span>|<span data-ttu-id="38dfc-149">속성 액세스</span><span class="sxs-lookup"><span data-stu-id="38dfc-149">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>|  
|<xref:System.Windows.Automation.AutomationElement.CultureProperty>|<span data-ttu-id="38dfc-150">해당 없음</span><span class="sxs-lookup"><span data-stu-id="38dfc-150">n/a</span></span>|  
|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsOffscreen%2A>|  
|<xref:System.Windows.Automation.AutomationElement.OrientationProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Orientation%2A>|  
  
### <a name="element-type"></a><span data-ttu-id="38dfc-151">요소 형식</span><span class="sxs-lookup"><span data-stu-id="38dfc-151">Element Type</span></span>  
  
|<span data-ttu-id="38dfc-152">속성 식별자</span><span class="sxs-lookup"><span data-stu-id="38dfc-152">Property identifier</span></span>|<span data-ttu-id="38dfc-153">속성 액세스</span><span class="sxs-lookup"><span data-stu-id="38dfc-153">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsContentElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsControlElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LocalizedControlType%2A>|  
  
### <a name="identification"></a><span data-ttu-id="38dfc-154">식별</span><span class="sxs-lookup"><span data-stu-id="38dfc-154">Identification</span></span>  
  
|<span data-ttu-id="38dfc-155">속성 식별자</span><span class="sxs-lookup"><span data-stu-id="38dfc-155">Property identifier</span></span>|<span data-ttu-id="38dfc-156">속성 액세스</span><span class="sxs-lookup"><span data-stu-id="38dfc-156">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AutomationId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClassNameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ClassName%2A>|  
|<xref:System.Windows.Automation.AutomationElement.FrameworkIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.FrameworkId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LabeledByProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LabeledBy%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ProcessIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ProcessId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.RuntimeIdProperty>|<xref:System.Windows.Automation.AutomationElement.GetRuntimeId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NativeWindowHandleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.NativeWindowHandle%2A>|  
  
### <a name="interaction"></a><span data-ttu-id="38dfc-157">상호 작용</span><span class="sxs-lookup"><span data-stu-id="38dfc-157">Interaction</span></span>  
  
|<span data-ttu-id="38dfc-158">속성 식별자</span><span class="sxs-lookup"><span data-stu-id="38dfc-158">Property identifier</span></span>|<span data-ttu-id="38dfc-159">속성 액세스</span><span class="sxs-lookup"><span data-stu-id="38dfc-159">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AcceleratorKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AccessKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>|<xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>|  
|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HasKeyboardFocus%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsEnabled%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsKeyboardFocusable%2A>|  
  
### <a name="support-for-patterns"></a><span data-ttu-id="38dfc-160">패턴에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="38dfc-160">Support for Patterns</span></span>  
  
|<span data-ttu-id="38dfc-161">속성 식별자</span><span class="sxs-lookup"><span data-stu-id="38dfc-161">Property identifier</span></span>|<span data-ttu-id="38dfc-162">속성 액세스</span><span class="sxs-lookup"><span data-stu-id="38dfc-162">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsDockPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsExpandCollapsePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsInvokePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsMultipleViewPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsRangeValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTableItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTablePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTogglePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTransformPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsWindowPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
  
### <a name="miscellaneous"></a><span data-ttu-id="38dfc-163">기타</span><span class="sxs-lookup"><span data-stu-id="38dfc-163">Miscellaneous</span></span>  
  
|<span data-ttu-id="38dfc-164">속성 식별자</span><span class="sxs-lookup"><span data-stu-id="38dfc-164">Property identifier</span></span>|<span data-ttu-id="38dfc-165">속성 액세스</span><span class="sxs-lookup"><span data-stu-id="38dfc-165">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsRequiredForFormProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsRequiredForForm%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsPassword%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemStatusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemStatus%2A>|  
  
<a name="Localization"></a>
## <a name="localization"></a><span data-ttu-id="38dfc-166">지역화</span><span class="sxs-lookup"><span data-stu-id="38dfc-166">Localization</span></span>  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="38dfc-167">공급자는 운영 체제의 언어에 다음과 같은 속성을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-167">providers should present the following properties in the language of the operating system:</span></span>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AccessKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>  
  
<a name="Properties_and_Events"></a>
## <a name="properties-and-events"></a><span data-ttu-id="38dfc-168">속성 및 이벤트</span><span class="sxs-lookup"><span data-stu-id="38dfc-168">Properties and Events</span></span>  
 <span data-ttu-id="38dfc-169">의 속성을 사용한 밀접한 관계는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성 변경 이벤트의 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-169">Closely tied in with the properties in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is the concept of property-changed events.</span></span> <span data-ttu-id="38dfc-170">동적 속성의 경우, 클라이언트 애플리케이션에서는 속성 값이 변경되었는지 확인하는 방법이 필요합니다. 그에 따라 정보 캐시를 업데이트하거나 다른 방법으로 새로운 정보에 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-170">For dynamic properties, the client application needs a way to know that a property value has changed, so that it can update its cache of information or react to the new information in some other way.</span></span>  
  
 <span data-ttu-id="38dfc-171">[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 에 변경이 수행되면 공급자가 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-171">Providers raise events when something in the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] changes.</span></span> <span data-ttu-id="38dfc-172">예를 들어, 확인란이 선택되거나 선택 취소되면 공급자의 Toggle 패턴 구현에서 속성 변경 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-172">For example, if a check box is selected or cleared, a property-changed event is raised by the provider's implementation of the Toggle pattern.</span></span> <span data-ttu-id="38dfc-173">공급자는 클라이언트가 이벤트 또는 특정 이벤트를 수신 대기하는지에 따라 선택적으로 이벤트를 발생시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-173">Providers can raise events selectively, depending on whether any clients are listening for events, or listening for specific events.</span></span>  
  
 <span data-ttu-id="38dfc-174">일부 공급자는 이벤트를 발생시키지 않습니다. 이는 요소에 대한 UI 자동화 공급자의 구현에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-174">Not all property changes raise events; that is entirely up to the implementation of the UI Automation provider for the element.</span></span> <span data-ttu-id="38dfc-175">예를 들어, 목록 상자에 대한 표준 프록시 공급자는 <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> 가 변경될 때 이벤트를 발생시키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-175">For example, the standard proxy providers for list boxes do not raise an event when the <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> changes.</span></span> <span data-ttu-id="38dfc-176">이 경우, 애플리케이션은 <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>를 수신 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-176">In this case, the application instead must listen for an <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>.</span></span>  
  
 <span data-ttu-id="38dfc-177">클라이언트는 이벤트를 구독하여 이벤트를 수신 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-177">Clients listen for events by subscribing to them.</span></span> <span data-ttu-id="38dfc-178">이벤트를 구독하는 것은 이벤트를 처리할 수 있는 대리자 메서드를 만들고, 이러한 메서드에서 처리될 특정 이벤트와 함께 해당 메서드를 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 에 전달한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-178">Subscribing to events means creating delegate methods that can handle the events, and then passing the methods to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] along with the specific events that will be dealt with in those methods.</span></span> <span data-ttu-id="38dfc-179">특히 속성 변경 이벤트의 경우 클라이언트는 <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38dfc-179">For property-changed events in particular, clients must implement <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38dfc-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38dfc-180">See also</span></span>

- [<span data-ttu-id="38dfc-181">UI 자동화 클라이언트에서 캐싱</span><span class="sxs-lookup"><span data-stu-id="38dfc-181">Caching in UI Automation Clients</span></span>](caching-in-ui-automation-clients.md)
- [<span data-ttu-id="38dfc-182">클라이언트에 대한 UI 자동화 속성</span><span class="sxs-lookup"><span data-stu-id="38dfc-182">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)
- [<span data-ttu-id="38dfc-183">서버 쪽 UI 자동화 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="38dfc-183">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)
- [<span data-ttu-id="38dfc-184">속성 조건에 따라 UI 자동화 요소 찾기</span><span class="sxs-lookup"><span data-stu-id="38dfc-184">Find a UI Automation Element Based on a Property Condition</span></span>](find-a-ui-automation-element-based-on-a-property-condition.md)
- [<span data-ttu-id="38dfc-185">UI 자동화 공급자에서 속성 반환</span><span class="sxs-lookup"><span data-stu-id="38dfc-185">Return Properties from a UI Automation Provider</span></span>](return-properties-from-a-ui-automation-provider.md)
- [<span data-ttu-id="38dfc-186">UI 자동화 공급자에서 이벤트 발생</span><span class="sxs-lookup"><span data-stu-id="38dfc-186">Raise Events from a UI Automation Provider</span></span>](raise-events-from-a-ui-automation-provider.md)
