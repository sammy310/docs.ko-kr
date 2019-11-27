---
title: TreeWalker를 사용하여 UI 자동화 요소 간 탐색
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, TreeWalker
- TreeWalker class
- elements, navigating among
- UI Automation, navigating among elements
ms.assetid: afcd21dc-2ffa-48c9-9332-51269f44b7e9
ms.openlocfilehash: 5c14a660481ed14c0d9f379c80f2d6934a3b6dcb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443177"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a><span data-ttu-id="6bff9-102">TreeWalker를 사용하여 UI 자동화 요소 간 탐색</span><span class="sxs-lookup"><span data-stu-id="6bff9-102">Navigate Among UI Automation Elements with TreeWalker</span></span>
> [!NOTE]
> <span data-ttu-id="6bff9-103">이 설명서는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 네임스페이스에 정의된 관리되는 <xref:System.Windows.Automation> 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6bff9-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6bff9-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6bff9-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="6bff9-105">이 항목에는 <xref:System.Windows.Automation.TreeWalker> 클래스를 사용 하 여 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 요소 간을 탐색 하는 방법을 보여 주는 예제 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bff9-105">This topic contains example code that shows how to navigate among [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements by using the <xref:System.Windows.Automation.TreeWalker> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bff9-106">예제</span><span class="sxs-lookup"><span data-stu-id="6bff9-106">Example</span></span>  
 <span data-ttu-id="6bff9-107">다음 예제에서는 <xref:System.Windows.Automation.TreeWalker.GetParent%2A>를 사용 하 여 루트 요소 또는 데스크톱을 찾을 때까지 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 트리를 탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bff9-107">The following example uses <xref:System.Windows.Automation.TreeWalker.GetParent%2A> to walk up the [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tree until it finds the root element, or desktop.</span></span> <span data-ttu-id="6bff9-108">지정 된 요소의 부모 창인 바로 아래에 있는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6bff9-108">The element just below that is the parent window of the specified element.</span></span>  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a><span data-ttu-id="6bff9-109">예제</span><span class="sxs-lookup"><span data-stu-id="6bff9-109">Example</span></span>  
 <span data-ttu-id="6bff9-110">다음 예제에서는 <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> 및 <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A>를 사용 하 여 컨트롤 뷰에 있고 사용 하도록 설정 된 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 요소의 전체 하위 트리를 보여 주는 <xref:System.Windows.Forms.TreeView>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6bff9-110">The following example uses <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> and <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> to create a <xref:System.Windows.Forms.TreeView> that shows an entire subtree of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements that are in the control view and that are enabled.</span></span>  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a><span data-ttu-id="6bff9-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6bff9-111">See also</span></span>

- [<span data-ttu-id="6bff9-112">UI 자동화 요소 가져오기</span><span class="sxs-lookup"><span data-stu-id="6bff9-112">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
