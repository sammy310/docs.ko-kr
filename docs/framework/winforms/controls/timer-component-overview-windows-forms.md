---
title: Timer 구성 요소 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 5bef0ba87d6a496acf7575965128be2b20b437ab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962619"
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="ac9a4-102">Timer 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ac9a4-102">Timer Component Overview (Windows Forms)</span></span>
<span data-ttu-id="ac9a4-103">Windows Forms <xref:System.Windows.Forms.Timer>는 일정한 간격마다 이벤트를 발생시키는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ac9a4-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="ac9a4-104">이 구성 요소는 Windows Forms 환경에 맞게 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ac9a4-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="ac9a4-105">서버 환경에 적합한 타이머가 필요한 경우 [서버 기반 타이머 소개](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac9a4-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="ac9a4-106">키 속성, 메서드 및 이벤트</span><span class="sxs-lookup"><span data-stu-id="ac9a4-106">Key Properties, Methods, and Events</span></span>  
 <span data-ttu-id="ac9a4-107">간격의 길이 정의한는 <xref:System.Windows.Forms.Timer.Interval%2A> 속성을 해당 값은 밀리초에서입니다.</span><span class="sxs-lookup"><span data-stu-id="ac9a4-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="ac9a4-108">구성 요소를 사용 하는 경우는 <xref:System.Windows.Forms.Timer.Tick> 이벤트는 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="ac9a4-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="ac9a4-109">코드 실행을 추가할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="ac9a4-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="ac9a4-110">자세한 내용은 [방법: Windows Forms Timer 구성 요소를 사용 하 여 설정 된 간격 프로시저를 실행](run-procedures-at-set-intervals-with-wf-timer-component.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ac9a4-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="ac9a4-111">주요 메서드는 <xref:System.Windows.Forms.Timer> 구성 요소는 <xref:System.Windows.Forms.Timer.Start%2A> 및 <xref:System.Windows.Forms.Timer.Stop%2A>, 타이머를 설정 하는 및 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac9a4-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="ac9a4-112">타이머 꺼진 재설정; 일시 중지 하려면 없기는 <xref:System.Windows.Forms.Timer> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ac9a4-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac9a4-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="ac9a4-113">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="ac9a4-114">Timer 구성 요소</span><span class="sxs-lookup"><span data-stu-id="ac9a4-114">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="ac9a4-115">Windows Forms Timer 구성 요소의 Interval 속성에 대한 제한 사항</span><span class="sxs-lookup"><span data-stu-id="ac9a4-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](limitations-of-the-timer-component-interval-property.md)
