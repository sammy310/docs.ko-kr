---
title: '방법: 텍스트에 변환 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], rotated text
- typography [WPF], scaled text
- skewed text [WPF]
- typography [WPF], translated text
- typography [WPF], shadowed text
- rotated text [WPF]
- translated text [WPF]
- shadowed text [WPF]
- transforms in text [WPF]
- typography [WPF], transforms
- scaled text [WPF]
- typography [WPF], skewed text
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
ms.openlocfilehash: 867f39e3df8493014d8601530e91310c3bbbeeb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141616"
---
# <a name="how-to-apply-transforms-to-text"></a><span data-ttu-id="ad3ca-102">방법: 텍스트에 변환 적용</span><span class="sxs-lookup"><span data-stu-id="ad3ca-102">How to: Apply Transforms to Text</span></span>
<span data-ttu-id="ad3ca-103">변환을 통해 애플리케이션에서 텍스트 표시를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-103">Transforms can alter the display of text in your application.</span></span> <span data-ttu-id="ad3ca-104">다음 예제에서는 컨트롤의 텍스트 표시에 영향을 주는 다양한 <xref:System.Windows.Controls.TextBlock> 유형의 렌더링 변환을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-104">The following examples use different types of rendering transforms to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad3ca-105">예제</span><span class="sxs-lookup"><span data-stu-id="ad3ca-105">Example</span></span>  
 <span data-ttu-id="ad3ca-106">다음 예에서는 2차원 x-y 평면에서 지정된 점을 기준으로 회전하는 텍스트를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-106">The following example shows text rotated about a specified point in the two-dimensional x-y plane.</span></span>  
  
 ![RotateTransform을 사용하여 회전된 텍스트](./media/how-to-apply-transforms-to-text/text-rotated-ninety-degrees.jpg)  
  
 <span data-ttu-id="ad3ca-108">다음 코드 예제에서는 <xref:System.Windows.Media.RotateTransform> a를 사용하여 텍스트를 회전합니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-108">The following code example uses a <xref:System.Windows.Media.RotateTransform> to rotate text.</span></span> <span data-ttu-id="ad3ca-109">값이 <xref:System.Windows.Media.RotateTransform.Angle%2A> 90이면 요소를 시계 방향으로 90도 회전합니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-109">An <xref:System.Windows.Media.RotateTransform.Angle%2A> value of 90 rotates the element 90 degrees clockwise.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 <span data-ttu-id="ad3ca-110">다음 예에서는 텍스트의 두 번째 라인은 x축을 따라 배율을 150% 조정하여 보여주고, 텍스트의 세 번째 라인은 y축을 따라 배율을 150% 조정하여 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-110">The following example shows the second line of text scaled by 150% along the x-axis, and the third line of text scaled by 150% along the y-axis.</span></span>  
  
 ![ScaleTransform을 사용하여 배율 조정된 텍스트](./media/how-to-apply-transforms-to-text/scaled-text-scaletransform.jpg)
  
 <span data-ttu-id="ad3ca-112">다음 코드 예제에서는 <xref:System.Windows.Media.ScaleTransform> a를 사용하여 원래 크기에서 텍스트의 배율을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-112">The following code example uses a <xref:System.Windows.Media.ScaleTransform> to scale text from its original size.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
> <span data-ttu-id="ad3ca-113">텍스트의 배율 조정은 텍스트의 글꼴 크기를 늘리는 것과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-113">Scaling text is not the same as increasing the font size of text.</span></span> <span data-ttu-id="ad3ca-114">여러 다른 크기에서 최상의 해상도를 제공하기 위해 글꼴 크기는 서로 독립적으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-114">Font sizes are calculated independently of each other in order to provide the best resolution at different sizes.</span></span> <span data-ttu-id="ad3ca-115">한편 배율 조정된 크기는 원래 크기의 텍스트에 계속 비례합니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-115">Scaled text, on the other hand, preserves the proportions of the original-sized text.</span></span>  
  
 <span data-ttu-id="ad3ca-116">다음 예에서는 x축을 따라 기울어진 텍스트를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-116">The following example shows text skewed along the x-axis.</span></span>  
  
 ![SkewTransform을 사용하여 기울인 텍스트](./media/how-to-apply-transforms-to-text/skewed-transformed-text.jpg)

 <span data-ttu-id="ad3ca-118">다음 코드 예제에서는 <xref:System.Windows.Media.SkewTransform> a를 사용하여 텍스트를 왜곡합니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-118">The following code example uses a <xref:System.Windows.Media.SkewTransform> to skew text.</span></span> <span data-ttu-id="ad3ca-119">전단이라고도 하는 기울이기는 일관되지 않은 방식으로 좌표 공간을 늘리는 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-119">A skew, also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="ad3ca-120">이 예에서 두 텍스트 문자열은 x축을 따라 -30°와 30°를 기울입니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-120">In this example, the two text strings are skewed -30° and 30° along the x-coordinate.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 <span data-ttu-id="ad3ca-121">다음 예에서는 x축과 y축을 따라 변환 또는 이동되는 텍스트를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-121">The following example shows text translated, or moved, along the x- and y-axis.</span></span>  
  
 ![TranslateTransform을 사용한 텍스트 오프셋](./media/how-to-apply-transforms-to-text/transformed-text-x-y-axis.jpg)
  
 <span data-ttu-id="ad3ca-123">다음 코드 예제에서는 <xref:System.Windows.Media.TranslateTransform> a를 사용하여 텍스트를 오프셋합니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-123">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="ad3ca-124">이 예에서 기본 텍스트 아래 약간 오프셋된 텍스트 사본이 그림자 효과를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-124">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
> <span data-ttu-id="ad3ca-125">는 <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> 그림자 효과를 제공하기 위한 다양한 기능 세트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-125">The <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> provides a rich set of features for providing shadow effects.</span></span> <span data-ttu-id="ad3ca-126">자세한 내용은 [그림자가 있는 텍스트 만들기](how-to-create-text-with-a-shadow.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad3ca-126">For more information, see [Create Text with a Shadow](how-to-create-text-with-a-shadow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad3ca-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad3ca-127">See also</span></span>

- [<span data-ttu-id="ad3ca-128">텍스트에 애니메이션 적용</span><span class="sxs-lookup"><span data-stu-id="ad3ca-128">Apply Animations to Text</span></span>](how-to-apply-animations-to-text.md)
