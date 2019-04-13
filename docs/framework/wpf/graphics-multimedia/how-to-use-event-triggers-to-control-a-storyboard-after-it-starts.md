---
title: '방법: 스토리보드가 시작되면 이벤트 트리거를 사용하여 제어'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: d444349f8bc9236e1d15f484f35b1326c77e2425
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170653"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>방법: 스토리보드가 시작되면 이벤트 트리거를 사용하여 제어
제어 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.Storyboard> 시작 합니다. 시작 하는 <xref:System.Windows.Media.Animation.Storyboard> 를 사용 하 여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 사용 하 여 <xref:System.Windows.Media.Animation.BeginStoryboard>, 개체 및 속성에 애니메이션을 적용 하 고 시작한 다음 스토리 보드에 애니메이션을 배포 하는 합니다. 제공 하는 경우 <xref:System.Windows.Media.Animation.BeginStoryboard> 이름을 지정 하 여 해당 <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> 속성을 만들면 제어 가능한 storyboard입니다. 제어할 수 있습니다 다음 대화형으로 스토리 보드 시작 된 후.  
  
 와 함께 다음 스토리 보드 작업을 사용 하 여 <xref:System.Windows.EventTrigger> storyboard를 제어 하는 개체입니다.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Storyboard를 일시 중지 합니다.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: 일시 중지 된 storyboard를 다시 시작합니다.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Storyboard 속도 변경합니다.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: 있는 경우 해당 채우기 기간의 끝에 스토리 보드를 이동 합니다.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Storyboard를 중지 합니다.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: 리소스를 확보 하 여 storyboard를 제거 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 제어 가능한 storyboard 작업이 storyboard를 대화형으로 제어 하려면  
  
 **참고:** 코드를 사용 하 여 스토리 보드 제어의 예제를 보려면 [컨트롤을 스토리 보드 후 해당 시작를 사용 하 여 해당 대화형 메서드](how-to-control-a-storyboard-after-it-starts.md)합니다.  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 추가 예제를 보려면 합니다 [애니메이션 예제 갤러리](https://go.microsoft.com/fwlink/?LinkID=159969)합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [대화형 메서드를 사용하여 이미 시작된 스토리보드 제어](how-to-control-a-storyboard-after-it-starts.md)
- [애니메이션 개요](animation-overview.md)
- [Storyboard 개요](storyboards-overview.md)
