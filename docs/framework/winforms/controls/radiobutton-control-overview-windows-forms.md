---
title: RadioButton 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
ms.openlocfilehash: bbc93046b69d39caadde4986ff56f067fc206a9e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741141"
---
# <a name="radiobutton-control-overview-windows-forms"></a>RadioButton 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.RadioButton> 컨트롤은 둘 이상의 상호 배타적인 선택 항목 집합을 사용자에 게 제공 합니다. 라디오 단추와 확인란이 비슷하게 작동 하는 것 처럼 보일 수 있지만 중요 한 차이점이 있습니다. 사용자가 라디오 단추를 선택 하면 동일한 그룹의 다른 라디오 단추도 선택할 수 없습니다. 이와 달리 확인란은 선택할 수 있습니다. 라디오 단추 그룹을 정의 하면 "한 번만 선택할 수 있는 선택 항목 집합이 있습니다." 라는 메시지가 표시 됩니다.  
  
## <a name="using-the-control"></a>컨트롤 사용  
 <xref:System.Windows.Forms.RadioButton> 컨트롤을 클릭 하면 해당 <xref:System.Windows.Forms.RadioButton.Checked%2A> 속성이 `true`로 설정 되 고 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기가 호출 됩니다. <xref:System.Windows.Forms.RadioButton.CheckedChanged> 이벤트는 때의 값을 <xref:System.Windows.Forms.RadioButton.Checked%2A> 속성 변경. <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> 속성이 `true` (기본값)로 설정 된 경우 라디오 단추를 선택 하면 그룹의 다른 모든 사용자가 자동으로 지워집니다. 유효성 검사 코드를 사용 하 여 선택한 라디오 단추가 허용 가능한 옵션 인지 확인 하는 경우에만이 속성은 일반적으로 `false`로 설정 됩니다. 컨트롤 내에 표시 되는 텍스트는 액세스 키 바로 가기를 포함할 수 있는 <xref:System.Windows.Forms.Control.Text%2A> 속성으로 설정 됩니다. 액세스 키를 사용 하면 사용자가 선택 키로 ALT 키를 눌러 컨트롤을 "클릭" 할 수 있습니다. 자세한 내용은 [방법: Windows Forms 컨트롤에 대 한 선택 키 만들기](how-to-create-access-keys-for-windows-forms-controls.md) 및 [방법: Windows Forms 컨트롤에 표시 되는 텍스트 설정](how-to-set-the-text-displayed-by-a-windows-forms-control.md)을 참조 하세요.  
  
 <xref:System.Windows.Forms.RadioButton> 컨트롤은 명령 단추 처럼 표시 될 수 있으며,이 단추를 선택 하면 <xref:System.Windows.Forms.RadioButton.Appearance%2A> 속성이 <xref:System.Windows.Forms.Appearance.Button>으로 설정 된 경우 눌려진 것 처럼 보입니다. 라디오 단추는 <xref:System.Windows.Forms.ButtonBase.Image%2A> 및 <xref:System.Windows.Forms.ButtonBase.ImageList%2A> 속성을 사용 하 여 이미지를 표시할 수도 있습니다. 자세한 내용은 [방법: Windows Forms 컨트롤에 의해 표시 되는 이미지 설정](how-to-set-the-image-displayed-by-a-windows-forms-control.md)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.RadioButton>
- [Panel 컨트롤 개요](panel-control-overview-windows-forms.md)
- [GroupBox 컨트롤 개요](groupbox-control-overview-windows-forms.md)
- [CheckBox 컨트롤 개요](checkbox-control-overview-windows-forms.md)
- [방법: Windows Forms 컨트롤에 대한 선택키 만들기](how-to-create-access-keys-for-windows-forms-controls.md)
- [방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [방법: 기능별로 Windows Forms RadioButton 컨트롤 그룹화](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)
- [RadioButton 컨트롤](radiobutton-control-windows-forms.md)
