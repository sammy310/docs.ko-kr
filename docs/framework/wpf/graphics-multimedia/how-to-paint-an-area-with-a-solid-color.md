---
title: '방법: 단색으로 영역 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: be28a0af04c4e43cdf745a5429468aee99e34c40
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849524"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="6b4af-102">방법: 단색으로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="6b4af-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="6b4af-103">단색으로 영역을 페인칠하려면 <xref:System.Windows.Media.Brushes.Red%2A> 또는 와 <xref:System.Windows.Media.Brushes.Blue%2A>같은 미리 정의된 시스템 브러시를 사용하거나 <xref:System.Windows.Media.SolidColorBrush> 알파, <xref:System.Windows.Media.SolidColorBrush.Color%2A> 빨간색, 녹색 및 파란색 값을 사용하여 새 브러시를 만들고 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4af-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="6b4af-104">XAML에서 16진수 표기법을 사용하여 단색으로 영역을 그릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4af-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="6b4af-105">다음 예제에서는 이러한 각 기술을 사용하여 <xref:System.Windows.Shapes.Rectangle> 파란색을 페인칠합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4af-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b4af-106">예제</span><span class="sxs-lookup"><span data-stu-id="6b4af-106">Example</span></span>  
 <span data-ttu-id="6b4af-107">**미리 정의된 브러시 사용**</span><span class="sxs-lookup"><span data-stu-id="6b4af-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="6b4af-108">다음 예제에서는 미리 정의된 <xref:System.Windows.Media.Brushes.Blue%2A> 브러시를 사용하여 사각형을 파란색으로 칠합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4af-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="6b4af-109">**16진수 표기법 사용**</span><span class="sxs-lookup"><span data-stu-id="6b4af-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="6b4af-110">다음 예제에서는 8자리 16진수 표기법을 사용하여 파란색 사각형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="6b4af-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="6b4af-111">**ARGB 값 사용**</span><span class="sxs-lookup"><span data-stu-id="6b4af-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="6b4af-112">다음 예제는 <xref:System.Windows.Media.SolidColorBrush> 파란색에 대한 <xref:System.Windows.Media.SolidColorBrush.Color%2A> ARGB 값을 사용하여 a를 만들고 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4af-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="6b4af-113">색상을 설명하는 다른 방법은 <xref:System.Windows.Media.Color> 구조를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b4af-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="6b4af-114">**관련 주제**</span><span class="sxs-lookup"><span data-stu-id="6b4af-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="6b4af-115">및 추가 <xref:System.Windows.Media.SolidColorBrush> 예제에 대한 자세한 내용은 [단색 및 그라데이션이 있는 페인팅 개요 개요를](painting-with-solid-colors-and-gradients-overview.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b4af-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="6b4af-116">이 코드 예제는에 대해 제공 된 큰 예제의 일부는 <xref:System.Windows.Media.SolidColorBrush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6b4af-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="6b4af-117">전체 샘플은 브러시 [샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b4af-117">For the complete sample, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b4af-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b4af-118">See also</span></span>

- <xref:System.Windows.Media.Brushes>
