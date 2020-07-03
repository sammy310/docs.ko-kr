---
title: 3D 그래픽 개요
description: WPF (Windows Presentation Foundation)에서 3D 그래픽을 사용 하 여 태그와 절차적 코드 모두에서 3D 그래픽을 그리거나, 변환 하 고, 애니메이션 효과를 적용 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D graphics [WPF]
- graphics [WPF], 3D
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
ms.openlocfilehash: 51da6a1ed6d5e98b99c64ee23be52f7b2385897f
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853874"
---
# <a name="3d-graphics-overview"></a>3D 그래픽 개요
<a name="introduction"></a>의 3D 기능을 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 사용 하면 개발자는 태그와 절차적 코드 모두에서 3d 그래픽을 그리거나, 변환 하 고, 애니메이션 효과를 적용할 수 있습니다. 개발자는 2D 및 3D 그래픽을 결합 하 여 다양 한 컨트롤을 만들거나 복잡 한 데이터 그림을 제공 하거나 응용 프로그램 인터페이스의 사용자 환경을 향상 시킬 수 있습니다. 의 3D 지원은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 완전 한 기능을 갖춘 게임 개발 플랫폼을 제공 하도록 설계 되지 않았습니다. 이 항목에서는 그래픽 시스템의 3D 기능에 대해 간략하게 설명 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .  

<a name="threed_in_2d"></a>
## <a name="3d-in-a-2d-container"></a>2D 컨테이너의 3D  
 의 3D 그래픽 콘텐츠는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Viewport3D> 2 차원 요소 구조에 참여할 수 있는 요소에 캡슐화 됩니다. 그래픽 시스템은 <xref:System.Windows.Controls.Viewport3D> 의 다른 여러 요소 처럼 2 차원 시각적 요소로 처리 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 합니다. <xref:System.Windows.Controls.Viewport3D>3 차원 장면으로 창 (뷰포트)으로 작동 합니다. 보다 정확 하 게, 3D 장면이 프로젝션 되는 표면입니다.  
  
 기존 2D 응용 프로그램에서 <xref:System.Windows.Controls.Viewport3D> 표 또는 Canvas와 같은 다른 컨테이너 요소를 사용 하 여를 사용 합니다.  <xref:System.Windows.Controls.Viewport3D>동일한 장면 그래프에서 다른 2d 그리기 개체와 함께를 사용할 수 있지만 내에서 2d 및 3d 개체를 상호 침투 시킬 수 없습니다 <xref:System.Windows.Controls.Viewport3D> .  이 항목에서는 내에서 3D 그래픽을 그리는 방법에 대해 집중적으로 설명 <xref:System.Windows.Controls.Viewport3D> 합니다.  
  
<a name="coord_space"></a>
## <a name="3d-coordinate-space"></a>3D 좌표 공간  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]2d 그래픽용 좌표계는 렌더링 영역 (일반적으로 화면)의 왼쪽 위에서 원점을 찾습니다. 2D 시스템에서 양의 x-축 값은 오른쪽으로 진행 되 고 양의 y-축 값은 아래로 진행 됩니다.  그러나 3D 좌표계에서는 원점이 렌더링 영역의 가운데에 위치 하 고 양의 x 축 값은 오른쪽으로 진행 되 고 양의 y 축 값은 위쪽으로 진행 되 고 양의 z-축 값은 원본에서 뷰어로 계속 진행 됩니다.  
  
 ![좌표계](./media/coordsystem-1.png "CoordSystem-1")  
기본 2D 및 3D 좌표계 표현  
  
 이러한 축으로 정의 되는 공간은의 3D 개체에 대 한 고정 참조 프레임입니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] . 이 공간에서 모델을 빌드하고 이를 보기 위한 광원과 카메라를 만들 때는 변환 적용 시 각 모델에 대해 만드는 로컬 참조 프레임을 이 고정 참조 프레임 또는 "월드 공간"과 구분하면 유용합니다. 또한 월드 공간의 개체는 광원 및 카메라 설정에 따라 완전히 다르게 보이거나 전혀 보이지 않을 수 있지만 카메라의 위치는 월드 공간에서 개체의 위치를 변경하지 않습니다.  
  
