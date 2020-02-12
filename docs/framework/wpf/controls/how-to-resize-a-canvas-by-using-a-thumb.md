---
title: '방법: Thumb을 사용하여 캔버스 크기 조정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resizing Canvas control [WPF]
- controls [WPF], Thumb
- controls [WPF], Canvas
- Thumb control [WPF]
- Canvas control [WPF]
ms.assetid: 7dc9f435-726c-4d4d-be41-eb24cfe17bef
ms.openlocfilehash: 84f5ac2b53124b7f4d7c15741e94b40e7ee81526
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124301"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a><span data-ttu-id="97bde-102">방법: Thumb을 사용하여 캔버스 크기 조정</span><span class="sxs-lookup"><span data-stu-id="97bde-102">How to: Resize a Canvas by Using a Thumb</span></span>
<span data-ttu-id="97bde-103">이 예제에서는 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤을 사용 하 여 <xref:System.Windows.Controls.Canvas> 컨트롤의 크기를 조정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97bde-103">This example shows how to use a <xref:System.Windows.Controls.Primitives.Thumb> control to resize a <xref:System.Windows.Controls.Canvas> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97bde-104">예제</span><span class="sxs-lookup"><span data-stu-id="97bde-104">Example</span></span>  
 <span data-ttu-id="97bde-105"><xref:System.Windows.Controls.Primitives.Thumb> 컨트롤은 <xref:System.Windows.Controls.Primitives.Thumb>의 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 및 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> 이벤트를 모니터링 하 여 컨트롤을 이동 하거나 크기를 조정 하는 데 사용할 수 있는 끌기 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="97bde-105">The <xref:System.Windows.Controls.Primitives.Thumb> control provides drag functionality that can be used to move or resize controls by monitoring the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> events of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="97bde-106">사용자가 마우스 포인터를 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤에서 일시 중지할 때 마우스 왼쪽 단추를 눌러 끌기 작업을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="97bde-106">The user begins a drag operation by pressing the left mouse button when the mouse pointer is paused on the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="97bde-107">마우스 왼쪽 단추를 누른 상태에서 끌기 작업을 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="97bde-107">The drag operation continues as long as the left mouse button remains pressed.</span></span> <span data-ttu-id="97bde-108">끌기 작업을 수행 하는 동안 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 두 번 이상 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97bde-108">During the drag operation, the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> can occur more than once.</span></span> <span data-ttu-id="97bde-109"><xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> 클래스는 발생 될 때마다 마우스 위치의 변경에 해당 하는 위치 변경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="97bde-109">Each time it occurs, the <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> class provides the change in position that corresponds to the change in mouse position.</span></span> <span data-ttu-id="97bde-110">사용자가 왼쪽 마우스 단추를 놓으면 끌기 작업이 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97bde-110">When the user releases the left mouse button, the drag operation is finished.</span></span> <span data-ttu-id="97bde-111">끌기 작업은 새 좌표를 제공 합니다. 자동으로 <xref:System.Windows.Controls.Primitives.Thumb>의 위치를 변경 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97bde-111">The drag operation only provides new coordinates; it does not automatically reposition the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="97bde-112">다음 예제에서는 <xref:System.Windows.Controls.Canvas> 컨트롤의 자식 요소인 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97bde-112">The following example shows a <xref:System.Windows.Controls.Primitives.Thumb> control that is the child element of a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="97bde-113"><xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 이벤트에 대 한 이벤트 처리기는 <xref:System.Windows.Controls.Primitives.Thumb>를 이동 하 고 <xref:System.Windows.Controls.Canvas>크기를 조정 하는 논리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="97bde-113">The event handler for its <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event provides the logic to move the <xref:System.Windows.Controls.Primitives.Thumb> and resize the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="97bde-114"><xref:System.Windows.Controls.Primitives.Thumb.DragStarted> 및 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> 이벤트에 대 한 이벤트 처리기는 끌기 작업 중 <xref:System.Windows.Controls.Primitives.Thumb> 색을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="97bde-114">The event handlers for the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event change the color of the <xref:System.Windows.Controls.Primitives.Thumb> during a drag operation.</span></span> <span data-ttu-id="97bde-115">다음 예에서는 <xref:System.Windows.Controls.Primitives.Thumb>를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="97bde-115">The following example defines the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 <span data-ttu-id="97bde-116">다음 예제에서는 <xref:System.Windows.Controls.Primitives.Thumb>를 이동 하 고 마우스 이동에 대 한 응답으로 <xref:System.Windows.Controls.Canvas> 크기를 조정 하는 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 이벤트 처리기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97bde-116">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event handler that moves the <xref:System.Windows.Controls.Primitives.Thumb> and resizes the <xref:System.Windows.Controls.Canvas> in response to a mouse movement.</span></span>  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 <span data-ttu-id="97bde-117">다음 예제는 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="97bde-117">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 <span data-ttu-id="97bde-118">다음 예제는 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="97bde-118">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 <span data-ttu-id="97bde-119">전체 샘플은 [Thumb Drag 기능 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97bde-119">For the complete sample, see [Thumb Drag Functionality Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97bde-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97bde-120">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
