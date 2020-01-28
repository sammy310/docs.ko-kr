---
title: 3D 성능 최대화
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D graphics [WPF]
ms.assetid: 4bcf949d-d92f-4d8d-8a9b-1e4c61b25bf6
ms.openlocfilehash: 414a4677a1e05cd69c382e35194328d6ce1bddf9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744602"
---
# <a name="maximize-wpf-3d-performance"></a>WPF 3D 성능 최대화
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]를 사용 하 여 3D 컨트롤을 빌드하고 응용 프로그램에 3D 장면을 포함 하는 경우 성능 최적화를 고려 하는 것이 중요 합니다. 이 항목에서는 응용 프로그램 성능에 영향을 주는 3D 클래스 및 속성의 목록을 제공 하며,이를 사용 하는 경우 성능 최적화에 대 한 권장 사항을 제공 합니다.  
  
 이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D 기능을 잘 이해 하 고 있다고 가정 합니다. 이 문서의 제안은 픽셀 셰이더 버전 2.0 및 꼭 짓 점 셰이더 버전 2.0을 지 원하는 하드웨어로 정의 된 "렌더링 계층 2"에 적용 됩니다. 자세한 내용은 [그래픽 렌더링 계층](../advanced/graphics-rendering-tiers.md)을 참조 하세요.  
  
## <a name="performance-impact-high"></a>성능 영향: 높음  
  
|속성|권장 구성|  
|-|-|  
|<xref:System.Windows.Media.Brush>|브러시 속도 (가장 빠름):<br /><br /> <xref:System.Windows.Media.SolidColorBrush><br /><br /> <xref:System.Windows.Media.LinearGradientBrush><br /><br /> <xref:System.Windows.Media.ImageBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush> (캐시 됨)<br /><br /> <xref:System.Windows.Media.VisualBrush> (캐시 됨)<br /><br /> <xref:System.Windows.Media.RadialGradientBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush> (캐시 되지 않은)<br /><br /> <xref:System.Windows.Media.VisualBrush> (캐시 되지 않은)|  
|<xref:System.Windows.UIElement.ClipToBoundsProperty>|Viewport3D's 사각형에 <xref:System.Windows.Controls.Viewport3D> 내용을 명시적으로 자르는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 없어도 될 때마다 `Viewport3D.ClipToBounds`를 false로 설정 합니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 앤티 앨리어싱 클리핑을 매우 느릴 수 있으며 <xref:System.Windows.Controls.Viewport3D>에서 기본적으로 `ClipToBounds` (느림)을 사용 합니다.|  
|<xref:System.Windows.UIElement.IsHitTestVisible%2A>|마우스 적중 테스트를 수행할 때 <xref:System.Windows.Controls.Viewport3D> 콘텐츠를 고려 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 하지 않아도 될 때마다 `Viewport3D.IsHitTestVisible`를 false로 설정 합니다.  테스트의 3D 콘텐츠 적중은 소프트웨어에서 수행 되며 메시를 사용 하는 경우 속도가 느릴 수 있습니다. <xref:System.Windows.Controls.Viewport3D>에서 <xref:System.Windows.UIElement.IsHitTestVisible%2A>은 기본적으로 사용 하도록 설정 되어 있습니다 (느림).|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D>|다른 자료 나 변환이 필요한 경우에만 다른 모델을 만듭니다.  그렇지 않은 경우에는 동일한 자료를 사용 하 여 많은 <xref:System.Windows.Media.Media3D.GeometryModel3D> 인스턴스를 몇 개의 큰 <xref:System.Windows.Media.Media3D.GeometryModel3D> 및 <xref:System.Windows.Media.Media3D.MeshGeometry3D> 인스턴스로 병합 해 보세요.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|메시 애니메이션-프레임 단위로 메시의 개별 꼭 짓 점을 변경 하는 것은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 효율적이 지 않습니다.  각 꼭 짓 점이 수정 될 때 변경 알림의 성능 영향을 최소화 하려면 꼭 짓 점 수정 작업을 수행 하기 전에 시각적 트리에서 메시를 분리 합니다.  메쉬가 수정 된 후에는 시각적 트리에 다시 연결 합니다.  또한 이러한 방식으로 애니메이션 효과를 주는 메시의 크기를 최소화 합니다.|  
|3D 앤티 앨리어싱|렌더링 속도를 높이려면 연결 된 속성 <xref:System.Windows.Media.RenderOptions.EdgeMode%2A>를 `Aliased`로 설정 하 여 <xref:System.Windows.Controls.Viewport3D>에서 다중 샘플링을 사용 하지 않도록 설정 합니다.  기본적으로 3D 앤티 앨리어싱은 픽셀 당 4 개의 샘플을 사용 하 여 Windows에서 사용 하도록 설정 됩니다.|  
|텍스트|3D 장면의 라이브 텍스트 (<xref:System.Windows.Media.DrawingBrush> 또는 <xref:System.Windows.Media.VisualBrush>에서 라이브)는 속도가 느릴 수 있습니다. 텍스트를 변경 하지 않는 한 텍스트 이미지를 대신 사용 하 여 (<xref:System.Windows.Media.Imaging.RenderTargetBitmap>을 통해) 시도 합니다.|  
|<xref:System.Windows.Media.TileBrush>|브러시의 내용이 정적이 아니기 때문에 3D 장면에서 <xref:System.Windows.Media.VisualBrush> 또는 <xref:System.Windows.Media.DrawingBrush>를 사용 해야 하는 경우 브러시를 캐시 해 보세요 (연결 된 속성 <xref:System.Windows.Media.RenderOptions.CachingHint%2A>를 `Cache`로 설정).  캐시 된 브러시를 너무 자주 다시 생성 하지 않고 원하는 품질 수준을 유지 하기 위해 최소 및 최대 크기 조정 무효화 임계값 (연결 된 속성 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> 및 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>)을 설정 합니다.  기본적으로 <xref:System.Windows.Media.DrawingBrush> 및 <xref:System.Windows.Media.VisualBrush>는 캐시 되지 않습니다. 즉, 브러시를 사용 하 여 그린 항목을 다시 렌더링 해야 할 때마다 브러시의 전체 내용을 먼저 중간 화면으로 다시 렌더링 해야 합니다.|  
|<xref:System.Windows.Media.Effects.BitmapEffect>|<xref:System.Windows.Media.Effects.BitmapEffect> 모든 영향을 받는 콘텐츠가 하드웨어 가속 없이 렌더링 되도록 합니다.  최상의 성능을 위해 <xref:System.Windows.Media.Effects.BitmapEffect>를 사용 하지 마십시오.|  
  
