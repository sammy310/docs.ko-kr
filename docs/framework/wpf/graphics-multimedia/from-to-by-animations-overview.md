---
title: 애니메이션 에 의한 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
ms.openlocfilehash: 135f01823d374b30f8d4d41762d2267a254f98c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186458"
---
# <a name="fromtoby-animations-overview"></a>From/To/By 애니메이션 개요
이 항목에서는 From/To/By 애니메이션을 사용하여 종속성 속성에 애니메이션 효과를 적용하는 방법을 설명합니다. From/To/By 애니메이션은 두 값 간에 변환을 생성합니다.  
  
<a name="prereq"></a>
## <a name="prerequisites"></a>전제 조건  
 이 항목을 이해하려면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션 기능에 대해 잘 알고 있어야 합니다. 애니메이션 기능에 대한 소개는 [애니메이션 개요를](animation-overview.md)참조하십시오.  
  
<a name="whatisanimation"></a>
## <a name="what-is-a-fromtoby-animation"></a>From/To/By 애니메이션이란?  
 시작/시작/별 애니메이션은 시작 <xref:System.Windows.Media.Animation.AnimationTimeline> 값과 끝 값 사이의 전환을 만드는 유형입니다. 전환이 완료되는 데 걸리는 시간은 해당 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 애니메이션의 시간에 따라 결정됩니다.  
  
 in 태그 및 코드를 사용하거나 코드에서 메서드를 <xref:System.Windows.Media.Animation.Storyboard> 사용하여 속성에 받는 시간/받는/ 별 애니메이션을 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 적용할 수 있습니다. 또한 From/To/By 애니메이션을 사용하여 하나 <xref:System.Windows.Media.Animation.AnimationClock> 이상의 속성에 만들고 적용할 수 있습니다. 애니메이션 적용 방법에 대한 자세한 내용은 [속성 애니메이션 기술 개요를](property-animation-techniques-overview.md)참조하십시오.  
  
 From/To/By 애니메이션은 2개 이하의 대상 값을 가질 수 있습니다. 2개를 초과하는 대상 값을 갖는 애니메이션이 필요한 경우 키 프레임 애니메이션을 사용합니다. 키 프레임 애니메이션은 키 [프레임 애니메이션 개요에 설명되어 있습니다.](key-frame-animations-overview.md)  
  
<a name="animation_types"></a>
## <a name="fromtoby-animation-types"></a>From/To/By 애니메이션 형식  
 애니메이션은 속성 값을 생성하므로 속성 형식이 다르면 애니메이션 형식도 다릅니다. 요소의 속성과 같이 <xref:System.Double> <xref:System.Windows.FrameworkElement.Width%2A> 를 사용하는 속성을 애니메이션하려면 값을 생성하는 애니메이션을 <xref:System.Double> 사용합니다. <xref:System.Windows.Point>을 사용하는 속성을 애니메이션하려면 <xref:System.Windows.Point> 값을 생성하는 애니메이션 등을 사용합니다.  
  
 From/To/By 애니메이션 클래스는 <xref:System.Windows.Media.Animation> 네임스페이스에 속하며 다음 명명 규칙을 사용합니다.  
  
 * \<유형>*`Animation`  
  
 유형>클래스가 애니메이션하는 값의 유형입니다. * \<*  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 다음 From/To/By 애니메이션 클래스를 제공합니다.  
  
|속성 형식|해당 From/To/By 애니메이션 클래스|  
|-------------------|------------------------------------------------|  
|<xref:System.Byte>|<xref:System.Windows.Media.Animation.ByteAnimation>|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|  
|<xref:System.Decimal>|<xref:System.Windows.Media.Animation.DecimalAnimation>|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|  
|<xref:System.Int16>|<xref:System.Windows.Media.Animation.Int16Animation>|  
|<xref:System.Int32>|<xref:System.Windows.Media.Animation.Int32Animation>|  
|<xref:System.Int64>|<xref:System.Windows.Media.Animation.Int64Animation>|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|  
|<xref:System.Windows.Media.Media3D.Quaternion>|<xref:System.Windows.Media.Animation.QuaternionAnimation>|  
|<xref:System.Windows.Rect>|<xref:System.Windows.Media.Animation.RectAnimation>|  
|<xref:System.Windows.Media.Media3D.Rotation3D>|<xref:System.Windows.Media.Animation.Rotation3DAnimation>|  
|<xref:System.Single>|<xref:System.Windows.Media.Animation.SingleAnimation>|  
|<xref:System.Windows.Size>|<xref:System.Windows.Media.Animation.SizeAnimation>|  
|<xref:System.Windows.Thickness>|<xref:System.Windows.Media.Animation.ThicknessAnimation>|  
|<xref:System.Windows.Media.Media3D.Vector3D>|<xref:System.Windows.Media.Animation.Vector3DAnimation>|  
|<xref:System.Windows.Vector>|<xref:System.Windows.Media.Animation.VectorAnimation>|  
  
