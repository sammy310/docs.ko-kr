---
title: UI 자동화 TableItem 컨트롤 패턴 구현
description: UI 자동화에서 TableItem 컨트롤 패턴을 구현 하기 위한 지침 및 규칙을 검토 합니다. ITableItemProvider 인터페이스에 필요한 멤버를 알고 있어야 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
ms.openlocfilehash: 3d6d31fe0e041fbba147df14d290a775188755f2
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163517"
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a><span data-ttu-id="1bdd1-104">UI 자동화 TableItem 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="1bdd1-104">Implementing the UI Automation TableItem Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="1bdd1-105">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1bdd1-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="1bdd1-106">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bdd1-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="1bdd1-107">이 항목에서는 이벤트 및 속성에 대한 정보를 포함하여 <xref:System.Windows.Automation.Provider.ITableItemProvider>를 구현하기 위한 지침 및 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1bdd1-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableItemProvider>, including information about events and properties.</span></span> <span data-ttu-id="1bdd1-108">추가 참조에 대한 링크는 개요의 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bdd1-108">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="1bdd1-109"><xref:System.Windows.Automation.TableItemPattern> 컨트롤 패턴은 <xref:System.Windows.Automation.Provider.ITableProvider>를 구현하는 컨테이너의 자식 컨트롤을 지원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bdd1-109">The <xref:System.Windows.Automation.TableItemPattern> control pattern is used to support child controls of containers that implement <xref:System.Windows.Automation.Provider.ITableProvider>.</span></span> <span data-ttu-id="1bdd1-110">개별 셀 기능에 대한 액세스는 <xref:System.Windows.Automation.Provider.IGridItemProvider>의 필수 동시 구현에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bdd1-110">Access to individual cell functionality is provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span> <span data-ttu-id="1bdd1-111">이 컨트롤 패턴은 <xref:System.Windows.Automation.Provider.IGridItemProvider>와 유사하지만, <xref:System.Windows.Automation.Provider.ITableItemProvider>를 구현하는 컨트롤은 개별 셀과 셀의 행 및 열 정보 간의 관계를 프로그래밍 방식으로 노출해야 한다는 점이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1bdd1-111">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridItemProvider> with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableItemProvider> must programmatically expose the relationship between the individual cell and its row and column information.</span></span> <span data-ttu-id="1bdd1-112">이 컨트롤 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bdd1-112">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="1bdd1-113">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="1bdd1-113">Implementation Guidelines and Conventions</span></span>  
  
- <span data-ttu-id="1bdd1-114">관련 그리드 항목 기능에 대해서는 [UI 자동화 GridItem 컨트롤 패턴 구현](implementing-the-ui-automation-griditem-control-pattern.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1bdd1-114">For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](implementing-the-ui-automation-griditem-control-pattern.md).</span></span>  
  
<a name="Required_Members_for_ITableItemProvider"></a>
## <a name="required-members-for-itableitemprovider"></a><span data-ttu-id="1bdd1-115">ITableItemProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="1bdd1-115">Required Members for ITableItemProvider</span></span>  
  
|<span data-ttu-id="1bdd1-116">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="1bdd1-116">Required member</span></span>|<span data-ttu-id="1bdd1-117">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="1bdd1-117">Member type</span></span>|<span data-ttu-id="1bdd1-118">참고</span><span class="sxs-lookup"><span data-stu-id="1bdd1-118">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|<span data-ttu-id="1bdd1-119">메서드</span><span class="sxs-lookup"><span data-stu-id="1bdd1-119">Method</span></span>|<span data-ttu-id="1bdd1-120">없음</span><span class="sxs-lookup"><span data-stu-id="1bdd1-120">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|<span data-ttu-id="1bdd1-121">메서드</span><span class="sxs-lookup"><span data-stu-id="1bdd1-121">Method</span></span>|<span data-ttu-id="1bdd1-122">없음</span><span class="sxs-lookup"><span data-stu-id="1bdd1-122">None</span></span>|  
  
 <span data-ttu-id="1bdd1-123">이 컨트롤 패턴에는 연결된 속성 또는 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1bdd1-123">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="1bdd1-124">예외</span><span class="sxs-lookup"><span data-stu-id="1bdd1-124">Exceptions</span></span>  
 <span data-ttu-id="1bdd1-125">이 컨트롤 패턴에 연결된 예외가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1bdd1-125">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bdd1-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1bdd1-126">See also</span></span>

- [<span data-ttu-id="1bdd1-127">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="1bdd1-127">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="1bdd1-128">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="1bdd1-128">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="1bdd1-129">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="1bdd1-129">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="1bdd1-130">UI 자동화 Table 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="1bdd1-130">Implementing the UI Automation Table Control Pattern</span></span>](implementing-the-ui-automation-table-control-pattern.md)
- [<span data-ttu-id="1bdd1-131">UI 자동화 GridItem 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="1bdd1-131">Implementing the UI Automation GridItem Control Pattern</span></span>](implementing-the-ui-automation-griditem-control-pattern.md)
- [<span data-ttu-id="1bdd1-132">UI 자동화 트리 개요</span><span class="sxs-lookup"><span data-stu-id="1bdd1-132">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="1bdd1-133">UI 자동화에서 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="1bdd1-133">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