<a name="cameras"></a>
## <a name="cameras-and-projections"></a>카메라 및 프로젝션  
 2D에서 작업 하는 개발자는 2 차원 화면에서 그리기 기본 형식을 지정 하는 데 익숙할 것입니다. 3D 장면을 만들 때 3D 개체의 2D 표현을 생성 하는 것을 기억해 야 합니다. 3D 장면은 보는이의 관점에 따라 다르게 보이므로 해당 시점을 지정 해야 합니다. 클래스를 사용 하 여 <xref:System.Windows.Media.Media3D.Camera> 3d 장면에 대해이 시점을 지정할 수 있습니다.  
  
 3D 장면이 2D 화면에 표시 되는 방식을 이해 하는 또 다른 방법은 장면을 보기 화면에 대 한 프로젝션으로 설명 하는 것입니다. 에서는 <xref:System.Windows.Media.Media3D.ProjectionCamera> 다양 한 프로젝션 및 해당 속성을 지정 하 여 보는이에서 3d 모델을 인식 하는 방법을 변경할 수 있습니다. 는 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 장면을 단축 하는 프로젝션을 지정 합니다.  즉,는 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 소실점 관점을 제공 합니다.  장면 좌표 공간에서의 카메라 위치, 카메라의 방향 및 시야, 장면의 "위쪽" 방향을 정의하는 벡터를 지정할 수 있습니다. 다음 다이어그램에서는 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 의 프로젝션을 보여 줍니다.  
  
 <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A>의 및 <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> 속성은 <xref:System.Windows.Media.Media3D.ProjectionCamera> 카메라의 프로젝션 범위를 제한 합니다. 카메라는 장면의 어느 위치에나 배치될 수 있으므로 카메라가 실제로 모델 내 또는 모델에 매우 가깝게 배치될 수 있으며 이로 인해 개체를 제대로 구별하기가 어려워집니다.  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A>카메라에서 개체를 그리지 않는 최소 거리를 지정할 수 있습니다.  반대로를 <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> 사용 하면 개체를 그리지 않을 때까지 카메라에서 거리를 지정할 수 있습니다. 이렇게 하면 개체가 너무 멀리 떨어져 있을 때 장면에 포함 되지 않습니다.  
  
 ![카메라 설정](./media/coordsystem-6.png "CoordSystem-6")  
카메라 위치  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera>3D 모델의 직교 프로젝션을 2D 시각적 화면으로 지정 합니다. 다른 카메라와 마찬가지로 이는 위치, 보기 방향 및 "위쪽" 방향을 지정합니다. 와 달리 <xref:System.Windows.Media.Media3D.PerspectiveCamera>그러나 <xref:System.Windows.Media.Media3D.OrthographicCamera> 원근 단축법을 포함 하지 않는 프로젝션을 설명 합니다. 즉,는 해당 측면이 <xref:System.Windows.Media.Media3D.OrthographicCamera> 카메라의 지점에서 만나는 것이 아니라 병렬 인 보기 상자를 설명 합니다. 다음 그림에서는 및을 사용 하 여 볼 때와 동일한 모델을 보여 줍니다 <xref:System.Windows.Media.Media3D.PerspectiveCamera> <xref:System.Windows.Media.Media3D.OrthographicCamera> .  
  
 ![직교 및 원근 프로젝션](./media/camera-projections4.png "Camera_projections4")  
원근 및 직교 프로젝션  
  
 다음 코드에서는 일반적인 카메라 설정을 보여 줍니다.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>
