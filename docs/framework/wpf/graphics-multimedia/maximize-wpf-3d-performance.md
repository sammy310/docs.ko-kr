---
title: WPF 3D 성능 최대화
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D graphics [WPF]
ms.assetid: 4bcf949d-d92f-4d8d-8a9b-1e4c61b25bf6
ms.openlocfilehash: 8629748c37aae8e35bb928c5a8d5a9caa7046942
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147526"
---
# <a name="maximize-wpf-3d-performance"></a>WPF 3D 성능 최대화
사용 된 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D 컨트롤을 빌드하고 응용 프로그램에서 3D 장면을 포함 하려면 성능 최적화를 고려해 야 할 중요 한 것입니다. 이 항목에서는 사용 하는 경우 성능을 최적화 하기 위한 권장 사항과 함께 응용 프로그램에 대 한 성능 영향을 미칠는 3D 클래스 및 속성의 목록을 제공 합니다.  
  
 이 항목에서는 고급 이해가 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D 기능입니다. 이 문서의 제안 "렌더링 계층 2"에 적용할-픽셀 셰이더 버전 2.0 및 꼭 짓 점 셰이더 버전 2.0 지 원하는 하드웨어에 대략적으로 정의 합니다. 자세한 내용은 참조 하세요. [그래픽 렌더링 계층](../advanced/graphics-rendering-tiers.md)합니다.  
  
## <a name="performance-impact-high"></a>성능 영향을 미침 높음  
  
|속성|권장 사항|  
|-|-|  
|<xref:System.Windows.Media.Brush>|브러시 속도 (가장 느린으로):<br /><br /> <xref:System.Windows.Media.SolidColorBrush><br /><br /> <xref:System.Windows.Media.LinearGradientBrush><br /><br /> <xref:System.Windows.Media.ImageBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush> (캐시 됨)<br /><br /> <xref:System.Windows.Media.VisualBrush> (캐시 됨)<br /><br /> <xref:System.Windows.Media.RadialGradientBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush> (캐쉬되지 않은)<br /><br /> <xref:System.Windows.Media.VisualBrush> (캐쉬되지 않은)|  
|<xref:System.Windows.UIElement.ClipToBoundsProperty>|설정 `Viewport3D.ClipToBounds` false 할 필요가 없습니다 때마다 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 명시적으로의 콘텐츠를 잘라는 <xref:System.Windows.Controls.Viewport3D> Viewport3D의 사각형에 합니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 앤티 앨리어싱 클리핑 매우 느려질 수 있습니다 하 고 `ClipToBounds` 기본적으로 (느리게) 사용은 <xref:System.Windows.Controls.Viewport3D>합니다.|  
|<xref:System.Windows.UIElement.IsHitTestVisible%2A>|설정 `Viewport3D.IsHitTestVisible` 않아도 때마다 false로 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 의 콘텐츠를 고려 하는 <xref:System.Windows.Controls.Viewport3D> 수행 마우스 적중 테스트 하는 경우.  적중된 테스트 3D 콘텐츠 소프트웨어에서 수행 되 고 대형 메시를 사용 하 여 속도가 느려질 수 있습니다. <xref:System.Windows.UIElement.IsHitTestVisible%2A> 기본적으로 (느리게) 사용은 <xref:System.Windows.Controls.Viewport3D>합니다.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D>|다른 자료 또는 변환 필요할 경우에 다른 모델을 만듭니다.  그렇지 않으면 많은 병합 하려고 <xref:System.Windows.Media.Media3D.GeometryModel3D> 소수의 큰에 동일한 자료 및 변환을 사용 하 여 인스턴스 <xref:System.Windows.Media.Media3D.GeometryModel3D> 및 <xref:System.Windows.Media.Media3D.MeshGeometry3D> 인스턴스.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|애니메이션 메시-프레임당 기준 메시의 개별 꼭 짓 점을 변경-은 항상 효율적 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]합니다.  영향을 최소화 하기 성능 변경 알림의 각 꼭 짓 점을 수정 될 때, 꼭 짓 점별 수정을 수행 하기 전에 시각적 트리에서 메시를 분리 합니다.  메시를 수정한 후 시각적 트리를 다시 연결 합니다.  또한이 방식으로 애니메이션 효과가 적용 됩니다는 메시의 크기를 최소화 하려고 합니다.|  
|3D 앤티앨리어싱|렌더링 속도를 높이려면 다중 샘플링에서 사용 안 함을 <xref:System.Windows.Controls.Viewport3D> 연결된 된 속성을 설정 하 여 <xref:System.Windows.Media.RenderOptions.EdgeMode%2A> 에 `Aliased`입니다.  기본적으로 3D 앤티앨리어싱에서 사용할 수 없습니다 [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] 에서 사용 하도록 설정 하 고 [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)] 픽셀당 4 개 샘플을 사용 하 여 합니다.|  
|텍스트|3D 장면에서 텍스트를 live (이기 때문에 live를 <xref:System.Windows.Media.DrawingBrush> 또는 <xref:System.Windows.Media.VisualBrush>) 속도가 느려질 수 있습니다. 텍스트의 이미지를 대신 사용 하도록 시도 (통해 <xref:System.Windows.Media.Imaging.RenderTargetBitmap>) 텍스트를 변경 하지 않는 한 합니다.|  
|<xref:System.Windows.Media.TileBrush>|사용 해야 하는 경우는 <xref:System.Windows.Media.VisualBrush> 또는 <xref:System.Windows.Media.DrawingBrush> 3D 장면에서 브러시의 콘텐츠를 정적 같지 않으므로 시도 브러시 캐싱 (연결 된 속성을 설정 <xref:System.Windows.Media.RenderOptions.CachingHint%2A> 에 `Cache`).  최소 및 최대 눈금 무효화 임계값 설정 (연결 된 속성을 사용 하 여 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> 및 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>)에 원하는 수준의 품질을 유지 하면서 캐시 된 브러시를 너무 자주 재생성지 않습니다 있도록 합니다.  기본적으로 <xref:System.Windows.Media.DrawingBrush> 고 <xref:System.Windows.Media.VisualBrush> , 캐시 되지 않습니다는 다시 렌더링 되어야 하는 브러시를 사용 하 여 그린 것 때마다 브러시의 전체 내용을 먼저 다시 하도록 렌더링 해야 중간 화면을 의미 합니다.|  
|<xref:System.Windows.Media.Effects.BitmapEffect>|<xref:System.Windows.Media.Effects.BitmapEffect> 하드웨어 가속이 없으면 렌더링할 모든 영향을 받는 콘텐츠를 강제로 수행 합니다.  최상의 성능을 위해 사용 하지 마십시오 <xref:System.Windows.Media.Effects.BitmapEffect>합니다.|  
  
