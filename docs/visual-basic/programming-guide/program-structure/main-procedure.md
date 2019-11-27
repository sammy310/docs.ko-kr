---
title: 기본 절차
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: 61cd397b82b4bb9a8b24a1a7d30eaea68e37368f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347352"
---
# <a name="main-procedure-in-visual-basic"></a><span data-ttu-id="a8f54-102">Visual Basic의 Main 프로시저</span><span class="sxs-lookup"><span data-stu-id="a8f54-102">Main Procedure in Visual Basic</span></span>
<span data-ttu-id="a8f54-103">모든 Visual Basic 응용 프로그램은 `Main`라는 프로시저를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-103">Every Visual Basic application must contain a procedure called `Main`.</span></span> <span data-ttu-id="a8f54-104">이 절차는 응용 프로그램에 대 한 시작 지점 및 전반적인 제어 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-104">This procedure serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="a8f54-105">.NET Framework는 응용 프로그램을 로드 하 고 제어를 전달할 준비가 되었을 때 `Main` 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-105">The .NET Framework calls your `Main` procedure when it has loaded your application and is ready to pass control to it.</span></span> <span data-ttu-id="a8f54-106">Windows Forms 응용 프로그램을 만드는 경우를 제외 하 고 자체적으로 실행 되는 응용 프로그램에 대 한 `Main` 프로시저를 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-106">Unless you are creating a Windows Forms application, you must write the `Main` procedure for applications that run on their own.</span></span>

 <span data-ttu-id="a8f54-107">`Main`에는 먼저 실행 되는 코드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-107">`Main` contains the code that runs first.</span></span> <span data-ttu-id="a8f54-108">`Main`프로그램이 시작 될 때 먼저 로드 되는 폼을 확인 하거나, 응용 프로그램의 복사본이 이미 시스템에서 실행 되 고 있는지 확인 하거나, 응용 프로그램에 대 한 변수 집합을 설정 하거나, 응용 프로그램에 필요한 데이터베이스를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-108">In `Main`, you can determine which form is to be loaded first when the program starts, find out if a copy of your application is already running on the system, establish a set of variables for your application, or open a database that the application requires.</span></span>

## <a name="requirements-for-the-main-procedure"></a><span data-ttu-id="a8f54-109">주 절차에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a8f54-109">Requirements for the Main Procedure</span></span>
 <span data-ttu-id="a8f54-110">자체 (일반적으로 확장명 .exe)에서 실행 되는 파일은 `Main` 프로시저를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-110">A file that runs on its own (usually with extension .exe) must contain a `Main` procedure.</span></span> <span data-ttu-id="a8f54-111">라이브러리 (예: 확장명 .dll)는 자체에서 실행 되지 않으며 `Main` 프로시저가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-111">A library (for example with extension .dll) does not run on its own and does not require a `Main` procedure.</span></span> <span data-ttu-id="a8f54-112">만들 수 있는 다양 한 프로젝트 형식에 대 한 요구 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-112">The requirements for the different types of projects you can create are as follows:</span></span>

- <span data-ttu-id="a8f54-113">콘솔 응용 프로그램은 자체적으로 실행 되므로 하나 이상의 `Main` 프로시저를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-113">Console applications run on their own, and you must supply at least one `Main` procedure.</span></span>

- <span data-ttu-id="a8f54-114">Windows Forms 응용 프로그램은 자체적으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-114">Windows Forms applications run on their own.</span></span> <span data-ttu-id="a8f54-115">그러나 Visual Basic 컴파일러는 이러한 응용 프로그램에서 `Main` 프로시저를 자동으로 생성 하며,이를 작성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-115">However, the Visual Basic compiler automatically generates a `Main` procedure in such an application, and you do not need to write one.</span></span>

- <span data-ttu-id="a8f54-116">클래스 라이브러리에는 `Main` 프로시저가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-116">Class libraries do not require a `Main` procedure.</span></span> <span data-ttu-id="a8f54-117">여기에는 Windows 컨트롤 라이브러리 및 웹 컨트롤 라이브러리가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-117">These include Windows Control Libraries and Web Control Libraries.</span></span> <span data-ttu-id="a8f54-118">웹 응용 프로그램은 클래스 라이브러리로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-118">Web applications are deployed as class libraries.</span></span>

