---
title: '방법: 디자인 타임에 Windows Form의 컨트롤에 대한 도구 설명 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 0d6725fc1a00826870e6400bffce63a1788e802c
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211693"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="db15f-102">방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정</span><span class="sxs-lookup"><span data-stu-id="db15f-102">How to: Set ToolTips for controls on a Windows Form at design time</span></span>

<span data-ttu-id="db15f-103">설정할 수 있습니다는 <xref:System.Windows.Forms.ToolTip> Visual Studio에서 Windows Forms 디자이너 또는 코드에서 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="db15f-103">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="db15f-104">에 대 한 자세한 내용은 합니다 <xref:System.Windows.Forms.ToolTip> 구성 요소를 참조 하세요 [ToolTip 구성 요소 개요](tooltip-component-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="db15f-104">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md).</span></span>

## <a name="set-a-tooltip-programmatically"></a><span data-ttu-id="db15f-105">프로그래밍 방식으로 도구 설명 설정</span><span class="sxs-lookup"><span data-stu-id="db15f-105">Set a ToolTip programmatically</span></span>

1. <span data-ttu-id="db15f-106">도구 설명이 표시 되는 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="db15f-106">Add the control that will display the ToolTip.</span></span>

2. <span data-ttu-id="db15f-107">사용 된 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 메서드의 <xref:System.Windows.Forms.ToolTip> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="db15f-107">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

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

## <a name="set-a-tooltip-in-the-designer"></a><span data-ttu-id="db15f-108">디자이너에서 도구 설명 설정</span><span class="sxs-lookup"><span data-stu-id="db15f-108">Set a ToolTip in the designer</span></span>

1. <span data-ttu-id="db15f-109">Visual Studio에서 추가 <xref:System.Windows.Forms.ToolTip> 폼에 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="db15f-109">In Visual Studio, add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>

2. <span data-ttu-id="db15f-110">도구 설명 표시 되거나 폼에 추가 하는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="db15f-110">Select the control that will display the ToolTip, or add it to the form.</span></span>

3. <span data-ttu-id="db15f-111">에 **속성** 창에서 **ToolTip1의 도구 설명** 텍스트 문자열을 적절 한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="db15f-111">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>

### <a name="to-remove-a-tooltip-programmatically"></a><span data-ttu-id="db15f-112">도구 설명에 프로그래밍 방식으로 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="db15f-112">To remove a ToolTip programmatically</span></span>

1. <span data-ttu-id="db15f-113">사용 된 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 메서드의 <xref:System.Windows.Forms.ToolTip> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="db15f-113">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

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

## <a name="remove-a-tooltip-in-the-designer"></a><span data-ttu-id="db15f-114">디자이너에서 도구 설명을 제거합니다</span><span class="sxs-lookup"><span data-stu-id="db15f-114">Remove a ToolTip in the designer</span></span>

1. <span data-ttu-id="db15f-115">Visual Studio에서 도구 설명에 표시 되는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="db15f-115">In Visual Studio, select the control that is displaying the ToolTip.</span></span>

2. <span data-ttu-id="db15f-116">에 **속성** 창에서 텍스트를 삭제 합니다 **ToolTip1의 도구 설명**합니다.</span><span class="sxs-lookup"><span data-stu-id="db15f-116">In the **Properties** window, delete the text in the **ToolTip on ToolTip1**.</span></span>

## <a name="see-also"></a><span data-ttu-id="db15f-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="db15f-117">See also</span></span>

- [<span data-ttu-id="db15f-118">ToolTip 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="db15f-118">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="db15f-119">방법: Windows Forms ToolTip 구성 요소의 지연 변경</span><span class="sxs-lookup"><span data-stu-id="db15f-119">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [<span data-ttu-id="db15f-120">ToolTip 구성 요소</span><span class="sxs-lookup"><span data-stu-id="db15f-120">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
