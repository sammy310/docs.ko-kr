---
title: Hello World -- 프로그램 처음 만들기 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 62aaf8785b0dfb646ea804dab6918940f1e33346
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635296"
---
# <a name="hello-world----your-first-program-c-programming-guide"></a><span data-ttu-id="97db2-102">Hello World -- 프로그램 처음 만들기(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="97db2-102">Hello World -- Your first program (C# Programming Guide)</span></span>

<span data-ttu-id="97db2-103">다음 절차에서는 기존 "Hello World!" 프로그램의 C# 버전을</span><span class="sxs-lookup"><span data-stu-id="97db2-103">The following procedure creates a C# version of the traditional "Hello World!"</span></span> <span data-ttu-id="97db2-104">만듭니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-104">program.</span></span> <span data-ttu-id="97db2-105">이 프로그램은 문자열 `Hello World!`를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-105">The program displays the string `Hello World!`</span></span>

<span data-ttu-id="97db2-106">소개 개념에 대한 추가 예제는 [Visual C# 및 Visual Basic 시작](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97db2-106">For more examples of introductory concepts, see [Getting Started with Visual C# and Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-and-run-a-console-application"></a><span data-ttu-id="97db2-107">콘솔 애플리케이션을 만들고 실행하려면</span><span class="sxs-lookup"><span data-stu-id="97db2-107">To create and run a console application</span></span>

1. <span data-ttu-id="97db2-108">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-108">Start Visual Studio.</span></span>

2. <span data-ttu-id="97db2-109">메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-109">On the menu bar, choose **File**, **New**, **Project**.</span></span>

     <span data-ttu-id="97db2-110">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-110">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="97db2-111">**설치됨**, **템플릿**, **Visual C#** 을 차례로 확장하고 **콘솔 애플리케이션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-111">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>

4. <span data-ttu-id="97db2-112">**이름** 상자에 프로젝트의 이름을 지정하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-112">In the **Name** box, specify a name for your project, and then choose the **OK** button.</span></span>

     <span data-ttu-id="97db2-113">**솔루션 탐색기**에 새 프로젝트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-113">The new project appears in **Solution Explorer**.</span></span>

5. <span data-ttu-id="97db2-114">Program.cs가 **코드 편집기**에 열려 있지 않으면 **솔루션 탐색기**에서 **Program.cs**의 바로 가기 메뉴를 열고 **코드 보기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-114">If Program.cs isn't open in the **Code Editor**, open the shortcut menu for **Program.cs** in **Solution Explorer**, and then choose **View Code**.</span></span>

6. <span data-ttu-id="97db2-115">Program.cs의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-115">Replace the contents of Program.cs with the following code.</span></span>

     [!code-csharp[csProgGuide#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#21)]

7. <span data-ttu-id="97db2-116">F5 키를 선택하여 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-116">Choose the F5 key to run the project.</span></span> <span data-ttu-id="97db2-117">`Hello World!` 줄이 포함된 명령 프롬프트 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-117">A Command Prompt window appears that contains the line `Hello World!`</span></span>

<span data-ttu-id="97db2-118">다음으로 이 프로그램의 중요 경로가 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-118">Next, the important parts of this program are examined.</span></span>

## <a name="comments"></a><span data-ttu-id="97db2-119">설명</span><span class="sxs-lookup"><span data-stu-id="97db2-119">Comments</span></span>

<span data-ttu-id="97db2-120">첫 번째 줄에는 설명이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-120">The first line contains a comment.</span></span> <span data-ttu-id="97db2-121">`//` 문자는 줄의 나머지 부분을 설명으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-121">The characters `//` convert the rest of the line to a comment.</span></span>

 [!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

<span data-ttu-id="97db2-122">텍스트 블록을 `/*` 및 `*/` 문자 사이에 포함하여 주석으로 처리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-122">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="97db2-123">다음 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-123">This is shown in the following example.</span></span>

 [!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

## <a name="main-method"></a><span data-ttu-id="97db2-124">Main 메서드</span><span class="sxs-lookup"><span data-stu-id="97db2-124">Main method</span></span>

<span data-ttu-id="97db2-125">C# 콘솔 애플리케이션에는 시작 및 끝을 제어하는 `Main` 메서드가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-125">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="97db2-126">`Main` 메서드에서 개체를 만들고 다른 메서드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-126">The `Main` method is where you create objects and execute other methods.</span></span>

<span data-ttu-id="97db2-127">`Main` 메서드는 클래스나 구조체 내부에 있는 [정적](../../../csharp/language-reference/keywords/static.md) 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-127">The `Main` method is a [static](../../../csharp/language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="97db2-128">이전 "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="97db2-128">In the previous "Hello World!"</span></span> <span data-ttu-id="97db2-129">예제에서 이 메서드는 `Hello` 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-129">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="97db2-130">다음 방법 중 하나로 `Main` 메서드를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-130">You can declare the `Main` method in one of the following ways:</span></span>

- <span data-ttu-id="97db2-131">이 메서드는 `void`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-131">It can return `void`.</span></span>

     [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- <span data-ttu-id="97db2-132">정수를 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-132">It can also return an integer.</span></span>

     [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- <span data-ttu-id="97db2-133">반환 형식은 각각 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-133">With either of the return types, it can take arguments.</span></span>

     [!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

     <span data-ttu-id="97db2-134">또는</span><span class="sxs-lookup"><span data-stu-id="97db2-134">-or-</span></span>

     [!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

<span data-ttu-id="97db2-135">`Main` 메서드의 매개 변수 `args`는 프로그램을 호출하는 데 사용된 명령줄 인수가 포함된 `string` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-135">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span> <span data-ttu-id="97db2-136">C++의 경우와는 달리 배열에 실행(exe) 파일의 이름이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-136">Unlike in C++, the array does not include the name of the executable (exe) file.</span></span>

<span data-ttu-id="97db2-137">명령줄 인수를 사용하는 방법에 대한 자세한 내용은 [Main() 및 명령줄 인수](../../../csharp/programming-guide/main-and-command-args/index.md) 및 [방법: 명령줄을 사용하여 어셈블리 만들기 및 사용](../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97db2-137">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) and [How to: Create and Use Assemblies Using the Command Line](../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span></span>

<span data-ttu-id="97db2-138">`Main` 메서드가 끝날 때 <xref:System.Console.ReadKey%2A>를 호출하면 프로그램을 디버그 모드에서 실행할 경우 F5 키를 눌러 출력을 읽을 수 있게 될 때까지 콘솔 창이 닫히지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-138">The call to <xref:System.Console.ReadKey%2A> at the end of the `Main` method prevents the console window from closing before you have a chance to read the output when you run your program in debug mode, by pressing F5.</span></span>

## <a name="input-and-output"></a><span data-ttu-id="97db2-139">입력 및 출력</span><span class="sxs-lookup"><span data-stu-id="97db2-139">Input and output</span></span>

<span data-ttu-id="97db2-140">일반적으로 C# 프로그램에서는 .NET Framework의 런타임 라이브러리에서 제공되는 입출력 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-140">C# programs generally use the input/output services provided by the run-time library of the .NET Framework.</span></span> <span data-ttu-id="97db2-141">`System.Console.WriteLine("Hello World!");` 문은 <xref:System.Console.WriteLine%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-141">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="97db2-142">이 메서드는 런타임 라이브러리에 있는 <xref:System.Console> 클래스의 출력 메서드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-142">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="97db2-143">이 메서드는 표준 출력 스트림에 문자열 매개 변수를 표시하고 이어서 새 줄을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-143">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="97db2-144">기타 <xref:System.Console> 메서드는 다양한 입력 및 출력 작업에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-144">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="97db2-145">프로그램 시작 부분에 `using System;` 지시문을 포함하면 <xref:System> 클래스 및 메서드를 정규화하지 않고 바로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-145">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="97db2-146">예를 들어 `System.Console.WriteLine` 대신 `Console.WriteLine`을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-146">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>

 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

 [!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="97db2-147">입출력 메서드에 대한 자세한 내용은 <xref:System.IO>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97db2-147">For more information about input/output methods, see <xref:System.IO>.</span></span>

## <a name="command-line-compilation-and-execution"></a><span data-ttu-id="97db2-148">명령줄 컴파일 및 실행</span><span class="sxs-lookup"><span data-stu-id="97db2-148">Command-line compilation and execution</span></span>

<span data-ttu-id="97db2-149">"Hello World!"</span><span class="sxs-lookup"><span data-stu-id="97db2-149">You can compile the "Hello World!"</span></span> <span data-ttu-id="97db2-150">프로그램을 컴파일하려면 Visual Studio IDE(통합 개발 환경) 대신 명령줄을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-150">program by using the command line instead of the Visual Studio Integrated Development Environment (IDE).</span></span>

### <a name="to-compile-and-run-from-a-command-prompt"></a><span data-ttu-id="97db2-151">명령 프롬프트에서 컴파일 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="97db2-151">To compile and run from a command prompt</span></span>

1. <span data-ttu-id="97db2-152">이전 절차의 코드를 텍스트 편집기에 붙여넣고 파일을 텍스트 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-152">Paste the code from the preceding procedure into any text editor, and then save the file as a text file.</span></span> <span data-ttu-id="97db2-153">파일 이름을 `Hello.cs`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-153">Name the file `Hello.cs`.</span></span> <span data-ttu-id="97db2-154">C# 소스 코드 파일에는 `.cs` 확장명이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-154">C# source code files use the extension `.cs`.</span></span>

2. <span data-ttu-id="97db2-155">다음 단계 중 하나를 수행하여 명령 프롬프트 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-155">Perform one of the following steps to open a command-prompt window:</span></span>

    - <span data-ttu-id="97db2-156">Windows 10의 경우 **시작** 메뉴에서 `Developer Command Prompt`를 검색하고 **VS 2017용 개발자 명령 프롬프트**를 탭하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-156">In Windows 10, on the **Start** menu, search for `Developer Command Prompt`, and then tap or choose **Developer Command Prompt for VS 2017**.</span></span>

         <span data-ttu-id="97db2-157">개발자 명령 프롬프트 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-157">A Developer Command Prompt window appears.</span></span>

    - <span data-ttu-id="97db2-158">Windows 7의 경우 **시작** 메뉴를 열고, Visual Studio 현재 버전의 폴더를 확장하고, **Visual Studio Tools**의 바로 가기 메뉴를 열고 나서, **VS 2017용 개발자 명령 프롬프트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-158">In Windows 7, open the **Start** menu, expand the folder for the current version of Visual Studio, open the shortcut menu for **Visual Studio Tools**, and then choose **Developer Command Prompt for VS 2017**.</span></span>

         <span data-ttu-id="97db2-159">개발자 명령 프롬프트 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-159">A Developer Command Prompt window appears.</span></span>

    - <span data-ttu-id="97db2-160">표준 명령 프롬프트 창에서 명령줄 빌드를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-160">Enable command-line builds from a standard Command Prompt window.</span></span>

         <span data-ttu-id="97db2-161">[방법: Visual Studio 명령줄에 필요한 환경 변수 설정](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97db2-161">See [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span></span>

3. <span data-ttu-id="97db2-162">명령 프롬프트 창에서 `Hello.cs` 파일이 포함된 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-162">In the command-prompt window, navigate to the folder that contains your `Hello.cs` file.</span></span>

4. <span data-ttu-id="97db2-163">다음 명령을 입력하여 `Hello.cs`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-163">Enter the following command to compile `Hello.cs`.</span></span>

     `csc Hello.cs`

     <span data-ttu-id="97db2-164">프로그램에 컴파일 오류가 없으면 `Hello.exe`라는 실행 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-164">If your program has no compilation errors, an executable file that is named `Hello.exe` is created.</span></span>

5. <span data-ttu-id="97db2-165">명령 프롬프트 창에서 다음 명령을 입력하여 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="97db2-165">In the command-prompt window, enter the following command to run the program:</span></span>

     `Hello`

 <span data-ttu-id="97db2-166">C# 컴파일러 및 관련 옵션에 대한 자세한 내용은 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97db2-166">For more information about the C# compiler and its options, see [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="97db2-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97db2-167">See also</span></span>

- [<span data-ttu-id="97db2-168">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="97db2-168">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="97db2-169">C# 프로그램 내부</span><span class="sxs-lookup"><span data-stu-id="97db2-169">Inside a C# Program</span></span>](../../../csharp/programming-guide/inside-a-program/index.md)
- [<span data-ttu-id="97db2-170">문자열</span><span class="sxs-lookup"><span data-stu-id="97db2-170">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
- [<span data-ttu-id="97db2-171">샘플 및 자습서</span><span class="sxs-lookup"><span data-stu-id="97db2-171">Samples and tutorials</span></span>](../../../samples-and-tutorials/index.md)
- [<span data-ttu-id="97db2-172">C# 참조</span><span class="sxs-lookup"><span data-stu-id="97db2-172">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="97db2-173">Main()과 명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="97db2-173">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)
- [<span data-ttu-id="97db2-174">Visual C# 및 Visual Basic 시작</span><span class="sxs-lookup"><span data-stu-id="97db2-174">Getting Started with Visual C# and Visual Basic</span></span>](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)
