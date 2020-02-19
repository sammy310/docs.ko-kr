---
title: '방법: 경로를 따라 개체에 애니메이션 효과 주기(Double 애니메이션)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
ms.openlocfilehash: 084caac26fd68b6914ec3858652ec44557a0dbd7
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452859"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a>방법: 경로를 따라 개체에 애니메이션 효과 주기(Double 애니메이션)
이 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 클래스를 사용 하 여 <xref:System.Windows.Media.PathGeometry>에서 정의한 경로를 따라 개체를 이동 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 개의 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 개체를 사용 하 여 기하학적 경로를 따라 사각형을 이동 합니다.  
  
- 첫 번째 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>는 사각형에 적용 되는 <xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.Media.TranslateTransform.X%2A>에 애니메이션 효과를 적용 합니다. 이를 통해 사각형이 경로를 따라 가로로 이동하게 됩니다.  
  
- 두 번째 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 사각형에 적용 되는 <xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.Media.TranslateTransform.Y%2A>에 애니메이션 효과를 적용 합니다. 이를 통해 사각형이 경로를 따라 세로로 이동하게 됩니다.  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 전체 샘플은 [경로 애니메이션 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)을 참조 하세요.  
  
 기하학적 경로를 사용 하 여 개체를 이동 하는 또 다른 방법은 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 개체를 사용 하는 것입니다. 예를 들어 경로를 [따라 개체에 애니메이션 효과 주기 (Matrix 애니메이션)](how-to-animate-an-object-along-a-path-matrix-animation.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [애니메이션 개요](animation-overview.md)
- [경로 애니메이션 방법 항목](path-animation-how-to-topics.md)
