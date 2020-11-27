---
title: UI 자동화 Table 컨트롤 패턴 구현
description: UI 자동화에서 Table 컨트롤 패턴을 구현 하기 위한 지침 및 규칙을 검토 합니다. ITableProvider 인터페이스에 필요한 멤버를 알고 있어야 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Table control pattern
- control patterns, Table
- TableControl pattern
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
ms.openlocfilehash: 9c1d57e46aed9ec2441a95544d26244d2dfa9496
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265754"
---
# <a name="implementing-the-ui-automation-table-control-pattern"></a><span data-ttu-id="4e0a0-104">UI 자동화 Table 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="4e0a0-104">Implementing the UI Automation Table Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="4e0a0-105">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4e0a0-106">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="4e0a0-107">이 항목에서는 속성, 메서드 및 이벤트에 대한 정보를 포함하여 <xref:System.Windows.Automation.Provider.ITableProvider>를 구현하기 위한 지침 및 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="4e0a0-108">추가 참조에 대한 링크는 개요의 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-108">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="4e0a0-109"><xref:System.Windows.Automation.TablePattern> 컨트롤 패턴은 자식 요소 컬렉션에 컨테이너 역할을 하는 컨트롤을 지원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-109">The <xref:System.Windows.Automation.TablePattern> control pattern is used to support controls that act as containers for a collection of child elements.</span></span> <span data-ttu-id="4e0a0-110">이 요소의 자식 항목은 <xref:System.Windows.Automation.Provider.ITableItemProvider> 를 구현해야 하며 행과 열로 트래버스할 수 있는 2차원의 논리적 좌표계로 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-110">The children of this element must implement <xref:System.Windows.Automation.Provider.ITableItemProvider> and be organized in a two-dimensional logical coordinate system that can be traversed by row and column.</span></span> <span data-ttu-id="4e0a0-111">이 컨트롤 패턴은 <xref:System.Windows.Automation.Provider.IGridProvider>와 비슷하지만, <xref:System.Windows.Automation.Provider.ITableProvider>를 구현하는 모든 컨트롤은 각 하위 요소에 대해 열 및/또는 행 헤더 관계도 노출해야 하는 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-111">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridProvider>, with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableProvider> must also expose a column and/or row header relationship for each child element.</span></span> <span data-ttu-id="4e0a0-112">이 컨트롤 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-112">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="4e0a0-113">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="4e0a0-113">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="4e0a0-114">Table 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-114">When implementing the Table control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="4e0a0-115">개별 셀의 내용은 <xref:System.Windows.Automation.Provider.IGridProvider>의 필수 동시 구현에서 제공된 배열 또는 2차원 논리적 좌표계를 통해 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-115">Access to the content of individual cells is through a two-dimensional logical coordinate system or array provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span>  
  
- <span data-ttu-id="4e0a0-116">열 또는 행 헤더는 테이블 개체 내에 포함되거나 테이블 개체와 연결된 별도의 헤더 개체에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-116">A column or row header can be contained within a table object or be a separate header object that is associated with a table object.</span></span>  
  
- <span data-ttu-id="4e0a0-117">열 및 행 헤더에는 모든 지원 헤더는 물론 기본 헤더가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-117">Column and row headers may include both a primary header as well as any supporting headers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4e0a0-118">이 개념은 사용자가 "이름" 열을 정의한 Microsoft Excel 스프레드시트에서 분명 하 게 드러납니다.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-118">This concept becomes evident in a Microsoft Excel spreadsheet where a user has defined a "First name" column.</span></span> <span data-ttu-id="4e0a0-119">이제 이 열에는 사용자가 정의한 &quot;이름&quot; 헤더와 애플리케이션에서 할당한 해당 열의 영숫자 지정 두 개의 헤더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-119">This column now has two headers—the "First name" header defined by the user and the alphanumeric designation for that column assigned by the application.</span></span>  
  
