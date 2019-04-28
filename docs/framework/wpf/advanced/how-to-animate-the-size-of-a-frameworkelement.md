---
title: '방법: FrameworkElement의 크기에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], FrameworkElement size
- FrameworkElement [WPF], animating size of
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
ms.openlocfilehash: d1995deec5ab2c9bf405911af43b4d242d599119
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776911"
---
# <a name="how-to-animate-the-size-of-a-frameworkelement"></a><span data-ttu-id="b677c-102">방법: FrameworkElement의 크기에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="b677c-102">How to: Animate the Size of a FrameworkElement</span></span>
<span data-ttu-id="b677c-103">크기에 애니메이션 효과를 <xref:System.Windows.FrameworkElement>, 애니메이션을 적용할 수 있거나 해당 <xref:System.Windows.FrameworkElement.Width%2A> 하 고 <xref:System.Windows.FrameworkElement.Height%2A> 속성 또는 애니메이션된을 사용 하 여 <xref:System.Windows.Media.ScaleTransform>입니다.</span><span class="sxs-lookup"><span data-stu-id="b677c-103">To animate the size of a <xref:System.Windows.FrameworkElement>, you can either animate its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties or use an animated <xref:System.Windows.Media.ScaleTransform>.</span></span>  
  
 <span data-ttu-id="b677c-104">다음 예제에서 이러한 두 가지 방법을 사용 하 여 두 단추의 크기에 애니메이션을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b677c-104">In the following example animates the size of two buttons using these two approaches.</span></span> <span data-ttu-id="b677c-105">애니메이션을 통해 하나의 단추 크기가 해당 <xref:System.Windows.FrameworkElement.Width%2A> 속성과 다른 애니메이션으로 크기가 조정 됩니다는 <xref:System.Windows.Media.ScaleTransform> 적용할 해당 <xref:System.Windows.UIElement.RenderTransform%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b677c-105">One button is resized by animating its <xref:System.Windows.FrameworkElement.Width%2A> property and another is resized by animating a <xref:System.Windows.Media.ScaleTransform> applied to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span> <span data-ttu-id="b677c-106">각 단추에는 몇 가지 텍스트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b677c-106">Each button contains some text.</span></span> <span data-ttu-id="b677c-107">처음에 텍스트가 표시 되는 두 단추에서 동일 있지만 두 번째 단추의 텍스트를 왜곡 단추 크기를 조정 하는 대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b677c-107">Initially, the text appears the same in both buttons, but as the buttons are resized, the text in the second button becomes distorted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b677c-108">예제</span><span class="sxs-lookup"><span data-stu-id="b677c-108">Example</span></span>  
 [!code-xaml[transformanimations_snip#1](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 <span data-ttu-id="b677c-109">요소를 변환 하는 경우에 전체 요소 및 해당 콘텐츠 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b677c-109">When you transform an element, the entire element and its contents are transformed.</span></span> <span data-ttu-id="b677c-110">첫 번째 단추의 경우 처럼 요소의 크기를 직접 변경 하는 경우 해당 부모 요소의 크기에 따라 달라 집니다 크기와 위치 하지 않는 한 요소의 내용은 조정 되지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b677c-110">When you directly alter the size of an element, as in the case of the first button, the element's contents are not resized unless their size and position depend on the size of their parent element.</span></span>  
  
 <span data-ttu-id="b677c-111">요소의 크기에 애니메이션 적용을 애니메이션이 적용 된 변환을 적용 하 여 해당 <xref:System.Windows.UIElement.RenderTransform%2A> 속성은 애니메이션 보다 더 나은 성능을 제공 해당 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 직접 때문에 <xref:System.Windows.UIElement.RenderTransform%2A> 속성 레이아웃 패스를 트리거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b677c-111">Animating the size of an element by applying an animated transform to its <xref:System.Windows.UIElement.RenderTransform%2A> property provides better performance than animated its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> directly, because the <xref:System.Windows.UIElement.RenderTransform%2A> property does not trigger a layout pass.</span></span>  
  
 <span data-ttu-id="b677c-112">속성에 애니메이션을 적용 하는 방법에 대 한 자세한 내용은 참조는 [애니메이션 개요](../graphics-multimedia/animation-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b677c-112">For more information about animating properties, see the [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="b677c-113">변환에 대 한 자세한 내용은 참조는 [변환 개요](../graphics-multimedia/transforms-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b677c-113">For more information about transforms, see the [Transforms Overview](../graphics-multimedia/transforms-overview.md).</span></span>
