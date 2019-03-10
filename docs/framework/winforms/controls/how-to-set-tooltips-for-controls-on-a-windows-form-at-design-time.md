---
title: '방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 541e50a8ee9c5338acc7c5e347549fd03a0f6323
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710721"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="43e31-102">방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정</span><span class="sxs-lookup"><span data-stu-id="43e31-102">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>
<span data-ttu-id="43e31-103">설정할 수 있습니다는 <xref:System.Windows.Forms.ToolTip> Windows Forms 디자이너 또는 코드에서 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="43e31-103">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer.</span></span> <span data-ttu-id="43e31-104">에 대 한 자세한 내용은 합니다 <xref:System.Windows.Forms.ToolTip> 구성 요소를 참조 하세요 [ToolTip 구성 요소 개요](tooltip-component-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="43e31-104">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43e31-105">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43e31-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="43e31-106">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43e31-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="43e31-107">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="43e31-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-a-tooltip-programmatically"></a><span data-ttu-id="43e31-108">프로그래밍 방식으로 도구 설명을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="43e31-108">To set a ToolTip programmatically</span></span>  
  
1.  <span data-ttu-id="43e31-109">도구 설명이 표시 되는 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="43e31-109">Add the control that will display the ToolTip.</span></span>  
  
2.  <span data-ttu-id="43e31-110">사용 된 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 메서드의 <xref:System.Windows.Forms.ToolTip> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="43e31-110">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### <a name="to-set-a-tooltip-in-the-designer"></a><span data-ttu-id="43e31-111">디자이너에서 도구 설명을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="43e31-111">To set a ToolTip in the designer</span></span>  
  
1.  <span data-ttu-id="43e31-112">폼에 <xref:System.Windows.Forms.ToolTip> 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="43e31-112">Add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>  
  
2.  <span data-ttu-id="43e31-113">도구 설명 표시 되거나 폼에 추가 하는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="43e31-113">Select the control that will display the ToolTip, or add it to the form.</span></span>  
  
3.  <span data-ttu-id="43e31-114">에 **속성** 창에서 **ToolTip1의 도구 설명** 텍스트 문자열을 적절 한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="43e31-114">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>  

### <a name="to-remove-a-tooltip-programmatically"></a><span data-ttu-id="43e31-115">도구 설명에 프로그래밍 방식으로 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="43e31-115">To remove a ToolTip programmatically</span></span>  
  
1.  <span data-ttu-id="43e31-116">사용 된 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 메서드의 <xref:System.Windows.Forms.ToolTip> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="43e31-116">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>  
  
    ```vb  
    ' In this example, Button1 is the control displaying the ToolTip.  
    ToolTip1.SetToolTip(Button1, Nothing)  
    ```  
  
    ```csharp  
    // In this example, button1 is the control displaying the ToolTip.  
    toolTip1.SetToolTip(button1, null);  
    ```  
  
    ```cpp  
    // In this example, button1 is the control displaying the ToolTip.  
    toolTip1->SetToolTip(button1, NULL);  
    ```  
  
### <a name="to-remove-a-tooltip-in-the-designer"></a><span data-ttu-id="43e31-117">디자이너에서 도구 설명을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="43e31-117">To remove a ToolTip in the designer</span></span>  
  
1.  <span data-ttu-id="43e31-118">도구 설명에 표시 되는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="43e31-118">Select the control that is displaying the ToolTip.</span></span>  
  
2.  <span data-ttu-id="43e31-119">에 **속성** 창에서 텍스트를 삭제 합니다 **ToolTip1의 도구 설명**합니다.</span><span class="sxs-lookup"><span data-stu-id="43e31-119">In the **Properties** window, delete the text in the **ToolTip on ToolTip1**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="43e31-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="43e31-120">See also</span></span>
- [<span data-ttu-id="43e31-121">ToolTip 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="43e31-121">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="43e31-122">방법: Windows Forms ToolTip 구성 요소의 지연 변경</span><span class="sxs-lookup"><span data-stu-id="43e31-122">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [<span data-ttu-id="43e31-123">ToolTip 구성 요소</span><span class="sxs-lookup"><span data-stu-id="43e31-123">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
