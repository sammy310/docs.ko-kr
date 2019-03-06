---
title: '방법: 3차원 모델에 그리기 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: cfd133b04e0c04b4a502d2466e67685700e3f408
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368916"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="56e14-102">방법: 3차원 모델에 그리기 적용</span><span class="sxs-lookup"><span data-stu-id="56e14-102">How to: Apply a Drawing to a 3-D Model</span></span>
<span data-ttu-id="56e14-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.DrawingBrush> 으로 <xref:System.Windows.Media.Media3D.Material> 적용할를 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="56e14-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="56e14-104">다음 코드는 정의 <xref:System.Windows.Media.DrawingGroup> 의 내용으로는 <xref:System.Windows.Media.DrawingBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="56e14-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="56e14-105"><xref:System.Windows.Media.DrawingBrush> 으로 설정 됩니다는 <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> 의 속성을 <xref:System.Windows.Media.Media3D.DiffuseMaterial> 적용할를 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 평면.</span><span class="sxs-lookup"><span data-stu-id="56e14-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] plane.</span></span>  
  
 <span data-ttu-id="56e14-106">**참고:** 코드를 단순화 하 고 다시 사용할 수 있는 리소스로 복잡 한 개체 및 아래의 그림과 같은 값을 정의 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="56e14-106">**Note:** It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="56e14-107">참조 [XAML 리소스](../advanced/xaml-resources.md) 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="56e14-107">See [XAML Resources](../advanced/xaml-resources.md) for more information.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## <a name="example"></a><span data-ttu-id="56e14-108">예제</span><span class="sxs-lookup"><span data-stu-id="56e14-108">Example</span></span>  
 <span data-ttu-id="56e14-109">다음 코드에는 전체 샘플을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="56e14-109">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="56e14-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="56e14-110">See also</span></span>
- [<span data-ttu-id="56e14-111">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="56e14-111">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="56e14-112">3차원 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="56e14-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="56e14-113">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="56e14-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="56e14-114">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="56e14-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
