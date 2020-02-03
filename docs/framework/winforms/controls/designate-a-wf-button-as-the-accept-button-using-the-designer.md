---
title: 디자이너를 사용 하 여 단추를 적용 단추로 지정
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 27a5de51f8c5b2c84cc205e09ac1a2179c315752
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746069"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a><span data-ttu-id="4b496-102">방법: 디자이너를 사용하여 Windows Forms 단추를 적용 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="4b496-102">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>
<span data-ttu-id="4b496-103">Windows Form에서 기본 단추가 라고도 하는 허용 단추로 <xref:System.Windows.Forms.Button> 컨트롤을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b496-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="4b496-104">사용자가 ENTER 키를 누를 때마다 폼의 다른 컨트롤에 포커스가 있는지 여부에 관계 없이 기본 단추가 클릭 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b496-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="4b496-105">이에 대 한 예외는 포커스가 있는 컨트롤이 다른 단추인 경우입니다 .이 경우 포커스가 있는 단추를 클릭 하거나 여러 줄 텍스트 상자를 클릭 하거나 ENTER 키를 트래핑 하는 사용자 지정 컨트롤을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b496-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>

## <a name="to-designate-the-accept-button"></a><span data-ttu-id="4b496-106">수락 단추를 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="4b496-106">To designate the accept button</span></span>

1. <span data-ttu-id="4b496-107">단추가 있는 폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b496-107">Select the form on which the button resides.</span></span>

2. <span data-ttu-id="4b496-108">**속성** 창에서 양식의 <xref:System.Windows.Forms.Form.AcceptButton%2A> 속성을 <xref:System.Windows.Forms.Button> 컨트롤의 이름으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b496-108">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b496-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b496-109">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="4b496-110">Button 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="4b496-110">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="4b496-111">Windows Forms Button 컨트롤 선택 방법</span><span class="sxs-lookup"><span data-stu-id="4b496-111">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="4b496-112">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="4b496-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="4b496-113">방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="4b496-113">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [<span data-ttu-id="4b496-114">Button 컨트롤</span><span class="sxs-lookup"><span data-stu-id="4b496-114">Button Control</span></span>](button-control-windows-forms.md)
