---
title: 지원되는 UI 자동화 컨트롤 패턴 가져오기
description: UI 자동화 요소에서 지원 되는 컨트롤 패턴 개체를 검색 하는 방법을 보여 주는 예제를 읽습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
ms.openlocfilehash: 68abe272e91c40932aba5bcf99394c4a8f815c53
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276453"
---
# <a name="get-supported-ui-automation-control-patterns"></a><span data-ttu-id="ca974-103">지원되는 UI 자동화 컨트롤 패턴 가져오기</span><span class="sxs-lookup"><span data-stu-id="ca974-103">Get Supported UI Automation Control Patterns</span></span>

> [!NOTE]
> <span data-ttu-id="ca974-104">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca974-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ca974-105">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca974-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="ca974-106">이 항목에서는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]  요소에서 컨트롤 패턴을 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca974-106">This topic shows how to retrieve control pattern objects from [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements.</span></span>  
  
### <a name="obtain-all-control-patterns"></a><span data-ttu-id="ca974-107">모든 컨트롤 패턴 가져오기</span><span class="sxs-lookup"><span data-stu-id="ca974-107">Obtain All Control Patterns</span></span>  
  
1. <span data-ttu-id="ca974-108">사용할 컨트롤 패턴이 있는 <xref:System.Windows.Automation.AutomationElement>를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca974-108">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="ca974-109">요소에서 모든 컨트롤 패턴을 가져오려면 <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ca974-109">Call <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> to get all control patterns from the element.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="ca974-110">클라이언트가 <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>를 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ca974-110">It is strongly recommended that a client not use <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span></span> <span data-ttu-id="ca974-111">이 메서드는 기존의 각 컨트롤 패턴에 대해 내부적으로 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>을 호출하기 때문에 성능에 심각한 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca974-111">Performance can be severely affected as this method calls <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internally for each existing control pattern.</span></span> <span data-ttu-id="ca974-112">가능하면 클라이언트는 사용할 키 패턴에 대해 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>을 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca974-112">If possible, a client should call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> for the key patterns of interest.</span></span>  
  
### <a name="obtain-a-specific-control-pattern"></a><span data-ttu-id="ca974-113">특정 컨트롤 패턴 가져오기</span><span class="sxs-lookup"><span data-stu-id="ca974-113">Obtain a Specific Control Pattern</span></span>  
  
1. <span data-ttu-id="ca974-114">사용할 컨트롤 패턴이 있는 <xref:System.Windows.Automation.AutomationElement>를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca974-114">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="ca974-115">특정 패턴을 쿼리하려면 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> 또는 <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ca974-115">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> to query for a specific pattern.</span></span> <span data-ttu-id="ca974-116">이러한 메서드는 비슷하지만, 해당 패턴을 찾을 수 없는 경우 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>에서 예외가 발생하고 <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>가 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca974-116">These methods are similar, but if the pattern is not found, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> raises an exception, and <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> returns `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca974-117">예제</span><span class="sxs-lookup"><span data-stu-id="ca974-117">Example</span></span>  

 <span data-ttu-id="ca974-118">다음 예제에서는 목록 항목에 대해 <xref:System.Windows.Automation.AutomationElement>를 검색하고 해당 요소에서 <xref:System.Windows.Automation.SelectionItemPattern>을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca974-118">The following example retrieves an <xref:System.Windows.Automation.AutomationElement> for a list item and obtains a <xref:System.Windows.Automation.SelectionItemPattern> from that element.</span></span>  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="ca974-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca974-119">See also</span></span>

- [<span data-ttu-id="ca974-120">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="ca974-120">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
