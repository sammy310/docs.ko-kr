---
title: 타이밍 이벤트 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- timelines [WPF]
- timing events [WPF]
ms.assetid: 597e3280-0867-4359-a97b-5b2f4149e350
ms.openlocfilehash: ee45441e9ad09c60d8b61ecce4ef08b0027ce29e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145412"
---
# <a name="timing-events-overview"></a>타이밍 이벤트 개요
이 항목에서는 사용 <xref:System.Windows.Media.Animation.Timeline> 가능한 5개의 타이밍 <xref:System.Windows.Media.Animation.Clock> 이벤트와 개체를 사용하는 방법을 설명합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 항목을 이해하려면 애니메이션을 만들고 사용하는 방법을 이해해야 합니다. 애니메이션을 시작하려면 애니메이션 [개요를](animation-overview.md)참조하십시오.  
  
 다음과 같은 여러 가지 방법으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]속성을 애니메이션할 수 있습니다.  
  
- **스토리보드 개체(태그** 및 코드): 개체를 사용하여 <xref:System.Windows.Media.Animation.Storyboard> 하나 이상의 개체에 애니메이션을 정렬하고 배포할 수 있습니다. 예를 들어 [스토리보드를 사용하여 속성 애니메이션을](how-to-animate-a-property-by-using-a-storyboard.md)참조하십시오.  
  
- **로컬** 애니메이션(코드만 사용): 애니메이션속성에 오브젝트를 직접 적용할 <xref:System.Windows.Media.Animation.AnimationTimeline> 수 있습니다. 예를 들어 [스토리보드를 사용하지 않고 속성 애니메이션을](how-to-animate-a-property-without-using-a-storyboard.md)참조하십시오.  
  
- **클록 사용**(코드만): 클록 생성을 명시적으로 관리하고 애니메이션 클록을 직접 배포할 수 있습니다.  예를 들어 [애니메이션 시계를 사용하여 속성 애니메이션 을](how-to-animate-a-property-by-using-an-animationclock.md)참조하십시오.  
  
 태그 및 코드에서 사용할 수 있으므로 이 개요의 예제에서는 개체를 사용합니다. <xref:System.Windows.Media.Animation.Storyboard> 그러나 설명된 개념을 속성에 애니메이션 효과를 주는 다른 방법에도 적용할 수 있습니다.  
  
### <a name="what-is-a-clock"></a>클록이란?  
 타임라인 자체는 실제로 시간 세그먼트를 설명하는 것 이외의 어떤 작업도 수행하지 않습니다. 실제 작업을 수행하는 타임라인의 개체는 타임라인에 <xref:System.Windows.Media.Animation.Clock> 대한 타이밍 관련 런타임 상태를 유지합니다. Storyboard를 사용할 때와 같이 대부분의 경우에 타임라인에 대해 자동으로 클록이 생성됩니다. <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> 메서드를 <xref:System.Windows.Media.Animation.Clock> 사용 하 여 명시적으로 만들 수도 있습니다. 개체에 대한 <xref:System.Windows.Media.Animation.Clock> 자세한 내용은 [애니메이션 및 타이밍 시스템 개요를](animation-and-timing-system-overview.md)참조하십시오.  
  
