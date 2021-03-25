---
title: Office interop 개체에 액세스하는 방법 - C# 프로그래밍 가이드
description: Office API 개체에 간편하게 액세스할 수 있는 C# 기능에 대해 알아봅니다. 새 기능을 사용하여 Excel 워크시트를 만들고 표시하는 코드를 작성합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- optional parameters [C#], Office programming
- named and optional arguments [C#], Office programming
- dynamic [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
- Office programming [C#]
ms.assetid: 041b25c2-3512-4e0f-a4ea-ceb2999e4d5e
ms.openlocfilehash: 6c2c49a9fd55c406b69c02586a9b0e4a1d16ccd4
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103479931"
---
# <a name="how-to-access-office-interop-objects-c-programming-guide"></a><span data-ttu-id="5c6c6-104">Office interop 개체에 액세스하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="5c6c6-104">How to access Office interop objects (C# Programming Guide)</span></span>

<span data-ttu-id="5c6c6-105">C#에는 Office API 개체에 간편하게 액세스할 수 있는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-105">C# has features that simplify access to Office API objects.</span></span> <span data-ttu-id="5c6c6-106">새로운 기능에는 명명된 인수와 선택적 인수, `dynamic`이라는 새 형식 그리고 인수를 값 매개 변수처럼 COM 메서드의 참조 매개 변수로 전달하는 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-106">The new features include named and optional arguments, a new type called `dynamic`, and the ability to pass arguments to reference parameters in COM methods as if they were value parameters.</span></span>

<span data-ttu-id="5c6c6-107">이 항목에서는 새 기능을 사용하여 Microsoft Office Excel 워크시트를 만들고 표시하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-107">In this topic you will use the new features to write code that creates and displays a Microsoft Office Excel worksheet.</span></span> <span data-ttu-id="5c6c6-108">그런 다음 Excel 워크시트에 연결된 아이콘이 들어 있는 Office Word 문서를 추가하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-108">You will then write code to add an Office Word document that contains an icon that is linked to the Excel worksheet.</span></span>

<span data-ttu-id="5c6c6-109">이 연습을 완료하려면 Microsoft Office Excel 2007 및 Microsoft Office Word 2007 이상 버전이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-109">To complete this walkthrough, you must have Microsoft Office Excel 2007 and Microsoft Office Word 2007, or later versions, installed on your computer.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-new-console-application"></a><span data-ttu-id="5c6c6-110">새 콘솔 애플리케이션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5c6c6-110">To create a new console application</span></span>

1. <span data-ttu-id="5c6c6-111">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-111">Start Visual Studio.</span></span>

2. <span data-ttu-id="5c6c6-112">**파일** 메뉴에서 **새로 만들기** 를 가리킨 다음 **프로젝트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-112">On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="5c6c6-113">**새 프로젝트** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-113">The **New Project** dialog box appears.</span></span>

3. <span data-ttu-id="5c6c6-114">**설치된 템플릿** 창에서 **Visual C#** 을 확장한 다음 **Windows** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-114">In the **Installed Templates** pane, expand **Visual C#**, and then click **Windows**.</span></span>

4. <span data-ttu-id="5c6c6-115">**새 프로젝트** 대화 상자 위쪽에서 **.NET Framework 4** 이상 버전이 대상 프레임워크로 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-115">Look at the top of the **New Project** dialog box to make sure that **.NET Framework 4** (or later version) is selected as a target framework.</span></span>

5. <span data-ttu-id="5c6c6-116">**템플릿** 창에서 **콘솔 애플리케이션** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-116">In the **Templates** pane, click **Console Application**.</span></span>

6. <span data-ttu-id="5c6c6-117">**이름** 필드에 프로젝트의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-117">Type a name for your project in the **Name** field.</span></span>

7. <span data-ttu-id="5c6c6-118">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-118">Click **OK**.</span></span>

     <span data-ttu-id="5c6c6-119">**솔루션 탐색기** 에 새 프로젝트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-119">The new project appears in **Solution Explorer**.</span></span>

## <a name="to-add-references"></a><span data-ttu-id="5c6c6-120">참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="5c6c6-120">To add references</span></span>

1. <span data-ttu-id="5c6c6-121">**솔루션 탐색기** 에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **참조 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-121">In **Solution Explorer**, right-click your project's name and then click **Add Reference**.</span></span> <span data-ttu-id="5c6c6-122">**참조 추가** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-122">The **Add Reference** dialog box appears.</span></span>

2. <span data-ttu-id="5c6c6-123">**어셈블리** 페이지의 **구성 요소 이름** 목록에서 **Microsoft.Office.Interop.Word** 를 선택하고 Ctrl 키를 누른 상태로 **Microsoft.Office.Interop.Excel** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-123">On the **Assemblies**  page, select **Microsoft.Office.Interop.Word** in the **Component Name** list, and then hold down the CTRL key and select **Microsoft.Office.Interop.Excel**.</span></span>  <span data-ttu-id="5c6c6-124">이러한 어셈블리가 보이지 않으면 어셈블리가 설치되어 있으며 표시되는지를 확인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-124">If you do not see the assemblies, you may need to ensure they are installed and displayed.</span></span> <span data-ttu-id="5c6c6-125">[방법: Office Primary Interop Assemblies](/visualstudio/vsto/how-to-install-office-primary-interop-assemblies)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-125">See [How to: Install Office Primary Interop Assemblies](/visualstudio/vsto/how-to-install-office-primary-interop-assemblies).</span></span>

3. <span data-ttu-id="5c6c6-126">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-126">Click **OK**.</span></span>

## <a name="to-add-necessary-using-directives"></a><span data-ttu-id="5c6c6-127">필요한 using 지시문을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="5c6c6-127">To add necessary using directives</span></span>

1. <span data-ttu-id="5c6c6-128">**솔루션 탐색기** 에서 *Program.cs* 파일을 마우스 오른쪽 단추로 클릭하고 **코드 보기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-128">In **Solution Explorer**, right-click the *Program.cs* file and then click **View Code**.</span></span>

2. <span data-ttu-id="5c6c6-129">다음 `using` 지시문을 코드 파일의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-129">Add the following `using` directives to the top of the code file:</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#1)]

## <a name="to-create-a-list-of-bank-accounts"></a><span data-ttu-id="5c6c6-130">은행 계좌 목록을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5c6c6-130">To create a list of bank accounts</span></span>

1. <span data-ttu-id="5c6c6-131">다음 클래스 정의를 **Program.cs** 의 `Program` 클래스 아래에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-131">Paste the following class definition into **Program.cs**, under the `Program` class.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#2)]

2. <span data-ttu-id="5c6c6-132">다음 코드를 `Main` 메서드에 추가하여 계좌 두 개가 포함된 `bankAccounts` 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-132">Add the following code to the `Main` method to create a `bankAccounts` list that contains two accounts.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#3)]

## <a name="to-declare-a-method-that-exports-account-information-to-excel"></a><span data-ttu-id="5c6c6-133">계좌 정보를 Excel로 내보내는 메서드를 선언하려면</span><span class="sxs-lookup"><span data-stu-id="5c6c6-133">To declare a method that exports account information to Excel</span></span>

1. <span data-ttu-id="5c6c6-134">다음 메서드를 `Program` 클래스에 추가하여 Excel 워크시트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-134">Add the following method to the `Program` class to set up an Excel worksheet.</span></span>

     <span data-ttu-id="5c6c6-135"><xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A> 메서드에는 특정 템플릿을 지정하기 위한 선택적 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-135">Method <xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A> has an optional parameter for specifying a particular template.</span></span> <span data-ttu-id="5c6c6-136">C# 4에서 도입된 선택적 매개 변수를 사용하면 매개 변수의 기본값을 사용하려는 경우 해당 매개 변수의 인수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-136">Optional parameters, new in C# 4, enable you to omit the argument for that parameter if you want to use the parameter's default value.</span></span> <span data-ttu-id="5c6c6-137">다음 코드에서는 인수가 전송되지 않으므로 `Add`는 기본 템플릿을 사용하며 새 통합 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-137">Because no argument is sent in the following code, `Add` uses the default template and creates a new workbook.</span></span> <span data-ttu-id="5c6c6-138">이전 버전의 C#에서 이와 동일한 문을 사용하려면 자리 표시자 인수인 `ExcelApp.Workbooks.Add(Type.Missing)`를 사용해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-138">The equivalent statement in earlier versions of C# requires a placeholder argument: `ExcelApp.Workbooks.Add(Type.Missing)`.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#4)]

2. <span data-ttu-id="5c6c6-139">`DisplayInExcel` 끝에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-139">Add the following code at the end of `DisplayInExcel`.</span></span> <span data-ttu-id="5c6c6-140">이 코드는 워크시트 첫 번째 행의 처음 두 열에 값을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-140">The code inserts values into the first two columns of the first row of the worksheet.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#5)]

3. <span data-ttu-id="5c6c6-141">`DisplayInExcel` 끝에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-141">Add the following code at the end of `DisplayInExcel`.</span></span> <span data-ttu-id="5c6c6-142">`foreach` 루프는 계좌 목록의 정보를 워크시트에서 연속 행의 처음 두 열에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-142">The `foreach` loop puts the information from the list of accounts into the first two columns of successive rows of the worksheet.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#7)]

4. <span data-ttu-id="5c6c6-143">열 너비를 콘텐츠에 맞게 조정하려면 `DisplayInExcel` 끝에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-143">Add the following code at the end of `DisplayInExcel` to adjust the column widths to fit the content.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#13)]

     <span data-ttu-id="5c6c6-144">이전 버전의 C#에서는 이러한 작업을 명시적으로 캐스트해야 했습니다. `ExcelApp.Columns[1]`은 `Object`를 반환하며 `AutoFit`은 Excel <xref:Microsoft.Office.Interop.Excel.Range> 메서드이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-144">Earlier versions of C# require explicit casting for these operations because `ExcelApp.Columns[1]` returns an `Object`, and `AutoFit` is an Excel <xref:Microsoft.Office.Interop.Excel.Range> method.</span></span> <span data-ttu-id="5c6c6-145">다음 줄에는 캐스팅이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-145">The following lines show the casting.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#14)]

     <span data-ttu-id="5c6c6-146">C# 4 이상 버전에서는 [**EmbedInteropTypes**](../../language-reference/compiler-options/inputs.md#embedinteroptypes) 컴파일러 옵션이 어셈블리를 참조한 경우 또는 이와 동등하게 Excel의 **Interop 형식 포함** 속성이 true로 설정되어 있는 경우, 반환된 `Object`를 `dynamic`으로 자동 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-146">C# 4, and later versions, converts the returned `Object` to `dynamic` automatically if the assembly is referenced by the [**EmbedInteropTypes**](../../language-reference/compiler-options/inputs.md#embedinteroptypes) compiler option or, equivalently, if the Excel **Embed Interop Types** property is set to true.</span></span> <span data-ttu-id="5c6c6-147">이 속성의 기본값은 true입니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-147">True is the default value for this property.</span></span>

## <a name="to-run-the-project"></a><span data-ttu-id="5c6c6-148">프로젝트를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="5c6c6-148">To run the project</span></span>

1. <span data-ttu-id="5c6c6-149">`Main` 끝에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-149">Add the following line at the end of `Main`.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#8)]

2. <span data-ttu-id="5c6c6-150">Ctrl+F5를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-150">Press CTRL+F5.</span></span>

     <span data-ttu-id="5c6c6-151">두 계좌의 데이터가 포함된 Excel 워크시트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-151">An Excel worksheet appears that contains the data from the two accounts.</span></span>

## <a name="to-add-a-word-document"></a><span data-ttu-id="5c6c6-152">Word 문서를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="5c6c6-152">To add a Word document</span></span>

1. <span data-ttu-id="5c6c6-153">C# 4 이상 버전에서 Office 프로그래밍을 향상하는 추가 방법을 설명하기 위해, 다음 코드에서는 Word 애플리케이션을 열고 Excel 워크시트에 연결되는 아이콘을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-153">To illustrate additional ways in which C# 4, and later versions, enhances Office programming, the following code opens a Word application and creates an icon that links to the Excel worksheet.</span></span>

     <span data-ttu-id="5c6c6-154">이 단계의 뒷부분에서 제공되는 `CreateIconInWordDoc` 메서드를 `Program` 클래스에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-154">Paste method `CreateIconInWordDoc`, provided later in this step, into the `Program` class.</span></span> <span data-ttu-id="5c6c6-155">`CreateIconInWordDoc`는 명명된 인수와 선택적 인수를 사용하여 <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> 및 <xref:Microsoft.Office.Interop.Word.Selection.PasteSpecial%2A>에 대한 메서드 호출의 복잡성을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-155">`CreateIconInWordDoc` uses named and optional arguments to reduce the complexity of the method calls to <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> and <xref:Microsoft.Office.Interop.Word.Selection.PasteSpecial%2A>.</span></span> <span data-ttu-id="5c6c6-156">이러한 호출에는 C# 4에 도입된 다른 두 가지 새 기능이 통합됩니다. 이러한 기능은 참조 매개 변수가 포함된 COM 메서드 호출을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-156">These calls incorporate two other new features introduced in C# 4 that simplify calls to COM methods that have reference parameters.</span></span> <span data-ttu-id="5c6c6-157">그 중 첫 번째 기능은 인수를 값 매개 변수처럼 참조 매개 변수로 전달하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-157">First, you can send arguments to the reference parameters as if they were value parameters.</span></span> <span data-ttu-id="5c6c6-158">즉, 각 참조 매개 변수에 대한 변수를 만들지 않고 직접 값을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-158">That is, you can send values directly, without creating a variable for each reference parameter.</span></span> <span data-ttu-id="5c6c6-159">컴파일러는 인수 값을 저장하기 위한 임시 변수를 생성하고 호출에서 값이 반환되면 해당 변수를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-159">The compiler generates temporary variables to hold the argument values, and discards the variables when you return from the call.</span></span> <span data-ttu-id="5c6c6-160">두 번째 기능은 인수 목록의 `ref` 키워드를 생략하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-160">Second, you can omit the `ref` keyword in the argument list.</span></span>

     <span data-ttu-id="5c6c6-161">`Add` 메서드에는 참조 매개 변수 4개가 있습니다(모두 선택적 매개 변수임).</span><span class="sxs-lookup"><span data-stu-id="5c6c6-161">The `Add` method has four reference parameters, all of which are optional.</span></span> <span data-ttu-id="5c6c6-162">C# 4.0 이상 버전에서는 기본값을 사용하려는 경우 모든 매개 변수 또는 원하는 매개 변수의 인수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-162">In C# 4.0 and later versions, you can omit arguments for any or all of the parameters if you want to use their default values.</span></span> <span data-ttu-id="5c6c6-163">C# 3.0 이하 버전에서는 각 매개 변수에 대해 인수를 제공해야 하며 매개 변수가 참조 매개 변수이므로 인수는 변수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-163">In C# 3.0 and earlier versions, an argument must be provided for each parameter, and the argument must be a variable because the parameters are reference parameters.</span></span>

     <span data-ttu-id="5c6c6-164">`PasteSpecial` 메서드는 클립보드의 내용을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-164">The `PasteSpecial` method inserts the contents of the Clipboard.</span></span> <span data-ttu-id="5c6c6-165">이 메서드에는 참조 매개 변수 7개가 있습니다(모두 선택적 매개 변수임).</span><span class="sxs-lookup"><span data-stu-id="5c6c6-165">The method has seven reference parameters, all of which are optional.</span></span> <span data-ttu-id="5c6c6-166">다음 코드는 이러한 매개 변수 중 두 개에 대해 인수를 지정합니다. 그 중 하나는 클립보드 내용의 소스에 대한 링크를 만드는 `Link`이고 다른 하나는 링크를 아이콘으로 표시하는 `DisplayAsIcon`입니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-166">The following code specifies arguments for two of them: `Link`, to create a link to the source of the Clipboard contents, and `DisplayAsIcon`, to display the link as an icon.</span></span> <span data-ttu-id="5c6c6-167">C# 4.0 이상 버전에서는 이 두 매개 변수에 대해 명명된 인수를 사용하고 나머지 인수는 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-167">In C# 4.0 and later versions, you can use named arguments for those two and omit the others.</span></span> <span data-ttu-id="5c6c6-168">이러한 매개 변수는 참조 매개 변수이지만 `ref` 키워드를 사용하거나 인수로 보낼 변수를 만들 필요가 없으며,</span><span class="sxs-lookup"><span data-stu-id="5c6c6-168">Although these are reference parameters, you do not have to use the `ref` keyword, or to create variables to send in as arguments.</span></span> <span data-ttu-id="5c6c6-169">값을 직접 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-169">You can send the values directly.</span></span> <span data-ttu-id="5c6c6-170">C# 3.0 이하 버전에서는 각 참조 매개 변수에 대해 가변 인수를 공급해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-170">In C# 3.0 and earlier versions, you must supply a variable argument for each reference parameter.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#9)]

     <span data-ttu-id="5c6c6-171">C# 3.0 이하 버전의 언어에서는 다음과 같은 더 복잡한 코드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-171">In C# 3.0 and earlier versions of the language, the following more complex code is required.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#10)]

2. <span data-ttu-id="5c6c6-172">`Main` 끝에 다음 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-172">Add the following statement at the end of `Main`.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#11)]

3. <span data-ttu-id="5c6c6-173">`DisplayInExcel` 끝에 다음 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-173">Add the following statement at the end of `DisplayInExcel`.</span></span> <span data-ttu-id="5c6c6-174">`Copy` 메서드는 클립보드에 워크시트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-174">The `Copy` method adds the worksheet to the Clipboard.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#12)]

4. <span data-ttu-id="5c6c6-175">Ctrl+F5를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-175">Press CTRL+F5.</span></span>

     <span data-ttu-id="5c6c6-176">아이콘이 포함된 Word 문서가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-176">A Word document appears that contains an icon.</span></span> <span data-ttu-id="5c6c6-177">아이콘을 두 번 클릭하여 워크시트를 포그라운드로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-177">Double-click the icon to bring the worksheet to the foreground.</span></span>

## <a name="to-set-the-embed-interop-types-property"></a><span data-ttu-id="5c6c6-178">Interop 형식 포함 속성을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="5c6c6-178">To set the Embed Interop Types property</span></span>

1. <span data-ttu-id="5c6c6-179">런타임에 PIA(주 interop 어셈블리)를 사용하지 않아도 되는 COM 형식을 호출할 때는 코드를 추가로 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-179">Additional enhancements are possible when you call a COM type that does not require a primary interop assembly (PIA) at run time.</span></span> <span data-ttu-id="5c6c6-180">PIA에 대한 종속성을 제거하면 버전을 독립적으로 실행할 수 있으며 보다 쉽게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-180">Removing the dependency on PIAs results in version independence and easier deployment.</span></span> <span data-ttu-id="5c6c6-181">PIA를 사용하지 않는 프로그래밍의 장점에 대한 자세한 내용은 [연습: 관리되는 어셈블리의 형식 포함](../../../standard/assembly/embed-types-visual-studio.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-181">For more information about the advantages of programming without PIAs, see [Walkthrough: Embedding Types from Managed Assemblies](../../../standard/assembly/embed-types-visual-studio.md).</span></span>

     <span data-ttu-id="5c6c6-182">또한 COM 메서드에서 사용해야 하며 반환되는 형식은 `dynamic`가 아닌 `Object` 형식을 사용하여 표시할 수 있으므로 프로그램이 더욱 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-182">In addition, programming is easier because the types that are required and returned by COM methods can be represented by using the type `dynamic` instead of `Object`.</span></span> <span data-ttu-id="5c6c6-183">`dynamic` 형식이 포함된 변수는 런타임까지 평가되지 않으므로 명시적 캐스팅을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-183">Variables that have type `dynamic` are not evaluated until run time, which eliminates the need for explicit casting.</span></span> <span data-ttu-id="5c6c6-184">자세한 내용은 [dynamic 형식 사용](../types/using-type-dynamic.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-184">For more information, see [Using Type dynamic](../types/using-type-dynamic.md).</span></span>

     <span data-ttu-id="5c6c6-185">C# 4에서는 PIA를 사용하는 대신 형식 정보를 포함하는 것이 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-185">In C# 4, embedding type information instead of using PIAs is default behavior.</span></span> <span data-ttu-id="5c6c6-186">이러한 기본 동작으로 인해 명시적 캐스팅이 필요하지 않으므로 위의 여러 예제가 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-186">Because of that default, several of the previous examples are simplified because explicit casting is not required.</span></span> <span data-ttu-id="5c6c6-187">예를 들어 `worksheet`의 `DisplayInExcel` 선언은 `Excel._Worksheet workSheet = excelApp.ActiveSheet`가 아닌 `Excel._Worksheet workSheet = (Excel.Worksheet)excelApp.ActiveSheet`로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-187">For example, the declaration of `worksheet` in `DisplayInExcel` is written as `Excel._Worksheet workSheet = excelApp.ActiveSheet` rather than `Excel._Worksheet workSheet = (Excel.Worksheet)excelApp.ActiveSheet`.</span></span> <span data-ttu-id="5c6c6-188">마찬가지로 기본 동작이 없으면 같은 메서드의 `AutoFit`에 대한 호출에서도 명시적 캐스팅을 수행해야 합니다. `ExcelApp.Columns[1]`는 `Object`를 반환하며 `AutoFit`은 Excel 메서드이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-188">The calls to `AutoFit` in the same method also would require explicit casting without the default, because `ExcelApp.Columns[1]` returns an `Object`, and `AutoFit` is an Excel  method.</span></span> <span data-ttu-id="5c6c6-189">다음 코드에서는 캐스팅을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-189">The following code shows the casting.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#14)]

2. <span data-ttu-id="5c6c6-190">형식 정보를 포함하는 대신 기본값을 변경하여 PIA를 사용하려면 **솔루션 탐색기** 에서 **참조** 노드를 확장하고 **Microsoft.Office.Interop.Excel** 또는 **Microsoft.Office.Interop.Word** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-190">To change the default and use PIAs instead of embedding type information, expand the **References** node in **Solution Explorer** and then select **Microsoft.Office.Interop.Excel** or **Microsoft.Office.Interop.Word**.</span></span>

3. <span data-ttu-id="5c6c6-191">**속성** 창이 보이지 않으면 **F4** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-191">If you cannot see the **Properties** window, press **F4**.</span></span>

4. <span data-ttu-id="5c6c6-192">속성 목록에서 **Interop 형식 포함** 을 찾은 다음 해당 값을 **False** 로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-192">Find **Embed Interop Types** in the list of properties, and change its value to **False**.</span></span> <span data-ttu-id="5c6c6-193">마찬가지로 명령 프롬프트에서 [**EmbedInteropTypes**](../../language-reference/compiler-options/inputs.md#embedinteroptypes) 대신 [**References**](../../language-reference/compiler-options/inputs.md#references) 컴파일러 옵션을 사용하여 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-193">Equivalently, you can compile by using the [**References**](../../language-reference/compiler-options/inputs.md#references) compiler option instead of [**EmbedInteropTypes**](../../language-reference/compiler-options/inputs.md#embedinteroptypes) at a command prompt.</span></span>

## <a name="to-add-additional-formatting-to-the-table"></a><span data-ttu-id="5c6c6-194">표에 서식을 더 추가하려면</span><span class="sxs-lookup"><span data-stu-id="5c6c6-194">To add additional formatting to the table</span></span>

1. <span data-ttu-id="5c6c6-195">`AutoFit`에서 `DisplayInExcel`에 대한 두 호출을 다음 문으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-195">Replace the two calls to `AutoFit` in `DisplayInExcel` with the following statement.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#15)]

     <span data-ttu-id="5c6c6-196"><xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> 메서드에는 모두 선택적 매개 변수인 값 매개 변수 7개가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-196">The <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> method has seven value parameters, all of which are optional.</span></span> <span data-ttu-id="5c6c6-197">명명된 인수와 선택적 인수를 사용하여 이러한 매개 변수 중 일부 또는 모두에 대해 인수를 제공할 수도 있고 모든 매개 변수에 인수를 제공하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-197">Named and optional arguments enable you to provide arguments for none, some, or all of them.</span></span> <span data-ttu-id="5c6c6-198">위의 문에서는 `Format` 매개 변수 하나에만 인수가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-198">In the previous statement, an argument is supplied for only one of the parameters, `Format`.</span></span> <span data-ttu-id="5c6c6-199">`Format`은 매개 변수 목록의 첫 번째 매개 변수이므로 매개 변수 이름은 지정하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-199">Because `Format` is the first parameter in the parameter list, you do not have to provide the parameter name.</span></span> <span data-ttu-id="5c6c6-200">그러나 다음 코드에 나와 있는 것처럼 매개 변수 이름을 포함하면 문을 더 쉽게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-200">However, the statement might be easier to understand if the parameter name is included, as is shown in the following code.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#16)]

2. <span data-ttu-id="5c6c6-201">결과를 보려면 CTRL+F5를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-201">Press CTRL+F5 to see the result.</span></span> <span data-ttu-id="5c6c6-202">기타 서식은 <xref:Microsoft.Office.Interop.Excel.XlRangeAutoFormat> 열거형에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-202">Other formats are listed in the <xref:Microsoft.Office.Interop.Excel.XlRangeAutoFormat> enumeration.</span></span>

3. <span data-ttu-id="5c6c6-203">1단계의 문을 다음 코드와 비교합니다. 이 코드는 C# 3.0 이하 버전에 필요한 인수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-203">Compare the statement in step 1 with the following code, which shows the arguments that are required in C# 3.0 and earlier versions.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#17)]

## <a name="example"></a><span data-ttu-id="5c6c6-204">예제</span><span class="sxs-lookup"><span data-stu-id="5c6c6-204">Example</span></span>

<span data-ttu-id="5c6c6-205">다음 코드에서는 전체 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-205">The following code shows the complete example.</span></span>

[!code-csharp[csProgGuideOfficeHowTo#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/walkthrough.cs#18)]

## <a name="see-also"></a><span data-ttu-id="5c6c6-206">참조</span><span class="sxs-lookup"><span data-stu-id="5c6c6-206">See also</span></span>

- <xref:System.Type.Missing?displayProperty=nameWithType>
- [<span data-ttu-id="5c6c6-207">dynamic</span><span class="sxs-lookup"><span data-stu-id="5c6c6-207">dynamic</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="5c6c6-208">dynamic 형식 사용</span><span class="sxs-lookup"><span data-stu-id="5c6c6-208">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="5c6c6-209">명명된 인수 및 선택적 인수</span><span class="sxs-lookup"><span data-stu-id="5c6c6-209">Named and Optional Arguments</span></span>](../classes-and-structs/named-and-optional-arguments.md)
- [<span data-ttu-id="5c6c6-210">Office 프로그래밍에 명명된 인수와 선택적 인수 사용 방법</span><span class="sxs-lookup"><span data-stu-id="5c6c6-210">How to use named and optional arguments in Office programming</span></span>](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