<a name="anim_values"></a>
## <a name="target-values"></a>대상 값  
 From/To/By 애니메이션은 두 대상 값 간에 변환을 생성합니다. 시작 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 값(속성을 사용하여 설정)과 끝 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 값(속성을 사용하여 설정)을 지정하는 것이 일반적입니다. 그러나 시작 값, 대상 값 또는 오프셋 값만 지정할 수도 있습니다. 이러한 경우 애니메이션은 애니메이션 효과를 적용할 속성에서 누락된 대상 값을 가져옵니다. 다음 목록에서는 애니메이션의 대상 값을 지정하는 여러 가지 방법을 설명합니다.  
  
- **시작 값**  
  
     애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 시작 값을 명시적으로 지정하려는 경우 속성을 사용합니다. 속성 자체를 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 사용하거나 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 또는 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성과 함께 사용할 수 있습니다. <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성만 지정하면 애니메이션이 해당 값에서 애니메이션 속성의 기준 값으로 전환됩니다.  
  
- **끝 값**  
  
     애니메이션의 끝 값을 지정하려면 해당 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성을 사용합니다. <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성을 단독으로 사용하는 경우 애니메이션은 애니메이션중인 속성또는 동일한 속성에 적용되는 다른 애니메이션의 출력에서 시작 값을 가져옵니다. 속성과 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 함께 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성을 사용하여 애니메이션의 시작 및 끝 값을 명시적으로 지정할 수 있습니다.  
  
- **오프셋 값**  
  
     이 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 사용하면 애니메이션에 대한 명시적 시작 또는 끝 값 대신 오프셋을 지정할 수 있습니다. 애니메이션의 속성은 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 애니메이션이 해당 기간 동안 값을 변경하는 정도를 지정합니다. 이 속성은 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 단독으로 또는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성과 함께 사용할 수 있습니다. <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성만 지정하면 애니메이션이 속성의 기준 값 또는 다른 애니메이션의 출력에 오프셋 값을 추가합니다.  
  
<a name="examples"></a>
## <a name="using-fromtoby-values"></a>From/To/By 값 사용  
 다음 섹션에서는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>에서 및 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 함께 또는 별도로 사용하는 방법을 설명합니다.  
  
 이 섹션의 예제에서는 각각 <xref:System.Windows.Media.Animation.DoubleAnimation>에서 부터/받는/By 애니메이션의 형식인 을 사용하여 <xref:System.Windows.FrameworkElement.Width%2A> 10개의 장치 독립 픽셀 높이와 100개의 장치 독립 픽셀 너비의 <xref:System.Windows.Shapes.Rectangle> 속성을 애니메이션합니다.  
  
 각 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>에서 를 사용 하지만 , 받는 여자, 받는 것 및 모든 의 속성/받는 것/By 애니메이션 동일 하 게 작동 합니다. 이러한 각 예제에서는 <xref:System.Windows.Media.Animation.Storyboard>를 사용하지만 다른 방법으로 부터/받는/별 애니메이션을 사용할 수 있습니다. 자세한 내용은 [속성 애니메이션 기술 개요를](property-animation-techniques-overview.md)참조하십시오.  
  
