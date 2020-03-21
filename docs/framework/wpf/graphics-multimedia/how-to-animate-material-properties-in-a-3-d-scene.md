---
title: '방법: 3D 장면에서 재질 속성 에 애니메이션'
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3D scenes
- animation [WPF], Material properties in 3D scenes
- 3D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: db59debcd7558cde52d8604cb04c8c4e68921825
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112195"
---
# <a name="how-to-animate-material-properties-in-a-3d-scene"></a>방법: 3D 장면에서 재질 속성 에 애니메이션
이 예제에서는 3D 모델에 <xref:System.Windows.Media.Brush.Opacity%2A> 적용된 <xref:System.Windows.Media.Media3D.Material> 속성에 애니메이션하는 방법을 보여 주며, 이 예제에서는 3D 모델에 적용된 속성을 애니메이션하는 방법을 보여 주며, 이 예제에서는  
  
 다음 코드 예제는 <xref:System.Windows.Media.LinearGradientBrush> 3D <xref:System.Windows.Media.Media3D.Material> 개체에 적용된 것으로 사용되는 것을 정의합니다.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 이 <xref:System.Windows.Media.Brush.Opacity%2A> <xref:System.Windows.Media.LinearGradientBrush> 속성은 아래 코드 예제를 사용하여 애니메이션됩니다.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a>예제  
 다음 코드에는 전체 샘플을 보여 줍니다.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목

- [3D 장면 만들기](how-to-create-a-3-d-scene.md)
- [3D 그래픽 개요](3-d-graphics-overview.md)
