---
title: From 애니메이션 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
ms.openlocfilehash: 661c035f55ba1fb550726d75921cd01a72b2eecc
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449007"
---
# <a name="fromtoby-animations-overview"></a>From/To/By 애니메이션 개요
이 항목에서는 From/To/By 애니메이션을 사용하여 종속성 속성에 애니메이션 효과를 적용하는 방법을 설명합니다. From/To/By 애니메이션은 두 값 간에 변환을 생성합니다.  
  
<a name="prereq"></a>   
## <a name="prerequisites"></a>사전 요구 사항  
 이 항목을 이해 하려면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션 기능에 대해 잘 알고 있어야 합니다. 애니메이션 기능에 대 한 소개는 [애니메이션 개요](animation-overview.md)를 참조 하세요.  
  
<a name="whatisanimation"></a>   
## <a name="what-is-a-fromtoby-animation"></a>From/To/By 애니메이션이란?  
 From/To/By 애니메이션은 시작 값과 끝 값 사이에 전환을 만드는 <xref:System.Windows.Media.Animation.AnimationTimeline> 형식입니다. 전환이 완료 되는 데 걸리는 시간은 해당 애니메이션의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>에 의해 결정 됩니다.  
  
 태그와 코드의 <xref:System.Windows.Media.Animation.Storyboard>를 사용 하거나 코드에서 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 사용 하 여 속성에 From/To/By 애니메이션을 적용할 수 있습니다. From/To/By 애니메이션을 사용 하 여 <xref:System.Windows.Media.Animation.AnimationClock> 만들고 하나 이상의 속성에 적용할 수도 있습니다. 애니메이션 효과를 주기 위한 여러 다양한 방법에 대한 자세한 내용은 [속성 애니메이션 기술 개요](property-animation-techniques-overview.md)를 참조하세요.  
  
 From/To/By 애니메이션은 2개 이하의 대상 값을 가질 수 있습니다. 2개를 초과하는 대상 값을 갖는 애니메이션이 필요한 경우 키 프레임 애니메이션을 사용합니다. 키 프레임 애니메이션은 [키 프레임 애니메이션 개요](key-frame-animations-overview.md)에 설명 되어 있습니다.  
  
<a name="animation_types"></a>   
## <a name="fromtoby-animation-types"></a>From/To/By 애니메이션 형식  
 애니메이션은 속성 값을 생성하므로 속성 형식이 다르면 애니메이션 형식도 다릅니다. 요소의 <xref:System.Windows.FrameworkElement.Width%2A> 속성과 같이 <xref:System.Double>를 사용 하는 속성에 애니메이션 효과를 주려면 <xref:System.Double> 값을 생성 하는 애니메이션을 사용 합니다. <xref:System.Windows.Point>를 사용 하는 속성에 애니메이션 효과를 주려면 <xref:System.Windows.Point> 값 등을 생성 하는 애니메이션을 사용 합니다.  
  
 From/To/By 애니메이션 클래스는 <xref:System.Windows.Media.Animation> 네임 스페이스에 속하고 다음 명명 규칙을 사용 합니다.  
  
 *\<형식 >* `Animation`  
  
 여기서 *\<Type>* 은 클래스가 애니메이션을 적용하는 값의 형식입니다.  
  
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
 From/To/By 애니메이션은 두 대상 값 간에 변환을 생성합니다. 일반적으로 시작 값 (<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성을 사용 하 여 설정)과 끝 값 (<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성을 사용 하 여 설정)을 지정 하는 것이 일반적입니다. 그러나 시작 값, 대상 값 또는 오프셋 값만 지정할 수도 있습니다. 이러한 경우 애니메이션은 애니메이션 효과를 적용할 속성에서 누락된 대상 값을 가져옵니다. 다음 목록에서는 애니메이션의 대상 값을 지정하는 여러 가지 방법을 설명합니다.  
  
- **시작 값**  
  
     애니메이션의 시작 값을 명시적으로 지정 하려면 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성을 사용 합니다. <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성을 단독으로 사용 하거나 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 또는 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성으로 사용할 수 있습니다. <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성만 지정 하는 경우 애니메이션은 해당 값에서 애니메이션 속성의 기준 값으로 전환 됩니다.  
  
- **끝 값**  
  
     애니메이션의 끝 값을 지정 하려면 해당 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성을 사용 합니다. <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성을 단독으로 사용 하는 경우 애니메이션은 애니메이션이 적용 되는 속성에서 또는 동일한 속성에 적용 되는 다른 애니메이션의 출력에서 시작 값을 가져옵니다. <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성과 함께 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성을 사용 하 여 애니메이션의 시작 값과 끝 값을 명시적으로 지정할 수 있습니다.  
  
- **오프셋 값**  
  
     <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 사용 하면 애니메이션에 대 한 명시적 시작 값 이나 끝 값 대신 오프셋을 지정할 수 있습니다. 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성은 애니메이션이 해당 기간 동안 값을 변경 하는 정도를 지정 합니다. <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 단독으로 사용 하거나 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성과 함께 사용할 수 있습니다. <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성만 지정 하는 경우 애니메이션은 속성의 기준 값 또는 다른 애니메이션의 출력에 오프셋 값을 추가 합니다.  
  
