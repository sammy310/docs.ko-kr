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
ms.openlocfilehash: 1b82302ff89d2e8407871cbfba6c10e8322ac4e7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435503"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="6a3eb-102">UI 자동화 요소 속성 가져오기</span><span class="sxs-lookup"><span data-stu-id="6a3eb-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
> <span data-ttu-id="6a3eb-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6a3eb-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6a3eb-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a3eb-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="6a3eb-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span><span class="sxs-lookup"><span data-stu-id="6a3eb-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="6a3eb-106">Get a Current Property Value</span><span class="sxs-lookup"><span data-stu-id="6a3eb-106">Get a Current Property Value</span></span>  
  
1. <span data-ttu-id="6a3eb-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span><span class="sxs-lookup"><span data-stu-id="6a3eb-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2. <span data-ttu-id="6a3eb-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span><span class="sxs-lookup"><span data-stu-id="6a3eb-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="6a3eb-109">Get a Cached Property Value</span><span class="sxs-lookup"><span data-stu-id="6a3eb-109">Get a Cached Property Value</span></span>  
  
1. <span data-ttu-id="6a3eb-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span><span class="sxs-lookup"><span data-stu-id="6a3eb-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="6a3eb-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span><span class="sxs-lookup"><span data-stu-id="6a3eb-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="6a3eb-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span><span class="sxs-lookup"><span data-stu-id="6a3eb-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a3eb-113">예제</span><span class="sxs-lookup"><span data-stu-id="6a3eb-113">Example</span></span>  
 <span data-ttu-id="6a3eb-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span><span class="sxs-lookup"><span data-stu-id="6a3eb-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="6a3eb-115">참조</span><span class="sxs-lookup"><span data-stu-id="6a3eb-115">See also</span></span>

- [<span data-ttu-id="6a3eb-116">클라이언트의 UI 자동화 속성</span><span class="sxs-lookup"><span data-stu-id="6a3eb-116">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)
- [<span data-ttu-id="6a3eb-117">UI 자동화의 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="6a3eb-117">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
- [<span data-ttu-id="6a3eb-118">UI 자동화 클라이언트의 캐싱</span><span class="sxs-lookup"><span data-stu-id="6a3eb-118">Caching in UI Automation Clients</span></span>](caching-in-ui-automation-clients.md)
