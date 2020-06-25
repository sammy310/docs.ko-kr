---
title: '방법: 디자인 타임에 Windows Form의 컨트롤에 대한 도구 설명 설정'
description: Visual Studio에서 프로그래밍 방식으로 또는 Windows Forms 디자이너 컨트롤에 대 한 도구 설명을 설정 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 15134b38d11de30d0e6a2f998f6ea266affc40d7
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325975"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="0efc5-103">방법: 디자인 타임에 Windows Form의 컨트롤에 대 한 도구 설명 설정</span><span class="sxs-lookup"><span data-stu-id="0efc5-103">How to: Set ToolTips for controls on a Windows Form at design time</span></span>

<span data-ttu-id="0efc5-104"><xref:System.Windows.Forms.ToolTip>Visual Studio의 코드 또는 Windows Forms 디자이너에서 문자열을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0efc5-104">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="0efc5-105">구성 요소에 대 한 자세한 내용은 <xref:System.Windows.Forms.ToolTip> [도구 설명 구성 요소 개요](tooltip-component-overview-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0efc5-105">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md).</span></span>

## <a name="set-a-tooltip-programmatically"></a><span data-ttu-id="0efc5-106">프로그래밍 방식으로 도구 설명 설정</span><span class="sxs-lookup"><span data-stu-id="0efc5-106">Set a ToolTip programmatically</span></span>

1. <span data-ttu-id="0efc5-107">도구 설명을 표시 하는 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0efc5-107">Add the control that will display the ToolTip.</span></span>

2. <span data-ttu-id="0efc5-108"><xref:System.Windows.Forms.ToolTip.SetToolTip%2A>구성 요소의 메서드를 사용 <xref:System.Windows.Forms.ToolTip> 합니다.</span><span class="sxs-lookup"><span data-stu-id="0efc5-108">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

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

## <a name="set-a-tooltip-in-the-designer"></a><span data-ttu-id="0efc5-109">디자이너에서 도구 설명 설정</span><span class="sxs-lookup"><span data-stu-id="0efc5-109">Set a ToolTip in the designer</span></span>

1. <span data-ttu-id="0efc5-110">Visual Studio에서 <xref:System.Windows.Forms.ToolTip> 구성 요소를 폼에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0efc5-110">In Visual Studio, add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>

2. <span data-ttu-id="0efc5-111">도구 설명이 표시 되는 컨트롤을 선택 하거나 폼에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0efc5-111">Select the control that will display the ToolTip, or add it to the form.</span></span>

3. <span data-ttu-id="0efc5-112">**속성** 창에서 **ToolTip1 값에 대 한 도구 설명을** 적절 한 텍스트 문자열로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0efc5-112">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>

### <a name="to-remove-a-tooltip-programmatically"></a><span data-ttu-id="0efc5-113">프로그래밍 방식으로 도구 설명을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="0efc5-113">To remove a ToolTip programmatically</span></span>

1. <span data-ttu-id="0efc5-114"><xref:System.Windows.Forms.ToolTip.SetToolTip%2A>구성 요소의 메서드를 사용 <xref:System.Windows.Forms.ToolTip> 합니다.</span><span class="sxs-lookup"><span data-stu-id="0efc5-114">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

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

## <a name="remove-a-tooltip-in-the-designer"></a><span data-ttu-id="0efc5-115">디자이너에서 도구 설명 제거</span><span class="sxs-lookup"><span data-stu-id="0efc5-115">Remove a ToolTip in the designer</span></span>

1. <span data-ttu-id="0efc5-116">Visual Studio에서 도구 설명을 표시 하는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0efc5-116">In Visual Studio, select the control that is displaying the ToolTip.</span></span>

2. <span data-ttu-id="0efc5-117">**속성** 창에서 **ToolTip1의 도구 설명**에 있는 텍스트를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0efc5-117">In the **Properties** window, delete the text in the **ToolTip on ToolTip1**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0efc5-118">참조</span><span class="sxs-lookup"><span data-stu-id="0efc5-118">See also</span></span>

- [<span data-ttu-id="0efc5-119">ToolTip 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="0efc5-119">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="0efc5-120">방법: Windows Forms ToolTip 구성 요소의 지연 변경</span><span class="sxs-lookup"><span data-stu-id="0efc5-120">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [<span data-ttu-id="0efc5-121">ToolTip 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0efc5-121">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
