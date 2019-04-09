---
title: '방법: Windows Forms에 컨트롤 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 72b5931a79284a93a4e0fdf3cb2cc3b03157f5f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106485"
---
# <a name="how-to-add-controls-to-windows-forms"></a>방법: Windows Forms에 컨트롤 추가
대부분의 폼은 사용자 인터페이스 (UI)를 정의 하도록 폼의 화면에 컨트롤을 추가 하 여 설계 되었습니다. A *제어* 정보를 표시 하거나 사용자 입력을 허용 하는 데 양식의 구성 요소입니다. 컨트롤에 대 한 자세한 내용은 참조 하세요. [Windows Forms 컨트롤](index.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-draw-a-control-on-a-form"></a>폼에서 컨트롤을 그리려면  
  
1.  폼을 엽니다. 자세한 내용은 [방법: Windows Forms 디자이너에서 표시할](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))합니다.  
  
2.  에 **도구 상자**, 폼에 추가 하려는 컨트롤을 클릭 합니다.  
  
3.  폼에 배치 될 컨트롤의 왼쪽 위 모퉁이 위치를 클릭 하 고 찾을 컨트롤의 오른쪽 아래 모서리를 원하는 위치로 끕니다.  
  
     컨트롤의 지정 된 위치와 크기를 사용 하 여 폼에 추가 됩니다.  
  
    > [!NOTE]
    >  각 컨트롤의 기본 크기는 정의 합니다. 끌어 오지 여 컨트롤의 기본 크기의 폼에 컨트롤을 추가할 수 있습니다 합니다 **도구 상자** 폼입니다.  
  
### <a name="to-drag-a-control-to-a-form"></a>폼에 컨트롤을 끌기  
  
1.  폼을 엽니다. 자세한 내용은 [방법: Windows Forms 디자이너에서 표시할](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))합니다.  
  
2.  에 **도구 상자**, 클릭 컨트롤을 폼으로 끕니다.  
  
     컨트롤의 기본 크기로 지정된 된 위치에서 폼에 추가 됩니다.  
  
    > [!NOTE]
    >  컨트롤을 두 번 클릭 수를 **도구 상자** 기본 크기의 폼의 왼쪽 위 모퉁이에 추가 합니다.  
  
     또한 컨트롤 추가할 수 있습니다 동적으로 폼에 런타임 시. 다음 코드 예제에서를 <xref:System.Windows.Forms.TextBox> 컨트롤이 폼에 추가 될 때를 <xref:System.Windows.Forms.Button> 컨트롤을 클릭 합니다.  
  
    > [!NOTE]
    >  다음 절차에 사용 하 여 폼의 존재 여부 필요는 **단추** 컨트롤 `Button1`, 이미 배치 합니다.  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a>프로그래밍 방식으로 폼에 컨트롤을 추가 하려면  
  
1.  단추를 처리 하는 방법에 `Click` 이벤트 클래스 폼의 컨트롤 변수에 대 한 참조를 추가 하려면 다음과 비슷한 삽입 코드 내에서 컨트롤의 설정 `Location`, 컨트롤을 추가 합니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim MyText As New TextBox()  
       MyText.Location = New Point(25, 25)  
       Me.Controls.Add(MyText)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       TextBox myText = new TextBox();  
       myText.Location = new Point(25,25);  
       this.Controls.Add (myText);  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void button1_Click(System::Object ^  sender,  
        System::EventArgs ^  e)  
      {  
        TextBox ^ myText = gcnew TextBox();  
        myText->Location = Point(25,25);  
        this->Controls->Add(myText);  
      }  
    ```  
  
    > [!NOTE]
    >  또한 컨트롤의 다른 속성을 초기화 하는 코드를 추가할 수 있습니다.  
  
    > [!IMPORTANT]
    >  악성 참조 하 여 로컬 컴퓨터가 네트워크를 통해 보안 위험에 노출 될 수 있습니다 `UserControl`합니다. 이 악의적인 사용자 실수로 프로젝트에 추가 하 여 사용자가 팔 로우 하는 손상을 일으킬 수 있는 사용자 지정 컨트롤을 만드는 경우 문제가 이어야 합니다.  
  
## <a name="see-also"></a>참고자료

- [Windows Forms 컨트롤](index.md)
- [Windows Forms에서 컨트롤 정렬](arranging-controls-on-windows-forms.md)
- [방법: Windows Forms에서 컨트롤 크기 조정](how-to-resize-controls-on-windows-forms.md)
- [방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Windows Forms에 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)
