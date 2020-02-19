---
title: '방법: 경로를 따라 개체에 애니메이션 효과 주기(포인트 애니메이션)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: eff0c24a9369ffaa0cfca1cc46af4eff39f58a38
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452898"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a>방법: 경로를 따라 개체에 애니메이션 효과 주기(포인트 애니메이션)
이 예제에서는 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 개체를 사용 하 여 곡선 경로를 따라 <xref:System.Windows.Point>에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 <xref:System.Windows.Media.PathGeometry>에서 정의한 경로를 따라 <xref:System.Windows.Media.EllipseGeometry>를 이동 합니다. <xref:System.Windows.Point> 값을 사용 하는 타원 기 하 도형의 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성은 해당 위치를 지정 합니다. 타원 기 하 도형을 이동 하려면 해당 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성에 애니메이션 효과를 적용 합니다. 이 예제에서는 <xref:System.Windows.Media.Animation.PointAnimationUsingPath>를 사용 하 여 <xref:System.Windows.Media.EllipseGeometry> 개체의 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성에 애니메이션 효과를 적용 합니다.  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 전체 샘플은 [경로 애니메이션 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)을 참조 하세요.  
  
 이전 샘플의 코드 버전은 하나의 애니메이션만 적용 된 경우에도 <xref:System.Windows.Media.EllipseGeometry>에 애니메이션 효과를 주기 위해 <xref:System.Windows.Media.Animation.Storyboard>를 사용 했습니다. <xref:System.Windows.Media.Animation.Storyboard>는 동일한 <xref:System.Windows.Media.Animation.Storyboard>에 의해 제어 될 수 있으므로 여러 애니메이션을 적용 하는 가장 쉬운 방법입니다. 그러나 코드를 사용할 때 속성에 단일 애니메이션을 적용 하는 보다 쉬운 방법은 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 사용 하는 것입니다. 예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](how-to-animate-a-property-without-using-a-storyboard.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- [경로 애니메이션 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [애니메이션 개요](animation-overview.md)
- [경로 애니메이션 방법 항목](path-animation-how-to-topics.md)
