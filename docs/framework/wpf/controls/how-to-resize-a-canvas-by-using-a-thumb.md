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
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a>방법: Thumb을 사용하여 캔버스 크기 조정
이 예제에서는 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤을 사용 하 여 <xref:System.Windows.Controls.Canvas> 컨트롤의 크기를 조정 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤은 <xref:System.Windows.Controls.Primitives.Thumb>의 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 및 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> 이벤트를 모니터링 하 여 컨트롤을 이동 하거나 크기를 조정 하는 데 사용할 수 있는 끌기 기능을 제공 합니다.  
  
 사용자가 마우스 포인터를 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤에서 일시 중지할 때 마우스 왼쪽 단추를 눌러 끌기 작업을 시작 합니다. 마우스 왼쪽 단추를 누른 상태에서 끌기 작업을 계속 합니다. 끌기 작업을 수행 하는 동안 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 두 번 이상 발생할 수 있습니다. <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> 클래스는 발생 될 때마다 마우스 위치의 변경에 해당 하는 위치 변경을 제공 합니다. 사용자가 왼쪽 마우스 단추를 놓으면 끌기 작업이 완료 됩니다. 끌기 작업은 새 좌표를 제공 합니다. 자동으로 <xref:System.Windows.Controls.Primitives.Thumb>의 위치를 변경 하지 않습니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Canvas> 컨트롤의 자식 요소인 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤을 보여 줍니다. <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 이벤트에 대 한 이벤트 처리기는 <xref:System.Windows.Controls.Primitives.Thumb>를 이동 하 고 <xref:System.Windows.Controls.Canvas>크기를 조정 하는 논리를 제공 합니다. <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> 및 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> 이벤트에 대 한 이벤트 처리기는 끌기 작업 중 <xref:System.Windows.Controls.Primitives.Thumb> 색을 변경 합니다. 다음 예에서는 <xref:System.Windows.Controls.Primitives.Thumb>를 정의 합니다.  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.Primitives.Thumb>를 이동 하 고 마우스 이동에 대 한 응답으로 <xref:System.Windows.Controls.Canvas> 크기를 조정 하는 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 이벤트 처리기를 보여 줍니다.  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 다음 예제는 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> 이벤트 처리기입니다.  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 다음 예제는 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> 이벤트 처리기입니다.  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 전체 샘플은 [Thumb Drag 기능 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
