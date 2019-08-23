---
title: UI 자동화 요소 속성 가져오기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
ms.openlocfilehash: e3b3b118c3db95f55c67c2b27149734efc8cbea8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968961"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="731fb-102">UI 자동화 요소 속성 가져오기</span><span class="sxs-lookup"><span data-stu-id="731fb-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
> <span data-ttu-id="731fb-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="731fb-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="731fb-104">에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] [최신 정보는 Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="731fb-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="731fb-105">이 항목에서는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 요소의 속성을 검색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="731fb-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="731fb-106">현재 속성 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="731fb-106">Get a Current Property Value</span></span>  
  
1. <span data-ttu-id="731fb-107">가져올 속성이 <xref:System.Windows.Automation.AutomationElement> 있는를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="731fb-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2. <span data-ttu-id="731fb-108">를 <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>호출 하거나 속성 구조 <xref:System.Windows.Automation.AutomationElement.Current%2A> 를 검색 하 고 해당 멤버 중 하나에서 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="731fb-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="731fb-109">캐시 된 속성 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="731fb-109">Get a Cached Property Value</span></span>  
  
1. <span data-ttu-id="731fb-110">가져올 속성이 <xref:System.Windows.Automation.AutomationElement> 있는를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="731fb-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="731fb-111">속성은에 <xref:System.Windows.Automation.CacheRequest>지정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="731fb-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="731fb-112">를 <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>호출 하거나 속성 구조 <xref:System.Windows.Automation.AutomationElement.Cached%2A> 를 검색 하 고 해당 멤버 중 하나에서 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="731fb-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="731fb-113">예제</span><span class="sxs-lookup"><span data-stu-id="731fb-113">Example</span></span>  
 <span data-ttu-id="731fb-114">다음 예제에서는의 <xref:System.Windows.Automation.AutomationElement>현재 속성을 검색 하는 다양 한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="731fb-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="731fb-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="731fb-115">See also</span></span>

- [<span data-ttu-id="731fb-116">클라이언트의 UI 자동화 속성</span><span class="sxs-lookup"><span data-stu-id="731fb-116">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)
- [<span data-ttu-id="731fb-117">UI 자동화의 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="731fb-117">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
- [<span data-ttu-id="731fb-118">UI 자동화 클라이언트의 캐싱</span><span class="sxs-lookup"><span data-stu-id="731fb-118">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