<a name="examples"></a>   
## <a name="using-fromtoby-values"></a>From/To/By 값 사용  
 다음 섹션에서는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 함께 사용 하거나 별도로 사용 하는 방법을 설명 합니다.  
  
 이 단원의 예제에서는 각각 From/To/By 애니메이션의 형식인 <xref:System.Windows.Media.Animation.DoubleAnimation>를 사용 하 여 장치 독립적 픽셀 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle>의 속성에 애니메이션 효과를 적용 하 고 장치 독립적 픽셀 너비를 100 합니다.  
  
 각 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>을 사용 하지만 모든 From/To/By 애니메이션의 From, To 및 By 속성은 동일 하 게 동작 합니다. 이러한 각 예제에서는 <xref:System.Windows.Media.Animation.Storyboard>을 사용 하지만 From/To/By 애니메이션을 다른 방법으로 사용할 수 있습니다. 자세한 내용은 [속성 애니메이션 기술 개요](property-animation-techniques-overview.md)를 참조 하세요.  
  
### <a name="fromto"></a>보낸 사람/받는 사람  
 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 값을 함께 설정 하면 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성에 지정 된 값에서 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성으로 지정 된 값으로 애니메이션이 진행 됩니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성을 50으로 설정 하 고 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성을 300으로 설정 합니다. 따라서 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.FrameworkElement.Width%2A>에 50에서 300으로 애니메이션 효과를 적용 합니다.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>수행할 작업  
 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성만 설정 하면 애니메이션 효과가 적용 된 속성의 기준 값 이나 이전에 동일한 속성에 적용 된 작성 애니메이션의 출력에서 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성으로 지정 된 값으로 애니메이션이 진행 됩니다.  
  
 ("작성 애니메이션"은 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> 전달 동작을 사용 하 여 현재 애니메이션을 적용할 때 여전히 적용 되는 동일한 속성에 이전에 적용 된 <xref:System.Windows.Media.Animation.ClockState.Active> 또는 <xref:System.Windows.Media.Animation.ClockState.Filling> 애니메이션을 나타냅니다.)  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성만 300으로 설정 합니다. 시작 값이 지정 되지 않았기 때문에 <xref:System.Windows.Media.Animation.DoubleAnimation>는 <xref:System.Windows.FrameworkElement.Width%2A> 속성의 기준 값 (100)을 시작 값으로 사용 합니다. <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.FrameworkElement.Width%2A>은 100에서 애니메이션의 대상 값 300으로 애니메이션 효과를 적용 합니다.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>기준  
 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성만 설정 하면 애니메이션이 적용 되는 속성의 기준 값 이나 구성 애니메이션의 출력에서 해당 값의 합계와 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성으로 지정 된 값에서 애니메이션이 진행 됩니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성만 300으로 설정 합니다. 이 예제에서는 시작 값을 지정 하지 않으므로 <xref:System.Windows.Media.Animation.DoubleAnimation> <xref:System.Windows.FrameworkElement.Width%2A> 속성 100의 기준 값을 시작 값으로 사용 합니다. 끝 값은 300 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 값을 시작 값 100:400에 더하여 결정 됩니다. 따라서 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.FrameworkElement.Width%2A>에 100에서 400으로 애니메이션 효과를 적용 합니다.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 설정 하는 경우 애니메이션은 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성에 지정 된 값에서 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성의 합계로 지정 된 값으로 진행 됩니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성을 50으로 설정 하 고 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 300으로 설정 합니다. 끝 값은 300 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 값을 시작 값 50:350에 더하여 결정 됩니다. 따라서 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.FrameworkElement.Width%2A>에 50에서 350으로 애니메이션 효과를 적용 합니다.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>보낸 사람  
 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 값만 지정 하는 경우 애니메이션은 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성으로 지정 된 값부터 애니메이션이 적용 되는 속성의 기준 값 또는 작성 애니메이션의 출력으로 진행 됩니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성만 50으로 설정 합니다. 끝 값이 지정 되지 않았기 때문에 <xref:System.Windows.Media.Animation.DoubleAnimation> <xref:System.Windows.FrameworkElement.Width%2A> 속성 100의 기준 값을 끝 값으로 사용 합니다. <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Width%2A> 속성 100의 기준 값으로 50에서 애니메이션을 적용 합니다.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 둘 다 설정 하면 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성이 무시 됩니다.  
  
<a name="otheranimationtypes"></a>   
## <a name="other-animation-types"></a>기타 애니메이션 형식  
 From/To/By 애니메이션은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 제공 하는 유일한 애니메이션 유형이 아닙니다. 또한 키 프레임 애니메이션과 경로 애니메이션을 제공 합니다.  
  
- 키 프레임 애니메이션은 키 프레임을 사용하여 설명되는 제한 없는 수의 대상 값에 따라 애니메이션을 적용합니다. 자세한 내용은 참조는 [키 프레임 애니메이션 개요](key-frame-animations-overview.md)합니다.  
  
- 경로 애니메이션은 <xref:System.Windows.Media.PathGeometry>에서 출력 값을 생성 합니다. 자세한 내용은 [경로 애니메이션 개요](path-animations-overview.md)를 참조 하세요.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 고유한 사용자 지정 애니메이션 형식도 만들 수 있습니다. 자세한 내용은 [사용자 지정 애니메이션 개요](custom-animations-overview.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [애니메이션 개요](animation-overview.md)
- [Storyboard 개요](storyboards-overview.md)
- [키 프레임 애니메이션 개요](key-frame-animations-overview.md)
- [경로 애니메이션 개요](path-animations-overview.md)
- [사용자 지정 애니메이션 개요](custom-animations-overview.md)
- [From, To 및 By 애니메이션 대상 값 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
