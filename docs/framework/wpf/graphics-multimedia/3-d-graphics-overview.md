---
title: 3D 그래픽 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D graphics [WPF]
- graphics [WPF], 3D
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
ms.openlocfilehash: b8a3876030c533dd37eca0b00ebd50bccf309e53
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112390"
---
# <a name="3d-graphics-overview"></a>3D 그래픽 개요
<a name="introduction"></a>개발자는 3D [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 기능을 통해 마크업 코드와 절차 코드 모두에서 3D 그래픽을 그리고 변환하고 애니메이션할 수 있습니다. 개발자는 2D 및 3D 그래픽을 결합하여 풍부한 컨트롤을 만들고, 복잡한 데이터 그림을 제공하거나, 응용 프로그램 인터페이스의 사용자 환경을 향상시킬 수 있습니다. 3D [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 지원은 모든 기능을 갖춘 게임 개발 플랫폼을 제공하도록 설계되지 않았습니다. 이 항목에서는 그래픽 시스템의 3D [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기능에 대한 개요를 제공합니다.  

<a name="threed_in_2d"></a>
## <a name="3d-in-a-2d-container"></a>2D 컨테이너의 3D  
 3D [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 그래픽 콘텐츠는 2차원 엘리먼트 <xref:System.Windows.Controls.Viewport3D>구조에 참여할 수 있는 요소로 캡슐화된다. 그래픽 시스템은 의 <xref:System.Windows.Controls.Viewport3D> 다른 요소와 마찬가지로 2차원 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]시각적 요소로 취급합니다. <xref:System.Windows.Controls.Viewport3D>창(뷰포트)을 3차원 장면으로 변환합니다. 더 정확하게 는 3D 장면이 투영되는 표면입니다.  
  
 기존의 2D 응용 프로그램에서는 Grid 또는 캔버스와 같은 다른 컨테이너 요소와 마찬가지로 사용합니다. <xref:System.Windows.Controls.Viewport3D>  동일한 장면 <xref:System.Windows.Controls.Viewport3D> 그래프에서 다른 2D 드로잉 오브젝트와 함께 사용할 수 있지만, 2D <xref:System.Windows.Controls.Viewport3D>및 3D 오브젝트 내의 2D 및 3D 오브젝트는 상호 침투할 수 없습니다.  이 항목에서는 에서 3D 그래픽을 <xref:System.Windows.Controls.Viewport3D>그리는 방법에 대해 중점합니다.  
  
<a name="coord_space"></a>
## <a name="3d-coordinate-space"></a>3D 좌표 공간  
 2D 그래픽의 좌표계는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 렌더링 영역의 왼쪽 위(일반적으로 화면)에서 원점이 찾습니다. 2D 시스템에서 양수 x축 값은 오른쪽으로 진행되고 양수 y축 값은 아래쪽으로 진행됩니다.  그러나 3D 좌표계에서 원점은 렌더링 영역의 중심에 위치하며 양수 x축 값은 오른쪽으로 진행되지만 양수 y축 값은 위쪽으로 진행되고 양수 z축 값은 원점에서 바깥쪽으로 진행됩니다. 뷰어쪽으로 향합니다.  
  
 ![좌표계](./media/coordsystem-1.png "코디시스템-1")  
기존의 2D 및 3D 좌표계 표현  
  
 이러한 축에 의해 정의된 공간은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 3D 객체에 대한 고정 참조 프레임입니다. 이 공간에서 모델을 빌드하고 이를 보기 위한 광원과 카메라를 만들 때는 변환 적용 시 각 모델에 대해 만드는 로컬 참조 프레임을 이 고정 참조 프레임 또는 "월드 공간"과 구분하면 유용합니다. 또한 월드 공간의 개체는 광원 및 카메라 설정에 따라 완전히 다르게 보이거나 전혀 보이지 않을 수 있지만 카메라의 위치는 월드 공간에서 개체의 위치를 변경하지 않습니다.  
  
<a name="cameras"></a>
## <a name="cameras-and-projections"></a>카메라 및 프로젝션  
 2D에서 작업하는 개발자는 드로잉 프리미티브를 2차원 화면에 배치하는 데 익숙합니다. 3D 장면을 만들 때는 3D 오브젝트의 2D 표현을 실제로 작성한다는 점을 기억해야 합니다. 3D 장면은 구경꾼의 관점에 따라 다르게 보이므로 해당 시점을 지정해야 합니다. 클래스를 <xref:System.Windows.Media.Media3D.Camera> 사용하면 3D 장면에 대해 이 시점을 지정할 수 있습니다.  
  
 3D 장면이 2D 표면에 표시되는 방식을 이해하는 또 다른 방법은 장면을 보기 표면에 투영으로 설명하는 것입니다. 을 <xref:System.Windows.Media.Media3D.ProjectionCamera> 사용하면 다른 투영과 해당 속성을 지정하여 구경꾼이 3D 모델을 보는 방식을 변경할 수 있습니다. A는 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 장면을 단축하는 투영을 지정합니다.  즉, 소실점 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 원근을 제공합니다.  장면 좌표 공간에서의 카메라 위치, 카메라의 방향 및 시야, 장면의 "위쪽" 방향을 정의하는 벡터를 지정할 수 있습니다. 다음 다이어그램은 <xref:System.Windows.Media.Media3D.PerspectiveCamera>'투영'을 보여 줍니다.  
  
 카메라 <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> 투영 <xref:System.Windows.Media.Media3D.ProjectionCamera> 범위를 제한하는 특성입니다. 카메라는 장면의 어느 위치에나 배치될 수 있으므로 카메라가 실제로 모델 내 또는 모델에 매우 가깝게 배치될 수 있으며 이로 인해 개체를 제대로 구별하기가 어려워집니다.  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A>이를 사용하면 그려지지 않는 오브젝트를 넘어 카메라로부터 의 최소 거리를 지정할 수 있습니다.  반대로, <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> 그려지지 않을 오브젝트를 넘어 카메라로부터의 거리를 지정할 수 있으므로 너무 멀리 있는 오브젝트가 장면에 포함되지 않도록 할 수 있습니다.  
  
 ![카메라 설정](./media/coordsystem-6.png "코디시스템-6")  
카메라 위치  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera>3D 모델의 직교 투영을 2D 시각적 표면에 지정합니다. 다른 카메라와 마찬가지로 이는 위치, 보기 방향 및 "위쪽" 방향을 지정합니다. 와 달리 <xref:System.Windows.Media.Media3D.PerspectiveCamera>그러나 <xref:System.Windows.Media.Media3D.OrthographicCamera> 원근 단축법을 포함 하지 않는 프로젝션을 설명 합니다. 즉, <xref:System.Windows.Media.Media3D.OrthographicCamera> 측면이 카메라의 한 지점에서 만나는 대신 측면이 평행한 보기 상자를 설명합니다. 다음 이미지는 를 사용하여 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 본 것과 <xref:System.Windows.Media.Media3D.OrthographicCamera>동일한 모델을 보여 주며.  
  
 ![직교 및 원근 프로젝션](./media/camera-projections4.png "Camera_projections4")  
원근 및 직교 프로젝션  
  
 다음 코드에서는 일반적인 카메라 설정을 보여 줍니다.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>
## <a name="model-and-mesh-primitives"></a>모델 및 메시 기본 형식  
  
 <xref:System.Windows.Media.Media3D.Model3D>은 제네릭 3D 개체를 나타내는 추상 기본 클래스입니다. 3D 장면을 작성하려면 볼 오브젝트와 장면 그래프를 구성하는 오브젝트가 에서 <xref:System.Windows.Media.Media3D.Model3D>파생됩니다. 현재 는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 을 통해 <xref:System.Windows.Media.Media3D.GeometryModel3D>모델링 형상을 지원합니다. 이 <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> 모델의 속성은 메시 기본 을 사용합니다.  
  
 모델을 빌드하려면 먼저 기본 형식 또는 메시를 빌드합니다. 3D 기본은 단일 3D 엔터티를 형성하는 정점 의 컬렉션입니다. 대부분의 3D 시스템은 가장 단순한 닫힌 그림(세 정점으로 정의된 삼각형)을 모델로 한 기본 을 제공합니다.  삼각형의 세 점은 같은 평면에 있으므로 메시라는 보다 복잡한 도형을 모델링하기 위해 계속해서 삼각형을 추가할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 3D 시스템은 현재 <xref:System.Windows.Media.Media3D.MeshGeometry3D> 모든 형상을 지정할 수 있는 클래스를 제공합니다. 현재 구 및 입방 형태와 같이 미리 정의된 3D 프리미티브를 지원하지 않습니다. 삼각형 정점 목록을 <xref:System.Windows.Media.Media3D.MeshGeometry3D> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 속성으로 지정하여 a를 작성하기 시작합니다. 각 정점은 <xref:System.Windows.Media.Media3D.Point3D>로 지정됩니다.  에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]이 속성을 각 정점의 좌표를 나타내는 세 개의 숫자로 그룹화된 숫자 목록으로 지정합니다. 지오메트리에 따라 메시는 여러 삼각형으로 구성될 수 있으며, 그 중 일부는 동일한 모서리(정점)를 공유합니다. 메시를 올바르게 그리려면 어떤 삼각형에 어떤 꼭짓점이 공유되는지에 대한 정보를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 제공해야 합니다. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> 속성에 삼각형 인덱스 목록을 지정 하 여이 정보를 제공 합니다. 이 목록은 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 목록에 지정된 점이 삼각형을 결정하는 순서를 지정합니다.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN3](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 앞의 예제에서 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 목록은 큐브 모양의 메시를 정의하기 위해 8개의 정점을 지정합니다. 속성은 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> 세 개의 인덱스로 구성된 12개 그룹 목록을 지정합니다.  목록의 각 숫자는 목록에 대한 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 오프셋을 나타냅니다.  예를 들어 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 목록에 지정된 처음 세 정점(1,1,0), (0,1,0) 및 (0,0,0)입니다. 목록에서 지정한 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> 처음 세 개의 인덱스는 0, 2 및 1이며, 이는 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 목록의 첫 번째, 세 번째 및 두 번째 점에 해당합니다. 그 결과 큐브 모델을 구성하는 첫 번째 삼각형은 (1,1,0)에서 (0,1,0) 및 (0,0,0)으로 이어지고 나머지 11개의 삼각형도 이와 비슷하게 결정됩니다.  
  
 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> 및 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> 속성에 대한 값을 지정하여 모델을 계속 정의할 수 있습니다.  모델의 표면을 렌더링하려면 지정된 임의의 삼각형에서 해당 표면이 어느 방향을 바라보고 있는지에 대한 정보를 그래픽 시스템에 제공해야 합니다. 그래픽 시스템은 이 정보를 사용하여 모델에 대한 조명 계산을 수행할 수 있습니다. 즉, 광원 쪽 표면이 광원 반대쪽 표면보다 밝게 나타납니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 위치 좌표를 사용하여 기본 법선 벡터를 결정할 수 있지만 다른 법선 벡터를 지정하여 곡선 표면의 모양을 대략적으로 나타낼 수도 있습니다.  
  
 이 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> 속성은 텍스처가 <xref:System.Windows.Point>메시의 정수에 그려지는 방식을 결정하는 좌표를 매핑하는 방법을 그래픽 시스템에 알려주는 s 컬렉션을 지정합니다. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>을 포함하여 0과 1 사이의 값으로 지정됩니다.  속성과 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> 마찬가지로 그래픽 시스템은 기본 텍스처 좌표를 계산할 수 있지만 다른 텍스처 좌표를 설정하여 반복 패턴의 일부를 포함하는 텍스처의 매핑을 제어하도록 선택할 수 있습니다. 질감 좌표에 대한 자세한 내용은 다음 항목 또는 Managed Direct3D SDK를 참조하세요.  
  
 다음 예제에서는 프로시저 코드로 큐브 모델의 한 면을 만드는 방법을 보여 줍니다. 큐브 전체를 단일 GeometryModel3D로 그릴 수 있지만 이 예제에서는 나중에 각 면에 별도의 질감을 적용하기 위해 큐브 면을 고유한 모델로 그립니다.  
  
 [!code-csharp[3doverview#3DOverview3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>'
## <a name="applying-materials-to-the-model"></a>모델에 재질 적용  
  
 메시가 3차원 개체로 보이도록 만들려면 카메라로 비추고 프로젝션할 수 있도록 해당 꼭짓점과 삼각형으로 정의된 표면에 질감을 적용해야 합니다. 2D에서는 클래스를 <xref:System.Windows.Media.Brush> 사용하여 화면 영역에 색상, 패턴, 그라데이션 또는 기타 시각적 콘텐츠를 적용합니다.  그러나 3D 오브젝트의 모양은 적용된 색상이나 패턴뿐만 아니라 조명 모델의 함수입니다. 실제 개체는 표면의 품질에 따라 빛을 다르게 반사합니다. 광택이 나거나 빛나는 표면은 거칠거나 윤기 없는 표면과 다르게 보이며 어떤 개체는 빛을 흡수하는 것처럼 보이는 반면 다른 개체는 빛이 납니다. 2D 객체에 적용할 수 있는 3D 오브젝트에 동일한 브러시를 모두 적용할 수 있지만 직접 적용할 수는 없습니다.  
  
 모델 표면의 특성을 정의하려면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 추상 <xref:System.Windows.Media.Media3D.Material> 클래스를 사용합니다. Material의 구체적 하위 클래스는 모델 표면의 일부 모양 특성을 결정하며 이들 각각은 SolidColorBrush, TileBrush 또는 VisualBrush를 전달할 수 있는 Brush 속성도 제공합니다.  
  
- <xref:System.Windows.Media.Media3D.DiffuseMaterial>브러시가 모델에 분산된 것처럼 모델에 적용되도록 지정합니다. 분산재재 사용 대부분의 경우 2D 모델에서 직접 브러시를 사용하는 것과 유사합니다. 모델 표면은 빛을 반짝이는 것처럼 반사하지 않습니다.  
  
- <xref:System.Windows.Media.Media3D.SpecularMaterial>모델의 표면이 단단하거나 광택이 있어 하이라이트를 반사할 수 있는 것처럼 브러시가 모델에 적용되도록 지정합니다. <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A> 속성값을 지정하여 텍스처가 이 반사 품질 또는 "광택"을 제안하는 정도를 설정할 수 있습니다.  
  
- <xref:System.Windows.Media.Media3D.EmissiveMaterial>을 사용하면 모델이 브러시의 색상과 동일한 라이트를 방출하는 것처럼 텍스처가 적용되도록 지정할 수 있습니다. 그러나 이로 인해 모델이 광원이 되는 것은 아니며 DiffuseMaterial 또는 SpecularMaterial을 사용하여 질감을 표현할 때와는 다른 방식으로 섀도잉에 참여합니다.  
  
 더 나은 성능을 위해 카메라에서 <xref:System.Windows.Media.Media3D.GeometryModel3D> 모델의 반대쪽에 있기 때문에 보이지 않는 얼굴의 뒷면이 장면에서 컬링됩니다.  평면과 <xref:System.Windows.Media.Media3D.Material> 같은 모델의 뒷면에 적용할 을 지정하려면 모델의 <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> 속성을 설정합니다.  
  
 빛이 나거나 반사되는 효과와 같은 일부 표면 품질을 얻으려면 모델에 여러 개의 서로 다른 브러시를 연속으로 적용해야 할 수 있습니다. 클래스를 <xref:System.Windows.Media.Media3D.MaterialGroup> 사용하여 여러 재질을 적용하고 다시 사용할 수 있습니다. MaterialGroup의 자식이 맨 먼저 적용되어 여러 렌더링 패스에서 지속됩니다.  
  
 다음 코드 예제는 단색과 드로잉을 3D 모델에 브러시로 적용하는 방법을 보여 주며 있습니다.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN5](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  ' [!code-xaml[3doverview#3DOverview3DN9](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
 ' [!code-csharp[3doverview#3DOverview3DN8](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
  [!code-vb[3doverview#3DOverview3DN8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>
## <a name="illuminating-the-scene"></a>장면 비추기  
 3D 그래픽의 라이트는 조명이 실제 환경에서 수행하는 작업을 수행합니다. 보다 정확히 말해 광원은 프로젝션에 포함될 장면의 부분을 결정합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 광원 개체는 다양한 명암 효과를 만들며 여러 실제 광원의 동작을 기반으로 모델링됩니다. 장면에 하나 이상의 광원을 포함하지 않으면 모델이 보이지 않습니다.  
  
 다음 라이트는 기본 클래스에서 <xref:System.Windows.Media.Media3D.Light>파생됩니다.  
  
- <xref:System.Windows.Media.Media3D.AmbientLight>: 위치나 방향에 관계없이 모든 피사체를 균일하게 비추는 주변 조명을 제공합니다.  
  
- <xref:System.Windows.Media.Media3D.DirectionalLight>: 원거리 광원처럼 조명합니다.  방향 라이트에는 <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A> Vector3D로 지정되었지만 지정된 위치는 없습니다.  
  
- <xref:System.Windows.Media.Media3D.PointLight>: 근처의 광원처럼 조명을 비춥니다. PointLight는 위치가 있으며 해당 위치에서 빛을 발합니다. 장면의 개체는 광원과 관련된 해당 위치 및 거리에 따라 비춰집니다. <xref:System.Windows.Media.Media3D.PointLightBase><xref:System.Windows.Media.Media3D.PointLightBase.Range%2A> 속성에 노출되며, 이 거리는 라이트에 의해 조명되지 않는 모델 과의 거리를 결정합니다. 또한 PointLight는 거리에 따라 광원의 강도가 감소되는 방식을 결정하는 감쇠 속성도 노출합니다. 광원 감쇠에 대해 상수, 선형 또는 정방형 보간을 지정할 수 있습니다.  
  
- <xref:System.Windows.Media.Media3D.SpotLight>: <xref:System.Windows.Media.Media3D.PointLight>에서 상속합니다. SpotLight는 PointLight와 유사하게 비추며 위치와 방향이 모두 있습니다. 각도로 지정된 원뿔 모양 영역과 <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A> 속성에 라이트를 투영합니다.  
  
 라이트는 <xref:System.Windows.Media.Media3D.Model3D> 객체이므로 위치, 색상, 방향 및 범위를 포함하여 라이트 특성을 변환하고 애니메이션할 수 있습니다.  
  
 [!code-xaml[hittest3d#HitTest3D3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>
## <a name="transforming-models"></a>모델 변환  
 모델을 만들 때 모델에는 장면에서의 특정 위치가 지정됩니다. 장면에서 이러한 모델을 이동하거나, 회전하거나, 크기를 변경하기 위해 모델 자체를 정의하는 꼭짓점을 변경하는 것은 비효율적입니다.  대신 2D와 마찬가지로 모델에 변환을 적용합니다.  
  
 각 모델 개체에는 모델을 이동, 방향 조정 또는 크기를 조정할 수 있는 <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> 속성이 있습니다.  변환을 적용할 때는 변환에 의해 지정된 벡터 또는 값이 무엇이든 실제적으로 모델의 모든 점을 오프셋합니다. 즉, 모델이 정의된 좌표 공간("모델 공간")은 변환하지만 장면 전체("월드 공간")의 좌표계에서 모델의 기하 도형을 구성하는 값은 변경하지 않습니다.  
  
 모델 변환에 대한 자세한 내용은 [3D 변환 개요를](3-d-transformations-overview.md)참조하십시오.  
  
<a name="animations"></a>
## <a name="animating-models"></a>모델에 애니메이션 효과 주기  
 3D 구현은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 2D 그래픽과 동일한 타이밍 및 애니메이션 시스템에 참여합니다. 즉, 3D 장면을 애니메이션하려면 모델의 속성에 애니메이션을 애니메이션합니다. 기본 형식의 속성에 직접 애니메이션 효과를 줄 수도 있지만 일반적으로 모델의 위치나 모양을 변경하는 변환에 애니메이션 효과를 주는 것이 보다 쉽습니다. 변환은 개별 모델뿐만 <xref:System.Windows.Media.Media3D.Model3DGroup> 아니라 개체에 적용할 수 있으므로 Model3DGroup의 자식에 한 애니메이션 집합과 다른 애니메이션 집합을 자식 오브젝트 그룹에 적용할 수 있습니다. 장면의 조명 속성에 애니메이션 효과를 주어 다양한 시각적 효과를 얻을 수도 있습니다. 마지막으로 카메라 위치 또는 시야에 애니메이션 효과를 주어 프로젝션 자체에 애니메이션 효과를 주도록 선택할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 타이밍 및 애니메이션 시스템에 대한 배경 정보는 [애니메이션 개요](animation-overview.md), [Storyboard 개요](storyboards-overview.md) 및 [Freezable 개체 개요](../advanced/freezable-objects-overview.md) 항목을 참조하세요.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 개체에 애니메이션 효과를 주려면 타임라인을 만들고 애니메이션(시간이 지남에 따른 일부 속성 값의 변경)을 정의한 다음 애니메이션을 적용할 속성을 지정합니다. 3D 장면의 모든 오브젝트는 자식이므로 <xref:System.Windows.Controls.Viewport3D>장면에 적용할 애니메이션의 대상 속성은 Viewport3D의 속성입니다.  
  
 모델이 제자리에서 비틀거리는 것처럼 보이게 만든다고 가정합니다. 모델에 a를 <xref:System.Windows.Media.Media3D.RotateTransform3D> 적용하고 한 벡터에서 다른 벡터로 회전 축에 애니메이션을 적용하도록 선택할 수 있습니다. 다음 코드 예제에서는 RotateTransform3D가 TransformGroup이 있는 모델에 적용된 여러 변환 중 하나라는 가정 하에 변환의 Rotation3D에 대한 Axis 속성에 Vector3DAnimation을 적용하는 방법을 보여 줍니다.  
  
 [!code-csharp[3doverview#3DOverview3DN1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>
## <a name="add-3d-content-to-the-window"></a>창에 3D 콘텐츠 추가  
 장면을 <xref:System.Windows.Media.Media3D.Model3DGroup>렌더링하려면 에 모델과 라이트를 추가한 <xref:System.Windows.Media.Media3D.Model3DGroup> 다음 <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> <xref:System.Windows.Media.Media3D.ModelVisual3D>을 의 로 설정합니다. <xref:System.Windows.Controls.Viewport3D>의 <xref:System.Windows.Media.Media3D.ModelVisual3D> 컬렉션에 <xref:System.Windows.Controls.Viewport3D.Children%2A> 을 추가합니다. 속성을 <xref:System.Windows.Controls.Viewport3D> 설정하여 카메라를 <xref:System.Windows.Controls.Viewport3D.Camera%2A> 추가합니다.  
  
 마지막으로 창에 <xref:System.Windows.Controls.Viewport3D> 를 추가합니다. 캔버스와 같은 레이아웃 요소의 콘텐츠로 포함된 경우 <xref:System.Windows.FrameworkElement.Height%2A> 해당 <xref:System.Windows.FrameworkElement.Width%2A> 요소와 속성을 설정하여 Viewport3D의 <xref:System.Windows.FrameworkElement>크기를 지정합니다(상속). <xref:System.Windows.Controls.Viewport3D>  
  
 [!code-xaml[hostingwpfusercontrolinwf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.Viewport3D>
- <xref:System.Windows.Media.Media3D.PerspectiveCamera>
- <xref:System.Windows.Media.Media3D.DirectionalLight>
- <xref:System.Windows.Media.Media3D.Material>
- [3D 변환 개요](3-d-transformations-overview.md)
- [WPF 3D 성능 최대화](maximize-wpf-3d-performance.md)
- [방법 주제](3-d-graphics-how-to-topics.md)
- [WPF에서 Shape 및 기본 그리기 개요](shapes-and-basic-drawing-in-wpf-overview.md)
- [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)
