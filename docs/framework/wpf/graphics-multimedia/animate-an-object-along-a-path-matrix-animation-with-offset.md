---
title: '방법: 경로를 따라 개체에 애니메이션 효과 주기(오프셋이 누적된 매트릭스 애니메이션)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: 8b3975ef5031b50381dfa9baf7f34a58fc05ab4e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453106"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a>방법: 경로를 따라 개체에 애니메이션 효과 주기(오프셋이 누적된 매트릭스 애니메이션)
이 예제에서는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 클래스를 사용 하 여 경로를 따라 개체에 애니메이션 효과를 주는 방법을 보여 주고 애니메이션이 반복 될 때 해당 오프셋 값을 누적 하도록 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 개체를 사용 하 여 단추에 적용 되는 <xref:System.Windows.Media.MatrixTransform>의 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 속성에 애니메이션 효과를 적용 합니다. 그 결과 단추가 곡선 경로를 따라 움직입니다.  
  
 또한이 예제에서는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> 속성을 `true`로 설정 합니다. 그러면 애니메이션이 반복 될 때 애니메이션 된 행렬의 오프셋이 누적 됩니다. 오프셋이 누적되므로 애니메이션이 반복되면 단추는 시작 위치로 재설정되는 것이 아니라 화면을 가로질러 더 크게 움직입니다.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> 속성은 오프셋 값이 반복을 통해 누적 되도록 하지만 회전 값이 누적 되지 않게 합니다. 회전 값이 누적 되도록 하려면 애니메이션의 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 및 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> 속성을 `true`로 설정 합니다.  
  
 전체 샘플은 [경로 애니메이션 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)을 참조 하세요. 오프셋 누적 없이 경로를 따라 <xref:System.Windows.Media.Matrix> 값에 애니메이션 효과를 주는 방법을 보여 주는 예제는 [경로를 따라 개체에 애니메이션 효과 주기 (매트릭스 애니메이션)](how-to-animate-an-object-along-a-path-matrix-animation.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [애니메이션 개요](animation-overview.md)
- [경로 애니메이션 방법 항목](path-animation-how-to-topics.md)
