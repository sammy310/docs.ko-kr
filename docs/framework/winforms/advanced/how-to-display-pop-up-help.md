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
ms.openlocfilehash: bf3bcbff0cd6f3bbf71e96e748cb170d5ce68dfc
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211409"
---
# <a name="how-to-display-pop-up-help"></a><span data-ttu-id="151f4-102">방법: 팝업 도움말 표시</span><span class="sxs-lookup"><span data-stu-id="151f4-102">How to: Display pop-up Help</span></span>

<span data-ttu-id="151f4-103">통해 Windows Forms에 도움말을 표시 하는 한 가지 방법은는 **도움말** 단추를 통해 액세스할 수 있는 제목 표시줄의 오른쪽에 있는 <xref:System.Windows.Forms.Form.HelpButton%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="151f4-103">One way to display Help on Windows Forms is through the **Help** button, located on the right side of the title bar, accessible through the <xref:System.Windows.Forms.Form.HelpButton%2A> property.</span></span> <span data-ttu-id="151f4-104">이 도움말 표시 유형은 대화 상자에서 사용하기에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="151f4-104">This type of Help display is well-suited for use with dialog boxes.</span></span> <span data-ttu-id="151f4-105">모달 대화 상자를 먼저 닫아야 다른 창으로 포커스를 이동할 수 있으므로 모달 형식으로 표시되는 대화 상자(<xref:System.Windows.Forms.Form.ShowDialog%2A> 메서드 사용)에서 외부 도움말 시스템을 가져오려면 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="151f4-105">Dialog boxes shown modally (with the <xref:System.Windows.Forms.Form.ShowDialog%2A> method) have trouble bringing up external Help systems, because modal dialog boxes need to be closed before focus can shift to another window.</span></span> <span data-ttu-id="151f4-106">또한 사용 하 여는 **도움말** 단추는 필요 없습니다 **최소화** 단추 또는 **최대화** 단추가 제목 표시줄에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="151f4-106">Additionally, using the **Help** button requires that there is no **Minimize** button or **Maximize** button shown in the title bar.</span></span> <span data-ttu-id="151f4-107">이 표준 대화 상자 규칙, 일반적으로 폼에는 있지만 **최소화** 하 고 **최대화** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="151f4-107">This is a standard dialog-box convention, whereas forms usually have **Minimize** and **Maximize** buttons.</span></span>

<span data-ttu-id="151f4-108">사용할 수도 있습니다는 <xref:System.Windows.Forms.HelpProvider> 팝업 도움말을 구현한 경우에 파일에 컨트롤을 도움말 시스템에서 연결 하려면 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="151f4-108">You can also use the <xref:System.Windows.Forms.HelpProvider> component to link controls to files in a Help system, even if you have implemented pop-up Help.</span></span> <span data-ttu-id="151f4-109">자세한 내용은 [는 Windows 응용 프로그램에서 도움말 제공](how-to-provide-help-in-a-windows-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="151f4-109">For more information, see [Providing Help in a Windows Application](how-to-provide-help-in-a-windows-application.md).</span></span>

## <a name="display-pop-up-help"></a><span data-ttu-id="151f4-110">팝업 도움말 표시</span><span class="sxs-lookup"><span data-stu-id="151f4-110">Display pop-up Help</span></span>

1. <span data-ttu-id="151f4-111">Visual Studio에서 끌어를 [HelpProvider](../controls/helpprovider-component-windows-forms.md) 폼에 도구 상자에서 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="151f4-111">In Visual Studio, drag a [HelpProvider](../controls/helpprovider-component-windows-forms.md) component from the Toolbox to your form.</span></span>

   <span data-ttu-id="151f4-112">Windows Forms 디자이너 아래쪽의 트레이에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="151f4-112">It will sit in the tray at the bottom of the Windows Forms Designer.</span></span>

2. <span data-ttu-id="151f4-113">속성 창에서 <xref:System.Windows.Forms.Form.HelpButton%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="151f4-113">In the Properties window, set the <xref:System.Windows.Forms.Form.HelpButton%2A> property to `true`.</span></span> <span data-ttu-id="151f4-114">그러면 폼의 제목 표시줄 오른쪽에 물음표가 있는 단추가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="151f4-114">This will display a button with a question mark in it on the right side of the title bar of the form.</span></span>

3. <span data-ttu-id="151f4-115"><xref:System.Windows.Forms.Form.HelpButton%2A>이 표시되려면 폼의 <xref:System.Windows.Forms.Form.MinimizeBox%2A> 및 <xref:System.Windows.Forms.Form.MaximizeBox%2A> 속성을 `false`로 설정하고 <xref:System.Windows.Forms.Form.ControlBox%2A> 속성을 `true`로 설정하고 <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 속성을 <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> 또는 <xref:System.Windows.Forms.FormBorderStyle.Sizable> 값 중 하나로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="151f4-115">In order for the <xref:System.Windows.Forms.Form.HelpButton%2A> to display, the form's <xref:System.Windows.Forms.Form.MinimizeBox%2A> and <xref:System.Windows.Forms.Form.MaximizeBox%2A> properties must be set to `false`, the <xref:System.Windows.Forms.Form.ControlBox%2A> property set to `true`, and the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to one of the following values: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> or <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span></span>

4. <span data-ttu-id="151f4-116">폼에서 도움말을 표시할 컨트롤을 선택하고 속성 창에서 도움말 문자열을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="151f4-116">Select the control for which you want to show help on your form and set the Help string in the Properties window.</span></span> <span data-ttu-id="151f4-117">비슷하게 창에 표시 되는 텍스트 문자열이 며이 [ToolTip](../controls/tooltip-component-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="151f4-117">This is the string of text that will be displayed in a window similar to a [ToolTip](../controls/tooltip-component-windows-forms.md).</span></span>

5. <span data-ttu-id="151f4-118">**F5**키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="151f4-118">Press **F5**.</span></span>

6. <span data-ttu-id="151f4-119">키를 눌러 합니다 **도움말** 제목 표시줄에 단추 및 도움말 문자열을 설정 하는 컨트롤을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="151f4-119">Press the **Help** button on the title bar and click the control on which you set the Help string.</span></span>

## <a name="see-also"></a><span data-ttu-id="151f4-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="151f4-120">See also</span></span>

- [<span data-ttu-id="151f4-121">ToolTip을 사용한 컨트롤 도움말</span><span class="sxs-lookup"><span data-stu-id="151f4-121">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)
- [<span data-ttu-id="151f4-122">Windows Forms에 사용자 도움말 통합</span><span class="sxs-lookup"><span data-stu-id="151f4-122">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="151f4-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="151f4-123">Windows Forms</span></span>](../index.md)
