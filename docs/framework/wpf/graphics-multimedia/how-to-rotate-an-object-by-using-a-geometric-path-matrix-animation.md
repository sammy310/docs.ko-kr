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
ms.openlocfilehash: 57402ba24e8dc75f3563e71329b54db9cb96aaab
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369086"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a>방법: 기하학적 경로를 사용하여 개체 회전(매트릭스 애니메이션)
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 및 <xref:System.Windows.Media.MatrixTransform> 회전 (피벗) 하 여 정의 된 기하학적 경로 따라 개체에는 <xref:System.Windows.Media.PathGeometry> 개체입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 합니다 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 애니메이션을 적용할 개체를 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 의 속성을 <xref:System.Windows.Media.MatrixTransform>. <xref:System.Windows.Media.MatrixTransform> 단추에 적용 되 고 곡선된 경로 따라 이동 되도록 합니다. 때문에 합니다 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 속성이 `true`, 사각형은 경로의 접선을 따라 회전 합니다.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 전체 샘플을 참조 하세요 [경로 애니메이션 샘플](https://go.microsoft.com/fwlink/?LinkID=160028)합니다.  
  
 사용 하는 이전 샘플의 코드 버전을 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션 효과를 주는 <xref:System.Windows.Media.EllipseGeometry>하나만 애니메이션이 적용 된 경우에 합니다. 코드에서 속성에 단일 애니메이션을 적용 하는 간단한 방법인 사용 하는 것은 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드. 예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](how-to-animate-a-property-without-using-a-storyboard.md)를 참조하세요.  
  
## <a name="see-also"></a>참고자료
- [애니메이션 개요](animation-overview.md)
- [경로 애니메이션 방법 항목](path-animation-how-to-topics.md)
- [경로 애니메이션 샘플](https://go.microsoft.com/fwlink/?LinkID=160028)
