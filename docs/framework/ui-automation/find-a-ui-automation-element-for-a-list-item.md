---
title: 목록 항목의 UI 자동화 요소 찾기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: ca4fdfabc4202ae9c9a36d4c511ebefc3ddd058d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969011"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="f01a3-102">목록 항목의 UI 자동화 요소 찾기</span><span class="sxs-lookup"><span data-stu-id="f01a3-102">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
> <span data-ttu-id="f01a3-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f01a3-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f01a3-104">에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] [최신 정보는 Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="f01a3-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="f01a3-105">이 항목에서는 항목의 인덱스를 <xref:System.Windows.Automation.AutomationElement> 알고 있을 때 목록 내의 항목에 대 한를 검색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f01a3-105">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f01a3-106">예제</span><span class="sxs-lookup"><span data-stu-id="f01a3-106">Example</span></span>  
 <span data-ttu-id="f01a3-107">다음 예제에서는 목록에서 지정 된 항목을 검색 하 <xref:System.Windows.Automation.TreeWalker> 는 두 가지 방법, 즉를 사용 하는 방법과를 사용 <xref:System.Windows.Automation.AutomationElement.FindAll%2A>하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f01a3-107">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="f01a3-108">첫 번째 기술은 컨트롤의 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 속도는 더 빠르지만 Windows Presentation Foundation (WPF) 컨트롤에 대 한 두 번째 기술은 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="f01a3-108">The first technique tends to be faster for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="f01a3-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="f01a3-109">See also</span></span>

- [<span data-ttu-id="f01a3-110">UI 자동화 요소 가져오기</span><span class="sxs-lookup"><span data-stu-id="f01a3-110">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
