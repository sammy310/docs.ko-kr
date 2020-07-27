---
title: UI 자동화 조각 공급자에서 탐색 사용
description: UI 자동화 공급자에서 조각 내에 있는 요소에 대해 탐색을 사용 하도록 설정 하는 방법을 보여 주는 예제를 읽습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, enabling navigation in provider
- navigation, enabling in UI Automation provider
ms.assetid: 3cb6092a-58c9-4ca0-84a5-0e54d5d00a0d
ms.openlocfilehash: bf9e43e9d70b9191fba93e5efa4eae544196c735
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168488"
---
# <a name="enable-navigation-in-a-ui-automation-fragment-provider"></a><span data-ttu-id="d98cc-103">UI 자동화 조각 공급자에서 탐색 사용</span><span class="sxs-lookup"><span data-stu-id="d98cc-103">Enable Navigation in a UI Automation Fragment Provider</span></span>
> [!NOTE]
> <span data-ttu-id="d98cc-104">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d98cc-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d98cc-105">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d98cc-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="d98cc-106">이 항목에는 UI 자동화 공급자에서 조각 내에 있는 요소에 대해 탐색을 사용 설정하는 방법을 보여주는 예제 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d98cc-106">This topic contains example code that shows how to enable navigation in a UI Automation provider for an element that is within a fragment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d98cc-107">예제</span><span class="sxs-lookup"><span data-stu-id="d98cc-107">Example</span></span>  
 <span data-ttu-id="d98cc-108">다음 예제 코드는 목록 내에 있는 목록 항목의 <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> 을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d98cc-108">The following example code implements <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> for a list item within a list.</span></span> <span data-ttu-id="d98cc-109">부모 요소가 목록 상자 요소이고, 형제 요소는 목록 컬렉션의 다른 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="d98cc-109">The parent element is the list box element, and the sibling elements are other items in the list collection.</span></span> <span data-ttu-id="d98cc-110">메서드가 유효하지 않은 방향에 대해 `null` 을 반환합니다(Visual Basic의 경우`Nothing` ). 이 경우, 요소에 자식이 없기 때문에 <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> 및 <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>입니다.</span><span class="sxs-lookup"><span data-stu-id="d98cc-110">The method returns `null` (`Nothing` in Visual Basic) for directions that are not valid; in this case, <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> and <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>, because the element has no children.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListItemFragment.cs#103)]
 [!code-vb[UIAFragmentProvider_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListItemFragment.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="d98cc-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d98cc-111">See also</span></span>

- [<span data-ttu-id="d98cc-112">UI 자동화 공급자 개요</span><span class="sxs-lookup"><span data-stu-id="d98cc-112">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="d98cc-113">서버 쪽 UI 자동화 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="d98cc-113">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)