## <a name="performance-impact-medium"></a>성능 영향: 중형  
  
|속성|권장 구성|  
|-|-|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|메쉬가 공유 꼭지점이 있는 인접 삼각형으로 정의 되 고 해당 꼭 짓 점, 표준 및 질감 좌표가 동일한 경우 각 공유 꼭 짓 점을 한 번만 정의한 다음 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>를 사용 하 여 인덱스로 삼각형을 정의 합니다.|  
|<xref:System.Windows.Media.ImageBrush>|크기를 명시적으로 제어 하는 경우 (<xref:System.Windows.Media.Imaging.RenderTargetBitmap> 및/또는 <xref:System.Windows.Media.ImageBrush>를 사용 하는 경우) 질감 크기를 최소화 하려고 합니다.  해상도가 낮은 질감이 시각적 품질을 저하 시킬 수 있으므로 품질 및 성능 간에 적절 한 균형을 찾아야 합니다.|  
|Opacity|투명 한 3D 콘텐츠 (예: 반사)를 렌더링 하는 경우 `Viewport3D.Opacity`를 1 보다 작은 값으로 설정 하 여 별도의 반투명 <xref:System.Windows.Controls.Viewport3D>를 만드는 대신 브러시 또는 자료의 불투명도 속성 (<xref:System.Windows.Media.Brush.Opacity%2A> 또는 <xref:System.Windows.Media.Media3D.DiffuseMaterial.Color%2A>를 통해)을 사용 합니다.|  
|<xref:System.Windows.Controls.Viewport3D>|장면에서 사용 중인 <xref:System.Windows.Controls.Viewport3D> 개체 수를 최소화 합니다.  각 모델에 대해 별도의 Viewport3D 인스턴스를 만들지 않고 동일한 Viewport3D에 많은 3D 모델을 배치 합니다.|  
|<xref:System.Windows.Freezable>|일반적으로 <xref:System.Windows.Media.Media3D.MeshGeometry3D>, <xref:System.Windows.Media.Media3D.GeometryModel3D>, 브러시 및 자료를 다시 사용 하는 것이 유용 합니다.  모든는 `Freezable`에서 파생 되므로 multiparentable 됩니다.|  
|<xref:System.Windows.Freezable>|응용 프로그램에서 해당 속성이 변경 되지 않은 상태로 유지 되는 경우 Freezable에 대 한 <xref:System.Windows.Freezable.Freeze%2A> 메서드를 호출 합니다.  고정 하면 작업 집합이 줄어들고 속도가 빨라집니다.|  
|<xref:System.Windows.Media.Brush>|<xref:System.Windows.Media.VisualBrush> 대신 <xref:System.Windows.Media.ImageBrush>를 사용 하거나 브러시의 내용이 변경 되지 않을 때 <xref:System.Windows.Media.DrawingBrush> 합니다.  2D 콘텐츠는 <xref:System.Windows.Media.Imaging.RenderTargetBitmap>를 통해 <xref:System.Windows.Controls.Image> 변환 된 다음 <xref:System.Windows.Media.ImageBrush>에 사용 될 수 있습니다.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>|실제로 <xref:System.Windows.Media.Media3D.GeometryModel3D>의 뒷면을 표시 해야 하는 경우를 제외 하 고 <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>를 사용 하지 마세요.|  
|<xref:System.Windows.Media.Media3D.Light>|가벼운 속도 (가장 빠름):<br /><br /> <xref:System.Windows.Media.Media3D.AmbientLight><br /><br /> <xref:System.Windows.Media.Media3D.DirectionalLight><br /><br /> <xref:System.Windows.Media.Media3D.PointLight><br /><br /> <xref:System.Windows.Media.Media3D.SpotLight>|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|이러한 제한에 따라 메시 크기를 유지 해 보세요.<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>: 20001 <xref:System.Windows.Media.Media3D.Point3D> 인스턴스<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>: 60003 <xref:System.Int32> 인스턴스|  
|<xref:System.Windows.Media.Media3D.Material>|재질 속도 (가장 빠름):<br /><br /> <xref:System.Windows.Media.Media3D.EmissiveMaterial><br /><br /> <xref:System.Windows.Media.Media3D.DiffuseMaterial><br /><br /> <xref:System.Windows.Media.Media3D.SpecularMaterial>|  
|<xref:System.Windows.Media.Brush>|[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D는 일관 된 방식으로 보이지 않는 브러시 (검정 앰비언트 브러시, clear 브러시 등)를 옵트아웃 (opt out) 하지 않습니다.  장면에서 생략 하는 것이 좋습니다.|  
|<xref:System.Windows.Media.Media3D.MaterialGroup>|<xref:System.Windows.Media.Media3D.MaterialGroup>의 각 <xref:System.Windows.Media.Media3D.Material>은 다른 렌더링 패스를 야기 하므로 많은 자료를 포함 하 여 간단한 자료를 포함 하 여 GPU에 대 한 채우기 수요를 크게 늘릴 수 있습니다.  <xref:System.Windows.Media.Media3D.MaterialGroup>자료의 수를 최소화 합니다.|  
  
## <a name="performance-impact-low"></a>성능 영향: 낮음  
  
|속성|권장 구성|  
|-|-|  
|<xref:System.Windows.Media.Media3D.Transform3DGroup>|여러 변환이 포함 된 변환 그룹을 사용 하는 대신 애니메이션이 나 데이터 바인딩이 필요 하지 않은 경우에는 단일 <xref:System.Windows.Media.Media3D.MatrixTransform3D>를 사용 하 여 변환 그룹에 독립적으로 존재 하는 모든 변환의 곱으로 설정 합니다.|  
|<xref:System.Windows.Media.Media3D.Light>|장면의 조명 수를 최소화 합니다. 장면에 너무 많은 표시등이 있으면 강제로 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 소프트웨어 렌더링으로 대체 됩니다.  한도는 대략 110 <xref:System.Windows.Media.Media3D.DirectionalLight> 개체, 70 <xref:System.Windows.Media.Media3D.PointLight> 개체 또는 40 <xref:System.Windows.Media.Media3D.SpotLight> 개체입니다.|  
|<xref:System.Windows.Media.Media3D.ModelVisual3D>|별도의 <xref:System.Windows.Media.Media3D.ModelVisual3D> 인스턴스에 배치 하 여 개체를 정적 개체에서 분리 합니다.  ModelVisual3D는 변환 된 범위를 캐시 하므로 <xref:System.Windows.Media.Media3D.GeometryModel3D> 보다 "굵게" 됩니다.  GeometryModel3D는 모델로 최적화 되어 있습니다. ModelVisual3D는 장면 노드가 되도록 최적화 되었습니다.  ModelVisual3D를 사용 하 여 GeometryModel3D의 공유 인스턴스를 장면에 배치 합니다.|  
|<xref:System.Windows.Media.Media3D.Light>|장면의 조명 수를 변경 하는 횟수를 최소화 합니다.  해당 구성이 이전에 존재 하지 않아 셰이더가 캐시 되지 않은 경우에는 각 빛 개수의 변화에 따라 셰이더를 다시 생성 하 고 다시 컴파일해야 합니다.|  
|밝게|검정 조명이 표시 되지 않지만 렌더링 시간에 추가 됩니다. 생략 하는 것이 좋습니다.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|MeshGeometry3D's <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>등 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 큰 컬렉션의 생성 시간을 최소화 하려면 값 채우기 전에 컬렉션의 크기를 미리 조정 합니다. 가능 하면 배열 또는 목록과 같은 컬렉션의 생성자 미리 채워진 데이터 구조를 전달 합니다.|  
  
## <a name="see-also"></a>참조

- [3차원 그래픽 개요](3-d-graphics-overview.md)
