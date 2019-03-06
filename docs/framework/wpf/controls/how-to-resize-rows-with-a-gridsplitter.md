---
title: '방법: GridSplitter로 행 크기 조정'
ms.date: 03/30/2017
helpviewer_keywords:
- resizing grid rows [WPF]
- grid rows [WPF], resizing
- GridSplitter control [WPF], resizing grid rows
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
ms.openlocfilehash: b05bda6cd33d3cdd0dda6288f30821d290c60cfc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370048"
---
# <a name="how-to-resize-rows-with-a-gridsplitter"></a><span data-ttu-id="cc8ab-102">방법: GridSplitter로 행 크기 조정</span><span class="sxs-lookup"><span data-stu-id="cc8ab-102">How to: Resize Rows with a GridSplitter</span></span>
<span data-ttu-id="cc8ab-103">이 예제에서는 가로 사용 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.GridSplitter> 에 있는 두 행 사이의 간격을 재배포 하는 <xref:System.Windows.Controls.Grid> 의 크기를 변경 하지 않고는 <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="cc8ab-103">This example shows how to use a horizontal <xref:System.Windows.Controls.GridSplitter> to redistribute the space between two rows in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc8ab-104">예제</span><span class="sxs-lookup"><span data-stu-id="cc8ab-104">Example</span></span>  
 <span data-ttu-id="cc8ab-105">**행의 가장자리를 오버레이하는 GridSplitter를 만드는 방법**</span><span class="sxs-lookup"><span data-stu-id="cc8ab-105">**How to create a GridSplitter that overlays the edge of a row**</span></span>  
  
 <span data-ttu-id="cc8ab-106">지정 하는 <xref:System.Windows.Controls.GridSplitter> 인접 행 크기를 조정 하는 <xref:System.Windows.Controls.Grid>설정는 <xref:System.Windows.Controls.Grid.Row%2A> 크기를 조정할 행 중 하나에 연결 된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cc8ab-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="cc8ab-107">경우에 <xref:System.Windows.Controls.Grid> 둘 이상의 열이 있는 설정의 <xref:System.Windows.Controls.Grid.ColumnSpan%2A> 연결 된 속성을 열 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc8ab-107">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to specify the number of columns.</span></span> <span data-ttu-id="cc8ab-108">설정한 합니다 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 하 <xref:System.Windows.VerticalAlignment.Top> 또는 <xref:System.Windows.VerticalAlignment.Bottom> (설정 하는 맞춤의 크기를 조정 하려는 두 개의 행에 따라 다름).</span><span class="sxs-lookup"><span data-stu-id="cc8ab-108">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Top> or <xref:System.Windows.VerticalAlignment.Bottom> (which alignment you set depends on which two rows you want to resize).</span></span> <span data-ttu-id="cc8ab-109">마지막으로 설정 합니다 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성을 <xref:System.Windows.HorizontalAlignment.Stretch>입니다.</span><span class="sxs-lookup"><span data-stu-id="cc8ab-109">Finally, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>.</span></span>  
  
 <span data-ttu-id="cc8ab-110">다음 예제에서는 가로 정의 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.GridSplitter> 인접 한 행의 크기를 조정 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc8ab-110">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterRowOverlay](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 <span data-ttu-id="cc8ab-111">A <xref:System.Windows.Controls.GridSplitter> 자체 행을 차지 하지 않습니다 다른 컨트롤에 의해 가려질 수 있습니다는 <xref:System.Windows.Controls.Grid>합니다.</span><span class="sxs-lookup"><span data-stu-id="cc8ab-111">A <xref:System.Windows.Controls.GridSplitter> that does not occupy its own row may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="cc8ab-112">이 문제를 방지하는 방법에 대한 자세한 내용은 [Make Sure That a GridSplitter Is Visible](how-to-make-sure-that-a-gridsplitter-is-visible.md)(GridSplitter가 표시되는지 확인)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc8ab-112">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 <span data-ttu-id="cc8ab-113">**행을 차지하는 GridSplitter를 만드는 방법**</span><span class="sxs-lookup"><span data-stu-id="cc8ab-113">**How to create a GridSplitter that occupies a row**</span></span>  
  
 <span data-ttu-id="cc8ab-114">지정 하는 <xref:System.Windows.Controls.GridSplitter> 에서 행을 차지 하는 <xref:System.Windows.Controls.Grid>설정는 <xref:System.Windows.Controls.Grid.Row%2A> 크기를 조정할 행 중 하나에 연결 된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cc8ab-114">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a row in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="cc8ab-115">경우에 <xref:System.Windows.Controls.Grid> 둘 이상의 열이 있는 설정의 <xref:System.Windows.Controls.Grid.ColumnSpan%2A> 연결 된 속성을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc8ab-115">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to the number of columns.</span></span> <span data-ttu-id="cc8ab-116">설정한를 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 를 <xref:System.Windows.VerticalAlignment.Center>설정 합니다 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성을 <xref:System.Windows.HorizontalAlignment.Stretch>, 설정 및를 <xref:System.Windows.Controls.RowDefinition.Height%2A> 포함 된 행의를 <xref:System.Windows.Controls.GridSplitter> 를 <xref:System.Windows.GridLength.Auto%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc8ab-116">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>, and set the <xref:System.Windows.Controls.RowDefinition.Height%2A> of the row that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="cc8ab-117">다음 예제에서는 가로 정의 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.GridSplitter> 행을 차지 하 고 양쪽에서 행의 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc8ab-117">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that occupies a row and resizes the rows on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart2](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="cc8ab-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="cc8ab-118">See also</span></span>
- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="cc8ab-119">방법 항목</span><span class="sxs-lookup"><span data-stu-id="cc8ab-119">How-to Topics</span></span>](gridsplitter-how-to-topics.md)
