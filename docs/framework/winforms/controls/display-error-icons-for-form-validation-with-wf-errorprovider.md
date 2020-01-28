---
title: ErrorProvider 구성 요소를 사용 하 여 폼 유효성 검사에 대 한 오류 아이콘 표시
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
ms.openlocfilehash: a1e346e332db489351f59c9a0c03ae731baf3dc3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745916"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a>방법: Windows Forms ErrorProvider 구성 요소를 사용하여 폼 유효성에 대한 오류 아이콘 표시
사용자가 잘못 된 데이터를 입력 하면 Windows Forms <xref:System.Windows.Forms.ErrorProvider> 구성 요소를 사용 하 여 오류 아이콘을 표시할 수 있습니다. 폼에 두 개 이상의 컨트롤이 있어야 컨트롤 사이를 탭 하 여 유효성 검사 코드를 호출할 수 있습니다.  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a>컨트롤의 값이 유효 하지 않은 경우 오류 아이콘을 표시 하려면  
  
1. 텍스트 상자와 같은 두 컨트롤을 Windows Form에 추가 합니다.  
  
2. 양식에 <xref:System.Windows.Forms.ErrorProvider> 구성 요소를 추가 합니다.  
  
3. 첫 번째 컨트롤을 선택 하 고 <xref:System.Windows.Forms.Control.Validating> 이벤트 처리기에 코드를 추가 합니다. 이 코드를 제대로 실행 하려면 프로시저를 이벤트에 연결 해야 합니다. 자세한 내용은 [방법: 런타임에 Windows Forms 이벤트 처리기 만들기](../how-to-create-event-handlers-at-run-time-for-windows-forms.md)를 참조 하세요.  
  
     다음 코드에서는 사용자가 입력 한 데이터의 유효성을 테스트 합니다. 데이터가 잘못 된 경우 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 메서드가 호출 됩니다. <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 메서드의 첫 번째 인수는 옆에 아이콘을 표시 하는 컨트롤을 지정 합니다. 두 번째 인수는 표시할 오류 텍스트입니다.  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
     (시각적 C#개체, C++시각적 개체) 폼의 생성자에 다음 코드를 추가 하 여 이벤트 처리기를 등록 합니다.  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. 프로젝트를 실행합니다. 첫 번째 컨트롤에 잘못 된 (이 예제에서는 숫자가 아닌) 데이터를 입력 한 다음 tab 키를 누릅니다. 오류 아이콘이 표시 되 면이 아이콘을 마우스로 가리켜 오류 텍스트를 확인 합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [ErrorProvider 구성 요소 개요](errorprovider-component-overview-windows-forms.md)
- [방법: Windows Forms ErrorProvider 구성 요소를 사용하여 데이터 세트에 있는 오류 보기](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
