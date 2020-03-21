---
title: '방법: 3D 모델에 도면 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3D models
- 3D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 5b10630ab674fa9489cdf7ad53516a680f19da08
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112182"
---
# <a name="how-to-apply-a-drawing-to-a-3d-model"></a><span data-ttu-id="de940-102">방법: 3D 모델에 도면 적용</span><span class="sxs-lookup"><span data-stu-id="de940-102">How to: Apply a Drawing to a 3D Model</span></span>

<span data-ttu-id="de940-103">이 예제에서는 a를 <xref:System.Windows.Media.DrawingBrush> 3D 모델에 적용된 <xref:System.Windows.Media.Media3D.Material> 것으로 사용하는 방법을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="de940-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3D model.</span></span>

<span data-ttu-id="de940-104">다음 코드는 을 <xref:System.Windows.Media.DrawingGroup> <xref:System.Windows.Media.DrawingBrush>의 콘텐츠로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="de940-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="de940-105">는 <xref:System.Windows.Media.DrawingBrush> 3D <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> 평면에 <xref:System.Windows.Media.Media3D.DiffuseMaterial> 적용 된의 속성으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de940-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3D plane.</span></span>

> [!NOTE]
> <span data-ttu-id="de940-106">아래 그림과 같은 복잡한 개체와 값을 코드를 재사용하고 단순화할 수 있는 리소스로 정의하는 것이 바람직합니다.</span><span class="sxs-lookup"><span data-stu-id="de940-106">It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="de940-107">자세한 내용은 [XAML 리소스를](../../../desktop-wpf/fundamentals/xaml-resources-define.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="de940-107">See [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) for more information.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a><span data-ttu-id="de940-108">예제</span><span class="sxs-lookup"><span data-stu-id="de940-108">Example</span></span>

<span data-ttu-id="de940-109">다음 코드에는 전체 샘플을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="de940-109">The following code shows the entire sample.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="de940-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de940-110">See also</span></span>

- [<span data-ttu-id="de940-111">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="de940-111">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="de940-112">3D 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="de940-112">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="de940-113">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="de940-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="de940-114">3D 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="de940-114">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
