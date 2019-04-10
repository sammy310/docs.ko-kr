---
title: '방법: 3차원 모델에 다중 변환 적용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D models [WPF], applying multiple transformations to
ms.assetid: cb72245a-5560-4c96-9f58-593c66296992
ms.openlocfilehash: 7a6a0dd4942eb2430ff79ab5df4a171a4064ac1c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186383"
---
# <a name="how-to-apply-multiple-transformations-to-a-3-d-model"></a><span data-ttu-id="895e6-102">방법: 3차원 모델에 다중 변환 적용</span><span class="sxs-lookup"><span data-stu-id="895e6-102">How to: Apply Multiple Transformations to a 3-D Model</span></span>
<span data-ttu-id="895e6-103">이 샘플에서는 사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Media.Media3D.RotateTransform3D> 및 <xref:System.Windows.Media.Media3D.ScaleTransform3D> 를 회전 하 고 3 차원 모델의 배율을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="895e6-103">This sample shows how to use a <xref:System.Windows.Media.Media3D.RotateTransform3D> and a <xref:System.Windows.Media.Media3D.ScaleTransform3D> to rotate and change the scale of a 3-D model.</span></span> <span data-ttu-id="895e6-104">아래 코드에 이러한 변환을 적용 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> 의 속성을 <xref:System.Windows.Media.Media3D.GeometryModel3D> XAML에서.</span><span class="sxs-lookup"><span data-stu-id="895e6-104">The code below shows how to apply these transforms to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexampleinline1)]  
  
 <span data-ttu-id="895e6-105">코드</span><span class="sxs-lookup"><span data-stu-id="895e6-105">In code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="895e6-106">예제</span><span class="sxs-lookup"><span data-stu-id="895e6-106">Example</span></span>  
 <span data-ttu-id="895e6-107">다음 코드는 XAML에서 전체 샘플을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="895e6-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="895e6-108">예제</span><span class="sxs-lookup"><span data-stu-id="895e6-108">Example</span></span>  
 <span data-ttu-id="895e6-109">전체 샘플 코드에서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="895e6-109">Below is the entire sample in code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="895e6-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="895e6-110">See also</span></span>

- [<span data-ttu-id="895e6-111">3차원 모델의 배율 변환</span><span class="sxs-lookup"><span data-stu-id="895e6-111">Transform the Scale of a 3-D Model</span></span>](how-to-transform-the-scale-of-a-3-d-model.md)
