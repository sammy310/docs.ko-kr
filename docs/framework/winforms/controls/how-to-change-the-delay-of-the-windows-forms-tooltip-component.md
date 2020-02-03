---
title: ToolTip 구성 요소의 지연 변경
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: 8ab0b0760e8c82d752eaada19f14cae57fa63fdc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746581"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a><span data-ttu-id="d8db9-102">방법: Windows Forms ToolTip 구성 요소의 지연 변경</span><span class="sxs-lookup"><span data-stu-id="d8db9-102">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>
<span data-ttu-id="d8db9-103">Windows Forms <xref:System.Windows.Forms.ToolTip> 구성 요소에 대해 설정할 수 있는 지연 값은 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8db9-103">There are multiple delay values that you can set for a Windows Forms <xref:System.Windows.Forms.ToolTip> component.</span></span> <span data-ttu-id="d8db9-104">이러한 모든 속성의 측정 단위는 밀리초입니다.</span><span class="sxs-lookup"><span data-stu-id="d8db9-104">The unit of measure for all these properties is milliseconds.</span></span> <span data-ttu-id="d8db9-105"><xref:System.Windows.Forms.ToolTip.InitialDelay%2A> 속성은 사용자가 연결 된 컨트롤에서 표시 되는 도구 설명 문자열을 가리켜야 하는 기간을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8db9-105">The <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> property determines how long the user must point at the associated control for the ToolTip string to appear.</span></span> <span data-ttu-id="d8db9-106"><xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> 속성은 마우스가 도구 설명에 연결 된 컨트롤 하나에서 다른 컨트롤로 이동할 때 이후의 도구 설명 문자열이 표시 되는 데 걸리는 시간 (밀리초)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8db9-106">The <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> property sets the number of milliseconds it takes for subsequent ToolTip strings to appear as the mouse moves from one ToolTip-associated control to another.</span></span> <span data-ttu-id="d8db9-107"><xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> 속성은 도구 설명 문자열이 표시 되는 기간을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8db9-107">The <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> property determines the length of time the ToolTip string is shown.</span></span> <span data-ttu-id="d8db9-108">이러한 값은 개별적으로 설정 하거나 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 속성의 값을 설정 하 여 설정할 수 있습니다. 다른 지연 속성은 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 속성에 할당 된 값을 기준으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8db9-108">You can set these values individually, or by setting the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property; the other delay properties are set based on the value assigned to the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property.</span></span> <span data-ttu-id="d8db9-109">예를 들어 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> N 값으로 설정 된 경우 <xref:System.Windows.Forms.ToolTip.InitialDelay%2A>가 N으로 설정 되 고, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 5 (또는 N/5)로 나눈 값으로 설정 되 고, <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A>가 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 속성 값 (또는 5N)의 5 배 값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8db9-109">For example, when <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> is set to a value N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> is set to N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> is set to the value of <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> divided by five (or N/5), and <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> is set to a value that is five times the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property (or 5N).</span></span>  
  
### <a name="to-set-the-delay"></a><span data-ttu-id="d8db9-110">지연 시간을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d8db9-110">To set the delay</span></span>  
  
1. <span data-ttu-id="d8db9-111">이 예제에 표시 된 대로 다음 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8db9-111">Set the following properties as shown in this example.</span></span>  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d8db9-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8db9-112">See also</span></span>

- [<span data-ttu-id="d8db9-113">ToolTip 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="d8db9-113">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="d8db9-114">방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정</span><span class="sxs-lookup"><span data-stu-id="d8db9-114">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [<span data-ttu-id="d8db9-115">ToolTip 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d8db9-115">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
