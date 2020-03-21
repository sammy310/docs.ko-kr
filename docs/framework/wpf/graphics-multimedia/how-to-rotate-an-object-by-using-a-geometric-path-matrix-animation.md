---
title: '방법: 기하학적 경로를 사용하여 개체 회전(매트릭스 애니메이션)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
ms.openlocfilehash: 63dc873a2b840ea3f870a8c60c5691ab271c1c9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187417"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a>방법: 기하학적 경로를 사용하여 개체 회전(매트릭스 애니메이션)
이 예제에서는 객체에 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 의해 <xref:System.Windows.Media.MatrixTransform> 정의된 기하학적 경로를 따라 a와 a를 사용하여 오브젝트를 회전(피벗)하는 방법을 보여 주며, 이 예제에서는 객체를 회전(피봇)하는 <xref:System.Windows.Media.PathGeometry> 방법을 보여 주며,  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 개체를 사용하여 의 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 속성을 <xref:System.Windows.Media.MatrixTransform>애니메이션합니다. 는 <xref:System.Windows.Media.MatrixTransform> 단추에 적용되고 곡선 된 경로를 따라 이동합니다. 속성이 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 설정되므로 `true`사각형이 패스의 접선을 따라 회전합니다.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 전체 샘플은 [경로 애니메이션 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)참조하십시오.  
  
 이전 샘플의 코드 버전은 하나의 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션만 적용되었음에도 불구하고 에 애니메이션을 <xref:System.Windows.Media.EllipseGeometry>적용하는 데 사용했습니다. 코드의 속성에 단일 애니메이션을 적용하는 더 쉬운 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 방법은 메서드를 사용하는 것입니다. 예를 들어 [스토리보드를 사용하지 않고 속성 애니메이션을](how-to-animate-a-property-without-using-a-storyboard.md)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- [애니메이션 개요](animation-overview.md)
- [경로 애니메이션 방법 항목](path-animation-how-to-topics.md)
- [경로 애니메이션 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
