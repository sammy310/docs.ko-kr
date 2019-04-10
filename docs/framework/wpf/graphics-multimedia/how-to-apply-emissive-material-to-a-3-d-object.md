---
title: '방법: 3차원 개체에 발광 재질 적용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3-D objects
- 3-D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: b898148fa07950e3ad1eddcaf9206f7d6a837241
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163126"
---
# <a name="how-to-apply-emissive-material-to-a-3-d-object"></a><span data-ttu-id="1115c-102">방법: 3차원 개체에 발광 재질 적용</span><span class="sxs-lookup"><span data-stu-id="1115c-102">How to: Apply Emissive Material to a 3-D Object</span></span>
<span data-ttu-id="1115c-103">다음 예제에서는 사용 하는 방법을 보여 줍니다 <xref:System.Windows.Media.Media3D.EmissiveMaterial> 색 EmissiveMaterial의 브러시의 색 같음는 기존 자료에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1115c-103">The following example shows how to use <xref:System.Windows.Media.Media3D.EmissiveMaterial> to add color to an existing Material equal to the color of the EmissiveMaterial's brush.</span></span> <span data-ttu-id="1115c-104">아래 코드 <xref:System.Windows.Media.Media3D.DiffuseMaterial> 고 <xref:System.Windows.Media.Media3D.EmissiveMaterial> 파란색 DiffuseMaterial의 모양을 추가할 조합에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1115c-104">The code below shows <xref:System.Windows.Media.Media3D.DiffuseMaterial> and <xref:System.Windows.Media.Media3D.EmissiveMaterial> applied in combination to add blue to the DiffuseMaterial's appearance.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 <span data-ttu-id="1115c-105">프로시저 코드</span><span class="sxs-lookup"><span data-stu-id="1115c-105">In procedural code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="1115c-106">예제</span><span class="sxs-lookup"><span data-stu-id="1115c-106">Example</span></span>  
 <span data-ttu-id="1115c-107">다음 코드는 XAML에서 전체 샘플을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1115c-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="1115c-108">예제</span><span class="sxs-lookup"><span data-stu-id="1115c-108">Example</span></span>  
 <span data-ttu-id="1115c-109">프로시저 코드에서 전체 샘플을 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1115c-109">Below is the entire sample in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="1115c-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="1115c-110">See also</span></span>

- [<span data-ttu-id="1115c-111">3차원 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="1115c-111">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="1115c-112">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="1115c-112">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="1115c-113">3차원 장면의 Material 속성에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="1115c-113">Animate Material Properties in a 3-D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="1115c-114">3차원 개체의 앞뒤에 재질 적용</span><span class="sxs-lookup"><span data-stu-id="1115c-114">Apply Material to the Front and Back of a 3-D Object</span></span>](how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
