---
title: 비트맵 효과 개요
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: e82a9596778a3c71aca6bdb8efcb9b3aa227cadb
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368222"
---
# <a name="bitmap-effects-overview"></a>비트맵 효과 개요
디자이너를 사용 하는 비트맵 효과 및 시각적 효과를 적용 하려면 개발자가 Windows Presentation Foundation (WPF)을 콘텐츠 렌더링 합니다. 예를 들어 비트맵 효과 사용 하면 쉽게 적용할 수는 <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> 효과나 흐림 효과를 이미지 또는 단추입니다.  
  
> [!IMPORTANT]
>  에 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 이상 버전에서는 <xref:System.Windows.Media.Effects.BitmapEffect> 클래스는 사용 되지 않습니다. 사용 하려는 경우는 <xref:System.Windows.Media.Effects.BitmapEffect> 클래스 사용 되지 않는 예외가 발생 합니다. 않는 대신 합니다 <xref:System.Windows.Media.Effects.BitmapEffect> 클래스는 <xref:System.Windows.Media.Effects.Effect> 클래스입니다. 대부분의 경우는 <xref:System.Windows.Media.Effects.Effect> 클래스는 훨씬 더 빠릅니다.  
  
  
  
<a name="wpf_effects"></a>   
## <a name="wpf-bitmap-effects"></a>WPF 비트맵 효과  
 비트맵 효과 (<xref:System.Windows.Media.Effects.BitmapEffect> 개체)는 간단한 픽셀 처리 작업입니다. 비트맵 효과 <xref:System.Windows.Media.Imaging.BitmapSource> 를 입력 하 고 새 생성 <xref:System.Windows.Media.Imaging.BitmapSource> 흐림 또는 그림자 같은 효과 적용 한 후입니다. 각 비트맵 효과 같은 필터링 속성을 제어할 수 있는 속성을 노출 <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> 의 <xref:System.Windows.Media.Effects.BlurBitmapEffect>합니다.  
  
 특수 한 경우에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 효과로 설정할 수 있습니다 속성에서 실시간 <xref:System.Windows.Media.Visual> 같은 개체를 <xref:System.Windows.Controls.Button> 또는 <xref:System.Windows.Controls.TextBox>합니다. 런타임에 픽셀 처리가 적용되고 렌더링됩니다. 렌더링 시이 경우에 <xref:System.Windows.Media.Visual> 자동으로 변환 되며 해당 <xref:System.Windows.Media.Imaging.BitmapSource> 해당 입력으로 공급 되 고는 <xref:System.Windows.Media.Effects.BitmapEffect>. 출력 대체는 <xref:System.Windows.Media.Visual> 개체의 기본 렌더링 동작 합니다. 이 인해 <xref:System.Windows.Media.Effects.BitmapEffect> 개체 강제로 시각적 개체가 렌더링 되도록 소프트웨어에만 즉, 하드웨어 가속이 없는 시각적 개체에 효과가 적용 될 때입니다.  
  
-   <xref:System.Windows.Media.Effects.BlurBitmapEffect> 포커스를 벗어난 표시 되는 개체를 시뮬레이션 합니다.  
  
-   <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect> 개체의 둘레에 색 후광을 만듭니다.  
  
-   <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> 개체 뒤에 그림자를 만듭니다.  
  
-   <xref:System.Windows.Media.Effects.BevelBitmapEffect> 지정된 된 곡선에 따라 이미지 표면을 올리는 3d 가장자리를 만듭니다.  
  
-   <xref:System.Windows.Media.Effects.EmbossBitmapEffect> 범프 매핑을 만듭니다는 <xref:System.Windows.Media.Visual> 인공 광원에서 깊이 및 질감 효과 제공 합니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 비트맵 효과는 소프트웨어 모드에서 렌더링됩니다. 효과를 적용하는 모든 개체도 소프트웨어에서 렌더링됩니다. 큰 시각적 개체에 비트맵 효과를 사용하거나 비트맵 효과의 속성에 애니메이션 효과를 줄 때 성능이 가장 크게 저하됩니다. 따라서 여러분도 이러한 방식으로 비트맵 효과를 사용하지 않아야 하는 것은 물론, 다른 사용자들도 바람직한 경험을 얻을 수 있도록 철저히 테스트하고 주의해야 합니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 비트맵 효과는 부분 신뢰 실행을 지원하지 않습니다. 비트맵 효과를 사용하려면 애플리케이션에 완전 신뢰 권한이 있어야 합니다.  
  
<a name="applyeffects"></a>   
## <a name="how-to-apply-an-effect"></a>효과를 적용하는 방법  
 <xref:System.Windows.Media.Effects.BitmapEffect> 가 <xref:System.Windows.Media.Visual>입니다. 와 같은 시각적 개체에 효과 따라서 적용을 <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>를 <xref:System.Windows.Media.DrawingVisual>, 또는 <xref:System.Windows.UIElement>, 속성을 설정 하기만 됩니다. <xref:System.Windows.UIElement.BitmapEffect%2A> single로 설정할 수 있습니다 <xref:System.Windows.Media.Effects.BitmapEffect> 개체나 여러 효과 사용 하 여 연결할 수는 <xref:System.Windows.Media.Effects.BitmapEffectGroup> 개체입니다.  
  
 다음 예제에서는 적용 하는 방법에 설명 된 <xref:System.Windows.Media.Effects.BitmapEffect> 에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 다음 예제에 적용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Media.Effects.BitmapEffect> 코드에서입니다.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
>  경우는 <xref:System.Windows.Media.Effects.BitmapEffect> 와 같은 레이아웃 컨테이너에 적용 됩니다 <xref:System.Windows.Controls.DockPanel> 또는 <xref:System.Windows.Controls.Canvas>, 효과가 요소 또는 시각적 개체를 모든 해당 자식 요소를 포함 하 여 시각적 트리에 적용 됩니다.  
  
<a name="customeffects"></a>   
## <a name="creating-custom-effects"></a>사용자 지정 효과 만들기  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 또한 관리되는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에서 사용할 수 있는 사용자 지정 효과를 만들기 위한 관리되지 않는 인터페이스를 제공합니다. 사용자 지정 비트맵 효과를 만들기 위한 추가 참조 자료에 대해서는 [관리되지 않는 WPF 비트맵 효과](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh) 설명서를 참조하세요.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Media.Effects.BitmapEffectGroup>
- <xref:System.Windows.Media.Effects.BitmapEffectInput>
- <xref:System.Windows.Media.Effects.BitmapEffectCollection>
- [관리 되지 않는 WPF 비트맵 효과](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)
- [이미징 개요](imaging-overview.md)
- [보안](../security-wpf.md)
- [WPF 그래픽 렌더링 개요](wpf-graphics-rendering-overview.md)
- [2차원 그래픽 및 이미징](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
