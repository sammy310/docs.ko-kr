---
title: '방법: MaskedTextBox 컨트롤에 데이터 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
- data binding [Windows Forms], MaskedTextBox control [Windows Forms]
- MaskedTextBox control [Windows Forms], binding data
ms.assetid: 34b29f07-e8df-48d4-b08b-53fcca524708
ms.openlocfilehash: 0cbb239e24b254c37c453486590185e934adf482
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142175"
---
# <a name="how-to-bind-data-to-the-maskedtextbox-control"></a><span data-ttu-id="20d91-102">방법: MaskedTextBox 컨트롤에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="20d91-102">How to: Bind Data to the MaskedTextBox Control</span></span>
<span data-ttu-id="20d91-103">다른 Windows Forms <xref:System.Windows.Forms.MaskedTextBox> 컨트롤과 마찬가지로 데이터를 컨트롤에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-103">You can bind data to a <xref:System.Windows.Forms.MaskedTextBox> control just as you can to any other Windows Forms control.</span></span> <span data-ttu-id="20d91-104">그러나 데이터베이스의 데이터 형식이 마스크 정의에서 예상한 형식과 일치하지 않으면 데이터를 다시 포맷해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-104">However, if the format of your data in the database does not match the format expected by your mask definition, you will need to reformat the data.</span></span> <span data-ttu-id="20d91-105">다음 절차에서는 <xref:System.Windows.Forms.Binding.Format> <xref:System.Windows.Forms.Binding.Parse> <xref:System.Windows.Forms.Binding> 클래스의 이벤트와 개별 전화 번호 및 전화 확장 데이터베이스 필드를 단일 편집 가능한 필드로 표시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-105">The following procedure demonstrates how to do this using the <xref:System.Windows.Forms.Binding.Format> and <xref:System.Windows.Forms.Binding.Parse> events of the <xref:System.Windows.Forms.Binding> class to display separate phone number and phone extension database fields as a single editable field.</span></span>  
  
 <span data-ttu-id="20d91-106">다음 절차에서는 Northwind 샘플 데이터베이스가 설치된 SQL Server 데이터베이스에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-106">The following procedure requires that you have access to a SQL Server database with the Northwind sample database installed.</span></span>  
  
### <a name="to-bind-data-to-a-maskedtextbox-control"></a><span data-ttu-id="20d91-107">데이터를 마스크된 텍스트 상자 컨트롤에 바인딩하려면</span><span class="sxs-lookup"><span data-stu-id="20d91-107">To bind data to a MaskedTextBox control</span></span>  
  
1. <span data-ttu-id="20d91-108">새 Windows Forms 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-108">Create a new Windows Forms project.</span></span>  
  
2. <span data-ttu-id="20d91-109">두 <xref:System.Windows.Forms.TextBox> 개의 컨트롤을 양식에 드래그합니다. 이름과 `FirstName` `LastName`.</span><span class="sxs-lookup"><span data-stu-id="20d91-109">Drag two <xref:System.Windows.Forms.TextBox> controls onto your form; name them `FirstName` and `LastName`.</span></span>  
  
3. <span data-ttu-id="20d91-110">컨트롤을 <xref:System.Windows.Forms.MaskedTextBox> 양식으로 드래그합니다. 이름을 `PhoneMask`지정합니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control onto your form; name it `PhoneMask`.</span></span>  
  
4. <span data-ttu-id="20d91-111"><xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 의 속성을 `PhoneMask` 로 `(000) 000-0000 x9999`설정합니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-111">Set the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property of `PhoneMask` to `(000) 000-0000 x9999`.</span></span>  
  
5. <span data-ttu-id="20d91-112">양식에 다음 네임스페이스 가져오기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-112">Add the following namespace imports to the form.</span></span>  
  
    ```csharp  
    using System.Data.SqlClient;  
    ```  
  
    ```vb  
    Imports System.Data.SqlClient  
    ```  
  
