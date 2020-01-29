---
title: CheckBox 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
ms.openlocfilehash: b42816cf1bc0ce1ab6db0a2a436b17b0d4370d59
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737099"
---
# <a name="checkbox-control-overview-windows-forms"></a>CheckBox 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.CheckBox> 컨트롤은 특정 조건이 설정 또는 해제되었는지를 나타냅니다. 일반적으로 예/아니요 또는 True/False 선택을 사용자에게 제공하는 데 사용됩니다. 확인란 컨트롤을 그룹으로 사용하여 사용자가 하나 이상 선택할 수 있는 여러 선택 항목을 표시할 수 있습니다.  
  
 확인란 컨트롤은 사용자가 선택한 항목을 나타내는 데 사용 되는의 라디오 단추 컨트롤과 비슷합니다. 그룹의 라디오 단추를 한 번에 하나만 선택할 수 있다는 점에서 차이가 있습니다. 그러나 확인란 컨트롤을 사용 하면 원하는 수의 확인란을 선택할 수 있습니다.  
  
 확인란은 단순 데이터 바인딩을 사용 하 여 데이터베이스의 요소에 연결 될 수 있습니다. <xref:System.Windows.Forms.GroupBox> 컨트롤을 사용 하 여 여러 확인란을 그룹화 할 수 있습니다. 이는 폼 디자이너에서 그룹화 된 컨트롤을 함께 이동할 수 있으므로 시각적 모양 및 사용자 인터페이스 디자인에도 유용 합니다. 자세한 내용은 [Windows Forms 데이터 바인딩](../windows-forms-data-binding.md) 및 [GroupBox 컨트롤](groupbox-control-windows-forms.md)을 참조 하세요.  
  
 <xref:System.Windows.Forms.CheckBox> 컨트롤에는 <xref:System.Windows.Forms.CheckBox.Checked%2A> 및 <xref:System.Windows.Forms.CheckBox.CheckState%2A>라는 두 가지 중요 한 속성이 있습니다. <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성은 `true` 또는 `false`를 반환 합니다. <xref:System.Windows.Forms.CheckBox.CheckState%2A> 속성은 <xref:System.Windows.Forms.CheckState.Checked> 또는 <xref:System.Windows.Forms.CheckState.Unchecked>를 반환 합니다. 또는 <xref:System.Windows.Forms.CheckBox.ThreeState%2A> 속성이 `true`로 설정 된 경우에도 <xref:System.Windows.Forms.CheckState.Indeterminate>를 반환할 수 <xref:System.Windows.Forms.CheckBox.CheckState%2A>. 비활성화 된 상태에서 상자는 흐리게 표시 되어 옵션을 사용할 수 없음을 나타낼 수 있습니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.CheckBox>
- [방법: Windows Forms CheckBox 컨트롤을 사용하여 옵션 설정](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [방법: Windows Forms CheckBox 클릭에 응답](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [CheckBox 컨트롤](checkbox-control-windows-forms.md)
