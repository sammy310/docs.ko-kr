---
title: ColorDialog 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 48d9d5072335908f85e65933dadafb1b69f28528
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736971"
---
# <a name="colordialog-component-overview-windows-forms"></a>ColorDialog 구성 요소 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ColorDialog> 구성 요소는 사용자가 색상표에서 색을 선택 하 고 해당 색상표에 사용자 지정 색을 추가할 수 있는 미리 구성 된 대화 상자입니다. 이 구성 요소는 다른 Windows 기반 애플리케이션에서 색상 선택하는 데 사용하는 대화 상자와 동일합니다. 고유한 대화 상자를 구성하는 대신 Windows 기반 애플리케이션 내에서 간단한 솔루션으로 사용합니다.  
  
 대화 상자에서 선택한 색은 <xref:System.Windows.Forms.ColorDialog.Color%2A> 속성에서 반환 됩니다. <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> 속성이 `false`로 설정 된 경우 "사용자 지정 색 정의" 단추를 사용할 수 없으며 사용자가 색상표의 미리 정의 된 색으로 제한 됩니다. <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> 속성이 `true`로 설정 된 경우 사용자는 디더링된 색을 선택할 수 없습니다. 대화 상자를 표시 하려면 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 호출 해야 합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.ColorDialog>
- [ColorDialog 구성 요소](colordialog-component-windows-forms.md)
- [대화 상자 컨트롤 및 구성 요소](dialog-box-controls-and-components-windows-forms.md)
- [방법: Windows Forms ColorDialog 구성 요소의 모양 변경](how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