6. <span data-ttu-id="20d91-113">폼을 마우스 오른쪽 단추로 클릭하고 **코드 보기를**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-113">Right-click the form and choose **View Code**.</span></span> <span data-ttu-id="20d91-114">양식 클래스의 아무 곳에나 이 코드를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-114">Place this code anywhere in your form class.</span></span>  
  
    ```csharp  
    Binding currentBinding, phoneBinding;  
    DataSet employeesTable = new DataSet();  
    SqlConnection sc;  
    SqlDataAdapter dataConnect;  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        DoMaskBinding();  
    }  
  
    private void DoMaskBinding()  
    {  
        try  
        {  
            sc = new SqlConnection("Data Source=CLIENTUE;Initial Catalog=NORTHWIND;Integrated Security=SSPI");  
            sc.Open();  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
  
        dataConnect = new SqlDataAdapter("SELECT * FROM Employees", sc);  
        dataConnect.Fill(employeesTable, "Employees");  
  
        // Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        // before adding them to the control - otherwise, we won't get a Format event on the
        // initial load.
        try  
        {  
            currentBinding = new Binding("Text", employeesTable, "Employees.FirstName");  
            firstName.DataBindings.Add(currentBinding);  
  
            currentBinding = new Binding("Text", employeesTable, "Employees.LastName");  
            lastName.DataBindings.Add(currentBinding);  
  
            phoneBinding =new Binding("Text", employeesTable, "Employees.HomePhone");  
            // We must add the event handlers before we bind, or the Format event will not get called  
            // for the first record.  
            phoneBinding.Format += new ConvertEventHandler(phoneBinding_Format);  
            phoneBinding.Parse += new ConvertEventHandler(phoneBinding_Parse);  
            phoneMask.DataBindings.Add(phoneBinding);  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
    }  
    ```  
  
    ```vb  
    Dim WithEvents CurrentBinding, PhoneBinding As Binding  
    Dim EmployeesTable As New DataSet()  
    Dim sc As SqlConnection  
    Dim DataConnect As SqlDataAdapter  
  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        DoMaskedBinding()  
    End Sub  
  
    Private Sub DoMaskedBinding()  
        Try  
            sc = New SqlConnection("Data Source=SERVERNAME;Initial Catalog=NORTHWIND;Integrated Security=SSPI")  
            sc.Open()  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Exit Sub  
        End Try  
  
        DataConnect = New SqlDataAdapter("SELECT * FROM Employees", sc)  
        DataConnect.Fill(EmployeesTable, "Employees")  
  
        ' Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        ' before adding them to the control - otherwise, we won't get a Format event on the
        ' initial load.  
        Try  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.FirstName")  
            firstName.DataBindings.Add(CurrentBinding)  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.LastName")  
            lastName.DataBindings.Add(CurrentBinding)  
            PhoneBinding = New Binding("Text", EmployeesTable, "Employees.HomePhone")  
            PhoneMask.DataBindings.Add(PhoneBinding)  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Application.Exit()  
        End Try  
    End Sub  
    ```  
  
7. <span data-ttu-id="20d91-115"><xref:System.Windows.Forms.Binding.Format> 및 <xref:System.Windows.Forms.Binding.Parse> 이벤트에 대한 이벤트 처리기를 추가하여 `PhoneNumber` 바인딩된 `Extension` <xref:System.Data.DataSet>및 필드를 결합하고 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-115">Add event handlers for the <xref:System.Windows.Forms.Binding.Format> and <xref:System.Windows.Forms.Binding.Parse> events to combine and separate the `PhoneNumber` and `Extension` fields from the bound <xref:System.Data.DataSet>.</span></span>  
  
    ```csharp  
    private void phoneBinding_Format(Object sender, ConvertEventArgs e)  
    {  
        String ext;  
  
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        if (currentRow["Extension"] == null)
        {  
            ext = "";  
        } else
        {  
            ext = currentRow["Extension"].ToString();  
        }  
  
        e.Value = e.Value.ToString().Trim() + " x" + ext;  
    }  
  
    private void phoneBinding_Parse(Object sender, ConvertEventArgs e)  
    {  
        String phoneNumberAndExt = e.Value.ToString();  
  
        int extIndex = phoneNumberAndExt.IndexOf("x");  
        String ext = phoneNumberAndExt.Substring(extIndex).Trim();  
        String phoneNumber = phoneNumberAndExt.Substring(0, extIndex).Trim();  
  
        //Get the current binding object, and set the new extension manually.
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        // Remove the "x" from the extension.  
        currentRow["Extension"] = ext.Substring(1);  
  
        //Return the phone number.  
        e.Value = phoneNumber;  
    }  
    ```  
  
    ```vb  
    Private Sub PhoneBinding_Format(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Format  
        Dim Ext As String  
  
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        If (CurrentRow("Extension") Is Nothing) Then  
            Ext = ""  
        Else  
            Ext = CurrentRow("Extension").ToString()  
        End If  
  
        e.Value = e.Value.ToString().Trim() & " x" & Ext  
    End Sub  
  
    Private Sub PhoneBinding_Parse(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Parse  
        Dim PhoneNumberAndExt As String = e.Value.ToString()  
  
        Dim ExtIndex As Integer = PhoneNumberAndExt.IndexOf("x")  
        Dim Ext As String = PhoneNumberAndExt.Substring(ExtIndex).Trim()  
        Dim PhoneNumber As String = PhoneNumberAndExt.Substring(0, ExtIndex).Trim()  
  
        ' Get the current binding object, and set the new extension manually.
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        ' Remove the "x" from the extension.  
        CurrentRow("Extension") = CObj(Ext.Substring(1))  
  
        ' Return the phone number.  
        e.Value = PhoneNumber  
    End Sub  
    ```  
  
