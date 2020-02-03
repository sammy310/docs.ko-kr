---
title: ToolTip 구성 요소의 지연 변경
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: 8ab0b0760e8c82d752eaada19f14cae57fa63fdc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746581"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a>방법: Windows Forms ToolTip 구성 요소의 지연 변경
Windows Forms <xref:System.Windows.Forms.ToolTip> 구성 요소에 대해 설정할 수 있는 지연 값은 여러 가지가 있습니다. 이러한 모든 속성의 측정 단위는 밀리초입니다. <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> 속성은 사용자가 연결 된 컨트롤에서 표시 되는 도구 설명 문자열을 가리켜야 하는 기간을 결정 합니다. <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> 속성은 마우스가 도구 설명에 연결 된 컨트롤 하나에서 다른 컨트롤로 이동할 때 이후의 도구 설명 문자열이 표시 되는 데 걸리는 시간 (밀리초)을 설정 합니다. <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> 속성은 도구 설명 문자열이 표시 되는 기간을 결정 합니다. 이러한 값은 개별적으로 설정 하거나 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 속성의 값을 설정 하 여 설정할 수 있습니다. 다른 지연 속성은 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 속성에 할당 된 값을 기준으로 설정 됩니다. 예를 들어 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> N 값으로 설정 된 경우 <xref:System.Windows.Forms.ToolTip.InitialDelay%2A>가 N으로 설정 되 고, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 5 (또는 N/5)로 나눈 값으로 설정 되 고, <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A>가 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 속성 값 (또는 5N)의 5 배 값으로 설정 됩니다.  
  
### <a name="to-set-the-delay"></a>지연 시간을 설정 하려면  
  
1. 이 예제에 표시 된 대로 다음 속성을 설정 합니다.  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a>참고 항목

- [ToolTip 구성 요소 개요](tooltip-component-overview-windows-forms.md)
- [방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [ToolTip 구성 요소](tooltip-component-windows-forms.md)
