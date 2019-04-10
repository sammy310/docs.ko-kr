---
title: '방법: Windows Forms 단추를 적용 단추로 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
ms.openlocfilehash: 1e24e410681b03a92c8c48b187dde569eccdc1c1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222148"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>방법: Windows Forms 단추를 적용 단추로 지정
모든 Windows Form에 지정할 수 있습니다는 <xref:System.Windows.Forms.Button> 컨트롤을 적용 단추가 기본 단추 라고도 합니다. ENTER 키를 누를 때마다 폼에서 다른 컨트롤에 포커스가 관계 없이 기본 단추 클릭 됩니다.  
  
> [!NOTE]
>  이 하는 경우 포커스가 있는 컨트롤은 다른 단추에 대 한 예외-포커스가 있는 단추를 클릭 하는 경우-여러 줄 텍스트 상자 또는 ENTER 키를 트래핑 하는 사용자 지정 컨트롤입니다.  
  
### <a name="to-designate-the-accept-button"></a>적용 단추를 지정 하려면  
  
1.  폼의 설정 <xref:System.Windows.Forms.Form.AcceptButton%2A> 속성을 적절 한 <xref:System.Windows.Forms.Button> 제어 합니다.  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn   
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Button 컨트롤 개요](button-control-overview-windows-forms.md)
- [Windows Forms Button 컨트롤 선택 방법](ways-to-select-a-windows-forms-button-control.md)
- [방법: Windows Forms 단추 클릭에 응답](how-to-respond-to-windows-forms-button-clicks.md)
- [방법: Windows Forms Button을 취소 단추로 지정](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [Button 컨트롤](button-control-windows-forms.md)