## <a name="declaring-the-main-procedure"></a><span data-ttu-id="a8f54-119">Main 프로시저 선언</span><span class="sxs-lookup"><span data-stu-id="a8f54-119">Declaring the Main Procedure</span></span>
 <span data-ttu-id="a8f54-120">`Main` 프로시저를 선언 하는 방법에는 네 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-120">There are four ways to declare the `Main` procedure.</span></span> <span data-ttu-id="a8f54-121">인수를 사용할 수 있으며 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-121">It can take arguments or not, and it can return a value or not.</span></span>

> [!NOTE]
> <span data-ttu-id="a8f54-122">클래스에서 `Main`를 선언 하는 경우 `Shared` 키워드를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-122">If you declare `Main` in a class, you must use the `Shared` keyword.</span></span> <span data-ttu-id="a8f54-123">모듈에서는 `Main` `Shared`필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-123">In a module, `Main` does not need to be `Shared`.</span></span>

- <span data-ttu-id="a8f54-124">가장 간단한 방법은 인수를 사용 하지 않거나 값을 반환 하지 않는 `Sub` 프로시저를 선언 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-124">The simplest way is to declare a `Sub` procedure that does not take arguments or return a value.</span></span>

    ```vb
    Module mainModule
        Sub Main()
            MsgBox("The Main procedure is starting the application.")
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```

- <span data-ttu-id="a8f54-125">`Main`는 운영 체제에서 프로그램의 종료 코드로 사용 하는 `Integer` 값을 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-125">`Main` can also return an `Integer` value, which the operating system uses as the exit code for your program.</span></span> <span data-ttu-id="a8f54-126">다른 프로그램은 Windows ERRORLEVEL 값을 검사 하 여이 코드를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-126">Other programs can test this code by examining the Windows ERRORLEVEL value.</span></span> <span data-ttu-id="a8f54-127">종료 코드를 반환 하려면 `Sub` 프로시저 대신 `Function` 프로시저로 `Main`를 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-127">To return an exit code, you must declare `Main` as a `Function` procedure instead of a `Sub` procedure.</span></span>

    ```vb
    Module mainModule
        Function Main() As Integer
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' Insert call to appropriate starting place in your code.
            ' On return, assign appropriate value to returnValue.
            ' 0 usually means successful completion.
            MsgBox("The application is terminating with error level " &
                 CStr(returnValue) & ".")
            Return returnValue
        End Function
    End Module
    ```

- <span data-ttu-id="a8f54-128">`Main` `String` 배열을 인수로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-128">`Main` can also take a `String` array as an argument.</span></span> <span data-ttu-id="a8f54-129">배열의 각 문자열은 프로그램을 호출 하는 데 사용 되는 명령줄 인수 중 하나를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-129">Each string in the array contains one of the command-line arguments used to invoke your program.</span></span> <span data-ttu-id="a8f54-130">값에 따라 다른 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-130">You can take different actions depending on their values.</span></span>

    ```vb
    Module mainModule
        Function Main(ByVal cmdArgs() As String) As Integer
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
            End If
            ' Insert call to appropriate starting place in your code.
            ' On return, assign appropriate value to returnValue.
            ' 0 usually means successful completion.
            MsgBox("The application is terminating with error level " &
                 CStr(returnValue) & ".")
            Return returnValue
        End Function
    End Module
    ```

- <span data-ttu-id="a8f54-131">다음과 같이 명령줄 인수를 검사 하지만 종료 코드를 반환 하지 않는 `Main`를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f54-131">You can declare `Main` to examine the command-line arguments but not return an exit code, as follows.</span></span>

    ```vb
    Module mainModule
        Sub Main(ByVal cmdArgs() As String)
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
            End If
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```
  
## <a name="see-also"></a><span data-ttu-id="a8f54-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8f54-132">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="a8f54-133">Visual Basic 프로그램의 구조</span><span class="sxs-lookup"><span data-stu-id="a8f54-133">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="a8f54-134">-main</span><span class="sxs-lookup"><span data-stu-id="a8f54-134">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="a8f54-135">공유</span><span class="sxs-lookup"><span data-stu-id="a8f54-135">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="a8f54-136">Sub 문</span><span class="sxs-lookup"><span data-stu-id="a8f54-136">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="a8f54-137">Function 문</span><span class="sxs-lookup"><span data-stu-id="a8f54-137">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="a8f54-138">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a8f54-138">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="a8f54-139">String 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a8f54-139">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
