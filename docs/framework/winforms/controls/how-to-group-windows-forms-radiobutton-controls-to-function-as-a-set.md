---
title: Set로 작동 하도록 RadioButton 컨트롤 그룹화
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: c4b37c84bf0f93837b91c743c7681d39fd83a659
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732945"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>방법: 기능별로 Windows Forms RadioButton 컨트롤 그룹화
Windows Forms <xref:System.Windows.Forms.RadioButton> 컨트롤은 둘 이상의 설정 중 하나를 사용자가 선택할 수 있도록 디자인 되었으며, 하나는 프로시저 또는 개체에 할당할 수 있습니다. 예를 들어 <xref:System.Windows.Forms.RadioButton> 컨트롤 그룹에는 주문에 대 한 패키지 캐리어 선택이 표시 될 수 있지만 하나의 매개체만 사용 됩니다. 따라서 기능 그룹의 일부인 경우에도 한 번에 하나의 <xref:System.Windows.Forms.RadioButton> 선택할 수 있습니다.  
  
 라디오 단추는 <xref:System.Windows.Forms.Panel> 컨트롤, <xref:System.Windows.Forms.GroupBox> 컨트롤 또는 폼과 같은 컨테이너 내에서 그리기로 그룹화 합니다. 양식에 직접 추가 된 모든 라디오 단추는 하나의 그룹이 됩니다. 별도의 그룹을 추가 하려면 패널 또는 그룹 상자 내에 두어야 합니다. 패널 또는 그룹 상자에 대 한 자세한 내용은 [Panel 컨트롤 개요](panel-control-overview-windows-forms.md) 또는 [GroupBox 컨트롤 개요](groupbox-control-overview-windows-forms.md)를 참조 하세요.  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>RadioButton 컨트롤을 다른 집합에 독립적으로 작동 하는 집합으로 그룹화 하려면  
  
1. **도구 상자** 의 **Windows Forms** 탭에 있는 <xref:System.Windows.Forms.GroupBox> 또는 <xref:System.Windows.Forms.Panel> 컨트롤을 폼으로 끌어 놓습니다.  
  
2. <xref:System.Windows.Forms.GroupBox> 또는 <xref:System.Windows.Forms.Panel> 컨트롤에 <xref:System.Windows.Forms.RadioButton> 컨트롤을 그립니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.RadioButton>
- [RadioButton 컨트롤 개요](radiobutton-control-overview-windows-forms.md)
- [Panel 컨트롤 개요](panel-control-overview-windows-forms.md)
- [GroupBox 컨트롤 개요](groupbox-control-overview-windows-forms.md)
- [CheckBox 컨트롤 개요](checkbox-control-overview-windows-forms.md)
- [RadioButton 컨트롤](radiobutton-control-windows-forms.md)