8. <span data-ttu-id="20d91-116">폼에 <xref:System.Windows.Forms.Button> 두 개의 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-116">Add two <xref:System.Windows.Forms.Button> controls to the form.</span></span> <span data-ttu-id="20d91-117">이름을 `previousButton` 지정하고 `nextButton`.</span><span class="sxs-lookup"><span data-stu-id="20d91-117">Name them `previousButton` and `nextButton`.</span></span> <span data-ttu-id="20d91-118">각 단추를 두 번 <xref:System.Windows.Forms.Control.Click> 클릭하여 이벤트 처리기를 추가하고 다음 코드 예제와 같이 이벤트 처리기를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-118">Double-click each button to add a <xref:System.Windows.Forms.Control.Click> event handler, and fill in the event handlers as shown in the following code example.</span></span>  
  
    ```csharp  
    private void previousButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position - 1;  
    }  
  
    private void nextButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position + 1;  
    }  
    ```  
  
    ```vb  
    Private Sub PreviousButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles PreviousButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position - 1  
    End Sub  
  
    Private Sub NextButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles NextButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position + 1  
    End Sub  
    ```  
  
9. <span data-ttu-id="20d91-119">예제를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-119">Run the sample.</span></span> <span data-ttu-id="20d91-120">데이터를 편집하고 **이전** 및 **다음** 단추를 사용하여 데이터가 <xref:System.Data.DataSet>에 제대로 유지되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-120">Edit the data, and use the **Previous** and **Next** buttons to see that the data is properly persisted to the <xref:System.Data.DataSet>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20d91-121">예제</span><span class="sxs-lookup"><span data-stu-id="20d91-121">Example</span></span>  
 <span data-ttu-id="20d91-122">다음 코드 예제는 이전 프로시저를 완료한 결과로 발생하는 전체 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-122">The following code example is the full code listing that results from completing the previous procedure.</span></span>  
  
 [!code-cpp[MaskedTextBoxData#1](~/samples/snippets/cpp/VS_Snippets_Winforms/MaskedTextBoxData/cpp/form1.cpp#1)]
 [!code-csharp[MaskedTextBoxData#1](~/samples/snippets/csharp/VS_Snippets_Winforms/MaskedTextBoxData/CS/form1.cs#1)]
 [!code-vb[MaskedTextBoxData#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/MaskedTextBoxData/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="20d91-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="20d91-123">Compiling the Code</span></span>  
  
- <span data-ttu-id="20d91-124">시각적 C# 또는 시각적 기본 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-124">Create a Visual C# or Visual Basic project.</span></span>  
  
- <span data-ttu-id="20d91-125">이전 <xref:System.Windows.Forms.TextBox> 절차에 <xref:System.Windows.Forms.MaskedTextBox> 설명된 대로 양식에 및 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-125">Add the <xref:System.Windows.Forms.TextBox> and <xref:System.Windows.Forms.MaskedTextBox> controls to the form, as described in the previous procedure.</span></span>  
  
- <span data-ttu-id="20d91-126">프로젝트의 기본 양식에 대한 소스 코드 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-126">Open the source code file for the project's default form.</span></span>  
  
- <span data-ttu-id="20d91-127">이 파일의 소스 코드를 이전 "코드" 섹션에 나열된 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-127">Replace the source code in this file with the code listed in the previous "Code" section.</span></span>  
  
- <span data-ttu-id="20d91-128">애플리케이션을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="20d91-128">Compile the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20d91-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20d91-129">See also</span></span>

- [<span data-ttu-id="20d91-130">연습: MaskedTextBox 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="20d91-130">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
