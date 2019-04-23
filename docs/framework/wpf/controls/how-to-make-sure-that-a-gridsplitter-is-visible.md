---
title: '방법: GridSplitter 표시'
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: b7543d14ba39d854b5a2c3f4d0d19b9a457ea89b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59147149"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a><span data-ttu-id="a4a27-102">방법: GridSplitter 표시</span><span class="sxs-lookup"><span data-stu-id="a4a27-102">How to: Make Sure That a GridSplitter Is Visible</span></span>
<span data-ttu-id="a4a27-103">있는지 확인 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.GridSplitter> 컨트롤에서 다른 컨트롤에 의해 숨겨지지 않은 <xref:System.Windows.Controls.Grid>합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a27-103">This example shows how to make sure a <xref:System.Windows.Controls.GridSplitter> control is not hidden by the other controls in a <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4a27-104">예제</span><span class="sxs-lookup"><span data-stu-id="a4a27-104">Example</span></span>  
 <span data-ttu-id="a4a27-105">합니다 <xref:System.Windows.Controls.Panel.Children%2A> 의 한 <xref:System.Windows.Controls.Grid> 컨트롤 태그 또는 코드에서 정의 된 순서 대로 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4a27-105">The <xref:System.Windows.Controls.Panel.Children%2A> of a <xref:System.Windows.Controls.Grid> control are rendered in the order that they are defined in markup or code.</span></span> <span data-ttu-id="a4a27-106"><xref:System.Windows.Controls.GridSplitter> 마지막 요소로 정의 하지 않는 경우 다른 컨트롤에서 컨트롤을 숨길 수 있습니다 합니다 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션 또는 다른를 제공 하는 경우 컨트롤에 더 높은 <xref:System.Windows.Controls.Panel.ZIndexProperty>합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a27-106"><xref:System.Windows.Controls.GridSplitter> controls can be hidden by other controls if you do not define them as the last elements in the <xref:System.Windows.Controls.Panel.Children%2A> collection or if you give other controls a higher <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span></span>  
  
 <span data-ttu-id="a4a27-107">방지 하기 위해 숨겨진 <xref:System.Windows.Controls.GridSplitter> 컨트롤 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a27-107">To prevent hidden <xref:System.Windows.Controls.GridSplitter> controls, do one of the following.</span></span>  
  
-   <span data-ttu-id="a4a27-108">했는지 <xref:System.Windows.Controls.GridSplitter> 컨트롤은 마지막 <xref:System.Windows.Controls.Panel.Children%2A> 에 추가 된 <xref:System.Windows.Controls.Grid>합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a27-108">Make sure that <xref:System.Windows.Controls.GridSplitter> controls are the last <xref:System.Windows.Controls.Panel.Children%2A> added to the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="a4a27-109">다음 예제와 <xref:System.Windows.Controls.GridSplitter> 에서 마지막 요소로 <xref:System.Windows.Controls.Panel.Children%2A> 의 컬렉션을 <xref:System.Windows.Controls.Grid>합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a27-109">The following example shows the <xref:System.Windows.Controls.GridSplitter> as the last element in the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   <span data-ttu-id="a4a27-110">설정 된 <xref:System.Windows.Controls.Panel.ZIndexProperty> 에 <xref:System.Windows.Controls.GridSplitter> 숨길 수 있는 컨트롤 보다 높을 수.</span><span class="sxs-lookup"><span data-stu-id="a4a27-110">Set the <xref:System.Windows.Controls.Panel.ZIndexProperty> on the <xref:System.Windows.Controls.GridSplitter> to be higher than a control that would otherwise hide it.</span></span> <span data-ttu-id="a4a27-111">다음 예제에서는 합니다 <xref:System.Windows.Controls.GridSplitter> 더 높은 제어 <xref:System.Windows.Controls.Panel.ZIndexProperty> 보다는 <xref:System.Windows.Controls.Button> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a27-111">The following example gives the <xref:System.Windows.Controls.GridSplitter> control a higher <xref:System.Windows.Controls.Panel.ZIndexProperty> than the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   <span data-ttu-id="a4a27-112">숨길 수 있는 컨트롤의 여백을 설정 합니다 <xref:System.Windows.Controls.GridSplitter> 있도록는 <xref:System.Windows.Controls.GridSplitter> 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4a27-112">Set margins on the control that would otherwise hide the <xref:System.Windows.Controls.GridSplitter> so that the <xref:System.Windows.Controls.GridSplitter> is exposed.</span></span> <span data-ttu-id="a4a27-113">다음 예제에서는 겹쳐져 컨트롤과 숨기기에 여백을 설정 하는 <xref:System.Windows.Controls.GridSplitter>합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a27-113">The following example sets margins on a control that would otherwise overlay and hide the <xref:System.Windows.Controls.GridSplitter>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a><span data-ttu-id="a4a27-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="a4a27-114">See also</span></span>

- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="a4a27-115">방법 항목</span><span class="sxs-lookup"><span data-stu-id="a4a27-115">How-to Topics</span></span>](gridsplitter-how-to-topics.md)
