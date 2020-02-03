---
title: 단추를 적용 단추로 지정
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
ms.openlocfilehash: 1063f649768cac2c866390718b261a21e18ec4d3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743274"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>방법: Windows Forms 단추를 적용 단추로 지정
Windows Form에서 기본 단추가 라고도 하는 허용 단추로 <xref:System.Windows.Forms.Button> 컨트롤을 지정할 수 있습니다. 사용자가 ENTER 키를 누를 때마다 폼의 다른 컨트롤에 포커스가 있는지 여부에 관계 없이 기본 단추가 클릭 됩니다.  
  
> [!NOTE]
> 이에 대 한 예외는 포커스가 있는 컨트롤이 다른 단추인 경우입니다 .이 경우 포커스가 있는 단추를 클릭 하거나 여러 줄 텍스트 상자를 클릭 하거나 ENTER 키를 트래핑 하는 사용자 지정 컨트롤을 클릭 합니다.  
  
### <a name="to-designate-the-accept-button"></a>수락 단추를 지정 하려면  
  
1. 양식의 <xref:System.Windows.Forms.Form.AcceptButton%2A> 속성을 적절 한 <xref:System.Windows.Forms.Button> 컨트롤로 설정 합니다.  
  
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