## <a name="why-use-events"></a>이벤트를 사용하는 이유  
 하나(마지막 틱에 맞춰진 검색)를 제외한 모든 대화형 타이밍 작업은 비동기적입니다. 실행될 시기를 정확히 알 방법은 없습니다. 타이밍 작업에 의존하는 다른 코드가 있을 때는 문제가 될 수입니다. 사각형에 애니메이션 효과를 적용한 타임라인을 중지하려고 한다고 가정해 보겠습니다. 이 타임라인이 중지된 후에 사각형의 색을 변경합니다.  
  
 [!code-csharp[events_procedural#NeedForEventsFragment](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#needforeventsfragment)]
 [!code-vb[events_procedural#NeedForEventsFragment](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#needforeventsfragment)]  
  
 앞의 예제에서 두 번째 코드 줄은 Storyboard가 중지되기 전에 실행될 수 있습니다. 중지는 비동기 작업이기 때문입니다. 타임라인이나 클록에 중지하도록 지시하면 타이밍 엔진의 다음 틱까지는 처리되지 않는 일종의 “중지 요청”이 만들어집니다.  
  
 타임라인이 완료된 후에 명령을 실행하려면 타이밍 이벤트를 사용합니다. 다음 예제에서 이벤트 처리기는 Storyboard가 재생을 중지한 후에 사각형의 색을 변경하는 데 사용됩니다.  
  
 [!code-csharp[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#registerforstoryboardcurrentstateinvalidatedevent)]
 [!code-vb[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#registerforstoryboardcurrentstateinvalidatedevent)]  
[!code-csharp[events_procedural#StoryboardCurrentStateInvalidatedEvent2](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#storyboardcurrentstateinvalidatedevent2)]
[!code-vb[events_procedural#StoryboardCurrentStateInvalidatedEvent2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#storyboardcurrentstateinvalidatedevent2)]  
  
 보다 자세한 예제는 [시계의 상태가 변경될 때 알림 수신을](how-to-receive-notification-when-clock-state-changes.md)참조하십시오.  
  
## <a name="public-events"></a>Public 이벤트  
 및 <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Clock> 클래스는 모두 5개의 타이밍 이벤트를 제공합니다. 다음 표에는 이러한 이벤트와 해당 이벤트를 트리거하는 조건이 나와 있습니다.  
  
|행사|트리거하는 대화형 작업|기타 트리거|  
|-----------|--------------------------------------|--------------------|  
|**완료**|건너뛰어서 채우기|클록이 완료됩니다.|  
|**CurrentGlobalSpeedInvalidated**|일시 중지, 다시 시작, 검색, 속도 비율 설정, 건너뛰어서 채우기, 중지|클록이 거꾸로 진행되거나, 가속되거나, 시작되거나, 중지됩니다.|  
|**CurrentStateInvalidated**|시작, 건너뛰어서 채우기, 중지|클록이 시작되거나, 중지되거나, 채워집니다.|  
|**CurrentTimeInvalidated**|시작, 검색, 건너뛰어서 채우기, 중지|클록이 진행됩니다.|  
|**RemoveRequested**|제거||  
  
## <a name="ticking-and-event-consolidation"></a>틱 및 이벤트 통합  
 에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]개체에 애니메이션을 애니메이션하면 애니메이션을 관리하는 타이밍 엔진이 됩니다. 타이밍 엔진은 시간의 진행을 추적하고 각 애니메이션의 상태를 계산합니다. 1초 안에 이러한 많은 계산 패스가 진행됩니다. 이러한 계산 패스를 "틱"이라고 합니다.  
  
 틱은 자주 발생하지만 틱 간에 많은 사항이 발생할 수 있습니다. 예를 들어 타임라인이 중지되었다가 시작된 후 다시 중지될 수 있습니다. 이 경우 현재 상태는 3번 변경됩니다. 이론적으로 단일 틱에서 이벤트가 여러 번 발생할 수 있지만 타이밍 엔진은 이벤트를 통합하므로 각 이벤트는 틱마다 한 번만 발생할 수 있습니다.  
  
## <a name="registering-for-events"></a>이벤트 등록  
 타이밍 이벤트를 등록하는 방법에는 두 가지가 있습니다. 하나는 타임라인에 등록하는 것이고 다른 하나는 타임라인에서 생성된 클록에 등록하는 것입니다. 이벤트를 클록에 직접 등록하는 과정은 매우 간단합니다. 단, 반드시 코드에서만 수행할 수 있다는 단점이 있습니다. 태그 또는 코드에서 타임라인에 이벤트를 등록할 수 있습니다. 다음 섹션에서는 타임라인에 클록 이벤트를 등록하는 방법을 설명합니다.  
  
<a name="registeringforclockeventswithatimeline"></a>
## <a name="registering-for-clock-events-with-a-timeline"></a>타임라인에 클록 이벤트 등록  
 <xref:System.Windows.Media.Animation.Timeline.Completed>타임라인의 <xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated>" <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>및 <xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated> <xref:System.Windows.Media.Animation.Timeline.RemoveRequested> 이벤트는 타임라인과 연관된 것처럼 보이지만 이러한 이벤트에 등록하면 실제로 이벤트 처리기를 타임라인에 대해 <xref:System.Windows.Media.Animation.Clock> 만든 이벤트 처리기를 연결합니다.  
  
 예를 들어 타임라인에서 <xref:System.Windows.Media.Animation.Timeline.Completed> 이벤트에 등록하면 실제로 타임라인에 대해 생성된 각 시계의 <xref:System.Windows.Media.Animation.Clock.Completed> 이벤트에 등록하라는 시스템이 표시됩니다. 코드에서는 이 타임라인에 대해 생성하기 전에 <xref:System.Windows.Media.Animation.Clock> 이 이벤트에 등록해야 합니다. 그렇지 않으면 알림을 받지 못합니다. 이 작업은 에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]자동으로 수행됩니다. 파서는 생성되기 전에 이벤트에 자동으로 <xref:System.Windows.Media.Animation.Clock> 등록됩니다.  
  
## <a name="see-also"></a>참고 항목

- [애니메이션 및 타이밍 시스템 개요](animation-and-timing-system-overview.md)
- [애니메이션 개요](animation-overview.md)
- [타이밍 동작 개요](timing-behaviors-overview.md)