## <a name="model-and-mesh-primitives"></a>모델 및 메시 기본 형식  
  
 <xref:System.Windows.Media.Media3D.Model3D>는 일반 3D 개체를 나타내는 추상 기본 클래스입니다. 3D 장면을 만들려면 보려는 개체가 필요 하며, 장면 그래프를 구성 하는 개체는에서 파생 <xref:System.Windows.Media.Media3D.Model3D> 됩니다. 현재는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 로 모델링 기 하 도형을 지원 합니다 <xref:System.Windows.Media.Media3D.GeometryModel3D> . <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A>이 모델의 속성은 메시 기본 형식을 사용 합니다.  
  
 모델을 빌드하려면 먼저 기본 형식 또는 메시를 빌드합니다. 3D 기본 형식은 단일 3D 엔터티를 형성 하는 꼭 짓 점 컬렉션입니다. 대부분의 3D 시스템은 가장 간단한 폐쇄형 그림 (세 개의 꼭 짓 점에 의해 정의 된 삼각형)에서 모델링 된 기본 형식을 제공 합니다.  삼각형의 세 점은 같은 평면에 있으므로 메시라는 보다 복잡한 도형을 모델링하기 위해 계속해서 삼각형을 추가할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]3d 시스템은 현재 <xref:System.Windows.Media.Media3D.MeshGeometry3D> 클래스를 제공 합니다 .이 클래스를 사용 하면 모든 기 하 도형을 지정할 수 있으며, 현재는 구 및 입방 형과 같은 미리 정의 된 3d 기본 형식을 지원 하지 않습니다. <xref:System.Windows.Media.Media3D.MeshGeometry3D>삼각형 꼭 짓 점 목록을 해당 속성으로 지정 하 여 만들기를 시작 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 합니다. 각 꼭 짓 점은로 지정 됩니다 <xref:System.Windows.Media.Media3D.Point3D> .  에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 이 속성은 각 꼭 짓 점의 좌표를 나타내는 세로 그룹화 된 숫자 목록으로 지정 합니다. 해당 기 하 도형에 따라 메시는 많은 삼각형으로 구성 될 수 있으며, 일부는 동일한 모퉁이 (꼭 짓 점)를 공유 합니다. 메시를 올바르게 그리려면 어떤 삼각형에 어떤 꼭짓점이 공유되는지에 대한 정보를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 제공해야 합니다. 속성을 사용 하 여 삼각형 인덱스 목록을 지정 하 여이 정보를 제공 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> 합니다. 이 목록에서는 목록에 지정 된 점이 삼각형을 결정 하는 순서를 지정 합니다 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> .  
  
 [!code-xaml[basic3d#Basic3DXAML3DN3](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 위의 예제에서 목록에는 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 큐브 모양의 메시를 정의 하는 8 개의 꼭지점이 지정 되어 있습니다. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>속성은 3 개 인덱스의 12 개 그룹 목록을 지정 합니다.  목록의 각 숫자는 목록의 오프셋을 참조 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 합니다.  예를 들어 목록에 지정 된 처음 3 개의 꼭 짓 점은 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> (1, 1, 0), (0, 1, 0) 및 (0, 0, 0)입니다. 목록에서 지정 하는 처음 세 인덱스는 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> 0, 2, 1입니다 .이는 목록의 첫 번째, 세 번째 및 두 번째 점에 해당 합니다 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> . 그 결과 큐브 모델을 구성하는 첫 번째 삼각형은 (1,1,0)에서 (0,1,0) 및 (0,0,0)으로 이어지고 나머지 11개의 삼각형도 이와 비슷하게 결정됩니다.  
  
 및 속성에 대 한 값을 지정 하 여 모델을 계속 정의할 수 있습니다 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> .  모델의 표면을 렌더링하려면 지정된 임의의 삼각형에서 해당 표면이 어느 방향을 바라보고 있는지에 대한 정보를 그래픽 시스템에 제공해야 합니다. 그래픽 시스템은 이 정보를 사용하여 모델에 대한 조명 계산을 수행할 수 있습니다. 즉, 광원 쪽 표면이 광원 반대쪽 표면보다 밝게 나타납니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 위치 좌표를 사용하여 기본 법선 벡터를 결정할 수 있지만 다른 법선 벡터를 지정하여 곡선 표면의 모양을 대략적으로 나타낼 수도 있습니다.  
  
 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>속성은의 컬렉션을 지정 하는 컬렉션을 지정 합니다 .이 컬렉션은 <xref:System.Windows.Point> 질감을 망상의 꼭 짓 점에 그리는 방법을 결정 하는 좌표를 매핑하는 방법을 그래픽 시스템에 알려 줍니다. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>는 0과 1 사이의 값 (포함)으로 지정 됩니다.  <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>속성과 마찬가지로 그래픽 시스템은 기본 질감 좌표를 계산할 수 있지만 반복 패턴의 일부를 포함 하는 질감의 매핑을 제어 하도록 다른 질감 좌표를 설정 하도록 선택할 수 있습니다 (예:). 질감 좌표에 대한 자세한 내용은 다음 항목 또는 Managed Direct3D SDK를 참조하세요.  
  
 다음 예제에서는 프로시저 코드로 큐브 모델의 한 면을 만드는 방법을 보여 줍니다. 전체 큐브를 단일 GeometryModel3D 그릴 수 있습니다. 이 예에서는 나중에 각 면에 별도의 질감을 적용 하기 위해 큐브의 표면을 고유한 모델로 그립니다.  
  
 [!code-csharp[3doverview#3DOverview3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>'
## <a name="applying-materials-to-the-model"></a>모델에 재질 적용  
  
 메시가 3차원 개체로 보이도록 만들려면 카메라로 비추고 프로젝션할 수 있도록 해당 꼭짓점과 삼각형으로 정의된 표면에 질감을 적용해야 합니다. 2D에서는 클래스를 사용 하 여 <xref:System.Windows.Media.Brush> 색, 패턴, 그라데이션 또는 기타 시각적 콘텐츠를 화면 영역에 적용 합니다.  그러나 3D 개체의 모양은 색 또는 패턴이 적용 되는 것이 아니라 조명 모델의 기능입니다. 실제 개체는 표면의 품질에 따라 빛을 다르게 반사합니다. 광택이 나거나 빛나는 표면은 거칠거나 윤기 없는 표면과 다르게 보이며 어떤 개체는 빛을 흡수하는 것처럼 보이는 반면 다른 개체는 빛이 납니다. 2D 개체에 적용할 수 있는 동일한 모든 브러시를 3D 개체에 적용할 수 있지만 직접 적용할 수는 없습니다.  
  
 모델 표면의 특성을 정의 하기 위해에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 추상 클래스를 사용 합니다 <xref:System.Windows.Media.Media3D.Material> . Material의 구체적 하위 클래스는 모델 표면의 일부 모양 특성을 결정하며 이들 각각은 SolidColorBrush, TileBrush 또는 VisualBrush를 전달할 수 있는 Brush 속성도 제공합니다.  
  
- <xref:System.Windows.Media.Media3D.DiffuseMaterial>모델이 lit 확산 모델에 브러시가 적용 되도록 지정 합니다. DiffuseMaterial를 사용 하는 것은 2D 모델에서 직접 브러시를 사용 하는 것과 비슷합니다. 모델 표면에는 빛나는 것 처럼 빛이 반영 되지 않습니다.  
  
- <xref:System.Windows.Media.Media3D.SpecularMaterial>모델의 표면이 하드 또는 반짝이는 것 처럼 브러시를 모델에 적용 하 여 하이라이트를 반영할 수 있도록 지정 합니다. 질감에서이 반사 품질을 제안 하는 정도 또는 속성의 값을 지정 하 여 "빛"을 설정할 수 있습니다 <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A> .  
  
- <xref:System.Windows.Media.Media3D.EmissiveMaterial>모델이 브러시 색과 같은 빛을 내보내는 것 처럼 질감이 적용 되도록 지정할 수 있습니다. 그러나 이로 인해 모델이 광원이 되는 것은 아니며 DiffuseMaterial 또는 SpecularMaterial을 사용하여 질감을 표현할 때와는 다른 방식으로 섀도잉에 참여합니다.  
  
 성능 향상을 위해 backfaces <xref:System.Windows.Media.Media3D.GeometryModel3D> (카메라에서 모델의 반대쪽에 있기 때문에 표시 되지 않는 얼굴)는 장면에서 추출 됩니다.  <xref:System.Windows.Media.Media3D.Material>평면과 같은 모델의 백 면에 적용할를 지정 하려면 모델의 속성을 설정 <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> 합니다.  
  
 빛이 나거나 반사되는 효과와 같은 일부 표면 품질을 얻으려면 모델에 여러 개의 서로 다른 브러시를 연속으로 적용해야 할 수 있습니다. 클래스를 사용 하 여 여러 자료를 적용 하 고 재사용할 수 있습니다 <xref:System.Windows.Media.Media3D.MaterialGroup> . MaterialGroup의 자식이 맨 먼저 적용되어 여러 렌더링 패스에서 지속됩니다.  
  
 다음 코드 예에서는 단색 및 그리기를 3D 모델에 브러시로 적용 하는 방법을 보여 줍니다.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN5](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  ' [!code-xaml[3doverview#3DOverview3DN9](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
 ' [!code-csharp[3doverview#3DOverview3DN8](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
  [!code-vb[3doverview#3DOverview3DN8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>
## <a name="illuminating-the-scene"></a>장면 비추기  
 3D 그래픽의 조명은 실제 세계에서 조명 효과를 제공 합니다. 즉, 표면을 표시 합니다. 보다 정확히 말해 광원은 프로젝션에 포함될 장면의 부분을 결정합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 광원 개체는 다양한 명암 효과를 만들며 여러 실제 광원의 동작을 기반으로 모델링됩니다. 장면에 하나 이상의 조명을 포함 하거나 모델이 표시 되지 않습니다.  
  
 다음 광원은 기본 클래스에서 파생 됩니다 <xref:System.Windows.Media.Media3D.Light> .  
  
- <xref:System.Windows.Media.Media3D.AmbientLight>: 위치 또는 방향에 관계 없이 모든 개체를 균일 하 게 비추는 주변 조명을 제공 합니다.  
  
- <xref:System.Windows.Media.Media3D.DirectionalLight>: 원거리 광원 처럼 비춥니다.  방향성 광원에는 <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A> Vector3D으로 지정 되었지만 지정 된 위치는 없습니다.  
  
- <xref:System.Windows.Media.Media3D.PointLight>: 주변 광원 처럼 비춥니다. PointLight는 위치가 있으며 해당 위치에서 빛을 발합니다. 장면의 개체는 광원과 관련된 해당 위치 및 거리에 따라 비춰집니다. <xref:System.Windows.Media.Media3D.PointLightBase>모델에 <xref:System.Windows.Media.Media3D.PointLightBase.Range%2A> 조명이 표시 되지 않는 거리를 결정 하는 속성을 노출 합니다. PointLight도 감쇠 속성을 노출 하 여 거리에 대 한 조명의 강도가 저하 되는 방법을 결정 합니다. 광원 감쇠에 대해 상수, 선형 또는 정방형 보간을 지정할 수 있습니다.  
  
- <xref:System.Windows.Media.Media3D.SpotLight>:에서 상속 <xref:System.Windows.Media.Media3D.PointLight> 됩니다. SpotLight는 PointLight와 유사하게 비추며 위치와 방향이 모두 있습니다. 이러한 프로젝트는 및 속성으로 설정 된 원뿔 모양 영역에서도로 지정 된 빛을 프로젝션 <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A> 합니다.  
  
 광원은 <xref:System.Windows.Media.Media3D.Model3D> 개체 이므로 위치, 색, 방향 및 범위를 비롯 한 밝은 속성을 변환 하 고 애니메이션 효과를 적용할 수 있습니다.  
  
 [!code-xaml[hittest3d#HitTest3D3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>
## <a name="transforming-models"></a>모델 변환  
 모델을 만들 때 모델에는 장면에서의 특정 위치가 지정됩니다. 장면에서 이러한 모델을 이동하거나, 회전하거나, 크기를 변경하기 위해 모델 자체를 정의하는 꼭짓점을 변경하는 것은 비효율적입니다.  대신 2D에서와 마찬가지로 모델에 변환을 적용 합니다.  
  
 각 모델 개체에는 <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> 모델을 이동 하거나, 이동 하거나, 크기를 조정할 수 있는 속성이 있습니다.  변환을 적용할 때는 변환에 의해 지정된 벡터 또는 값이 무엇이든 실제적으로 모델의 모든 점을 오프셋합니다. 즉, 모델이 정의된 좌표 공간("모델 공간")은 변환하지만 장면 전체("월드 공간")의 좌표계에서 모델의 기하 도형을 구성하는 값은 변경하지 않습니다.  
  
 모델 변환에 대 한 자세한 내용은 [3D 변환 개요](3-d-transformations-overview.md)를 참조 하세요.  
  
<a name="animations"></a>
## <a name="animating-models"></a>모델에 애니메이션 효과 주기  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]3d 구현은 2d 그래픽과 동일한 타이밍 및 애니메이션 시스템에 참여 합니다. 즉, 3D 장면에 애니메이션 효과를 주려면 해당 모델의 속성에 애니메이션 효과를 적용 합니다. 기본 형식의 속성에 직접 애니메이션 효과를 줄 수도 있지만 일반적으로 모델의 위치나 모양을 변경하는 변환에 애니메이션 효과를 주는 것이 보다 쉽습니다. 변환은 개체 뿐만 아니라 개별 모델에 적용 될 수 있기 때문에 <xref:System.Windows.Media.Media3D.Model3DGroup> Model3DGroup의 자식에는 하나의 애니메이션 집합을 적용 하 고 다른 애니메이션 집합은 자식 개체 그룹에 적용할 수 있습니다. 장면의 조명 속성에 애니메이션 효과를 주어 다양한 시각적 효과를 얻을 수도 있습니다. 마지막으로 카메라 위치 또는 시야에 애니메이션 효과를 주어 프로젝션 자체에 애니메이션 효과를 주도록 선택할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 타이밍 및 애니메이션 시스템에 대한 배경 정보는 [애니메이션 개요](animation-overview.md), [Storyboard 개요](storyboards-overview.md) 및 [Freezable 개체 개요](../advanced/freezable-objects-overview.md) 항목을 참조하세요.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 개체에 애니메이션 효과를 주려면 타임라인을 만들고 애니메이션(시간이 지남에 따른 일부 속성 값의 변경)을 정의한 다음 애니메이션을 적용할 속성을 지정합니다. 3D 장면의 모든 개체는의 자식 이므로 <xref:System.Windows.Controls.Viewport3D> 장면에 적용 하려는 애니메이션의 대상이 되는 속성은 Viewport3D의 속성입니다.  
  
 모델이 제자리에서 비틀거리는 것처럼 보이게 만든다고 가정합니다. 을 <xref:System.Windows.Media.Media3D.RotateTransform3D> 모델에 적용 하 고 한 벡터에서 다른 벡터로 회전 축에 애니메이션 효과를 주는 효과를 선택할 수 있습니다. 다음 코드 예제에서는 RotateTransform3D가 TransformGroup이 있는 모델에 적용된 여러 변환 중 하나라는 가정 하에 변환의 Rotation3D에 대한 Axis 속성에 Vector3DAnimation을 적용하는 방법을 보여 줍니다.  
  
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
 장면을 렌더링 하려면에 모델 및 조명을 추가 하 고를 <xref:System.Windows.Media.Media3D.Model3DGroup> 의로 설정 합니다 <xref:System.Windows.Media.Media3D.Model3DGroup> <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> <xref:System.Windows.Media.Media3D.ModelVisual3D> . 의 컬렉션에를 추가 합니다 <xref:System.Windows.Media.Media3D.ModelVisual3D> <xref:System.Windows.Controls.Viewport3D.Children%2A> <xref:System.Windows.Controls.Viewport3D> . 해당 속성을 설정 하 여에 카메라를 추가 합니다 <xref:System.Windows.Controls.Viewport3D> <xref:System.Windows.Controls.Viewport3D.Camera%2A> .  
  
 마지막으로 창에를 추가 합니다 <xref:System.Windows.Controls.Viewport3D> . <xref:System.Windows.Controls.Viewport3D>가 Canvas와 같은 레이아웃 요소의 콘텐츠로 포함 된 경우 <xref:System.Windows.FrameworkElement.Height%2A> 및 <xref:System.Windows.FrameworkElement.Width%2A> 속성 (에서 상속)을 설정 하 여 Viewport3D의 크기를 지정 합니다 <xref:System.Windows.FrameworkElement> .  
  
 [!code-xaml[hostingwpfusercontrolinwf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Controls.Viewport3D>
- <xref:System.Windows.Media.Media3D.PerspectiveCamera>
- <xref:System.Windows.Media.Media3D.DirectionalLight>
- <xref:System.Windows.Media.Media3D.Material>
- [3D 변환 개요](3-d-transformations-overview.md)
- [WPF 3D 성능 최대화](maximize-wpf-3d-performance.md)
- [방법 도움말 항목](3-d-graphics-how-to-topics.md)
- [WPF에서 Shape 및 기본 그리기 개요](shapes-and-basic-drawing-in-wpf-overview.md)
- [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)
