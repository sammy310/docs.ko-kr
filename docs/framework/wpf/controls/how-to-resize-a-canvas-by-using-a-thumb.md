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
ms.openlocfilehash: 80b873e81acc243ff61257bc305c4f782b5bf867
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351831"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a><span data-ttu-id="ab074-102">방법: Thumb을 사용하여 캔버스 크기 조정</span><span class="sxs-lookup"><span data-stu-id="ab074-102">How to: Resize a Canvas by Using a Thumb</span></span>
<span data-ttu-id="ab074-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤의 크기를 조정 하는 <xref:System.Windows.Controls.Canvas> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="ab074-103">This example shows how to use a <xref:System.Windows.Controls.Primitives.Thumb> control to resize a <xref:System.Windows.Controls.Canvas> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab074-104">예제</span><span class="sxs-lookup"><span data-stu-id="ab074-104">Example</span></span>  
 <span data-ttu-id="ab074-105"><xref:System.Windows.Controls.Primitives.Thumb> 컨트롤을 이동 하거나 모니터링 하 여 컨트롤을 크기 조정에 사용할 수 있는 끌기 기능을 제공 합니다 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 및 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> 의 이벤트는 <xref:System.Windows.Controls.Primitives.Thumb>합니다.</span><span class="sxs-lookup"><span data-stu-id="ab074-105">The <xref:System.Windows.Controls.Primitives.Thumb> control provides drag functionality that can be used to move or resize controls by monitoring the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> events of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="ab074-106">사용자가 마우스 포인터의 일시 중지 되 면 마우스 왼쪽된 단추를 눌러 끌기 작업을 시작 합니다 <xref:System.Windows.Controls.Primitives.Thumb> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab074-106">The user begins a drag operation by pressing the left mouse button when the mouse pointer is paused on the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="ab074-107">끌기 작업에는 마우스 왼쪽된 단추를 누른 동안 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab074-107">The drag operation continues as long as the left mouse button remains pressed.</span></span> <span data-ttu-id="ab074-108">끌기 작업 중의 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 두 번 이상 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab074-108">During the drag operation, the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> can occur more than once.</span></span> <span data-ttu-id="ab074-109">발생할 때마다는 <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> 클래스는 해당 마우스 위치를 변경 하는 위치에 변경 내용을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab074-109">Each time it occurs, the <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> class provides the change in position that corresponds to the change in mouse position.</span></span> <span data-ttu-id="ab074-110">마우스 왼쪽된 단추를 놓을 때 끌기 작업 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab074-110">When the user releases the left mouse button, the drag operation is finished.</span></span> <span data-ttu-id="ab074-111">끌기 작업만 새 좌표를 제공 합니다. 자동으로 위치를 유지 합니다 <xref:System.Windows.Controls.Primitives.Thumb>합니다.</span><span class="sxs-lookup"><span data-stu-id="ab074-111">The drag operation only provides new coordinates; it does not automatically reposition the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="ab074-112">에서는 다음 예제는 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤의 자식 요소인은 <xref:System.Windows.Controls.Canvas> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab074-112">The following example shows a <xref:System.Windows.Controls.Primitives.Thumb> control that is the child element of a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="ab074-113">이벤트 처리기를 해당 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 이동할 논리를 제공 하는 이벤트를 <xref:System.Windows.Controls.Primitives.Thumb> 크기를 조정 하 고는 <xref:System.Windows.Controls.Canvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="ab074-113">The event handler for its <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event provides the logic to move the <xref:System.Windows.Controls.Primitives.Thumb> and resize the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="ab074-114">에 대 한 이벤트 처리기를 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> 하 고 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> 의 색을 변경 하는 이벤트를 <xref:System.Windows.Controls.Primitives.Thumb> 끌기 작업 중입니다.</span><span class="sxs-lookup"><span data-stu-id="ab074-114">The event handlers for the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event change the color of the <xref:System.Windows.Controls.Primitives.Thumb> during a drag operation.</span></span> <span data-ttu-id="ab074-115">다음 예제에서는 정의 된 <xref:System.Windows.Controls.Primitives.Thumb>합니다.</span><span class="sxs-lookup"><span data-stu-id="ab074-115">The following example defines the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 <span data-ttu-id="ab074-116">다음 예제와 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 이동 하는 이벤트 처리기는 <xref:System.Windows.Controls.Primitives.Thumb> 크기를 조정 하 고는 <xref:System.Windows.Controls.Canvas> 마우스 이동에 대 한 응답에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab074-116">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event handler that moves the <xref:System.Windows.Controls.Primitives.Thumb> and resizes the <xref:System.Windows.Controls.Canvas> in response to a mouse movement.</span></span>  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 <span data-ttu-id="ab074-117">다음 예제는 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="ab074-117">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 <span data-ttu-id="ab074-118">다음 예제는 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="ab074-118">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 <span data-ttu-id="ab074-119">전체 샘플을 참조 하세요 [Thumb 끌기 기능 샘플](https://go.microsoft.com/fwlink/?LinkID=160042)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab074-119">For the complete sample, see [Thumb Drag Functionality Sample](https://go.microsoft.com/fwlink/?LinkID=160042).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab074-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="ab074-120">See also</span></span>
- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
