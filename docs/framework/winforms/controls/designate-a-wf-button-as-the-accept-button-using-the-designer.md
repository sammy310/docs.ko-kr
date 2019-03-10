---
title: '방법: Windows Forms 단추를 디자이너를 사용 하 여 적용 단추로 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 61f0c99560d008cc10c94403ac936e5b97267d3a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707653"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a><span data-ttu-id="c6d3c-102">방법: Windows Forms 단추를 디자이너를 사용 하 여 적용 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="c6d3c-102">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>
<span data-ttu-id="c6d3c-103">모든 Windows Form에 지정할 수 있습니다는 <xref:System.Windows.Forms.Button> 컨트롤을 적용 단추가 기본 단추 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d3c-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="c6d3c-104">ENTER 키를 누를 때마다 폼에서 다른 컨트롤에 포커스가 관계 없이 기본 단추 클릭 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6d3c-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="c6d3c-105">이 하는 경우 포커스가 있는 컨트롤은 다른 단추에 대 한 예외-포커스가 있는 단추를 클릭 하는 경우-여러 줄 텍스트 상자 또는 ENTER 키를 트래핑 하는 사용자 지정 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="c6d3c-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6d3c-106">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6d3c-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c6d3c-107">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d3c-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c6d3c-108">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6d3c-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="c6d3c-109">적용 단추를 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="c6d3c-109">To designate the accept button</span></span>  
  
1.  <span data-ttu-id="c6d3c-110">단추 상주 하는 폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d3c-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="c6d3c-111">에 **속성** 창에서 양식의 설정 <xref:System.Windows.Forms.Form.AcceptButton%2A> 속성을를 <xref:System.Windows.Forms.Button> 컨트롤의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c6d3c-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6d3c-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="c6d3c-112">See also</span></span>
- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="c6d3c-113">Button 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="c6d3c-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="c6d3c-114">Windows Forms Button 컨트롤 선택 방법</span><span class="sxs-lookup"><span data-stu-id="c6d3c-114">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="c6d3c-115">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="c6d3c-115">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="c6d3c-116">방법: Windows Forms 단추를 디자이너를 사용 하는 취소 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="c6d3c-116">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [<span data-ttu-id="c6d3c-117">Button 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c6d3c-117">Button Control</span></span>](button-control-windows-forms.md)
