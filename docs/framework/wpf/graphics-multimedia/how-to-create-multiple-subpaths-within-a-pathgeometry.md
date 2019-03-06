---
title: '방법: PathGeometry 내에 다중 하위 경로 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: 0b57d0441c1aa9d5972af1f1c6b989aacba7f87f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353372"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a><span data-ttu-id="389df-102">방법: PathGeometry 내에 다중 하위 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="389df-102">How to: Create Multiple Subpaths Within a PathGeometry</span></span>
<span data-ttu-id="389df-103">이 예제에서 여러 하위 경로를 만드는 방법을 보여 줍니다는 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="389df-103">This example shows how to create multiple subpaths in a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="389df-104">다중 하위 경로 만들려면, 한 <xref:System.Windows.Media.PathFigure> 각 하위 경로 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="389df-104">To create multiple subpaths, you create a <xref:System.Windows.Media.PathFigure> for each subpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="389df-105">예제</span><span class="sxs-lookup"><span data-stu-id="389df-105">Example</span></span>  
 <span data-ttu-id="389df-106">다음 예제에서는 두 개의 하위 경로 각 삼각형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="389df-106">The following example creates two subpaths, each one a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#38](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 <span data-ttu-id="389df-107">다음 예제에 사용 하 여 다중 하위 경로 만드는 방법을 보여 줍니다는 <xref:System.Windows.Shapes.Path> 고 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 특성 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="389df-107">The following example shows how to create multiple subpaths by using a <xref:System.Windows.Shapes.Path> and [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax.</span></span> <span data-ttu-id="389df-108">각 `M` 예제에서는 각각 삼각형을 그리는 두 개의 하위 경로 만들 수 있도록 새 하위 경로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="389df-108">Each `M` creates a new subpath so that the example creates two subpaths that each draw a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#58](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 <span data-ttu-id="389df-109">(이 특성 구문은 실제로 만들어지는 참고를 <xref:System.Windows.Media.StreamGeometry>, 가벼운 버전의는 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="389df-109">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="389df-110">자세한 내용은 [경로 태그 구문](path-markup-syntax.md) 페이지를 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="389df-110">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="389df-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="389df-111">See also</span></span>
- [<span data-ttu-id="389df-112">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="389df-112">Geometry Overview</span></span>](geometry-overview.md)