## <a name="performance-impact-medium"></a>성능 영향을 미침 중간  
  
|속성|권장 사항|  
|-|-|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|메시 인접 꼭 짓 점을 공유 삼각형으로 정의 됩니다 하 고 이러한 꼭 짓 점은 동일한 위치, 정규 및 텍스처 좌표를 각 공유 꼭 짓 점을 한 번만 정의 하 고 다음 사용 하 여 인덱스 여 삼각형을 정의 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>합니다.|  
|<xref:System.Windows.Media.ImageBrush>|크기를 명시적으로 제어 해야 하는 경우 질감 크기를 최소화 하려고 합니다. (사용 하는 경우는 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 및/또는 <xref:System.Windows.Media.ImageBrush>).  낮은 해상도 질감 시각적 품질이 저하, 품질 및 성능 간에 적절 한 균형을 찾으려고 시도 하므로 수는 note 합니다.|  
|Opacity|반투명 3D 콘텐츠 (예: 리플렉션) 렌더링 하는 경우 불투명도 속성을 사용 하 여 브러시 또는 자료 (통해 <xref:System.Windows.Media.Brush.Opacity%2A> 또는 <xref:System.Windows.Media.Media3D.DiffuseMaterial.Color%2A>) 별도 반투명 만드는 대신 <xref:System.Windows.Controls.Viewport3D> 설정 하 여 `Viewport3D.Opacity` 1 보다 작은 값으로.|  
|<xref:System.Windows.Controls.Viewport3D>|수를 최소화 <xref:System.Windows.Controls.Viewport3D> 장면에서 사용 하는 개체입니다.  각 모델에 대 한 별도 Viewport3D 인스턴스를 만드는 것이 아니라 동일한 Viewport3D 많은 3D 모델을 배치 합니다.|  
|<xref:System.Windows.Freezable>|일반적으로는 다시 사용 하는 데 유용한 <xref:System.Windows.Media.Media3D.MeshGeometry3D>, <xref:System.Windows.Media.Media3D.GeometryModel3D>, 브러시 및 자료입니다.  파생 되었기 때문 multiparentable 모두 `Freezable`입니다.|  
|<xref:System.Windows.Freezable>|호출을 <xref:System.Windows.Freezable.Freeze%2A> 메서드 Freezable 해당 속성은 유지 하는 경우에 응용 프로그램에서 변경 되지 않습니다.  고정 작업 집합을 감소 하 고 속도 높일 수 있습니다.|  
|<xref:System.Windows.Media.Brush>|사용 하 여 <xref:System.Windows.Media.ImageBrush> of <xref:System.Windows.Media.VisualBrush> 또는 <xref:System.Windows.Media.DrawingBrush> 브러시의 콘텐츠가 변경 되지 것입니다.  2D 콘텐츠를 변환할 수는 <xref:System.Windows.Controls.Image> 를 통해 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 한 다음에 사용 된 <xref:System.Windows.Media.ImageBrush>.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>|사용 하지 마세요 <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> 의 뒷면에 실제로 필요한 경우가 아니면 프로그램 <xref:System.Windows.Media.Media3D.GeometryModel3D>합니다.|  
|<xref:System.Windows.Media.Media3D.Light>|광속 (가장 느린으로).<br /><br /> <xref:System.Windows.Media.Media3D.AmbientLight><br /><br /> <xref:System.Windows.Media.Media3D.DirectionalLight><br /><br /> <xref:System.Windows.Media.Media3D.PointLight><br /><br /> <xref:System.Windows.Media.Media3D.SpotLight>|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|이러한 한도 아래 메시 크기를 유지 하려고 합니다.<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>: 20001 <xref:System.Windows.Media.Media3D.Point3D> 인스턴스<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>: 60,003 <xref:System.Int32> 인스턴스|  
|<xref:System.Windows.Media.Media3D.Material>|재질 속도 (가장 느린으로).<br /><br /> <xref:System.Windows.Media.Media3D.EmissiveMaterial><br /><br /> <xref:System.Windows.Media.Media3D.DiffuseMaterial><br /><br /> <xref:System.Windows.Media.Media3D.SpecularMaterial>|  
|<xref:System.Windows.Media.Brush>|[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D는 보이지 않는 브러시 (검은색 앰비언트 브러시, clear 브러시, 등)에서 일관 된 방식으로 옵트아웃 하지 않으면.  장면에서 이러한 항목을 제거 하는 것이 좋습니다.|  
|<xref:System.Windows.Media.Media3D.MaterialGroup>|각 <xref:System.Windows.Media.Media3D.Material> 에 <xref:System.Windows.Media.Media3D.MaterialGroup> 하므로 많은 자료를 비롯 하 여 다른 렌더링 패스 사용 하면 간단한 자료에도, GPU의 채우기 수요를 크게 늘릴 수 있습니다.  자료의 수를 최소화 하면 <xref:System.Windows.Media.Media3D.MaterialGroup>합니다.|  
  
## <a name="performance-impact-low"></a>성능 영향을 미침 낮음  
  
|속성|권장 사항|  
|-|-|  
|<xref:System.Windows.Media.Media3D.Transform3DGroup>|애니메이션 필요가 또는 데이터 바인딩, 여러 변환을 포함 하는 변환 그룹을 사용 하는 대신 단일을 사용할 경우 <xref:System.Windows.Media.Media3D.MatrixTransform3D>는 그렇지 않은 경우 독립적으로 존재 변환 그룹의 모든 변환은의 제품 수를 설정 합니다.|  
|<xref:System.Windows.Media.Media3D.Light>|장면에서 조명의 수를 최소화 합니다. 장면에서 너무 많은 광원을 강제로 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 소프트웨어 렌더링으로 대체 합니다.  제한은 110 대략 <xref:System.Windows.Media.Media3D.DirectionalLight> 개체를 70 <xref:System.Windows.Media.Media3D.PointLight> 개체나 40 <xref:System.Windows.Media.Media3D.SpotLight> 개체입니다.|  
|<xref:System.Windows.Media.Media3D.ModelVisual3D>|별개의 배치 하 여 정적 개체에서 개체를 이동 하는 별도 <xref:System.Windows.Media.Media3D.ModelVisual3D> 인스턴스.  ModelVisual3D는 "무거운" 보다 <xref:System.Windows.Media.Media3D.GeometryModel3D> 변환된 범위 캐시 때문입니다.  GeometryModel3D 모델을 최적화 됩니다. ModelVisual3D는 장면 노드가 하도록 최적화 됩니다.  GeometryModel3D의 공유 인스턴스 장면 넣을 ModelVisual3D를 사용 합니다.|  
|<xref:System.Windows.Media.Media3D.Light>|장면에서 광원의 수를 변경 하는 횟수를 최소화 합니다.  밝은 수가 변경 될 때마다 해당 구성이 이미 존재 합니다 (및 따라서 셰이더 캐시 된) 하지 않는 한 셰이더 다시 생성 하 고 다시 컴파일할 되도록 합니다.|  
|밝게|검정 광원 표시 되지 않지만 렌더링 시간; 사용 하지 않는 것이 좋습니다.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|큰 컬렉션의 생성 시간을 최소화 하 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], MeshGeometry3D의 같은 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>, 및 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>, 사전 값 채우기 전에 컬렉션 크기 조정 합니다. 가능 하면 배열 또는 목록 같은 컬렉션의 생성자 미리 채워진된 데이터 구조를 전달 합니다.|  
  
## <a name="see-also"></a>참고자료

- [3차원 그래픽 개요](3-d-graphics-overview.md)
