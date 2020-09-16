---
title: UI 자동화를 사용하여 표의 콘텐츠 노출
description: UI 자동화를 사용 하 여 테이블 내용을 노출 하는 방법을 참조 하세요. 테이블 형식 컨트롤 내에 있는 각 셀의 내용 및 기본 속성이 노출 됩니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables, exposing content of
- UI Automation, exposing content of tables
- exposing content of tables using UI Automation
ms.assetid: ac3c5eaa-49c7-4653-b83e-532e2a2604a2
ms.openlocfilehash: e32ee52ca17120dbfef6f948711c468dd1d8a021
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540812"
---
# <a name="expose-the-content-of-a-table-using-ui-automation"></a><span data-ttu-id="8d483-104">UI 자동화를 사용하여 표의 콘텐츠 노출</span><span class="sxs-lookup"><span data-stu-id="8d483-104">Expose the Content of a Table Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="8d483-105">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8d483-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8d483-106">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d483-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="8d483-107">이 항목에서는를 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 사용 하 여 테이블 형식 컨트롤 내에서 각 셀의 내용 및 기본 속성을 노출 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d483-107">This topic shows how [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] can be used to expose the content and intrinsic properties of each cell within a tabular control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d483-108">예제</span><span class="sxs-lookup"><span data-stu-id="8d483-108">Example</span></span>  
 <span data-ttu-id="8d483-109">다음 코드 예에서는 <xref:System.Windows.Automation.AutomationElement> 테이블 셀의 내용을 나타내는를 가져오는 방법을 보여 줍니다. 행 및 열 인덱스, 행 및 열 범위, 행 및 열 머리글 정보 등의 셀 속성도 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8d483-109">The following code example demonstrates how to obtain a <xref:System.Windows.Automation.AutomationElement> that represents the content of a table cell; cell properties such as row and column indices, row and column spans, and row and column header information are also obtained.</span></span> <span data-ttu-id="8d483-110">이 예제에서는 포커스 변경 이벤트 처리기를 사용 하 여을 구현 하는 테이블 형식 컨트롤의 키보드 트래버스를 시뮬레이션 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d483-110">This example uses a focus change event handler to simulate keyboard traversal of a tabular control that implements [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="8d483-111">각 테이블 항목에 대 한 정보는 포커스 변경 이벤트에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d483-111">Information for each table item is exposed on a focus change event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d483-112">포커스 변경은 전역 데스크톱 이벤트 이므로 테이블 외부의 포커스 변경 이벤트가 필터링 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d483-112">Since focus changes are global desktop events, focus change events outside the table should be filtered.</span></span> <span data-ttu-id="8d483-113">관련 구현에 대 한 이동 [포커스 샘플](/previous-versions/dotnet/netframework-3.5/ms771428(v=vs.90)) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d483-113">See the [TrackFocus Sample](/previous-versions/dotnet/netframework-3.5/ms771428(v=vs.90)) for a related implementation.</span></span>  
  
 [!code-csharp[UIATableItemPattern_snip#StartTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#starttarget)]
 [!code-vb[UIATableItemPattern_snip#StartTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#starttarget)]  
[!code-csharp[UIATableItemPattern_snip#GetTableElement](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#gettableelement)]
[!code-vb[UIATableItemPattern_snip#GetTableElement](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#gettableelement)]  
[!code-csharp[UIATableItemPattern_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#101)]
[!code-vb[UIATableItemPattern_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#101)]  
[!code-csharp[UIATableItemPattern_snip#1015](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#1015)]
[!code-vb[UIATableItemPattern_snip#1015](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#1015)]  
[!code-csharp[UIATableItemPattern_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#102)]
[!code-vb[UIATableItemPattern_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#102)]  
[!code-csharp[UIATableItemPattern_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#103)]
[!code-vb[UIATableItemPattern_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="8d483-114">참조</span><span class="sxs-lookup"><span data-stu-id="8d483-114">See also</span></span>

- [<span data-ttu-id="8d483-115">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="8d483-115">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="8d483-116">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="8d483-116">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="8d483-117">UI 자동화 Table 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="8d483-117">Implementing the UI Automation Table Control Pattern</span></span>](implementing-the-ui-automation-table-control-pattern.md)
- [<span data-ttu-id="8d483-118">UI 자동화 TableItem 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="8d483-118">Implementing the UI Automation TableItem Control Pattern</span></span>](implementing-the-ui-automation-tableitem-control-pattern.md)
- [<span data-ttu-id="8d483-119">UI 자동화 Grid 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="8d483-119">Implementing the UI Automation Grid Control Pattern</span></span>](implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="8d483-120">UI 자동화 GridItem 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="8d483-120">Implementing the UI Automation GridItem Control Pattern</span></span>](implementing-the-ui-automation-griditem-control-pattern.md)
