---
title: '방법: 가로 또는 세로로 UIElement 대칭 이동'
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 6b3da322493d17e4f8e36a35b9a0e40fdc9dc685
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215523"
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a><span data-ttu-id="3916c-102">방법: 가로 또는 세로로 UIElement 대칭 이동</span><span class="sxs-lookup"><span data-stu-id="3916c-102">How to: Flip a UIElement Horizontally or Vertically</span></span>
<span data-ttu-id="3916c-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.ScaleTransform> 대칭으로 배열할지를 <xref:System.Windows.UIElement> 가로나 세로 방향으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3916c-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to flip a <xref:System.Windows.UIElement> horizontally or vertically.</span></span> <span data-ttu-id="3916c-104">이 예제에서는 <xref:System.Windows.Controls.Button> 컨트롤 (유형의 <xref:System.Windows.UIElement>) 적용 하 여 대칭 이동를 <xref:System.Windows.Media.ScaleTransform> 에 해당 <xref:System.Windows.UIElement.RenderTransform%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3916c-104">In this example, a <xref:System.Windows.Controls.Button> control (a type of <xref:System.Windows.UIElement>) is flipped by applying a <xref:System.Windows.Media.ScaleTransform> to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3916c-105">예제</span><span class="sxs-lookup"><span data-stu-id="3916c-105">Example</span></span>  
 <span data-ttu-id="3916c-106">다음 그림에서는 대칭 이동 하려면 단추를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3916c-106">The following illustration shows the button to flip.</span></span>  
  
 <span data-ttu-id="3916c-107">![변형이 없는 단추](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span><span class="sxs-lookup"><span data-stu-id="3916c-107">![A button with no transform](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span></span>  
<span data-ttu-id="3916c-108">UIElement 대칭 이동</span><span class="sxs-lookup"><span data-stu-id="3916c-108">The UIElement to flip</span></span>  
  
 <span data-ttu-id="3916c-109">다음 단추를 만드는 코드를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="3916c-109">The following shows the code that creates the button.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a><span data-ttu-id="3916c-110">예제</span><span class="sxs-lookup"><span data-stu-id="3916c-110">Example</span></span>  
 <span data-ttu-id="3916c-111">만들기 단추를 가로로 대칭 이동 하는 <xref:System.Windows.Media.ScaleTransform> 설정 및 해당 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 속성을-1입니다.</span><span class="sxs-lookup"><span data-stu-id="3916c-111">To flip the button horizontally, create a <xref:System.Windows.Media.ScaleTransform> and set its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property to -1.</span></span> <span data-ttu-id="3916c-112">적용 된 <xref:System.Windows.Media.ScaleTransform> 단추를 <xref:System.Windows.UIElement.RenderTransform%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3916c-112">Apply the <xref:System.Windows.Media.ScaleTransform> to the button's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 <span data-ttu-id="3916c-113">![단추에 대 한 가로 대칭 이동 된 &#40;0, 0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span><span class="sxs-lookup"><span data-stu-id="3916c-113">![A button flipped horizontally about &#40;0,0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span></span>  
<span data-ttu-id="3916c-114">ScaleTransform을 적용 한 후 단추</span><span class="sxs-lookup"><span data-stu-id="3916c-114">The button after applying the ScaleTransform</span></span>  
  
## <a name="example"></a><span data-ttu-id="3916c-115">예제</span><span class="sxs-lookup"><span data-stu-id="3916c-115">Example</span></span>  
 <span data-ttu-id="3916c-116">위의 그림에서 보듯이 단추 대칭 되는 이동 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3916c-116">As you can see from the previous illustration, the button was flipped, but it was also moved.</span></span> <span data-ttu-id="3916c-117">단추를 왼쪽된 위 모서리에서 대칭 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3916c-117">That's because the button was flipped from its top left corner.</span></span> <span data-ttu-id="3916c-118">적용 하려는 곳에서 단추를 뒤집고,는 <xref:System.Windows.Media.ScaleTransform> 해당 센터로 구석에 해당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3916c-118">To flip the button in place, you want to apply the <xref:System.Windows.Media.ScaleTransform> to its center, not its corner.</span></span> <span data-ttu-id="3916c-119">적용 하는 쉬운 방법을 합니다 <xref:System.Windows.Media.ScaleTransform> 단추를 가운데 단추를 설정 하는 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 속성을 0.5, 0.5입니다.</span><span class="sxs-lookup"><span data-stu-id="3916c-119">An easy way to apply the <xref:System.Windows.Media.ScaleTransform> to the buttons center is to set the button's <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to 0.5, 0.5.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 <span data-ttu-id="3916c-120">![가운데를 중심으로 가로 대칭 이동 된 단추](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="3916c-120">![A button flipped horizontally about its center](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span></span>  
<span data-ttu-id="3916c-121">RenderTransformOrigin 0.5를 사용 하 여 단추 0.5</span><span class="sxs-lookup"><span data-stu-id="3916c-121">The button with a RenderTransformOrigin of 0.5, 0.5</span></span>  
  
## <a name="example"></a><span data-ttu-id="3916c-122">예제</span><span class="sxs-lookup"><span data-stu-id="3916c-122">Example</span></span>  
 <span data-ttu-id="3916c-123">상하 대칭 이동 단추를 설정 합니다 <xref:System.Windows.Media.ScaleTransform> 개체의 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 속성 대신 해당 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3916c-123">To flip the button vertically, set the <xref:System.Windows.Media.ScaleTransform> object's <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> property instead of its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 <span data-ttu-id="3916c-124">![가운데를 중심으로 세로 대칭 이동 된 단추](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="3916c-124">![A button flipped vertically about its center](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span></span>  
<span data-ttu-id="3916c-125">수직 대칭 이동 된 단추</span><span class="sxs-lookup"><span data-stu-id="3916c-125">The vertically flipped button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3916c-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="3916c-126">See also</span></span>

- [<span data-ttu-id="3916c-127">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="3916c-127">Transforms Overview</span></span>](../graphics-multimedia/transforms-overview.md)
