---
title: '방법: 시각적 요소에 텍스트 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: 1ea31540ad59ab419e209e4133bcb88640cc01fe
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368913"
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="758db-102">방법: 시각적 요소에 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="758db-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="758db-103">다음 예제에서는 텍스트를 그리는 방법에는 <xref:System.Windows.Media.DrawingVisual> 를 사용 하 여를 <xref:System.Windows.Media.DrawingContext> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="758db-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="758db-104">그리기 컨텍스트 호출에서 반환 되는 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> 메서드는 <xref:System.Windows.Media.DrawingVisual> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="758db-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="758db-105">그리기 컨텍스트에 그래픽 및 텍스트를 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="758db-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="758db-106">텍스트를 그리려면 그리기 컨텍스트에 사용 합니다 <xref:System.Windows.Media.DrawingContext.DrawText%2A> 메서드를 <xref:System.Windows.Media.DrawingContext> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="758db-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="758db-107">그리기 컨텍스트에 콘텐츠 그리기 작업을 완료 하는 경우 호출 된 <xref:System.Windows.Media.DrawingContext.Close%2A> 그리기 컨텍스트에 닫고 콘텐츠를 유지 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="758db-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="758db-108">예제</span><span class="sxs-lookup"><span data-stu-id="758db-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="758db-109">위의 코드 예제가 발췌된 전체 코드 샘플을 보려면 [DrawingVisuals를 사용하여 적중 테스트 샘플](https://go.microsoft.com/fwlink/?LinkID=159994)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="758db-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](https://go.microsoft.com/fwlink/?LinkID=159994).</span></span>
