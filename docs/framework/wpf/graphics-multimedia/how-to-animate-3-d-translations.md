---
title: '방법: 3차원 변환에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations
- 3-D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 3e27c2d5f0cd44235a1d897b1b8f057808ae6bd8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762204"
---
# <a name="how-to-animate-3-d-translations"></a>방법: 3차원 변환에 애니메이션 효과 주기
이 항목에 설정 된 번역 변형 애니메이션 효과를 주는 방법을 보여 줍니다는 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 모델입니다.  
  
 아래 코드의 응용 프로그램을 보여 줍니다를 <xref:System.Windows.Media.Media3D.TranslateTransform3D> 개체를 <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> 의 속성을 <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 합니다 <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> 이 <xref:System.Windows.Media.Media3D.TranslateTransform3D> 개체 아래 코드를 사용 하 여 애니메이션 효과가 적용 됩니다.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a>예제  
 다음 코드에는 전체 샘플을 보여 줍니다.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a>참고자료

- [애니메이션 개요](animation-overview.md)
- [3차원 장면 만들기](how-to-create-a-3-d-scene.md)
- [3차원 그래픽 개요](3-d-graphics-overview.md)
- [Transform 개요](transforms-overview.md)
