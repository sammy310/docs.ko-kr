---
title: TreeWalker를 사용하여 UI 자동화 요소 간 탐색
description: TreeWalker 클래스를 사용 하 여 UI 자동화 요소 사이를 탐색 하는 방법을 보여 주는 코드 예제를 참조 하세요.
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
ms.openlocfilehash: e1784862433083f15d600ea2ec39aee2323bbd12
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168017"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a><span data-ttu-id="3b559-103">TreeWalker를 사용하여 UI 자동화 요소 간 탐색</span><span class="sxs-lookup"><span data-stu-id="3b559-103">Navigate Among UI Automation Elements with TreeWalker</span></span>
> [!NOTE]
> <span data-ttu-id="3b559-104">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3b559-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="3b559-105">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b559-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="3b559-106">이 항목에는 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 클래스를 사용 하 여 요소 간을 탐색 하는 방법을 보여 주는 예제 코드가 있습니다 <xref:System.Windows.Automation.TreeWalker> .</span><span class="sxs-lookup"><span data-stu-id="3b559-106">This topic contains example code that shows how to navigate among [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements by using the <xref:System.Windows.Automation.TreeWalker> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b559-107">예제</span><span class="sxs-lookup"><span data-stu-id="3b559-107">Example</span></span>  
 <span data-ttu-id="3b559-108">다음 예제에서는 <xref:System.Windows.Automation.TreeWalker.GetParent%2A> 를 사용 하 여 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 루트 요소 또는 데스크톱을 찾을 때까지 트리를 탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b559-108">The following example uses <xref:System.Windows.Automation.TreeWalker.GetParent%2A> to walk up the [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tree until it finds the root element, or desktop.</span></span> <span data-ttu-id="3b559-109">지정 된 요소의 부모 창인 바로 아래에 있는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3b559-109">The element just below that is the parent window of the specified element.</span></span>  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a><span data-ttu-id="3b559-110">예제</span><span class="sxs-lookup"><span data-stu-id="3b559-110">Example</span></span>  
 <span data-ttu-id="3b559-111">다음 예제에서는 <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> 및 <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> 를 사용 하 여 <xref:System.Windows.Forms.TreeView> [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 컨트롤 뷰에 있고 사용 하도록 설정 된 요소의 전체 하위 트리를 보여 주는를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3b559-111">The following example uses <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> and <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> to create a <xref:System.Windows.Forms.TreeView> that shows an entire subtree of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements that are in the control view and that are enabled.</span></span>  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a><span data-ttu-id="3b559-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b559-112">See also</span></span>

- [<span data-ttu-id="3b559-113">UI 자동화 요소 가져오기</span><span class="sxs-lookup"><span data-stu-id="3b559-113">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
