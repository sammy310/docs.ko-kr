---
title: '방법: 정방형 3차원 곡선 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
ms.openlocfilehash: caaf967b7cb5447d86dd031beeb16195413b0393
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452073"
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a>방법: 정방형 3차원 곡선 만들기
이 예제에서는 정방형 3 차원 곡선을 만드는 방법을 보여 줍니다.  정방형 3 차원 곡선을 만들려면 <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>및 <xref:System.Windows.Media.QuadraticBezierSegment> 클래스를 사용 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 (10100)에서 (300100)로 정방형 3 차원 곡선을 그립니다. 곡선의 제어점은 (200200)입니다.  
  
 [xaml]  
  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 특성 구문을 사용 하 여 경로를 설명할 수 있습니다.  
  
 [!code-xaml[GeometrySample#54](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 [xaml]  
  
 (이 특성 구문은 실제로 <xref:System.Windows.Media.PathGeometry>의 더 간단한 버전인 <xref:System.Windows.Media.StreamGeometry>를 만듭니다. 자세한 내용은 [경로 태그 구문](path-markup-syntax.md) 페이지를 참조하세요.)  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 개체 요소 구문을 사용 하 여 정방형 3 차원 곡선을 그릴 수도 있습니다. 다음 예제는 이전 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제와 동일합니다.  
  
 [!code-xaml[GeometrySample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 이 예제는 더 큰 샘플에 속합니다. 전체 샘플을 보려면 [기하 도형 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- [타원형 원호 만들기](how-to-create-an-elliptical-arc.md)
- [입방형 3차원 곡선 만들기](how-to-create-a-cubic-bezier-curve.md)
