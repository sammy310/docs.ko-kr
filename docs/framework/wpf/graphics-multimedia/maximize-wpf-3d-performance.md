---
title: 3D 성능 극대화
ms.date: 03/30/2017
helpviewer_keywords:
- 3D graphics [WPF]
ms.assetid: 4bcf949d-d92f-4d8d-8a9b-1e4c61b25bf6
ms.openlocfilehash: 3825ea8e57c6863e2ee654072efda623db21c2a8
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112000"
---
# <a name="maximize-wpf-3d-performance"></a>WPF 3D 성능 최대화
3D [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 컨트롤을 빌드하고 응용 프로그램에 3D 장면을 포함하려면 성능 최적화를 고려해야 합니다. 이 항목에서는 응용 프로그램에 성능에 영향을 주는 3D 클래스 및 속성 목록과 사용할 때 성능을 최적화하기 위한 권장 사항을 제공합니다.  
  
 이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D 기능에 대한 고급 이해를 가정합니다. 이 문서의 제안 사항은 픽셀 샤더 버전 2.0 및 정점 샤더 버전 2.0을 지원하는 하드웨어로 정의된 "렌더링 계층 2"에 적용됩니다. 자세한 내용은 [그래픽 렌더링 계층을](../advanced/graphics-rendering-tiers.md)참조하십시오.  
  
## <a name="performance-impact-high"></a>성능 영향: 높음  
  
|속성|권장|  
|-|-|  
|<xref:System.Windows.Media.Brush>|브러시 속도(가장 빠르고 가장 느립니다):<br /><br /> <xref:System.Windows.Media.SolidColorBrush><br /><br /> <xref:System.Windows.Media.LinearGradientBrush><br /><br /> <xref:System.Windows.Media.ImageBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush>(캐시)<br /><br /> <xref:System.Windows.Media.VisualBrush>(캐시)<br /><br /> <xref:System.Windows.Media.RadialGradientBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush>(캐시되지 않은)<br /><br /> <xref:System.Windows.Media.VisualBrush>(캐시되지 않은)|  
|<xref:System.Windows.UIElement.ClipToBoundsProperty>|Viewport3D의 사각형에 a의 `Viewport3D.ClipToBounds` [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.Viewport3D> 내용을 명시적으로 잘라야 할 필요가 없을 때마다 false로 설정합니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]안티 alialiased 클리핑은 매우 `ClipToBounds` 느릴 수 있으며 <xref:System.Windows.Controls.Viewport3D>기본적으로 에서 (느리게) 활성화됩니다.|  
|<xref:System.Windows.UIElement.IsHitTestVisible%2A>|마우스 `Viewport3D.IsHitTestVisible` 적중 테스트를 수행할 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 때 a의 <xref:System.Windows.Controls.Viewport3D> 내용을 고려할 필요가 없을 때마다 false로 설정합니다.  히트 테스트 3D 콘텐츠는 소프트웨어에서 수행되며 큰 메시로 속도가 느려질 수 있습니다. <xref:System.Windows.UIElement.IsHitTestVisible%2A>에서 기본적으로 <xref:System.Windows.Controls.Viewport3D>활성화(느림)입니다.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D>|다른 재질 또는 변형이 필요한 경우에만 다른 모델을 작성합니다.  그렇지 않으면 동일한 재질과 변환을 사용하여 많은 <xref:System.Windows.Media.Media3D.GeometryModel3D> 인스턴스를 <xref:System.Windows.Media.Media3D.GeometryModel3D> 몇 <xref:System.Windows.Media.Media3D.MeshGeometry3D> 가지 더 큰 인스턴스로 병합하려고 합니다.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|프레임단위로 메시의 개별 정점을 변경하는 메시 애니메이션이 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 항상 효율적이지는 않습니다.  각 정점을 수정할 때 변경 알림의 성능 영향을 최소화하려면 정점별 수정을 수행하기 전에 시각적 트리에서 메시를 분리합니다.  메시가 수정되면 시각적 트리에 다시 연결합니다.  또한 이러한 방식으로 애니메이션될 메시 크기를 최소화하십시오.|  
|3D 안티알리아징|렌더링 속도를 높이려면 연결된 속성을 <xref:System.Windows.Controls.Viewport3D> <xref:System.Windows.Media.RenderOptions.EdgeMode%2A> 로 설정하여 `Aliased`에서 다중 샘플링을 사용하지 않도록 설정합니다.  기본적으로 픽셀당 4개의 샘플이 있는 Windows에서 3D 안티앨리어싱이 활성화됩니다.|  
|텍스트|3D 장면의 라이브 <xref:System.Windows.Media.DrawingBrush> 텍스트(또는 <xref:System.Windows.Media.VisualBrush>에 있기 때문에 라이브)는 느릴 수 있습니다. 텍스트가 변경되지 않는 한 대신 <xref:System.Windows.Media.Imaging.RenderTargetBitmap>(via) 텍스트의 이미지를 사용해 보십시오.|  
|<xref:System.Windows.Media.TileBrush>|브러시의 내용이 <xref:System.Windows.Media.VisualBrush> 정적이지 않기 때문에 3D 장면에서 또는 a를 <xref:System.Windows.Media.DrawingBrush> 사용해야 하는 경우 브러시를 <xref:System.Windows.Media.RenderOptions.CachingHint%2A> 캐싱(연결된 속성을 설정)으로 캐싱해 `Cache`보십시오.  캐시된 브러시가 원하는 품질 수준을 유지하면서 너무 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>자주 재생성되지 않도록 최소 및 최대 축척 무효화 임계값(연결된 속성 및)을 설정합니다.  기본적으로 <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush> 캐시되지 않으므로 브러시로 페인팅된 내용을 다시 렌더링해야 할 때마다 먼저 브러시의 전체 내용을 중간 표면으로 다시 렌더링해야 합니다.|  
|<xref:System.Windows.Media.Effects.BitmapEffect>|<xref:System.Windows.Media.Effects.BitmapEffect>영향을 받는 모든 콘텐츠를 하드웨어 가속 없이 렌더링해야 합니다.  최상의 성능을 위해 을 <xref:System.Windows.Media.Effects.BitmapEffect>사용하지 마십시오.|  
  
## <a name="performance-impact-medium"></a>성능 영향: 중간  
  
|속성|권장|  
|-|-|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|메시가 공유 정점이 있는 인접 삼각형으로 정의되고 해당 정점이 동일한 위치, 법선 및 텍스처 좌표를 가지면 각 공유 정점을 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>한 번만 정의한 다음 을 사용하는 인덱스별로 삼각형을 정의합니다.|  
|<xref:System.Windows.Media.ImageBrush>|(a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 및/또는 를 사용하는 <xref:System.Windows.Media.ImageBrush>경우) 크기를 명시적으로 제어할 때 텍스처 크기를 최소화하십시오.  해상도가 낮은 텍스처는 시각적 품질을 떨어뜨릴 수 있으므로 품질과 성능 간의 적절한 균형을 찾아보십시오.|  
|불투명도|반투명 3D 콘텐츠(예: 반사)를 렌더링할 때 1보다 작은 값으로 <xref:System.Windows.Media.Brush.Opacity%2A> <xref:System.Windows.Media.Media3D.DiffuseMaterial.Color%2A> <xref:System.Windows.Controls.Viewport3D> 설정하여 `Viewport3D.Opacity` 별도의 반투명을 만드는 대신 브러시 또는 재질(via or) 의 불투명도 속성을 사용합니다.|  
|<xref:System.Windows.Controls.Viewport3D>|장면에서 사용 <xref:System.Windows.Controls.Viewport3D> 하려는 개체수를 최소화 합니다.  각 모델에 대해 별도의 Viewport3D 인스턴스를 만드는 대신 많은 3D 모델을 동일한 Viewport3D에 배치합니다.|  
|<xref:System.Windows.Freezable>|일반적으로 , , <xref:System.Windows.Media.Media3D.MeshGeometry3D> <xref:System.Windows.Media.Media3D.GeometryModel3D>브러시 및 재질을 재사용하는 것이 좋습니다.  모두 `Freezable`에서 파생되므로 다중 부모가 사용할 수 있습니다.|  
|<xref:System.Windows.Freezable>|해당 <xref:System.Windows.Freezable.Freeze%2A> 속성이 응용 프로그램에서 변경되지 않은 상태로 유지될 때 Freezables에서 메서드를 호출합니다.  동결은 작업 세트를 감소시키고 속도를 증가시킬 수 있습니다.|  
|<xref:System.Windows.Media.Brush>|<xref:System.Windows.Media.ImageBrush> 브러시의 <xref:System.Windows.Media.VisualBrush> 내용이 변경되지 않는 대신 사용하십시오. <xref:System.Windows.Media.DrawingBrush>  2D 컨텐더는 <xref:System.Windows.Controls.Image> via로 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 변환한 다음 <xref:System.Windows.Media.ImageBrush>에서 사용할 수 있습니다.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>|실제로 <xref:System.Windows.Media.Media3D.GeometryModel3D>의 <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> 뒷면을 볼 필요가 없는 한 사용하지 마십시오.|  
|<xref:System.Windows.Media.Media3D.Light>|라이트 속도(가장 빠르고 가장 느립니다):<br /><br /> <xref:System.Windows.Media.Media3D.AmbientLight><br /><br /> <xref:System.Windows.Media.Media3D.DirectionalLight><br /><br /> <xref:System.Windows.Media.Media3D.PointLight><br /><br /> <xref:System.Windows.Media.Media3D.SpotLight>|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|메시 크기를 다음 제한 이하로 유지해 보십시오.<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>: 20,001개의 <xref:System.Windows.Media.Media3D.Point3D> 인스턴스<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>: 60,003개 <xref:System.Int32> 인스턴스|  
|<xref:System.Windows.Media.Media3D.Material>|재질 속도(가장 빠르고 가장 느립니다):<br /><br /> <xref:System.Windows.Media.Media3D.EmissiveMaterial><br /><br /> <xref:System.Windows.Media.Media3D.DiffuseMaterial><br /><br /> <xref:System.Windows.Media.Media3D.SpecularMaterial>|  
|<xref:System.Windows.Media.Brush>|[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]3D는 보이지 않는 브러쉬(검은색 주변 브러시, 클리어 브러쉬 등)를 일관되게 옵트아웃하지 않습니다.  장면에서 이러한 것을 생략하는 것이 좋습니다.|  
|<xref:System.Windows.Media.Media3D.MaterialGroup>|각 <xref:System.Windows.Media.Media3D.Material> 렌더링 <xref:System.Windows.Media.Media3D.MaterialGroup> 패스는 다른 렌더링 패스를 발생하므로 많은 재질, 심지어 간단한 재질을 포함하여 GPU의 채우기 요구가 크게 증가할 수 있습니다.  의 재료 수를 최소화합니다. <xref:System.Windows.Media.Media3D.MaterialGroup>|  
  
## <a name="performance-impact-low"></a>성능 영향: 낮음  
  
|속성|권장|  
|-|-|  
|<xref:System.Windows.Media.Media3D.Transform3DGroup>|애니메이션 또는 데이터 바인딩이 필요하지 않은 경우 여러 변환이 포함된 변환 그룹을 <xref:System.Windows.Media.Media3D.MatrixTransform3D>사용하는 대신 단일 을 사용하여 변환 그룹에 독립적으로 존재하는 모든 변환의 곱으로 설정합니다.|  
|<xref:System.Windows.Media.Media3D.Light>|장면의 라이트 수를 최소화합니다. 장면의 라이트가 너무 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 많면 소프트웨어 렌더링으로 대체됩니다.  제한은 대략 110개의 개체, <xref:System.Windows.Media.Media3D.DirectionalLight> 70개의 <xref:System.Windows.Media.Media3D.SpotLight> <xref:System.Windows.Media.Media3D.PointLight> 개체 또는 40개의 객체입니다.|  
|<xref:System.Windows.Media.Media3D.ModelVisual3D>|이동하는 객체를 별도의 <xref:System.Windows.Media.Media3D.ModelVisual3D> 인스턴스에 배치하여 정적 개체와 분리합니다.  ModelVisual3D는 변환된 <xref:System.Windows.Media.Media3D.GeometryModel3D> 경계를 캐시하기 때문에 보다 "무겁다".  지오메트리Model3D는 모델로 최적화됩니다. ModelVisual3D는 장면 노드로 최적화됩니다.  ModelVisual3D를 사용하여 지오메트리Model3D의 공유 인스턴스를 장면에 넣습니다.|  
|<xref:System.Windows.Media.Media3D.Light>|장면의 라이트 수를 변경하는 횟수를 최소화합니다.  라이트 카운트가 변경될 때마다 해당 구성이 이전에 존재하지 않는 한 섀도백 및 재컴파일이 강제로 변경되고 섀도가 캐시되지 않는 한|  
|라이트|검은 색 표시등은 표시되지 않지만 렌더링 시간을 추가합니다. 생략하는 것을 고려하십시오.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]MeshGeometry3D의 및 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>및 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>, 값 채우기 전에 컬렉션의 사전 크기를 조정하는 등 에서 큰 컬렉션의 구성 시간을 최소화합니다. 가능하면 컬렉션의 생성자가 배열 또는 목록과 같은 미리 채워진 데이터 구조를 전달합니다.|  
  
## <a name="see-also"></a>참고 항목

- [3D 그래픽 개요](3-d-graphics-overview.md)
