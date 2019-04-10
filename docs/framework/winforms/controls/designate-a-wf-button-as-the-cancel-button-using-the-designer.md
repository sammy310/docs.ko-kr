---
title: '방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: be0847d1837ec85ed9d82dc7cc879d0cffa19cd6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156223"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a><span data-ttu-id="af1f4-102">방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="af1f4-102">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>
<span data-ttu-id="af1f4-103">모든 Windows Form에 지정할 수 있습니다는 <xref:System.Windows.Forms.Button> 취소 단추를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af1f4-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="af1f4-104">사용자에 관계 없이 폼에서 다른 컨트롤에 포커스가 ESC 키를 누를 때마다 취소 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="af1f4-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="af1f4-105">신속 하 게 조치를 커밋하지 않고 작업을 종료할 수 있도록 프로그래밍할 때 일반적으로 이러한 단추를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="af1f4-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af1f4-106">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af1f4-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="af1f4-107">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af1f4-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="af1f4-108">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af1f4-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="af1f4-109">취소 단추를 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="af1f4-109">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="af1f4-110">단추 상주 하는 폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af1f4-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="af1f4-111">에 **속성** 창에서 양식의 설정 <xref:System.Windows.Forms.Form.CancelButton%2A> 속성을를 <xref:System.Windows.Forms.Button> 컨트롤의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="af1f4-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af1f4-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="af1f4-112">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="af1f4-113">Button 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="af1f4-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="af1f4-114">Windows Forms Button 컨트롤 선택 방법</span><span class="sxs-lookup"><span data-stu-id="af1f4-114">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="af1f4-115">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="af1f4-115">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="af1f4-116">방법: 디자이너를 사용하여 Windows Forms 단추를 적용 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="af1f4-116">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [<span data-ttu-id="af1f4-117">Button 컨트롤</span><span class="sxs-lookup"><span data-stu-id="af1f4-117">Button Control</span></span>](button-control-windows-forms.md)
