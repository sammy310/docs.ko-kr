---
title: 컨트롤의 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: c60713917b9c84aa7fad50fb1c81fc9252149ad6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745758"
---
# <a name="events-in-windows-forms-controls"></a><span data-ttu-id="73231-102">Windows Forms 컨트롤의 이벤트</span><span class="sxs-lookup"><span data-stu-id="73231-102">Events in Windows Forms Controls</span></span>
<span data-ttu-id="73231-103">Windows Forms 컨트롤은 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>에서 60 개 이상의 이벤트를 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="73231-103">A Windows Forms control inherits more than sixty events from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="73231-104">여기에는 컨트롤을 그리는 이벤트, 창 표시와 관련 된 이벤트 (예: <xref:System.Windows.Forms.Control.Resize> 및 <xref:System.Windows.Forms.Control.Layout> 이벤트, 하위 수준 마우스 및 키보드 이벤트)가 <xref:System.Windows.Forms.Control.Paint> 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73231-104">These include the <xref:System.Windows.Forms.Control.Paint> event, which causes a control to be drawn, events related to displaying a window, such as the <xref:System.Windows.Forms.Control.Resize> and <xref:System.Windows.Forms.Control.Layout> events, and low-level mouse and keyboard events.</span></span> <span data-ttu-id="73231-105">일부 하위 수준 이벤트는 <xref:System.Windows.Forms.Control.Click> 및 <xref:System.Windows.Forms.Control.DoubleClick>와 같은 의미 체계 이벤트에 <xref:System.Windows.Forms.Control> 하 여 합성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73231-105">Some low-level events are synthesized by <xref:System.Windows.Forms.Control> into semantic events such as <xref:System.Windows.Forms.Control.Click> and <xref:System.Windows.Forms.Control.DoubleClick>.</span></span> <span data-ttu-id="73231-106">상속 된 이벤트에 대 한 자세한 내용은 <xref:System.Windows.Forms.Control>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73231-106">For details about inherited events, see <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="73231-107">사용자 지정 컨트롤이 상속된 이벤트 기능을 재정의해야 하는 경우 대리자를 연결하는 대신 상속된 `On`*EventName* 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="73231-107">If your custom control needs to override inherited event functionality, override the inherited `On`*EventName* method instead of attaching a delegate.</span></span> <span data-ttu-id="73231-108">.NET Framework에서 이벤트 모델에 익숙하지 않다면 [구성 요소에서 이벤트 발생 시키기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73231-108">If you are not familiar with the event model in the .NET Framework, see [Raising Events from a Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73231-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73231-109">See also</span></span>

- [<span data-ttu-id="73231-110">OnPaint 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="73231-110">Overriding the OnPaint Method</span></span>](overriding-the-onpaint-method.md)
- [<span data-ttu-id="73231-111">사용자 입력 처리</span><span class="sxs-lookup"><span data-stu-id="73231-111">Handling User Input</span></span>](handling-user-input.md)
- [<span data-ttu-id="73231-112">이벤트 정의</span><span class="sxs-lookup"><span data-stu-id="73231-112">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="73231-113">이벤트</span><span class="sxs-lookup"><span data-stu-id="73231-113">Events</span></span>](../../../standard/events/index.md)
