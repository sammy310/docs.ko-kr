---
title: Button 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
ms.openlocfilehash: 4ba7b333e5414efb4814d64ce50c55e08b27f859
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747086"
---
# <a name="button-control-overview-windows-forms"></a>Button 컨트롤 개요(Windows Forms)
사용자는 Windows Forms <xref:System.Windows.Forms.Button> 컨트롤을 클릭하여 작업을 수행할 수 있습니다. 단추를 클릭하면 눌렀다 놓는 것처럼 표시됩니다. 사용자가 단추를 클릭할 때마다 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기가 호출 됩니다. <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 코드를 추가 하 여 선택한 작업을 수행 합니다.  
  
 단추에 표시 되는 텍스트는 <xref:System.Windows.Forms.Control.Text%2A> 속성에 포함 되어 있습니다. 텍스트가 단추의 너비를 초과 하면 다음 줄로 줄 바꿈됩니다. 그러나 컨트롤이 전체 높이를 수용할 수 없는 경우에는 잘립니다. 자세한 내용은 [방법: Windows Forms 컨트롤에 표시 되는 텍스트 설정](how-to-set-the-text-displayed-by-a-windows-forms-control.md)을 참조 하세요. <xref:System.Windows.Forms.Control.Text%2A> 속성은 액세스 키를 포함 하 여 사용자가 선택 키로 ALT 키를 눌러 컨트롤을 "클릭" 할 수 있습니다. 자세한 내용은 [방법: Windows Forms 컨트롤에 대 한 선택 키 만들기](how-to-create-access-keys-for-windows-forms-controls.md)를 참조 하세요. 텍스트의 모양은 <xref:System.Windows.Forms.Control.Font%2A> 속성과 <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> 속성에 의해 제어 됩니다.  
  
 <xref:System.Windows.Forms.Button> 컨트롤은 <xref:System.Windows.Forms.ButtonBase.Image%2A> 및 <xref:System.Windows.Forms.ButtonBase.ImageList%2A> 속성을 사용 하 여 이미지를 표시할 수도 있습니다. 자세한 내용은 [방법: Windows Forms 컨트롤에 의해 표시 되는 이미지 설정](how-to-set-the-image-displayed-by-a-windows-forms-control.md)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Button>
- [방법: Windows Forms 단추 클릭에 응답](how-to-respond-to-windows-forms-button-clicks.md)
- [Windows Forms Button 컨트롤 선택 방법](ways-to-select-a-windows-forms-button-control.md)
- [방법: 디자이너를 사용하여 Windows Forms 단추를 적용 단추로 지정](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Button 컨트롤](button-control-windows-forms.md)
