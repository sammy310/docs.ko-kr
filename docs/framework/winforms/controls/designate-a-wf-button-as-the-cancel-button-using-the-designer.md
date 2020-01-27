---
title: 디자이너를 사용 하 여 단추를 취소 단추로 지정
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: 95d1139b6e339055f944ad0b0967a6d91283d49e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746057"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a><span data-ttu-id="f94c3-102">방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="f94c3-102">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>
<span data-ttu-id="f94c3-103">Windows Form에서 <xref:System.Windows.Forms.Button> 컨트롤이 취소 단추가 되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f94c3-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="f94c3-104">폼의 다른 컨트롤에 포커스가 있는지 여부에 관계 없이 사용자가 ESC 키를 누를 때마다 취소 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f94c3-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="f94c3-105">이러한 단추는 일반적으로 사용자가 작업을 커밋하지 않고도 신속 하 게 작업을 종료할 수 있도록 프로그래밍 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f94c3-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>

## <a name="to-designate-the-cancel-button"></a><span data-ttu-id="f94c3-106">취소 단추를 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="f94c3-106">To designate the cancel button</span></span>

1. <span data-ttu-id="f94c3-107">단추가 있는 폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f94c3-107">Select the form on which the button resides.</span></span>

2. <span data-ttu-id="f94c3-108">**속성** 창에서 양식의 <xref:System.Windows.Forms.Form.CancelButton%2A> 속성을 <xref:System.Windows.Forms.Button> 컨트롤의 이름으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f94c3-108">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>

## <a name="see-also"></a><span data-ttu-id="f94c3-109">참조</span><span class="sxs-lookup"><span data-stu-id="f94c3-109">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="f94c3-110">Button 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="f94c3-110">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="f94c3-111">Windows Forms Button 컨트롤 선택 방법</span><span class="sxs-lookup"><span data-stu-id="f94c3-111">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="f94c3-112">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="f94c3-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="f94c3-113">방법: 디자이너를 사용하여 Windows Forms 단추를 적용 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="f94c3-113">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [<span data-ttu-id="f94c3-114">Button 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f94c3-114">Button Control</span></span>](button-control-windows-forms.md)
