---
title: '방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: f127a1a74643c975aea73b24896c098b365aa327
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59327544"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정
모든 Windows Form에 지정할 수 있습니다는 <xref:System.Windows.Forms.Button> 취소 단추를 제어 합니다. 사용자에 관계 없이 폼에서 다른 컨트롤에 포커스가 ESC 키를 누를 때마다 취소 단추를 클릭 합니다. 신속 하 게 조치를 커밋하지 않고 작업을 종료할 수 있도록 프로그래밍할 때 일반적으로 이러한 단추를 사용 합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-designate-the-cancel-button"></a>취소 단추를 지정 하려면  
  
1. 단추 상주 하는 폼을 선택 합니다.  
  
2. 에 **속성** 창에서 양식의 설정 <xref:System.Windows.Forms.Form.CancelButton%2A> 속성을를 <xref:System.Windows.Forms.Button> 컨트롤의 이름입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Button 컨트롤 개요](button-control-overview-windows-forms.md)
- [Windows Forms Button 컨트롤 선택 방법](ways-to-select-a-windows-forms-button-control.md)
- [방법: Windows Forms 단추 클릭에 응답](how-to-respond-to-windows-forms-button-clicks.md)
- [방법: Windows Forms 단추를 디자이너를 사용 하 여 적용 단추로 지정](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Button 컨트롤](button-control-windows-forms.md)
