---
title: 단추를 수락 단추로 지정합니다.
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
ms.openlocfilehash: ca5f691fb26db5c4adcb48405c9600b54827104c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142149"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>방법: Windows Forms 단추를 적용 단추로 지정
모든 Windows 양식에서 컨트롤을 <xref:System.Windows.Forms.Button> 기본 단추라고도 하는 수락 단추로 지정할 수 있습니다. 사용자가 ENTER 키를 누를 때마다 폼의 다른 컨트롤에 포커스가 있는 컨트롤에 관계없이 기본 단추를 클릭합니다.  
  
> [!NOTE]
> 이에 대한 예외는 포커스가 있는 컨트롤이 다른 단추인 경우 포커스가 있는 단추를 클릭하거나 여러 줄텍스트 상자 또는 ENTER 키를 트랩하는 사용자 지정 컨트롤인 경우입니다.  
  
### <a name="to-designate-the-accept-button"></a>수락 단추를 지정하려면  
  
1. 폼의 <xref:System.Windows.Forms.Form.AcceptButton%2A> 속성을 적절한 <xref:System.Windows.Forms.Button> 컨트롤로 설정합니다.  
  
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
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Button 컨트롤 개요](button-control-overview-windows-forms.md)
- [Windows Forms Button 컨트롤 선택 방법](ways-to-select-a-windows-forms-button-control.md)
- [방법: Windows Forms 단추 클릭에 응답](how-to-respond-to-windows-forms-button-clicks.md)
- [방법: Windows Forms Button을 취소 단추로 지정](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [Button 컨트롤](button-control-windows-forms.md)
