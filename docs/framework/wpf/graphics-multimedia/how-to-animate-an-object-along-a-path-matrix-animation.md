---
title: '방법: 경로를 따라 개체에 애니메이션 효과 주기(매트릭스 애니메이션)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: 7dfc233fe60e1cea293edc44a2bba79dc6962f7c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452911"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a>방법: 경로를 따라 개체에 애니메이션 효과 주기(매트릭스 애니메이션)
이 예제에서는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 클래스를 사용 하 여 <xref:System.Windows.Media.PathGeometry>에서 정의한 경로를 따라 개체에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 다음을 수행하여 경로를 따라 개체에 애니메이션 효과를 줍니다.  
  
- 개체를 이동 하기 위해 개체에 <xref:System.Windows.Media.MatrixTransform>을 적용 합니다.  
  
- <xref:System.Windows.Media.PathGeometry>를 사용 하 여 경로를 정의 합니다.  
  
- <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>를 만들고이를 사용 하 여 <xref:System.Windows.Media.MatrixTransform>의 <xref:System.Windows.Media.Matrix> 속성에 애니메이션 효과를 적용 합니다. <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> <xref:System.Windows.Media.PathGeometry>를 사용 하 고이를 사용 하 여 <xref:System.Windows.Media.Matrix> 값을 생성 합니다.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 전체 샘플은 [경로 애니메이션 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)을 참조 하세요. 기하학적 경로에 대 한 자세한 내용은 [Geometry 개요](geometry-overview.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [애니메이션 개요](animation-overview.md)
- [경로 애니메이션 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [경로 애니메이션 방법 항목](path-animation-how-to-topics.md)
