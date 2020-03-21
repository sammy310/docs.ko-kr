---
title: '방법: 요소 변환'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: addff0e22fb3f27ea924887809c0635aeb3ad67d
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111974"
---
# <a name="how-to-translate-an-element"></a><span data-ttu-id="f5c8e-102">방법: 요소 변환</span><span class="sxs-lookup"><span data-stu-id="f5c8e-102">How to: Translate an Element</span></span>
<span data-ttu-id="f5c8e-103">이 예제에서는 <xref:System.Windows.Media.TranslateTransform>을 사용하여 요소를 변환(이동)하는 방법을 보여 주며.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-103">This example shows how to translate (move) an element by using a <xref:System.Windows.Media.TranslateTransform>.</span></span>  
  
 <span data-ttu-id="f5c8e-104">클래스는 <xref:System.Windows.Media.TranslateTransform> 절대 위치 지정을 지원하지 않는 패널 내부의 요소를 이동하는 데 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-104">The <xref:System.Windows.Media.TranslateTransform> class is especially useful for moving elements inside panels that do not support absolute positioning.</span></span> <span data-ttu-id="f5c8e-105">예를 들어 요소의 <xref:System.Windows.Media.TranslateTransform> 속성에 <xref:System.Windows.UIElement.RenderTransform%2A> a를 적용하여 <xref:System.Windows.Controls.StackPanel> 또는 에서 <xref:System.Windows.Controls.DockPanel>요소를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-105">For example, by applying a <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of an element, you can move an element within a <xref:System.Windows.Controls.StackPanel> or <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="f5c8e-106">의 <xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.Media.TranslateTransform.X%2A> 속성을 사용하여 x축을 따라 요소를 이동하는 양을 픽셀 단위로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-106">Use the <xref:System.Windows.Media.TranslateTransform.X%2A> property of the <xref:System.Windows.Media.TranslateTransform> to specify the amount, in pixels, to move the element along the x-axis.</span></span> <span data-ttu-id="f5c8e-107">속성을 <xref:System.Windows.Media.TranslateTransform.Y%2A> 사용하여 y축을 따라 요소를 이동하는 양을 픽셀 단위로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-107">Use the <xref:System.Windows.Media.TranslateTransform.Y%2A> property to specify the amount, in pixels, to move the element along the y-axis.</span></span> <span data-ttu-id="f5c8e-108">마지막으로 요소의 <xref:System.Windows.Media.TranslateTransform> 속성에 <xref:System.Windows.UIElement.RenderTransform%2A> 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-108">Finally, apply the <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="f5c8e-109">다음 예제에서는 <xref:System.Windows.Media.TranslateTransform> a를 사용하여 요소를 50픽셀 을 오른쪽으로, 50픽셀 아래로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-109">The following example uses a <xref:System.Windows.Media.TranslateTransform> to move an element 50 pixels to the right and 50 pixels down.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5c8e-110">예제</span><span class="sxs-lookup"><span data-stu-id="f5c8e-110">Example</span></span>  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 <span data-ttu-id="f5c8e-111">전체 샘플은 [2D 변환 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-111">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5c8e-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5c8e-112">See also</span></span>

- [<span data-ttu-id="f5c8e-113">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="f5c8e-113">Transforms Overview</span></span>](transforms-overview.md)
