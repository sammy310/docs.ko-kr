---
title: '방법: 3D 번역 애니메이션'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations
- 3D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 7d4fff9c74663bd220ad5d15a983bcb639621afd
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112260"
---
# <a name="how-to-animate-3d-translations"></a><span data-ttu-id="e5caa-102">방법: 3D 번역 애니메이션</span><span class="sxs-lookup"><span data-stu-id="e5caa-102">How to: Animate 3D Translations</span></span>
<span data-ttu-id="e5caa-103">이 항목에서는 3D 모델에서 설정된 변환 변환을 애니메이션하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5caa-103">This topic demonstrates how to animate a translation transformation set on a 3D model.</span></span>  
  
 <span data-ttu-id="e5caa-104">아래 코드는 <xref:System.Windows.Media.Media3D.TranslateTransform3D> <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> <xref:System.Windows.Media.Media3D.GeometryModel3D>의 속성에 대한 개체의 응용 프로그램을 보여 주며 의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e5caa-104">The code below shows the application of a <xref:System.Windows.Media.Media3D.TranslateTransform3D> object to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 <span data-ttu-id="e5caa-105">이 <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> <xref:System.Windows.Media.Media3D.TranslateTransform3D> 개체의 속성은 아래 코드를 사용하여 애니메이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5caa-105">The <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> property of this <xref:System.Windows.Media.Media3D.TranslateTransform3D> object is animated using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a><span data-ttu-id="e5caa-106">예제</span><span class="sxs-lookup"><span data-stu-id="e5caa-106">Example</span></span>  
 <span data-ttu-id="e5caa-107">다음 코드에는 전체 샘플을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5caa-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e5caa-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5caa-108">See also</span></span>

- [<span data-ttu-id="e5caa-109">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="e5caa-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="e5caa-110">3D 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="e5caa-110">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="e5caa-111">3D 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="e5caa-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="e5caa-112">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="e5caa-112">Transforms Overview</span></span>](transforms-overview.md)