- <span data-ttu-id="4e0a0-120">관련 그리드 기능에 대 한 [UI 자동화 Grid 컨트롤 패턴 구현](implementing-the-ui-automation-grid-control-pattern.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-120">See [Implementing the UI Automation Grid Control Pattern](implementing-the-ui-automation-grid-control-pattern.md) for related grid functionality.</span></span>  
  
 <span data-ttu-id="4e0a0-121">![복잡한 헤더 항목이 있는 표](./media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span><span class="sxs-lookup"><span data-stu-id="4e0a0-121">![Table with complex header items.](./media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span></span>  
<span data-ttu-id="4e0a0-122">복잡한 열 헤더가 있는 테이블의 예</span><span class="sxs-lookup"><span data-stu-id="4e0a0-122">Example of a Table with Complex Column Headers</span></span>  
  
 <span data-ttu-id="4e0a0-123">![모호한 RowOrColumnMajor 속성이 있는 표](./media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span><span class="sxs-lookup"><span data-stu-id="4e0a0-123">![Table with ambiguous RowOrColumnMajor property.](./media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span></span>  
<span data-ttu-id="4e0a0-124">모호한 RowOrColumnMajor 속성이 있는 테이블</span><span class="sxs-lookup"><span data-stu-id="4e0a0-124">Example of a Table with Ambiguous RowOrColumnMajor Property</span></span>  
  
<a name="Required_Members_for_ITableProvider"></a>

## <a name="required-members-for-itableprovider"></a><span data-ttu-id="4e0a0-125">ITableProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="4e0a0-125">Required Members for ITableProvider</span></span>  

 <span data-ttu-id="4e0a0-126">ITableProvider 인터페이스에는 다음과 같은 속성 및 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-126">The following properties and methods are required for the ITableProvider interface.</span></span>  
  
|<span data-ttu-id="4e0a0-127">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="4e0a0-127">Required members</span></span>|<span data-ttu-id="4e0a0-128">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="4e0a0-128">Member type</span></span>|<span data-ttu-id="4e0a0-129">참고</span><span class="sxs-lookup"><span data-stu-id="4e0a0-129">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableProvider.RowOrColumnMajor%2A>|<span data-ttu-id="4e0a0-130">속성</span><span class="sxs-lookup"><span data-stu-id="4e0a0-130">Property</span></span>|<span data-ttu-id="4e0a0-131">없음</span><span class="sxs-lookup"><span data-stu-id="4e0a0-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetColumnHeaders%2A>|<span data-ttu-id="4e0a0-132">메서드</span><span class="sxs-lookup"><span data-stu-id="4e0a0-132">Method</span></span>|<span data-ttu-id="4e0a0-133">없음</span><span class="sxs-lookup"><span data-stu-id="4e0a0-133">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetRowHeaders%2A>|<span data-ttu-id="4e0a0-134">메서드</span><span class="sxs-lookup"><span data-stu-id="4e0a0-134">Method</span></span>|<span data-ttu-id="4e0a0-135">없음</span><span class="sxs-lookup"><span data-stu-id="4e0a0-135">None</span></span>|  
  
 <span data-ttu-id="4e0a0-136">이 컨트롤 패턴에 연결된 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-136">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="4e0a0-137">예외</span><span class="sxs-lookup"><span data-stu-id="4e0a0-137">Exceptions</span></span>  

 <span data-ttu-id="4e0a0-138">이 컨트롤 패턴에 연결된 예외가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e0a0-138">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e0a0-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e0a0-139">See also</span></span>

- [<span data-ttu-id="4e0a0-140">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="4e0a0-140">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="4e0a0-141">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="4e0a0-141">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="4e0a0-142">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="4e0a0-142">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="4e0a0-143">UI 자동화 TableItem 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="4e0a0-143">Implementing the UI Automation TableItem Control Pattern</span></span>](implementing-the-ui-automation-tableitem-control-pattern.md)
- [<span data-ttu-id="4e0a0-144">UI 자동화 Grid 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="4e0a0-144">Implementing the UI Automation Grid Control Pattern</span></span>](implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="4e0a0-145">UI 자동화 트리 개요</span><span class="sxs-lookup"><span data-stu-id="4e0a0-145">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="4e0a0-146">UI 자동화에서 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="4e0a0-146">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
