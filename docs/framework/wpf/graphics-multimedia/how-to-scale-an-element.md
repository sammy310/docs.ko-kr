---
title: '방법: 요소 배율 조정'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 34d954f68747be9eedc0ef71634e0c18b411d260
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112052"
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="31952-102">방법: 요소 배율 조정</span><span class="sxs-lookup"><span data-stu-id="31952-102">How to: Scale an Element</span></span>
<span data-ttu-id="31952-103">이 예제에서는 a를 <xref:System.Windows.Media.ScaleTransform> 사용하여 요소를 배율 조정하는 방법을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="31952-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="31952-104"><xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 및 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 속성을 사용하여 지정한 요소별로 요소의 크기를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="31952-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="31952-105">예를 들어 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 값이 1.5이면 요소가 원래 너비의 150%로 늘어입니다.</span><span class="sxs-lookup"><span data-stu-id="31952-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="31952-106"><xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 값이 0.5이면 요소의 높이가 50% 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="31952-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="31952-107"><xref:System.Windows.Media.ScaleTransform.CenterX%2A> 및 속성을 <xref:System.Windows.Media.ScaleTransform.CenterY%2A> 사용하여 축척 작업의 중심인 점을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31952-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="31952-108">기본적으로 a는 <xref:System.Windows.Media.ScaleTransform> 사각형의 왼쪽 위 모서리에 해당하는 점(0,0)의 중심에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31952-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="31952-109">이렇게 하면 <xref:System.Windows.Media.Transform>요소를 이동하고 요소를 더 크게 표시하는 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31952-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="31952-110">다음 예제에서는 <xref:System.Windows.Media.ScaleTransform> a를 사용하여 50-50의 크기를 <xref:System.Windows.Shapes.Rectangle>두 배로 늘렸습니다.</span><span class="sxs-lookup"><span data-stu-id="31952-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="31952-111">의 <xref:System.Windows.Media.ScaleTransform> 값은 0(기본값)과 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A>에 대한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="31952-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31952-112">예제</span><span class="sxs-lookup"><span data-stu-id="31952-112">Example</span></span>  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="31952-113">일반적으로 크기조정된 <xref:System.Windows.Media.ScaleTransform.CenterY%2A> 객체의 중심(/2,<xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A>/2)을 설정하고 중심으로 설정합니다. <xref:System.Windows.Media.ScaleTransform.CenterX%2A></span><span class="sxs-lookup"><span data-stu-id="31952-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="31952-114">다음 예제에서는 <xref:System.Windows.Shapes.Rectangle> 크기가 두 배가 되는 다른 예제를 보여 주며, 그러나 이 <xref:System.Windows.Media.ScaleTransform> 값은 둘 다와 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A>사각형의 중심에 해당하는 값 25입니다.</span><span class="sxs-lookup"><span data-stu-id="31952-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="31952-115">다음 그림에서는 두 <xref:System.Windows.Media.ScaleTransform> 작업 간의 차이점을 보여 주십습니다.</span><span class="sxs-lookup"><span data-stu-id="31952-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="31952-116">점선은 크기 조정 전의 사각형 크기 및 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="31952-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="31952-117">![여러 중심점을 사용한 2x 배율 조정](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="31952-117">![2x scales with different center points](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="31952-118">ScaleX 및 ScaleY 값은 같지만 중심은 다른 두 개의 ScaleTransform 작업</span><span class="sxs-lookup"><span data-stu-id="31952-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="31952-119">전체 샘플은 [2D 변환 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="31952-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31952-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31952-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="31952-121">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="31952-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="31952-122">방법 주제</span><span class="sxs-lookup"><span data-stu-id="31952-122">How-to Topics</span></span>](transformations-how-to-topics.md)
