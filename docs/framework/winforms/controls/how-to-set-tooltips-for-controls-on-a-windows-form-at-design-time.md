---
title: '방법: 디자인 타임에 Windows Form의 컨트롤에 대한 도구 설명 설정'
description: Visual Studio에서 프로그래밍 방식으로 또는 Windows Forms 디자이너에서 컨트롤에 대 한 도구 설명을 설정 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 144ba5b6bffb4a538e345f7b2df4a453fc6fd63d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618027"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>방법: 디자인 타임에 Windows Form의 컨트롤에 대 한 도구 설명 설정

<xref:System.Windows.Forms.ToolTip>Visual Studio의 코드 또는 Windows Forms 디자이너에서 문자열을 설정할 수 있습니다. 구성 요소에 대 한 자세한 내용은 <xref:System.Windows.Forms.ToolTip> [도구 설명 구성 요소 개요](tooltip-component-overview-windows-forms.md)를 참조 하세요.

## <a name="set-a-tooltip-programmatically"></a>프로그래밍 방식으로 도구 설명 설정

1. 도구 설명을 표시 하는 컨트롤을 추가 합니다.

2. <xref:System.Windows.Forms.ToolTip.SetToolTip%2A>구성 요소의 메서드를 사용 <xref:System.Windows.Forms.ToolTip> 합니다.

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

## <a name="set-a-tooltip-in-the-designer"></a>디자이너에서 도구 설명 설정

1. Visual Studio에서 <xref:System.Windows.Forms.ToolTip> 구성 요소를 폼에 추가 합니다.

2. 도구 설명이 표시 되는 컨트롤을 선택 하거나 폼에 추가 합니다.

3. **속성** 창에서 **ToolTip1 값에 대 한 도구 설명을** 적절 한 텍스트 문자열로 설정 합니다.

### <a name="to-remove-a-tooltip-programmatically"></a>프로그래밍 방식으로 도구 설명을 제거 하려면

1. <xref:System.Windows.Forms.ToolTip.SetToolTip%2A>구성 요소의 메서드를 사용 <xref:System.Windows.Forms.ToolTip> 합니다.

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

## <a name="remove-a-tooltip-in-the-designer"></a>디자이너에서 도구 설명 제거

1. Visual Studio에서 도구 설명을 표시 하는 컨트롤을 선택 합니다.

2. **속성** 창에서 **ToolTip1의 도구 설명**에 있는 텍스트를 삭제 합니다.

## <a name="see-also"></a>참고 항목

- [ToolTip 구성 요소 개요](tooltip-component-overview-windows-forms.md)
- [방법: Windows Forms ToolTip 구성 요소의 지연 변경](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [ToolTip 구성 요소](tooltip-component-windows-forms.md)
