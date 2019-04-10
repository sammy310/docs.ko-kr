---
title: '방법: Windows Forms ErrorProvider 구성 요소를 사용하여 양식 유효성 오류 아이콘 표시'
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
ms.openlocfilehash: 9487d4f82878ffefe17c576b16f654293ef01106
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316507"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="67474-102">방법: Windows Forms ErrorProvider 구성 요소를 사용하여 양식 유효성 오류 아이콘 표시</span><span class="sxs-lookup"><span data-stu-id="67474-102">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="67474-103">Windows Forms를 사용할 수 있습니다 <xref:System.Windows.Forms.ErrorProvider> 구성 요소에 잘못 된 데이터를 입력할 때 오류 아이콘을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="67474-103">You can use a Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to display an error icon when the user enters invalid data.</span></span> <span data-ttu-id="67474-104">두 개 이상의 폼의 컨트롤 간에 이동 하 여 유효성 검사 코드를 호출할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67474-104">You must have at least two controls on the form in order to tab between them and thereby invoke the validation code.</span></span>  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a><span data-ttu-id="67474-105">컨트롤의 값에 유효 하지 않을 때 오류 아이콘을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="67474-105">To display an error icon when a control's value is invalid</span></span>  
  
1. <span data-ttu-id="67474-106">두 개의 컨트롤 추가-예를 들어, 텍스트 상자-Windows 폼에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67474-106">Add two controls — for example, text boxes — to a Windows Form.</span></span>  
  
2. <span data-ttu-id="67474-107">추가 <xref:System.Windows.Forms.ErrorProvider> 폼에 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="67474-107">Add an <xref:System.Windows.Forms.ErrorProvider> component to the form.</span></span>  
  
3. <span data-ttu-id="67474-108">첫 번째 컨트롤을 선택 하 고 코드를 추가 하는 <xref:System.Windows.Forms.Control.Validating> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="67474-108">Select the first control and add code to its <xref:System.Windows.Forms.Control.Validating> event handler.</span></span> <span data-ttu-id="67474-109">이 코드를 제대로 실행 되려면, 절차 이벤트에 연결 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67474-109">In order for this code to run properly, the procedure must be connected to the event.</span></span> <span data-ttu-id="67474-110">자세한 내용은 [방법: 런타임에 Windows Forms에 대 한 이벤트 처리기를 만들](../how-to-create-event-handlers-at-run-time-for-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="67474-110">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="67474-111">다음 코드는 사용자가 입력 한; 데이터의 유효성을 테스트 데이터가 유효 하지 않은 경우는 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67474-111">The following code tests the validity of the data the user has entered; if the data is invalid, the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method is called.</span></span> <span data-ttu-id="67474-112">첫 번째 인수는 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 메서드 아이콘 옆에 표시할 컨트롤을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67474-112">The first argument of the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method specifies which control to display the icon next to.</span></span> <span data-ttu-id="67474-113">두 번째 인수에 표시할 오류 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="67474-113">The second argument is the error text to display.</span></span>  
  
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
  
     <span data-ttu-id="67474-114">(Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="67474-114">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. <span data-ttu-id="67474-115">프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="67474-115">Run the project.</span></span> <span data-ttu-id="67474-116">그 다음으로 첫 번째 컨트롤을 두 번째 탭에 (이 예제에서는 숫자가 아닌)의 잘못 된 데이터를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="67474-116">Type invalid (in this example, non-numeric) data into the first control, and then tab to the second.</span></span> <span data-ttu-id="67474-117">오류 텍스트를 보려면 마우스 포인터를 사용 하 여 오류 아이콘이 표시 되 면 해당 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="67474-117">When the error icon is displayed, point at it with the mouse pointer to see the error text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67474-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="67474-118">See also</span></span>

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [<span data-ttu-id="67474-119">ErrorProvider 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="67474-119">ErrorProvider Component Overview</span></span>](errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="67474-120">방법: Windows Forms ErrorProvider 구성 요소를 사용하여 DataSet 내의 오류 보기</span><span class="sxs-lookup"><span data-stu-id="67474-120">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
