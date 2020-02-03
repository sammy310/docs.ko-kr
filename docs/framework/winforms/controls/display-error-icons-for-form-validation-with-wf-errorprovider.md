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
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="4748c-102">방법: Windows Forms ErrorProvider 구성 요소를 사용하여 폼 유효성에 대한 오류 아이콘 표시</span><span class="sxs-lookup"><span data-stu-id="4748c-102">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="4748c-103">사용자가 잘못 된 데이터를 입력 하면 Windows Forms <xref:System.Windows.Forms.ErrorProvider> 구성 요소를 사용 하 여 오류 아이콘을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4748c-103">You can use a Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to display an error icon when the user enters invalid data.</span></span> <span data-ttu-id="4748c-104">폼에 두 개 이상의 컨트롤이 있어야 컨트롤 사이를 탭 하 여 유효성 검사 코드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4748c-104">You must have at least two controls on the form in order to tab between them and thereby invoke the validation code.</span></span>  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a><span data-ttu-id="4748c-105">컨트롤의 값이 유효 하지 않은 경우 오류 아이콘을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="4748c-105">To display an error icon when a control's value is invalid</span></span>  
  
1. <span data-ttu-id="4748c-106">텍스트 상자와 같은 두 컨트롤을 Windows Form에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4748c-106">Add two controls — for example, text boxes — to a Windows Form.</span></span>  
  
2. <span data-ttu-id="4748c-107">양식에 <xref:System.Windows.Forms.ErrorProvider> 구성 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4748c-107">Add an <xref:System.Windows.Forms.ErrorProvider> component to the form.</span></span>  
  
3. <span data-ttu-id="4748c-108">첫 번째 컨트롤을 선택 하 고 <xref:System.Windows.Forms.Control.Validating> 이벤트 처리기에 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4748c-108">Select the first control and add code to its <xref:System.Windows.Forms.Control.Validating> event handler.</span></span> <span data-ttu-id="4748c-109">이 코드를 제대로 실행 하려면 프로시저를 이벤트에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4748c-109">In order for this code to run properly, the procedure must be connected to the event.</span></span> <span data-ttu-id="4748c-110">자세한 내용은 [방법: 런타임에 Windows Forms 이벤트 처리기 만들기](../how-to-create-event-handlers-at-run-time-for-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4748c-110">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="4748c-111">다음 코드에서는 사용자가 입력 한 데이터의 유효성을 테스트 합니다. 데이터가 잘못 된 경우 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4748c-111">The following code tests the validity of the data the user has entered; if the data is invalid, the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method is called.</span></span> <span data-ttu-id="4748c-112"><xref:System.Windows.Forms.ErrorProvider.SetError%2A> 메서드의 첫 번째 인수는 옆에 아이콘을 표시 하는 컨트롤을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4748c-112">The first argument of the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method specifies which control to display the icon next to.</span></span> <span data-ttu-id="4748c-113">두 번째 인수는 표시할 오류 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="4748c-113">The second argument is the error text to display.</span></span>  
  
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
  
     <span data-ttu-id="4748c-114">(시각적 C#개체, C++시각적 개체) 폼의 생성자에 다음 코드를 추가 하 여 이벤트 처리기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4748c-114">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. <span data-ttu-id="4748c-115">프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4748c-115">Run the project.</span></span> <span data-ttu-id="4748c-116">첫 번째 컨트롤에 잘못 된 (이 예제에서는 숫자가 아닌) 데이터를 입력 한 다음 tab 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="4748c-116">Type invalid (in this example, non-numeric) data into the first control, and then tab to the second.</span></span> <span data-ttu-id="4748c-117">오류 아이콘이 표시 되 면이 아이콘을 마우스로 가리켜 오류 텍스트를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4748c-117">When the error icon is displayed, point at it with the mouse pointer to see the error text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4748c-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4748c-118">See also</span></span>

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [<span data-ttu-id="4748c-119">ErrorProvider 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="4748c-119">ErrorProvider Component Overview</span></span>](errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="4748c-120">방법: Windows Forms ErrorProvider 구성 요소를 사용하여 데이터 세트에 있는 오류 보기</span><span class="sxs-lookup"><span data-stu-id="4748c-120">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
