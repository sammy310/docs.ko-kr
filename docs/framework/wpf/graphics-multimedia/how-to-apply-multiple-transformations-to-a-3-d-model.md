---
title: '방법: 3D 모델에 다중 변환 적용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D models [WPF], applying multiple transformations to
ms.assetid: cb72245a-5560-4c96-9f58-593c66296992
ms.openlocfilehash: 6400d224fb51b93c76c5e9798b4bcc68ff3b9de6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112130"
---
# <a name="how-to-apply-multiple-transformations-to-a-3d-model"></a><span data-ttu-id="2aff5-102">방법: 3D 모델에 다중 변환 적용</span><span class="sxs-lookup"><span data-stu-id="2aff5-102">How to: Apply Multiple Transformations to a 3D Model</span></span>
<span data-ttu-id="2aff5-103">이 샘플에서는 a와 <xref:System.Windows.Media.Media3D.RotateTransform3D> a를 <xref:System.Windows.Media.Media3D.ScaleTransform3D> 사용하여 3D 모델의 축척을 회전하고 변경하는 방법을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="2aff5-103">This sample shows how to use a <xref:System.Windows.Media.Media3D.RotateTransform3D> and a <xref:System.Windows.Media.Media3D.ScaleTransform3D> to rotate and change the scale of a 3D model.</span></span> <span data-ttu-id="2aff5-104">아래 코드는 이러한 변환을 XAML의 <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> <xref:System.Windows.Media.Media3D.GeometryModel3D> 속성에 적용하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aff5-104">The code below shows how to apply these transforms to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexampleinline1)]  
  
 <span data-ttu-id="2aff5-105">코드:</span><span class="sxs-lookup"><span data-stu-id="2aff5-105">In code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="2aff5-106">예제</span><span class="sxs-lookup"><span data-stu-id="2aff5-106">Example</span></span>  
 <span data-ttu-id="2aff5-107">다음 코드는 XAML의 전체 샘플을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="2aff5-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="2aff5-108">예제</span><span class="sxs-lookup"><span data-stu-id="2aff5-108">Example</span></span>  
 <span data-ttu-id="2aff5-109">다음은 코드의 전체 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="2aff5-109">Below is the entire sample in code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="2aff5-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2aff5-110">See also</span></span>

- [<span data-ttu-id="2aff5-111">3D 모델의 배율 변환</span><span class="sxs-lookup"><span data-stu-id="2aff5-111">Transform the Scale of a 3D Model</span></span>](how-to-transform-the-scale-of-a-3-d-model.md)
