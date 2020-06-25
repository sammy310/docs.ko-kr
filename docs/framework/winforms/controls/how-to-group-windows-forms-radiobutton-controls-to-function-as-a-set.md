---
title: Set로 작동 하도록 RadioButton 컨트롤 그룹화
description: 다른 집합에 독립적으로 작동 하도록 Windows Forms RadioButton 컨트롤을 그룹화 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: 9f6795330922e739cca1f2b5c11bb2ec68bb4e84
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325924"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>방법: Windows Forms RadioButton 컨트롤을 기능 집합으로 그룹화
Windows Forms <xref:System.Windows.Forms.RadioButton> 컨트롤은 사용자가 하나 이상의 설정 중에서 선택할 수 있도록 디자인 되었으며, 하나는 프로시저 또는 개체에 할당 될 수 있습니다. 예를 들어, 컨트롤 그룹이 <xref:System.Windows.Forms.RadioButton> 주문에 대 한 패키지 캐리어를 선택 하는 것으로 표시 될 수 있지만이 중 하나만 사용 됩니다. 따라서 <xref:System.Windows.Forms.RadioButton> 기능 그룹의 일부인 경우에도 한 번에 하나만 선택할 수 있습니다.  
  
 <xref:System.Windows.Forms.Panel>컨트롤, 컨트롤, 폼 등의 컨테이너 내에서 라디오 단추를 그려서 그룹화 할 수 있습니다 <xref:System.Windows.Forms.GroupBox> . 양식에 직접 추가 된 모든 라디오 단추는 하나의 그룹이 됩니다. 별도의 그룹을 추가 하려면 패널 또는 그룹 상자 내에 두어야 합니다. 패널 또는 그룹 상자에 대 한 자세한 내용은 [Panel 컨트롤 개요](panel-control-overview-windows-forms.md) 또는 [GroupBox 컨트롤 개요](groupbox-control-overview-windows-forms.md)를 참조 하세요.  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>RadioButton 컨트롤을 다른 집합에 독립적으로 작동 하는 집합으로 그룹화 하려면  
  
1. <xref:System.Windows.Forms.GroupBox>또는 컨트롤을 <xref:System.Windows.Forms.Panel> **도구 상자** 의 **Windows Forms** 탭에서 폼으로 끌어 옵니다.  
  
2. <xref:System.Windows.Forms.RadioButton>또는 컨트롤에 컨트롤을 그립니다 <xref:System.Windows.Forms.GroupBox> <xref:System.Windows.Forms.Panel> .  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.RadioButton>
- [RadioButton 컨트롤 개요](radiobutton-control-overview-windows-forms.md)
- [Panel 컨트롤 개요](panel-control-overview-windows-forms.md)
- [GroupBox 컨트롤 개요](groupbox-control-overview-windows-forms.md)
- [CheckBox 컨트롤 개요](checkbox-control-overview-windows-forms.md)
- [RadioButton 컨트롤](radiobutton-control-windows-forms.md)
