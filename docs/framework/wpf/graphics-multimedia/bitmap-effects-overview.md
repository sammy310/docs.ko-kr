---
title: 비트맵 효과 개요
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: 4a5e73f21d4ce4988f56c139d13038dca902b5b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186998"
---
# <a name="bitmap-effects-overview"></a>비트맵 효과 개요
비트맵 효과를 사용하면 디자이너와 개발자가 렌더링된 WPF(Windows 프레젠테이션 파운데이션) 콘텐츠에 시각 효과를 적용할 수 있습니다. 예를 들어 비트맵 효과를 사용하면 이미지 <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> 나 버튼에 효과 나 흐림 효과를 쉽게 적용할 수 있습니다.  
  
> [!IMPORTANT]
> .NET Framework 4 이상에서는 <xref:System.Windows.Media.Effects.BitmapEffect> 클래스가 더 이상 사용되지 않습니다. 클래스를 <xref:System.Windows.Media.Effects.BitmapEffect> 사용하려고 하면 더 이상 사용되지 않는 예외가 표시됩니다. 클래스에 <xref:System.Windows.Media.Effects.BitmapEffect> 대한 사용되지 않는 대안은 <xref:System.Windows.Media.Effects.Effect> 클래스입니다. 대부분의 경우 클래스가 <xref:System.Windows.Media.Effects.Effect> 훨씬 빠릅니다.  

<a name="wpf_effects"></a>
## <a name="wpf-bitmap-effects"></a>WPF 비트맵 효과  
 비트맵 효과(개체)는<xref:System.Windows.Media.Effects.BitmapEffect> 간단한 픽셀 처리 작업입니다. 비트맵 효과는 입력으로 사용하여 <xref:System.Windows.Media.Imaging.BitmapSource> 흐림 또는 <xref:System.Windows.Media.Imaging.BitmapSource> 그림자 와 같은 효과를 적용한 후 새 효과를 생성합니다. 각 비트맵 효과는 <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> <xref:System.Windows.Media.Effects.BlurBitmapEffect>의 와 같은 필터링 속성을 제어할 수 있는 속성을 노출합니다.  
  
 특수한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]경우에서 효과는 <xref:System.Windows.Media.Visual> <xref:System.Windows.Controls.Button> 또는 와 <xref:System.Windows.Controls.TextBox>같은 라이브 개체의 속성으로 설정할 수 있습니다. 런타임에 픽셀 처리가 적용되고 렌더링됩니다. 이 경우 렌더링 시 a가 <xref:System.Windows.Media.Visual> 자동으로 <xref:System.Windows.Media.Imaging.BitmapSource> 해당 로 변환되고 <xref:System.Windows.Media.Effects.BitmapEffect>에 대한 입력으로 공급됩니다. 출력은 오브젝트의 <xref:System.Windows.Media.Visual> 기본 렌더링 동작을 대체합니다. 이 때문에 <xref:System.Windows.Media.Effects.BitmapEffect> 오브젝트는 효과를 적용할 때 시각적 개체에 대한 하드웨어 가속이 없는 소프트웨어에서만 렌더링하도록 시각적 개체를 강제로 적용합니다.  
  
- <xref:System.Windows.Media.Effects.BlurBitmapEffect>은 초점이 벗어난 것처럼 보이는 오브젝트를 시뮬레이션합니다.  
  
- <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect>개체 둘레에 색상의 후광을 만듭니다.  
  
- <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>오브젝트 뒤에 그림자를 만듭니다.  
  
- <xref:System.Windows.Media.Effects.BevelBitmapEffect>지정된 곡선에 따라 이미지의 표면을 올리는 경사를 만듭니다.  
  
- <xref:System.Windows.Media.Effects.EmbossBitmapEffect>인공 광원에서 <xref:System.Windows.Media.Visual> 깊이와 질감의 인상을 주기 위해 a의 범프 매핑을 만듭니다.  
  
> [!NOTE]
> WPF 비트맵 효과는 소프트웨어 모드에서 렌더링됩니다. 효과를 적용하는 모든 개체도 소프트웨어에서 렌더링됩니다. 큰 시각적 개체에 비트맵 효과를 사용하거나 비트맵 효과의 속성에 애니메이션 효과를 줄 때 성능이 가장 크게 저하됩니다. 따라서 여러분도 이러한 방식으로 비트맵 효과를 사용하지 않아야 하는 것은 물론, 다른 사용자들도 바람직한 경험을 얻을 수 있도록 철저히 테스트하고 주의해야 합니다.  
  
> [!NOTE]
> WPF 비트맵 효과는 부분 신뢰 실행을 지원하지 않습니다. 비트맵 효과를 사용하려면 애플리케이션에 완전 신뢰 권한이 있어야 합니다.  
  
<a name="applyeffects"></a>
## <a name="how-to-apply-an-effect"></a>효과를 적용하는 방법  
 <xref:System.Windows.Media.Effects.BitmapEffect>은 의 <xref:System.Windows.Media.Visual>속성입니다. 따라서 <xref:System.Windows.Controls.Button>에 <xref:System.Windows.Controls.Image> <xref:System.Windows.Media.DrawingVisual>대한 효과를 시각적 개체에 적용하는 <xref:System.Windows.UIElement>것만큼 이나 , 에 대한 효과를 쉽게 적용할 수 있습니다. <xref:System.Windows.UIElement.BitmapEffect%2A>개체를 사용하여 <xref:System.Windows.Media.Effects.BitmapEffectGroup> 여러 <xref:System.Windows.Media.Effects.BitmapEffect> 효과를 체인으로 설정할 수 있습니다.  
  
 다음 예제에서는 에서 <xref:System.Windows.Media.Effects.BitmapEffect> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 적용하는 방법을 보여 줍니다.  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 다음 예제에서는 <xref:System.Windows.Media.Effects.BitmapEffect> in 코드를 적용하는 방법을 보여 줍니다.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
> 또는 <xref:System.Windows.Media.Effects.BitmapEffect> <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Canvas>과 같은 레이아웃 컨테이너에 a를 적용하면 모든 자식 요소를 포함하여 요소가나 시각적 개체의 시각적 트리에 효과가 적용됩니다.  
  
<a name="customeffects"></a>
## <a name="creating-custom-effects"></a>사용자 지정 효과 만들기  
 또한 WPF는 관리되는 WPF 응용 프로그램에서 사용할 수 있는 사용자 지정 효과를 만들기 위해 관리되지 않는 인터페이스를 제공합니다. 사용자 지정 비트맵 효과를 만들기 위한 추가 참조 자료에 대해서는 [관리되지 않는 WPF 비트맵 효과](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh) 설명서를 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.Effects.BitmapEffectGroup>
- <xref:System.Windows.Media.Effects.BitmapEffectInput>
- <xref:System.Windows.Media.Effects.BitmapEffectCollection>
- [관리되지 않는 WPF 비트맵 효과](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)
- [이미징 개요](imaging-overview.md)
- [보안](../security-wpf.md)
- [WPF 그래픽 렌더링 개요](wpf-graphics-rendering-overview.md)
- [2D 그래픽 및 이미징](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
