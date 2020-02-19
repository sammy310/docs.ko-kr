---
title: '방법: PathGeometry를 사용하여 도형 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: bdf3c937bfff1780a72e8743bc86a3c3dad2558d
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452047"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a>방법: PathGeometry를 사용하여 도형 만들기
이 예제에서는 <xref:System.Windows.Media.PathGeometry> 클래스를 사용 하 여 모양을 만드는 방법을 보여 줍니다. <xref:System.Windows.Media.PathGeometry> 개체는 하나 이상의 <xref:System.Windows.Media.PathFigure> 개체로 구성 됩니다. 각 <xref:System.Windows.Media.PathFigure>는 다른 "그림" 또는 도형을 나타냅니다. 각 <xref:System.Windows.Media.PathFigure>는 각각 그림 또는 모양의 연결 된 부분을 나타내는 하나 이상의 <xref:System.Windows.Media.PathSegment> 개체로 구성 됩니다. 세그먼트 형식은 <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>및 <xref:System.Windows.Media.BezierSegment>를 포함 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 <xref:System.Windows.Media.PathGeometry>를 사용 하 여 삼각형을 만듭니다. <xref:System.Windows.Shapes.Path> 요소를 사용 하 여 <xref:System.Windows.Media.PathGeometry> 표시 됩니다.  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 다음 그림은 이전 예제에서 만든 도형을 보여 줍니다.  
  
 ![PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")  
PathGeometry를 사용 하 여 만든 삼각형입니다.  
  
 앞의 예제에서는 비교적 간단한 모양의 삼각형을 만드는 방법을 살펴보았습니다. <xref:System.Windows.Media.PathGeometry>를 사용 하 여 호와 곡선을 포함 하 여 더 복잡 한 도형을 만들 수도 있습니다. 예제는 [타원형 원호 만들기](how-to-create-an-elliptical-arc.md), [입방 형 3 차원 곡선 만들기](how-to-create-a-cubic-bezier-curve.md)및 [정방형 3 차원 곡선 만들기](how-to-create-a-quadratic-bezier-curve.md)를 참조 하세요.  
  
 이 예제는 더 큰 샘플에 속합니다. 전체 샘플을 보려면 [기하 도형 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [Geometry 개요](geometry-overview.md)
- [기 하 도형 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)
