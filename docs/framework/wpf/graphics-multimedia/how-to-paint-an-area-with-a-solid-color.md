---
title: '방법: 단색으로 영역 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: ae6be062313e9340edefd86c15b7a044996fe280
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373112"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="6f1ec-102">방법: 단색으로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="6f1ec-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="6f1ec-103">단색으로 영역을 그릴 사용할 수는 미리 정의 된 시스템 브러시와 같은 <xref:System.Windows.Media.Brushes.Red%2A> 또는 <xref:System.Windows.Media.Brushes.Blue%2A>, 하거나 새로 만들 수 있습니다 <xref:System.Windows.Media.SolidColorBrush> 설명 하 고 해당 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 알파, 빨강, 녹색 및 파랑 값을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f1ec-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="6f1ec-104">XAML에서 16진수 표기법을 사용하여 단색으로 영역을 그릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f1ec-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="6f1ec-105">다음 예제에서는 이러한 각 기법을를 그릴 때 사용 된 <xref:System.Windows.Shapes.Rectangle> 파란색입니다.</span><span class="sxs-lookup"><span data-stu-id="6f1ec-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f1ec-106">예제</span><span class="sxs-lookup"><span data-stu-id="6f1ec-106">Example</span></span>  
 <span data-ttu-id="6f1ec-107">**미리 정의된 브러시 사용**</span><span class="sxs-lookup"><span data-stu-id="6f1ec-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="6f1ec-108">다음 예제에서는 미리 정의 된 브러시를 사용 하 여 <xref:System.Windows.Media.Brushes.Blue%2A> 에 파란색 사각형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="6f1ec-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="6f1ec-109">**16진수 표기법 사용**</span><span class="sxs-lookup"><span data-stu-id="6f1ec-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="6f1ec-110">다음 예제에서는 8자리 16진수 표기법을 사용하여 파란색 사각형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="6f1ec-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="6f1ec-111">**ARGB 값 사용**</span><span class="sxs-lookup"><span data-stu-id="6f1ec-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="6f1ec-112">다음 예제에서는 만듭니다는 <xref:System.Windows.Media.SolidColorBrush> 에 대해 설명 하 고 해당 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 파란색 값의 ARGB를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f1ec-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="6f1ec-113">색을 설명 하는 다른 방법에 대해서는 <xref:System.Windows.Media.Color> 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="6f1ec-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="6f1ec-114">**관련 항목**</span><span class="sxs-lookup"><span data-stu-id="6f1ec-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="6f1ec-115">에 대 한 자세한 내용은 <xref:System.Windows.Media.SolidColorBrush> 및 추가 예제를 보려면 합니다 [단색 및 그라데이션 개요 그리기](painting-with-solid-colors-and-gradients-overview.md) 개요.</span><span class="sxs-lookup"><span data-stu-id="6f1ec-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="6f1ec-116">이 코드 예제는에 대해 제공 된 큰 예제의 일부는 <xref:System.Windows.Media.SolidColorBrush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6f1ec-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="6f1ec-117">전체 샘플을 보려면 [브러시 샘플](https://go.microsoft.com/fwlink/?LinkID=159973)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f1ec-117">For the complete sample, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f1ec-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="6f1ec-118">See also</span></span>
- <xref:System.Windows.Media.Brushes>
