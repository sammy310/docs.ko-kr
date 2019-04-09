---
title: '방법: 기존 Windows Forms 컨트롤에서 상속'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
ms.openlocfilehash: 90008b00c95906ba43364c5a4ae3f85d9fdf0e22
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087874"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>방법: 기존 Windows Forms 컨트롤에서 상속
기존 컨트롤의 기능을 확장하려는 경우 상속을 통해 기존 컨트롤에서 파생된 컨트롤을 만들 수 있습니다. 기존 컨트롤에서 상속하는 경우 해당 컨트롤의 모든 기능 및 시각적 속성을 상속합니다. 예를 들어에서 상속 된 컨트롤을 만들려는 <xref:System.Windows.Forms.Button>, 새 컨트롤 모양 및 act에는 정확히 표준 같은 <xref:System.Windows.Forms.Button> 제어 합니다. 그런 다음 사용자 지정 메서드 및 속성의 구현을 통해 새 컨트롤의 기능을 확장하거나 수정할 수 있습니다. 일부 컨트롤에서는 변경할 수 있습니다도 상속 된 컨트롤의 시각적 모양을 재정의 하 여 해당 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-create-an-inherited-control"></a>상속된 컨트롤을 만들려면  
  
1.  새 **Windows Forms 애플리케이션** 프로젝트를 만듭니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  
  
     **새 항목 추가** 대화 상자가 나타납니다.  
  
3.  **새 항목 추가** 대화 상자에서 **사용자 지정 컨트롤**을 두 번 클릭합니다.  
  
     새 사용자 지정 컨트롤을 프로젝트에 추가합니다.  
  
4.  Visual Basic을 사용하면 **솔루션 탐색기**의 맨 위에서 **모든 파일 표시**를 클릭합니다. CustomControl1.vb를 확장한 다음 코드 편집기에서 CustomControl1.Designer.vb를 엽니다.  
  
5.  C#을 사용하는 경우 코드 편집기에서 CustomControl1.cs를 엽니다.  
  
6.  상속 되는 클래스 선언을 찾습니다 <xref:System.Windows.Forms.Control>합니다.  
  
7.  기본 클래스를 상속하려는 컨트롤로 변경합니다.  
  
     예를 들어에서 상속 하려는 경우 <xref:System.Windows.Forms.Button>, 다음 클래스 선언을 변경 합니다.  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8.  Visual Basic을 사용하는 경우 저장하고 CustomControl1.Designer.vb를 닫습니다. 코드 편집기에서 CustomControl1.vb를 엽니다.  
  
9. 컨트롤이 통합하는 사용자 지정 메서드 또는 속성을 구현합니다.  
  
10. 컨트롤의 그래픽 모양을 수정 하려는 경우 재정의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.  
  
    > [!NOTE]
    >  재정의 <xref:System.Windows.Forms.Control.OnPaint%2A> 모든 컨트롤의 모양을 수정 하려는 허용 하지 것입니다. 모든 Windows 수행한 그리기가 있는 해당 컨트롤 (예를 들어 <xref:System.Windows.Forms.TextBox>)를 호출 하지 않습니다 해당 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 따라서 사용 하지 것입니다 사용자 지정 코드 및 합니다. 경우를 확인 하려면 수정 하려는 특정 컨트롤에 대 한 도움말 설명서를 참조 합니다 <xref:System.Windows.Forms.Control.OnPaint%2A> 방법은 사용할 수 있습니다. 모든 Windows Form 컨트롤의 목록은 [Windows Forms에서 사용할 컨트롤](controls-to-use-on-windows-forms.md)을 참조하세요. 컨트롤에 없는 경우 <xref:System.Windows.Forms.Control.OnPaint%2A> 구성원 메서드로 나열 하 여 변경할 수 없습니다 모양을이 메서드를 재정의 합니다. 사용자 지정 그리기에 대한 자세한 내용은 [사용자 지정 컨트롤 그리기 및 렌더링](custom-control-painting-and-rendering.md)을 참조하세요.  
  
    ```vb  
    Protected Overrides Sub OnPaint(ByVal e As _  
       System.Windows.Forms.PaintEventArgs)  
       MyBase.OnPaint(e)  
       ' Insert code to do custom painting.   
       ' If you want to completely change the appearance of your control,  
       ' do not call MyBase.OnPaint(e).  
    End Sub  
    ```  
  
    ```csharp  
    protected override void OnPaint(PaintEventArgs pe)  
    {  
       base.OnPaint(pe);  
       // Insert code to do custom painting.  
       // If you want to completely change the appearance of your control,  
       // do not call base.OnPaint(pe).  
    }  
    ```  
  
11. 컨트롤을 저장하고 테스트합니다.  
  
## <a name="see-also"></a>참고자료

- [사용자 지정 컨트롤의 종류](varieties-of-custom-controls.md)
- [방법: Control 클래스에서 상속](how-to-inherit-from-the-control-class.md)
- [방법: UserControl 클래스에서 상속](how-to-inherit-from-the-usercontrol-class.md)
- [방법: Windows Forms 컨트롤 작성](how-to-author-controls-for-windows-forms.md)
- [Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [연습: Visual C#을 사용하여 Windows Forms 컨트롤에서 상속](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
