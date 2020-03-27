---
title: '방법: 키 프레임 애니메이션 타이밍 제어'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 8cfd2be0bbc526ed92a5fb1b558a5a41dc9c3113
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344731"
---
# <a name="how-to-control-key-frame-animation-timing"></a>방법: 키 프레임 애니메이션 타이밍 제어

이 예제에서는 키 프레임 애니메이션 내에서 키 프레임의 타이밍을 제어하는 방법을 보여 주며, 키 프레임 애니메이션을 보여 주며, 키 프레임의 타이밍을 제어하는 방법을 보여 주며, 이 예제에서는 키 프레임 애니메이션의 타이밍을 제어합니다. 다른 애니메이션과 마찬가지로 키 프레임 애니메이션에는 속성이 있습니다. <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 애니메이션의 지속 시간을 지정하는 것 외에도 해당 기간의 일부가 각 키 프레임에 할당되도록 지정해야 합니다. 시간을 할당하려면 애니메이션의 각 <xref:System.Windows.Media.Animation.KeyTime> 키 프레임에 대해 a를 지정합니다.

각 <xref:System.Windows.Media.Animation.KeyTime> 키 프레임에 대해 키 프레임이 끝날 때 지정합니다(키 프레임이 재생되는 시간을 지정하지 않음). a를 <xref:System.Windows.Media.Animation.KeyTime> <xref:System.TimeSpan> 값으로, 백분율로 또는 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 특수 값으로 지정할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> a를 사용하여 화면에서 사각형을 애니메이션합니다. 키 프레임의 키 시간은 <xref:System.TimeSpan> 값으로 설정됩니다.

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

다음 그림은 각 키 프레임의 값에 도달하는 시기를 보여 주며,

![3, 4, 10초에 키 값에 도달](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")

다음 예제에서는 키 프레임의 키 시간이 백분율 값으로 설정되는 경우를 제외하고 동일한 애니메이션을 보여 주며, 이 애니메이션은 다음과 같습니다.

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

다음 그림은 각 키 프레임의 값에 도달하는 시기를 보여 주며,

![3, 4, 10초에 키 값에 도달](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")

다음 예제에서는 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> 키 시간 값을 사용합니다.

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

다음 그림은 각 키 프레임의 값에 도달하는 시기를 보여 주며,

![키 값은 3.3, 6.6 및 9.9초에 도달](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")

마지막 예제에서는 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 키 시간 값을 사용합니다.

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

다음 그림은 각 키 프레임의 값에 도달하는 시기를 보여 주며,

![0, 5, 10초에 키 값에 도달](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")

간단히 하기 위해 이 예제의 코드 버전은 단일 애니메이션만 단일 속성에 적용되기 때문에 스토리보드가 아닌 로컬 애니메이션을 사용하지만 예제는 스토리보드를 대신 사용하도록 수정할 수 있습니다. 코드에서 스토리보드를 선언하는 방법을 보여 줄 예제에서는 [스토리보드를 사용하여 속성 애니메이션을](how-to-animate-a-property-by-using-a-storyboard.md)참조하세요.

전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)을 참조하세요. 키 프레임 애니메이션에 대한 자세한 내용은 [키 프레임 애니메이션 개요를](key-frame-animations-overview.md)참조하십시오.

## <a name="see-also"></a>참조

- [키 프레임 애니메이션 개요](key-frame-animations-overview.md)
- [애니메이션 개요](animation-overview.md)
- [방법 항목](animation-and-timing-how-to-topics.md)
