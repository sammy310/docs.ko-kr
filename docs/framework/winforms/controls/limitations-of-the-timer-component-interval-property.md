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
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a><span data-ttu-id="f622e-102">Windows Forms Timer 구성 요소의 Interval 속성에 대한 제한 사항</span><span class="sxs-lookup"><span data-stu-id="f622e-102">Limitations of the Windows Forms Timer Component's Interval Property</span></span>
<span data-ttu-id="f622e-103">Windows Forms <xref:System.Windows.Forms.Timer> 구성 요소에는 한 타이머 이벤트와 그 다음에 전달 되는 시간 (밀리초)을 지정 하는 <xref:System.Windows.Forms.Timer.Interval%2A> 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f622e-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="f622e-104">구성 요소를 사용 하지 않도록 설정 하지 않으면 타이머는 거의 동일한 간격으로 <xref:System.Windows.Forms.Timer.Tick> 이벤트를 계속 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f622e-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="f622e-105">이 구성 요소는 Windows Forms 환경에 맞게 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f622e-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="f622e-106">서버 환경에 적합한 타이머가 필요한 경우 [서버 기반 타이머 소개](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f622e-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="f622e-107">Interval 속성</span><span class="sxs-lookup"><span data-stu-id="f622e-107">The Interval Property</span></span>  
 <span data-ttu-id="f622e-108"><xref:System.Windows.Forms.Timer.Interval%2A> 속성에는 <xref:System.Windows.Forms.Timer> 구성 요소를 프로그래밍할 때 고려해 야 할 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f622e-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
- <span data-ttu-id="f622e-109">응용 프로그램 또는 다른 응용 프로그램에서 긴 루프, 집약적 계산, 드라이브, 네트워크 또는 포트 액세스와 같은 시스템에 많은 수요를 발생 하는 경우 응용 프로그램은 <xref:System.Windows.Forms.Timer.Interval%2A> 속성이 지정 하는 것 처럼 타이머 이벤트를 자주 가져오지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f622e-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
- <span data-ttu-id="f622e-110">시간 간격이 정확히 정해져 있지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f622e-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="f622e-111">정확성을 보장 하기 위해 타이머는 내부적으로 누적 된 시간을 추적 하는 대신 필요에 따라 시스템 클록을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f622e-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
- <span data-ttu-id="f622e-112"><xref:System.Windows.Forms.Timer.Interval%2A> 속성의 전체 자릿수는 밀리초 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="f622e-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="f622e-113">일부 컴퓨터는 해결 방법이 밀리초 보다 높은 고해상도 카운터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f622e-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="f622e-114">이러한 카운터의 가용성은 컴퓨터의 프로세서 하드웨어에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f622e-114">The availability of such a counter depends on the processor hardware of your computer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f622e-115">참조</span><span class="sxs-lookup"><span data-stu-id="f622e-115">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="f622e-116">Timer 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f622e-116">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="f622e-117">Timer 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="f622e-117">Timer Component Overview</span></span>](timer-component-overview-windows-forms.md)