### <a name="fromto"></a>시작/끝  
 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 값을 함께 설정하면 애니메이션이 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성에 의해 지정된 값에서 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성에 의해 지정된 값으로 진행됩니다.  
  
 다음 예제는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 50의 <xref:System.Windows.Media.Animation.DoubleAnimation> 속성을 설정하고 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 해당 속성을 300으로 설정합니다. 결과적으로, 의 <xref:System.Windows.FrameworkElement.Width%2A> 50에서 300 <xref:System.Windows.Shapes.Rectangle> 애니메이션.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>수행할 작업  
 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성만 설정하면 애니메이션이 애니메이션 속성의 기본 값또는 이전에 동일한 속성에 적용된 구성 애니메이션의 출력에서 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성에서 지정한 값으로 진행됩니다.  
  
 ("애니메이션 구성"은 핸드오프 동작을 <xref:System.Windows.Media.Animation.ClockState.Active> 사용하여 현재 애니메이션을 적용했을 때 여전히 적용되는 동일한 속성에 이전에 적용된 애니메이션 또는 <xref:System.Windows.Media.Animation.ClockState.Filling> 애니메이션을 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> 나타냅니다.  
  
 다음 예제는 의 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성만 <xref:System.Windows.Media.Animation.DoubleAnimation> 300으로 설정합니다. 시작 값이 지정되지 않으므로 <xref:System.Windows.Media.Animation.DoubleAnimation> <xref:System.Windows.FrameworkElement.Width%2A> 속성의 기본 값(100)을 시작 값으로 사용합니다. 의 <xref:System.Windows.FrameworkElement.Width%2A> 는 <xref:System.Windows.Shapes.Rectangle> 100에서 애니메이션의 대상 값 300으로 애니메이션됩니다.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>기준  
 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성만 설정하면 애니메이션이 애니메이션중인 속성의 기본 값또는 구성 애니메이션의 출력에서 해당 값의 합계 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성에 의해 지정된 값으로 진행됩니다.  
  
 다음 예제는 의 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성만 <xref:System.Windows.Media.Animation.DoubleAnimation> 300으로 설정합니다. 예제에서는 시작 값을 지정하지 않으므로 <xref:System.Windows.Media.Animation.DoubleAnimation> <xref:System.Windows.FrameworkElement.Width%2A> 속성의 기본 값(100)을 시작 값으로 사용합니다. 끝 값은 애니메이션 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 300의 값을 시작 값인 100: 400에 추가하여 결정됩니다. 결과적으로, 의 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle> 애니메이션100 받는 사람으로 400.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 애니메이션의 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 설정하면 애니메이션이 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성에 의해 지정된 값에서 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성의 합계로 지정된 값으로 진행됩니다.  
  
 다음 예제는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 50의 <xref:System.Windows.Media.Animation.DoubleAnimation> 속성을 설정하고 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 해당 속성을 300으로 설정합니다. 끝 값은 애니메이션 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 300의 값을 시작 값인 50: 350에 추가하여 결정됩니다. 결과적으로, 의 <xref:System.Windows.FrameworkElement.Width%2A> 50에서 350 <xref:System.Windows.Shapes.Rectangle> 애니메이션.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>보낸 사람  
 애니메이션 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 의 값만 지정하면 애니메이션이 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성에 의해 지정된 값에서 애니메이션되는 속성의 기준 값 또는 구성 애니메이션의 출력으로 진행됩니다.  
  
 다음 예제는 50의 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> <xref:System.Windows.Media.Animation.DoubleAnimation> 속성만 설정합니다. 끝 값을 지정하지 않으므로 <xref:System.Windows.Media.Animation.DoubleAnimation> <xref:System.Windows.FrameworkElement.Width%2A> 속성의 기본 값 인 100을 끝 값으로 사용합니다. 의 <xref:System.Windows.FrameworkElement.Width%2A> 는 <xref:System.Windows.Shapes.Rectangle> 속성의 <xref:System.Windows.FrameworkElement.Width%2A> 기본 값, 100에 50에서 애니메이션됩니다.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 애니메이션의 속성과 속성을 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 모두 설정하면 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성이 무시됩니다.  
  
<a name="otheranimationtypes"></a>
## <a name="other-animation-types"></a>기타 애니메이션 형식  
 From/To/By 애니메이션은 키 프레임 애니메이션과 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 경로 애니메이션을 제공합니다.  
  
- 키 프레임 애니메이션은 키 프레임을 사용하여 설명되는 제한 없는 수의 대상 값에 따라 애니메이션을 적용합니다. 자세한 내용은 키 [프레임 애니메이션 개요를](key-frame-animations-overview.md)참조하십시오.  
  
- 경로 애니메이션은 <xref:System.Windows.Media.PathGeometry>에서 출력 값을 생성합니다. 자세한 내용은 경로 [애니메이션 개요를](path-animations-overview.md)참조하십시오.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 고유한 사용자 지정 애니메이션 형식도 만들 수 있습니다. 자세한 내용은 사용자 [지정 애니메이션 개요를](custom-animations-overview.md)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [애니메이션 개요](animation-overview.md)
- [Storyboard 개요](storyboards-overview.md)
- [키 프레임 애니메이션 개요](key-frame-animations-overview.md)
- [경로 애니메이션 개요](path-animations-overview.md)
- [사용자 지정 애니메이션 개요](custom-animations-overview.md)
- [From, To 및 By 애니메이션 대상 값 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
