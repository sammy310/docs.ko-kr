---
title: Timer Component Interval 속성의 제한 사항
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 15626a53f0541ff79e2098377d9dfdb4626ac155
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745238"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a>Windows Forms Timer 구성 요소의 Interval 속성에 대한 제한 사항
Windows Forms <xref:System.Windows.Forms.Timer> 구성 요소에는 한 타이머 이벤트와 그 다음에 전달 되는 시간 (밀리초)을 지정 하는 <xref:System.Windows.Forms.Timer.Interval%2A> 속성이 있습니다. 구성 요소를 사용 하지 않도록 설정 하지 않으면 타이머는 거의 동일한 간격으로 <xref:System.Windows.Forms.Timer.Tick> 이벤트를 계속 받습니다.  
  
 이 구성 요소는 Windows Forms 환경에 맞게 설계되었습니다. 서버 환경에 적합한 타이머가 필요한 경우 [서버 기반 타이머 소개](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))를 참조하세요.  
  
## <a name="the-interval-property"></a>Interval 속성  
 <xref:System.Windows.Forms.Timer.Interval%2A> 속성에는 <xref:System.Windows.Forms.Timer> 구성 요소를 프로그래밍할 때 고려해 야 할 몇 가지 제한 사항이 있습니다.  
  
- 응용 프로그램 또는 다른 응용 프로그램에서 긴 루프, 집약적 계산, 드라이브, 네트워크 또는 포트 액세스와 같은 시스템에 많은 수요를 발생 하는 경우 응용 프로그램은 <xref:System.Windows.Forms.Timer.Interval%2A> 속성이 지정 하는 것 처럼 타이머 이벤트를 자주 가져오지 못할 수 있습니다.  
  
- 시간 간격이 정확히 정해져 있지는 않습니다. 정확성을 보장 하기 위해 타이머는 내부적으로 누적 된 시간을 추적 하는 대신 필요에 따라 시스템 클록을 확인 해야 합니다.  
  
- <xref:System.Windows.Forms.Timer.Interval%2A> 속성의 전체 자릿수는 밀리초 단위입니다. 일부 컴퓨터는 해결 방법이 밀리초 보다 높은 고해상도 카운터를 제공 합니다. 이러한 카운터의 가용성은 컴퓨터의 프로세서 하드웨어에 따라 달라 집니다.
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.Timer>
- [Timer 구성 요소](timer-component-windows-forms.md)
- [Timer 구성 요소 개요](timer-component-overview-windows-forms.md)
