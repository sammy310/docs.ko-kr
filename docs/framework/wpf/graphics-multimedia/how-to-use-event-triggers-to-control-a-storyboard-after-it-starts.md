---
title: '방법: Storyboard를 시작한 후 이벤트 트리거를 사용하여 제어'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 518f5d7ea0b5dc00677489f1383814563c565145
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186710"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>방법: Storyboard를 시작한 후 이벤트 트리거를 사용하여 제어

이 예제에서는 시작 <xref:System.Windows.Media.Animation.Storyboard> 후 a를 제어하는 방법을 보여 주며, a를 제어하는 방법을 보여 주어 있습니다. 을 사용하여 <xref:System.Windows.Media.Animation.Storyboard> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]시작하려면 <xref:System.Windows.Media.Animation.BeginStoryboard>애니메이션이 애니메이션된 개체 및 속성에 애니메이션을 배포한 다음 스토리보드를 시작하는 을 사용합니다. 속성을 <xref:System.Windows.Media.Animation.BeginStoryboard> <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> 지정하여 이름을 지정하면 컨트롤 가능한 스토리보드로 만듭니다. 그런 다음 스토리보드가 시작된 후 대화식으로 스토리보드를 제어할 수 있습니다.

다음 스토리보드 작업을 개체와 <xref:System.Windows.EventTrigger> 함께 사용하여 스토리보드를 제어합니다.

- <xref:System.Windows.Media.Animation.PauseStoryboard>: 스토리보드를 일시 중지합니다.

- <xref:System.Windows.Media.Animation.ResumeStoryboard>: 일시 중지된 스토리보드를 다시 시작합니다.

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: 스토리보드 속도가 변경됩니다.

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: 스토리보드가 있는 경우 채우기 기간이 끝날 때까지 스토리보드를 진행합니다.

- <xref:System.Windows.Media.Animation.StopStoryboard>: 스토리보드를 중지합니다.

- <xref:System.Windows.Media.Animation.RemoveStoryboard>: 스토리보드를 제거하여 리소스를 확보합니다.

## <a name="example"></a>예제

다음 예제에서는 제어 가능한 스토리보드 작업을 사용하여 스토리보드를 대화형으로 제어합니다.

> [!NOTE]
> 코드를 사용하여 스토리보드를 제어하는 예제를 보려면 [대화형 메서드를 사용하기 시작한 후 스토리보드 제어를](how-to-control-a-storyboard-after-it-starts.md)참조하십시오.

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

추가 예제는 애니메이션 [예제 갤러리를](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)참조하십시오.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [대화형 메서드를 사용하여 이미 시작된 Storyboard 제어](how-to-control-a-storyboard-after-it-starts.md)
- [애니메이션 개요](animation-overview.md)
- [Storyboard 개요](storyboards-overview.md)
