---
title: '방법: 기하학적 경로를 사용하여 개체 회전'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: a351fdc936f634b7c57ba5a49e51501f7572a3c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186870"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a>방법: 기하학적 경로를 사용하여 개체 회전
이 예제에서는 오브젝트에 의해 정의된 기하학적 경로를 따라 오브젝트를 회전(피벗)하는 방법을 보여 주며, 이 예제에서는 오브젝트를 <xref:System.Windows.Media.PathGeometry> 회전(피벗)하는 방법을 보여 주며,  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 세 개의 오브젝트를 사용하여 기하학적 경로를 따라 사각형을 이동합니다.  
  
- 첫 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 번째 애니메이션은 <xref:System.Windows.Media.RotateTransform> 사각형에 적용되는 애니메이션을 적용합니다. 애니메이션은 각도 값을 생성합니다. 이를 통해 사각형이 경로 윤곽을 따라 회전(피벗)하게 됩니다.  
  
- 다른 두 개체는 <xref:System.Windows.Media.TranslateTransform.X%2A> 사각형에 <xref:System.Windows.Media.TranslateTransform.Y%2A> 적용되는 <xref:System.Windows.Media.TranslateTransform> a의 값과 애니메이션을 적용합니다. 이를 통해 사각형이 경로를 따라 가로 및 세로로 이동하게 됩니다.  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 기하학적 경로를 사용하여 오브젝트를 회전하는 또 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 다른 방법은 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 객체를 `true`사용하고 해당 속성을 로 설정하는 것입니다. 자세한 정보 및 예제는 [기하학적 경로(행렬 애니메이션)를 사용하여 오브젝트 회전을](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md)참조하십시오.  
  
 전체 샘플은 [경로 애니메이션 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- [애니메이션 개요](animation-overview.md)
- [경로 애니메이션 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [경로 애니메이션 방법 항목](path-animation-how-to-topics.md)
