---
title: '방법: 팝업 도움말 표시'
ms.date: 03/30/2017
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
ms.openlocfilehash: f805840ea3b1a8aef6a289dba064c468a4da0cb0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331483"
---
# <a name="how-to-display-pop-up-help"></a><span data-ttu-id="6e099-102">방법: 팝업 도움말 표시</span><span class="sxs-lookup"><span data-stu-id="6e099-102">How to: Display Pop-up Help</span></span>
<span data-ttu-id="6e099-103">통해 Windows Forms에 도움말을 표시 하는 한 가지 방법은는 **도움말** 단추를 통해 액세스할 수 있는 제목 표시줄의 오른쪽에 있는 <xref:System.Windows.Forms.Form.HelpButton%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-103">One way to display Help on Windows Forms is through the **Help** button, located on the right side of the title bar, accessible through the <xref:System.Windows.Forms.Form.HelpButton%2A> property.</span></span> <span data-ttu-id="6e099-104">이 도움말 표시 유형은 대화 상자에서 사용하기에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-104">This type of Help display is well-suited for use with dialog boxes.</span></span> <span data-ttu-id="6e099-105">모달 대화 상자를 먼저 닫아야 다른 창으로 포커스를 이동할 수 있으므로 모달 형식으로 표시되는 대화 상자(<xref:System.Windows.Forms.Form.ShowDialog%2A> 메서드 사용)에서 외부 도움말 시스템을 가져오려면 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-105">Dialog boxes shown modally (with the <xref:System.Windows.Forms.Form.ShowDialog%2A> method) have trouble bringing up external Help systems, because modal dialog boxes need to be closed before focus can shift to another window.</span></span> <span data-ttu-id="6e099-106">또한 사용 하 여는 **도움말** 단추는 필요 없습니다 **최소화** 단추 또는 **최대화** 단추가 제목 표시줄에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-106">Additionally, using the **Help** button requires that there is no **Minimize** button or **Maximize** button shown in the title bar.</span></span> <span data-ttu-id="6e099-107">이 표준 대화 상자 규칙, 일반적으로 폼에는 있지만 **최소화** 하 고 **최대화** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-107">This is a standard dialog-box convention, whereas forms usually have **Minimize** and **Maximize** buttons.</span></span>  
  
 <span data-ttu-id="6e099-108">또한 팝업 도움말을 구현한 경우에도 <xref:System.Windows.Forms.HelpProvider> 구성 요소를 사용하여 컨트롤을 도움말 시스템의 파일에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-108">Be aware that you can also use the <xref:System.Windows.Forms.HelpProvider> component to link controls to files in a Help system, even if you have implemented pop-up Help.</span></span> <span data-ttu-id="6e099-109">자세한 내용은 [는 Windows 응용 프로그램에서 도움말 제공](how-to-provide-help-in-a-windows-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-109">For more information, see [Providing Help in a Windows Application](how-to-provide-help-in-a-windows-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e099-110">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6e099-111">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6e099-112">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e099-112">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-display-pop-up-help"></a><span data-ttu-id="6e099-113">팝업 도움말을 표시하려면</span><span class="sxs-lookup"><span data-stu-id="6e099-113">To display pop-up Help</span></span>  
  
1. <span data-ttu-id="6e099-114">끌어서를 [HelpProvider](../controls/helpprovider-component-windows-forms.md) 폼에 도구 상자에서 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-114">Drag a [HelpProvider](../controls/helpprovider-component-windows-forms.md) component from the Toolbox to your form.</span></span>  
  
     <span data-ttu-id="6e099-115">Windows Forms 디자이너 아래쪽의 트레이에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-115">It will sit in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
2. <span data-ttu-id="6e099-116">속성 창에서 <xref:System.Windows.Forms.Form.HelpButton%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-116">In the Properties window, set the <xref:System.Windows.Forms.Form.HelpButton%2A> property to `true`.</span></span> <span data-ttu-id="6e099-117">그러면 폼의 제목 표시줄 오른쪽에 물음표가 있는 단추가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-117">This will display a button with a question mark in it on the right side of the title bar of the form.</span></span>  
  
3. <span data-ttu-id="6e099-118"><xref:System.Windows.Forms.Form.HelpButton%2A>이 표시되려면 폼의 <xref:System.Windows.Forms.Form.MinimizeBox%2A> 및 <xref:System.Windows.Forms.Form.MaximizeBox%2A> 속성을 `false`로 설정하고 <xref:System.Windows.Forms.Form.ControlBox%2A> 속성을 `true`로 설정하고 <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 속성을 <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> 또는 <xref:System.Windows.Forms.FormBorderStyle.Sizable> 값 중 하나로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-118">In order for the <xref:System.Windows.Forms.Form.HelpButton%2A> to display, the form's <xref:System.Windows.Forms.Form.MinimizeBox%2A> and <xref:System.Windows.Forms.Form.MaximizeBox%2A> properties must be set to `false`, the <xref:System.Windows.Forms.Form.ControlBox%2A> property set to `true`, and the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to one of the following values: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> or <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span></span>  
  
4. <span data-ttu-id="6e099-119">폼에서 도움말을 표시할 컨트롤을 선택하고 속성 창에서 도움말 문자열을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-119">Select the control for which you want to show help on your form and set the Help string in the Properties window.</span></span> <span data-ttu-id="6e099-120">비슷하게 창에 표시 되는 텍스트 문자열이 며이 [ToolTip](../controls/tooltip-component-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-120">This is the string of text that will be displayed in a window similar to a [ToolTip](../controls/tooltip-component-windows-forms.md).</span></span>  
  
5. <span data-ttu-id="6e099-121">**F5**키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-121">Press **F5**.</span></span>  
  
6. <span data-ttu-id="6e099-122">키를 눌러 합니다 **도움말** 제목 표시줄에 단추 및 도움말 문자열을 설정 하는 컨트롤을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e099-122">Press the **Help** button on the title bar and click the control on which you set the Help string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e099-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="6e099-123">See also</span></span>

- [<span data-ttu-id="6e099-124">ToolTip을 사용한 컨트롤 도움말</span><span class="sxs-lookup"><span data-stu-id="6e099-124">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)
- [<span data-ttu-id="6e099-125">Windows Forms에 사용자 도움말 통합</span><span class="sxs-lookup"><span data-stu-id="6e099-125">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="6e099-126">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6e099-126">Windows Forms</span></span>](../index.md)
