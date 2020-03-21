---
title: '연습: MaskedTextBox 컨트롤 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: db32b3ec88a07747ea3e286af9f04edce3f1ba3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182068"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a>연습: MaskedTextBox 컨트롤 사용
이 연습에서 설명하는 작업은 다음과 같습니다.  
  
- <xref:System.Windows.Forms.MaskedTextBox> 컨트롤 초기화  
  
- 문자가 <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> 마스크를 준수하지 않을 때 이벤트 처리기를 사용하여 사용자에게 경고  
  
- <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 속성에 형식을 할당하고 <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> 이벤트 처리기를 사용하여 커밋하려는 값이 형식에 대해 유효하지 않은 경우 사용자에게 경고합니다.  
  
## <a name="creating-the-project-and-adding-a-control"></a>프로젝트 만들기 및 컨트롤 추가  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a>양식에 마스크된 텍스트 상자 컨트롤을 추가하려면  
  
1. 컨트롤을 배치할 양식을 엽니다. <xref:System.Windows.Forms.MaskedTextBox>  
  
2. 도구 <xref:System.Windows.Forms.MaskedTextBox> **상자에서** 폼으로 컨트롤을 끕입니다.  
  
3. 컨트롤을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다. **속성** 창에서 **Mask** 속성을 선택하고 속성 이름 옆에 있는 ...(타원) 단추를 클릭합니다. **...**  
  
4. 입력 **마스크** 대화 상자에서 **짧은 날짜** 마스크를 선택하고 **확인을**클릭합니다.  
  
5. **속성** 창에서 <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> 속성을 로 `true`설정합니다. 이 속성은 사용자가 마스크 정의를 위반하는 문자를 입력하려고 할 때마다 짧은 경고음이 울립니다.  
  
 Mask 속성이 지원하는 문자에 대한 요약은 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성의 설명 섹션을 참조하십시오.  
  
## <a name="alert-the-user-to-input-errors"></a>사용자에게 입력 오류 경고  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a>거부된 마스크 입력에 대한 부품 번호 팁 추가  
  
1. **도구 상자로** 돌아가서 <xref:System.Windows.Forms.ToolTip> 양식에 를 추가합니다.  
  
2. 입력 오류가 발생할 <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> <xref:System.Windows.Forms.ToolTip> 때를 발생 시키는 이벤트에 대 한 이벤트 처리기를 만듭니다. 풍선 팁은 5초 동안 또는 사용자가 이를 클릭할 때까지 표시됩니다.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a>사용자에게 유효하지 않은 형식에 대해 경고합니다.  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a>잘못된 데이터 유형에 대한 부품 번호 팁 추가  
  
1. 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 <xref:System.Type> <xref:System.DateTime> 컨트롤의 <xref:System.Windows.Forms.MaskedTextBox> <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 속성에 형식을 나타내는 개체를 할당합니다.  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2. <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> 이벤트에 대한 이벤트 처리기를 추가합니다.  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.MaskedTextBox>
- [MaskedTextBox 컨트롤](maskedtextbox-control-windows-forms.md)
