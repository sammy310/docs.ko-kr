---
title: ToolTip 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: 731f7ad0ce6670000d8c3d3e901e1506f7ef470a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741909"
---
# <a name="tooltip-component-overview-windows-forms"></a>ToolTip 구성 요소 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ToolTip> 구성 요소는 사용자가 컨트롤을 가리킬 때 텍스트를 표시합니다. 도구 설명은 모든 컨트롤에 연결될 수 있습니다. 이 구성 요소를 사용 하는 예: 폼의 공간을 절약 하기 위해 단추에 작은 아이콘을 표시 하 고 도구 설명을 사용 하 여 단추의 기능을 설명할 수 있습니다.  
  
## <a name="working-with-the-tooltip-component"></a>ToolTip 구성 요소 작업  
 <xref:System.Windows.Forms.ToolTip> 구성 요소는 Windows Form 또는 다른 컨테이너의 여러 컨트롤에 `ToolTip` 속성을 제공 합니다. 예를 들어 폼에 하나의 <xref:System.Windows.Forms.ToolTip> 구성 요소를 배치한 경우 <xref:System.Windows.Forms.TextBox> 컨트롤의 경우 "여기에 이름 입력"을 표시 하 고 <xref:System.Windows.Forms.Button> 컨트롤의 경우 "여기를 클릭 하 여 변경 내용을 저장할 수 있습니다."를 표시할 수 있습니다.  
  
 <xref:System.Windows.Forms.ToolTip> 구성 요소의 주요 메서드는 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 및 <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>됩니다. <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 메서드를 사용 하 여 컨트롤에 대해 표시 되는 도구 설명을 설정할 수 있습니다. 자세한 내용은 [방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)을 참조 하세요. 키 속성은 도구 설명이 나타나도록 `true`로 설정 해야 하 고, 도구 설명 문자열이 표시 되는 시간을 설정 하는 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, 도구 설명에 표시 되는 컨트롤을 가리켜야 하는 시간, 다음 도구 설명 창이 표시 될 때까지 걸리는 시간을 설정 하는 <xref:System.Windows.Forms.ToolTip.Active%2A>입니다. 자세한 내용은 [방법: Windows Forms ToolTip 구성 요소의 지연 변경](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.ToolTip>
- [방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [방법: Windows Forms ToolTip 구성 요소의 지연 변경](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
