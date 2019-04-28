---
title: '방법: 시작 된 Storyboard 제어'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: 107391386dfbb718f9436d9a039b08439fbc3279
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762139"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a>방법: 시작 된 Storyboard 제어
컨트롤에 코드를 사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.Storyboard> 시작 된 후입니다. 스토리 보드 제어 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 사용 하 여 <xref:System.Windows.Trigger> 및 <xref:System.Windows.TriggerAction> 개체, 참조 예를 들어 [이벤트 트리거는 Storyboard를 시작한 후 제어를 사용 하 여](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)합니다.  
  
 Storyboard를 시작 하려면 해당 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 분산 스토리 보드의 애니메이션 속성에 애니메이션을 적용 하며 storyboard를 시작 하는 메서드.  
  
 Storyboard를 제어할 수 있도록 하려면 사용 합니다 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 지정 하 고 **true** 두 번째 매개 변수로 합니다. 그런 다음 일시 중지, 다시 시작, 검색, 중지, 속도, 또는 스토리 보드를 저하 또는 채우기 기간으로 이동 하려면 스토리 보드의 대화형 메서드를 사용할 수 있습니다. 다음은 스토리 보드의 대화형 메서드 목록입니다.  
  
- <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Storyboard를 일시 중지 합니다.  
  
- <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: 일시 중지 된 storyboard를 다시 시작합니다.  
  
- <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: 스토리 보드의 대화형 속도 설정합니다.  
  
- <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: 스토리 보드 지정된 된 위치를 찾습니다.  
  
- <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: 지정된 된 위치에 스토리 보드를 검색 합니다. 달리는 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 메서드를이 작업의 다음 틱 보다 먼저 처리 됩니다.  
  
- <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: 있는 경우 채우기 기간이 스토리 보드를 이동 합니다.  
  
- <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Storyboard를 중지 합니다.  
  
 다음 예제에서는 여러 스토리 보드 메서드는 스토리 보드를 대화형으로 제어 사용 됩니다.  
  
 **참고:** 트리거를 사용 하 여 storyboard 제어의 예제를 보려면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 참조 하세요 [제어는 Storyboard를 시작한 후 이벤트 트리거를 사용 하 여](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)입니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a>참고자료

- [Storyboard를 시작한 후 이벤트 트리거를 사용하여 제어](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
