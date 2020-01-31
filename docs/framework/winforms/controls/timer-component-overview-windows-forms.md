---
title: Timer 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 83b52d395cdc3e3357bcf83517eab258a5c8ae08
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742778"
---
# <a name="timer-component-overview-windows-forms"></a>Timer 구성 요소 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.Timer>는 일정한 간격마다 이벤트를 발생시키는 구성 요소입니다. 이 구성 요소는 Windows Forms 환경에 맞게 설계되었습니다. 서버 환경에 적합한 타이머가 필요한 경우 [서버 기반 타이머 소개](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))를 참조하세요.  
  
## <a name="key-properties-methods-and-events"></a>키 속성, 메서드 및 이벤트  
 간격의 길이는 값 (밀리초)을 갖는 <xref:System.Windows.Forms.Timer.Interval%2A> 속성으로 정의 됩니다. 구성 요소가 활성화 되 면 간격 마다 <xref:System.Windows.Forms.Timer.Tick> 이벤트가 발생 합니다. 실행할 코드를 추가 합니다. 자세한 내용은 [방법: Windows Forms Timer 구성 요소를 사용 하 여 설정 된 간격 마다 프로시저 실행](run-procedures-at-set-intervals-with-wf-timer-component.md)을 참조 하세요. <xref:System.Windows.Forms.Timer> 구성 요소의 주요 메서드는 타이머를 설정 및 해제 하는 <xref:System.Windows.Forms.Timer.Start%2A> 및 <xref:System.Windows.Forms.Timer.Stop%2A>입니다. 타이머가 꺼져 있는 경우 다시 설정 됩니다. <xref:System.Windows.Forms.Timer> 구성 요소를 일시 중지할 수 있는 방법은 없습니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.Timer>
- [Timer 구성 요소](timer-component-windows-forms.md)
- [Windows Forms Timer 구성 요소의 Interval 속성에 대한 제한 사항](limitations-of-the-timer-component-interval-property.md)
