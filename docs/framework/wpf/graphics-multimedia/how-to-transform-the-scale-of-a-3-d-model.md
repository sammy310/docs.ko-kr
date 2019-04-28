---
title: '방법: 3차원 모델의 배율 변환'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3-D objects
- 3-D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: 6d668de08201d819ce9f8752bedf6c388a6bc718
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769332"
---
# <a name="how-to-transform-the-scale-of-a-3-d-model"></a><span data-ttu-id="96bd0-102">방법: 3차원 모델의 배율 변환</span><span class="sxs-lookup"><span data-stu-id="96bd0-102">How to: Transform the Scale of a 3-D Model</span></span>
<span data-ttu-id="96bd0-103">이 예제에서는 3 차원 개체를 확장 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96bd0-103">This example shows how to scale a 3-D object.</span></span> <span data-ttu-id="96bd0-104">3 차원 개체의 크기를 조정 하려면 사용을 <xref:System.Windows.Media.Media3D.ScaleTransform3D>입니다.</span><span class="sxs-lookup"><span data-stu-id="96bd0-104">To scale a 3-D object, use a <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span></span> <span data-ttu-id="96bd0-105">합니다 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, 및 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> 속성 하 여 지정한 배율로 요소 크기 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96bd0-105">The <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, and <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> properties resize the element by the factor you specify.</span></span> <span data-ttu-id="96bd0-106">예를 들어, 한 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> 원래 너비의 150%로 개체를 확장 하는 값이 1.5 합니다.</span><span class="sxs-lookup"><span data-stu-id="96bd0-106">For example, a <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> value of 1.5 stretches an object to 150 percent of its original width.</span></span> <span data-ttu-id="96bd0-107"><xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> 값 0.5는 50% 개체의 높이 축소 합니다.</span><span class="sxs-lookup"><span data-stu-id="96bd0-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> value of 0.5 shrinks the height of an object by 50 percent.</span></span> <span data-ttu-id="96bd0-108">아래 코드에서는 사용 하 여는 <xref:System.Windows.Media.Media3D.ScaleTransform3D> 에 대 한 변환으로는 <xref:System.Windows.Media.Media3D.GeometryModel3D>합니다.</span><span class="sxs-lookup"><span data-stu-id="96bd0-108">The code below shows using a <xref:System.Windows.Media.Media3D.ScaleTransform3D> as the transform for a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="96bd0-109">예제</span><span class="sxs-lookup"><span data-stu-id="96bd0-109">Example</span></span>  
 <span data-ttu-id="96bd0-110">다음 코드에는 전체 샘플을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96bd0-110">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="96bd0-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="96bd0-111">See also</span></span>

- [<span data-ttu-id="96bd0-112">3차원 변환에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="96bd0-112">Animate 3-D Translations</span></span>](how-to-animate-3-d-translations.md)
- [<span data-ttu-id="96bd0-113">3차원 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="96bd0-113">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="96bd0-114">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="96bd0-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
