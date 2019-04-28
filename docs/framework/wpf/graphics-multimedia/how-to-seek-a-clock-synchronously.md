---
title: '방법: 동기적으로 시계 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
ms.openlocfilehash: 9b6b1f5523effc56ccd9ddaa4f478e1d3a20ada8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651261"
---
# <a name="how-to-seek-a-clock-synchronously"></a><span data-ttu-id="e713d-102">방법: 동기적으로 시계 검색</span><span class="sxs-lookup"><span data-stu-id="e713d-102">How to: Seek a Clock Synchronously</span></span>
<span data-ttu-id="e713d-103">사용 된 <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> 특정 시점으로 시계를 동기적으로 검색 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e713d-103">Use the <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> method to seek a clock to a specific point synchronously.</span></span> <span data-ttu-id="e713d-104">다음 예제에서는 둘 다를 <xref:System.Windows.Media.Animation.ClockController.Seek%2A> 하 고 <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> 의 메서드를 <xref:System.Windows.Media.Animation.ClockController>합니다.</span><span class="sxs-lookup"><span data-stu-id="e713d-104">The following example demonstrates both the <xref:System.Windows.Media.Animation.ClockController.Seek%2A> and <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> methods of a <xref:System.Windows.Media.Animation.ClockController>.</span></span>  
  
 <span data-ttu-id="e713d-105">검색 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.Clock>; 내용은 storyboard 검색 하는 방법을 보여 주는 예제 [는 스토리 보드 동기적으로 검색](how-to-seek-a-storyboard-synchronously.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="e713d-105">This example shows how to seek a <xref:System.Windows.Media.Animation.Clock>; for an example showing how to seek a storyboard, see [Seek a Storyboard Synchronously](how-to-seek-a-storyboard-synchronously.md) .</span></span>  
  
## <a name="example"></a><span data-ttu-id="e713d-106">예제</span><span class="sxs-lookup"><span data-stu-id="e713d-106">Example</span></span>  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
