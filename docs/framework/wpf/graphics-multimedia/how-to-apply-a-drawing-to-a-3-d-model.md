---
title: '방법: 3차원 모델에 그리기 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 14470d0adeb948ea46a0720b5713c20fb7d8e6d8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855874"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="f09c9-102">방법: 3차원 모델에 그리기 적용</span><span class="sxs-lookup"><span data-stu-id="f09c9-102">How to: Apply a Drawing to a 3-D Model</span></span>

<span data-ttu-id="f09c9-103">이 예제에서는을 <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.Media3D.Material> 3 차원 모델에 적용 하 여를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f09c9-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3-D model.</span></span>

<span data-ttu-id="f09c9-104">다음 코드에서는를 <xref:System.Windows.Media.DrawingGroup> <xref:System.Windows.Media.DrawingBrush>의 콘텐츠로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09c9-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="f09c9-105">는 3 차원 평면에 <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> 적용 된 <xref:System.Windows.Media.Media3D.DiffuseMaterial> 의 속성으로 설정 됩니다.<xref:System.Windows.Media.DrawingBrush></span><span class="sxs-lookup"><span data-stu-id="f09c9-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3-D plane.</span></span>

> [!NOTE]
> <span data-ttu-id="f09c9-106">코드를 다시 사용 하 고 단순화할 수 있는 리소스로 아래 드로잉과 같이 복잡 한 개체 및 값을 정의 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f09c9-106">It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="f09c9-107">자세한 내용은 [XAML 리소스](../advanced/xaml-resources.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f09c9-107">See [XAML Resources](../advanced/xaml-resources.md) for more information.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a><span data-ttu-id="f09c9-108">예제</span><span class="sxs-lookup"><span data-stu-id="f09c9-108">Example</span></span>

<span data-ttu-id="f09c9-109">다음 코드에는 전체 샘플을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f09c9-109">The following code shows the entire sample.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="f09c9-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="f09c9-110">See also</span></span>

- [<span data-ttu-id="f09c9-111">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="f09c9-111">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="f09c9-112">3차원 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="f09c9-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="f09c9-113">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="f09c9-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="f09c9-114">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="f09c9-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
