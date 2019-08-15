---
title: '방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: cc352f15fb1e8b531cd0f9b298b2db4ce649d3cf
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039644"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a><span data-ttu-id="8a363-102">방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="8a363-102">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>
<span data-ttu-id="8a363-103">Windows Form에서 <xref:System.Windows.Forms.Button> 컨트롤이 취소 단추가 되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="8a363-104">폼의 다른 컨트롤에 포커스가 있는지 여부에 관계 없이 사용자가 ESC 키를 누를 때마다 취소 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="8a363-105">이러한 단추는 일반적으로 사용자가 작업을 커밋하지 않고도 신속 하 게 작업을 종료할 수 있도록 프로그래밍 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>

## <a name="to-designate-the-cancel-button"></a><span data-ttu-id="8a363-106">취소 단추를 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="8a363-106">To designate the cancel button</span></span>

1. <span data-ttu-id="8a363-107">단추가 있는 폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-107">Select the form on which the button resides.</span></span>

2. <span data-ttu-id="8a363-108">**속성** 창에서 폼의 <xref:System.Windows.Forms.Form.CancelButton%2A> 속성을 <xref:System.Windows.Forms.Button> 컨트롤의 이름으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-108">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a363-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="8a363-109">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="8a363-110">Button 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="8a363-110">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="8a363-111">Windows Forms Button 컨트롤 선택 방법</span><span class="sxs-lookup"><span data-stu-id="8a363-111">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="8a363-112">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="8a363-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="8a363-113">방법: 디자이너를 사용 하 여 Windows Forms 단추를 적용 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="8a363-113">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [<span data-ttu-id="8a363-114">Button 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8a363-114">Button Control</span></span>](button-control-windows-forms.md)
