---
title: '방법: 타원형 원호 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: d0fffbb25f3c5aaceb2cd80af4f1093e44111200
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453067"
---
# <a name="how-to-create-an-elliptical-arc"></a>방법: 타원형 원호 만들기
이 예제에서는 타원형 원호를 그리는 방법을 보여 줍니다. 타원형 호를 만들려면 <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>및 <xref:System.Windows.Media.ArcSegment> 클래스를 사용 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서 타원형 원호는 (10100)에서 (200100)로 그려집니다. 호에는 50 장치 독립적 픽셀, 45의 <xref:System.Windows.Media.ArcSegment.RotationAngle%2A>, `true`의 <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> 설정 및 <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> <xref:System.Windows.Media.SweepDirection.Counterclockwise>의 100 <xref:System.Windows.Media.ArcSegment.Size%2A> 있습니다.  
  
 [xaml]  
  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 특성 구문을 사용 하 여 경로를 설명할 수 있습니다.  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 [xaml]  
  
 (이 특성 구문은 실제로 <xref:System.Windows.Media.PathGeometry>의 더 간단한 버전인 <xref:System.Windows.Media.StreamGeometry>를 만듭니다. 자세한 내용은 [경로 태그 구문](path-markup-syntax.md) 페이지를 참조하세요.)  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 개체 태그를 사용 하 여 명시적으로 타원형 호를 그릴 수도 있습니다. 다음은 앞의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그와 동일 합니다.  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 이 예제는 더 큰 샘플의 일부입니다. 전체 샘플을 보려면 [기 하 도형 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [정방형 3차원 곡선 만들기](how-to-create-a-quadratic-bezier-curve.md)
- [입방형 3차원 곡선 만들기](how-to-create-a-cubic-bezier-curve.md)
