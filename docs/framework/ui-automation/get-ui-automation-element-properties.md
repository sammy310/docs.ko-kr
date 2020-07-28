---
title: UI 자동화 요소 속성 가져오기
description: UI 자동화 요소의 현재 또는 캐시 된 속성을 검색 하는 방법을 보여 주는 예제 및 지침을 참조 하세요.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
ms.openlocfilehash: 277822c9d89046bfbad50df16bce83da7dd45b3b
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164109"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="52515-103">UI 자동화 요소 속성 가져오기</span><span class="sxs-lookup"><span data-stu-id="52515-103">Get UI Automation Element Properties</span></span>
> [!NOTE]
> <span data-ttu-id="52515-104">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="52515-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="52515-105">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52515-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="52515-106">이 항목에서는 요소의 속성을 검색 하는 방법을 보여 줍니다 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52515-106">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="52515-107">현재 속성 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52515-107">Get a Current Property Value</span></span>  
  
1. <span data-ttu-id="52515-108"><xref:System.Windows.Automation.AutomationElement>가져올 속성이 있는를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52515-108">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2. <span data-ttu-id="52515-109"><xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>를 호출 하거나 <xref:System.Windows.Automation.AutomationElement.Current%2A> 속성 구조를 검색 하 고 해당 멤버 중 하나에서 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52515-109">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="52515-110">캐시 된 속성 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="52515-110">Get a Cached Property Value</span></span>  
  
1. <span data-ttu-id="52515-111"><xref:System.Windows.Automation.AutomationElement>가져올 속성이 있는를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52515-111">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="52515-112">속성은에 지정 되어 있어야 합니다 <xref:System.Windows.Automation.CacheRequest> .</span><span class="sxs-lookup"><span data-stu-id="52515-112">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="52515-113"><xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>를 호출 하거나 <xref:System.Windows.Automation.AutomationElement.Cached%2A> 속성 구조를 검색 하 고 해당 멤버 중 하나에서 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52515-113">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52515-114">예제</span><span class="sxs-lookup"><span data-stu-id="52515-114">Example</span></span>  
 <span data-ttu-id="52515-115">다음 예제에서는의 현재 속성을 검색 하는 다양 한 방법을 보여 줍니다 <xref:System.Windows.Automation.AutomationElement> .</span><span class="sxs-lookup"><span data-stu-id="52515-115">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="52515-116">참조</span><span class="sxs-lookup"><span data-stu-id="52515-116">See also</span></span>

- [<span data-ttu-id="52515-117">클라이언트에 대한 UI 자동화 속성</span><span class="sxs-lookup"><span data-stu-id="52515-117">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)
- [<span data-ttu-id="52515-118">UI 자동화에서 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="52515-118">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
- [<span data-ttu-id="52515-119">UI 자동화 클라이언트에서 캐싱</span><span class="sxs-lookup"><span data-stu-id="52515-119">Caching in UI Automation Clients</span></span>](caching-in-ui-automation-clients.md)
