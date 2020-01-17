---
title: Hello World -- Windows 또는 Mac에서 Visual Studio를 사용하여 프로그램 처음 만들기 - C# 프로그래밍 가이드
ms.date: 09/12/2019
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 910fa4af1b4e45ce627b589a06910dc168490047
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712145"
---
# <a name="hello-world----your-first-program"></a><span data-ttu-id="14b54-102">Hello World -- 프로그램 처음 만들기</span><span class="sxs-lookup"><span data-stu-id="14b54-102">Hello World -- Your first program</span></span>

<span data-ttu-id="14b54-103">이 문서에서는 Visual Studio를 사용하여 전통적인 "Hello World!" 프로그램을</span><span class="sxs-lookup"><span data-stu-id="14b54-103">In this article, you'll use Visual Studio to create the traditional "Hello World!"</span></span> <span data-ttu-id="14b54-104">만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-104">program.</span></span> <span data-ttu-id="14b54-105">Visual Studio는 .NET 개발용으로 설계된 다양한 기능을 갖춘 전문적인 IDE(통합 개발 환경)입니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-105">Visual Studio is a professional Integrated Development Environment (IDE) with many features designed for .NET development.</span></span> <span data-ttu-id="14b54-106">이 프로그램은 Visual Studio의 일부 기능만 사용하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-106">You'll use only a few of the features in Visual Studio to create this program.</span></span> <span data-ttu-id="14b54-107">Visual Studio에 대해 자세히 알아보려면 [Visual C# 시작](/visualstudio/ide/quickstart-csharp-console)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14b54-107">To learn more about Visual Studio, see [Getting Started with Visual C#](/visualstudio/ide/quickstart-csharp-console).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="create-a-new-application"></a><span data-ttu-id="14b54-108">새 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="14b54-108">Create a new application</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[<span data-ttu-id="14b54-109">Windows</span><span class="sxs-lookup"><span data-stu-id="14b54-109">Windows</span></span>](#tab/windows)

<span data-ttu-id="14b54-110">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-110">Start Visual Studio.</span></span> <span data-ttu-id="14b54-111">Windows에 다음 이미지와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-111">You'll see the following image on Windows:</span></span>

![Windows의 Visual Studio 시작 화면](./media/hello-world-your-first-program/visual-studio-windows-start-screen.png)

<span data-ttu-id="14b54-113">이미지 오른쪽 아래 모서리에서 **새 프로젝트 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-113">Select **Create a new project** in the lower right corner of the image.</span></span> <span data-ttu-id="14b54-114">Visual Studio에 **새 프로젝트** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-114">Visual Studio displays the **New Project** dialog:</span></span>

![Windows의 Visual Studio 새 프로젝트 화면](./media/hello-world-your-first-program/visual-studio-windows-new-project.png)

> [!NOTE]
> <span data-ttu-id="14b54-116">Visual Studio를 처음 시작하는 경우 **최근 프로젝트 템플릿** 목록이 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-116">If this is the first time you've started Visual Studio, the **Recent project templates** list is empty.</span></span>

<span data-ttu-id="14b54-117">새 프로젝트 대화 상자에서 "콘솔 앱(.NET Core)"을 선택한 후 **다음**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-117">On the new project dialog, choose "Console App (.NET Core)" and then press **Next**.</span></span> <span data-ttu-id="14b54-118">프로젝트에 "HelloWorld"와 같은 이름을 지정한 다음 **만들기**를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-118">Give your project a name, such as "HelloWorld", then press **Create**.</span></span>

<span data-ttu-id="14b54-119">Visual Studio에서 프로젝트가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-119">Visual Studio opens your project.</span></span> <span data-ttu-id="14b54-120">이미 기본적인 "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="14b54-120">It's already a basic "Hello World!"</span></span> <span data-ttu-id="14b54-121">예가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-121">example.</span></span> <span data-ttu-id="14b54-122">`Ctrl` + `F5`를 눌러 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-122">Press `Ctrl` + `F5` to run your project.</span></span> <span data-ttu-id="14b54-123">Visual Studio가 프로젝트를 빌드하고 소스 코드를 실행 파일로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-123">Visual Studio builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="14b54-124">그런 다음 새 애플리케이션을 실행하는 명령 창이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-124">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="14b54-125">창에 다음 텍스트가 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-125">You should see the following text in the window:</span></span>

```console
Hello World!

C:\Program Files\dotnet\dotnet.exe (process 11964) exited with code 0.
Press any key to close this window . . .
```

<span data-ttu-id="14b54-126">아무 키나 눌러 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-126">Press a key to close the window.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="14b54-127">macOS</span><span class="sxs-lookup"><span data-stu-id="14b54-127">macOS</span></span>](#tab/macos)

<span data-ttu-id="14b54-128">Mac용 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-128">Start Visual Studio for Mac.</span></span> <span data-ttu-id="14b54-129">Mac에 다음 이미지와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-129">You'll see the following image on Mac:</span></span>

![Mac의 Visual Studio 시작 화면](./media/hello-world-your-first-program/visual-studio-mac-start-screen.png)

> [!NOTE]
> <span data-ttu-id="14b54-131">Mac용 Visual Studio를 처음 시작하는 경우 **최근 프로젝트** 목록이 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-131">If this is the first time you've started Visual Studio for Mac, the **Recent projects** list is empty.</span></span>

<span data-ttu-id="14b54-132">이미지의 오른쪽 위 모서리에서 **새로 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-132">Select **New** in the upper right corner of the image.</span></span> <span data-ttu-id="14b54-133">Mac용 Visual Studio에 **새 프로젝트** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-133">Visual Studio for Mac displays the **New Project** dialog:</span></span>

![Mac의 Visual Studio 새 프로젝트 화면](./media/hello-world-your-first-program/visual-studio-mac-new-project.png)

<span data-ttu-id="14b54-135">새 프로젝트 대화 상자에서 ".NET Core"와 “콘솔 앱”을 선택한 후 **다음**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-135">On the new project dialog, choose ".NET Core", and "Console App" and then press **Next**.</span></span> <span data-ttu-id="14b54-136">대상 프레임워크를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-136">You'll need to select the target framework.</span></span> <span data-ttu-id="14b54-137">기본값을 사용해도 되므로 다음을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-137">The default is fine, so press next.</span></span> <span data-ttu-id="14b54-138">프로젝트에 "HelloWorld"와 같은 이름을 지정한 다음 **만들기**를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-138">Give your project a name, such as "HelloWorld", then press **Create**.</span></span> <span data-ttu-id="14b54-139">기본 프로젝트 위치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-139">You can use the default project location.</span></span> <span data-ttu-id="14b54-140">소스 제어에 이 프로젝트를 추가하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="14b54-140">Don't add this project to source control.</span></span>

<span data-ttu-id="14b54-141">Mac용 Visual Studio에서 프로젝트가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-141">Visual Studio for Mac opens your project.</span></span> <span data-ttu-id="14b54-142">이미 기본적인 "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="14b54-142">It's already a basic "Hello World!"</span></span> <span data-ttu-id="14b54-143">예가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-143">example.</span></span> <span data-ttu-id="14b54-144">`Ctrl` + `Fn` + `F5`를 눌러 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-144">Press `Ctrl` + `Fn` + `F5` to run your project.</span></span> <span data-ttu-id="14b54-145">Mac용 Visual Studio가 프로젝트를 빌드하고 소스 코드를 실행 파일로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-145">Visual Studio for Mac builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="14b54-146">그런 다음 새 애플리케이션을 실행하는 명령 창이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-146">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="14b54-147">창에 다음 텍스트가 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-147">You should see the following text in the window:</span></span>

```console
Hello World!

Press any key to close this window . . .
```

<span data-ttu-id="14b54-148">세션을 종료하려면 아무 키나 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-148">Press a key to end the session.</span></span>

---

## <a name="elements-of-a-c-program"></a><span data-ttu-id="14b54-149">C# 프로그램의 요소</span><span class="sxs-lookup"><span data-stu-id="14b54-149">Elements of a C# program</span></span>

<span data-ttu-id="14b54-150">이 프로그램의 중요한 부분을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-150">Let's examine the important parts of this program.</span></span> <span data-ttu-id="14b54-151">첫 번째 줄에는 설명이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-151">The first line contains a comment.</span></span> <span data-ttu-id="14b54-152">`//` 문자는 줄의 나머지 부분을 설명으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-152">The characters `//` convert the rest of the line to a comment.</span></span>

[!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

<span data-ttu-id="14b54-153">텍스트 블록을 `/*` 및 `*/` 문자 사이에 포함하여 주석으로 처리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-153">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="14b54-154">다음 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-154">This is shown in the following example.</span></span>

[!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

<span data-ttu-id="14b54-155">C# 콘솔 애플리케이션에는 시작 및 끝을 제어하는 `Main` 메서드가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-155">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="14b54-156">`Main` 메서드에서 개체를 만들고 다른 메서드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-156">The `Main` method is where you create objects and execute other methods.</span></span>

<span data-ttu-id="14b54-157">`Main` 메서드는 클래스나 구조체 내부에 있는 [정적](../../language-reference/keywords/static.md) 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-157">The `Main` method is a [static](../../language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="14b54-158">이전 "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="14b54-158">In the previous "Hello World!"</span></span> <span data-ttu-id="14b54-159">예제에서 이 메서드는 `Hello` 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-159">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="14b54-160">다음 방법 중 하나로 `Main` 메서드를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-160">You can declare the `Main` method in one of the following ways:</span></span>

- <span data-ttu-id="14b54-161">이 메서드는 `void`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-161">It can return `void`.</span></span> <span data-ttu-id="14b54-162">즉, 프로그램에서 값을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-162">That means your program doesn't return a value.</span></span>

[!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- <span data-ttu-id="14b54-163">정수를 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-163">It can also return an integer.</span></span> <span data-ttu-id="14b54-164">이 정수는 애플리케이션의 **종료 코드**입니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-164">The integer is the **exit code** for your application.</span></span>

[!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- <span data-ttu-id="14b54-165">반환 형식은 각각 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-165">With either of the return types, it can take arguments.</span></span>

[!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

<span data-ttu-id="14b54-166">또는</span><span class="sxs-lookup"><span data-stu-id="14b54-166">-or-</span></span>

[!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

<span data-ttu-id="14b54-167">`Main` 메서드의 매개 변수 `args`는 프로그램을 호출하는 데 사용된 명령줄 인수가 포함된 `string` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-167">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span>

<span data-ttu-id="14b54-168">명령줄 인수를 사용하는 방법에 대한 자세한 내용은 [Main() 및 명령줄 인수](../main-and-command-args/index.md)의 예를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14b54-168">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../main-and-command-args/index.md).</span></span>

## <a name="input-and-output"></a><span data-ttu-id="14b54-169">입력 및 출력</span><span class="sxs-lookup"><span data-stu-id="14b54-169">Input and output</span></span>

<span data-ttu-id="14b54-170">일반적으로 C# 프로그램에서는 .NET Framework의 런타임 라이브러리에서 제공되는 입출력 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-170">C# programs generally use the input/output services provided by the run-time library of the .NET Framework.</span></span> <span data-ttu-id="14b54-171">`System.Console.WriteLine("Hello World!");` 문은 <xref:System.Console.WriteLine%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-171">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="14b54-172">이 메서드는 런타임 라이브러리에 있는 <xref:System.Console> 클래스의 출력 메서드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-172">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="14b54-173">이 메서드는 표준 출력 스트림에 문자열 매개 변수를 표시하고 이어서 새 줄을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-173">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="14b54-174">기타 <xref:System.Console> 메서드는 다양한 입력 및 출력 작업에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-174">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="14b54-175">프로그램 시작 부분에 `using System;` 지시문을 포함하면 <xref:System> 클래스 및 메서드를 정규화하지 않고 바로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-175">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="14b54-176">예를 들어 `System.Console.WriteLine` 대신 `Console.WriteLine`을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b54-176">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="14b54-177">입출력 메서드에 대한 자세한 내용은 <xref:System.IO>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14b54-177">For more information about input/output methods, see <xref:System.IO>.</span></span>

## <a name="see-also"></a><span data-ttu-id="14b54-178">참조</span><span class="sxs-lookup"><span data-stu-id="14b54-178">See also</span></span>

- [<span data-ttu-id="14b54-179">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="14b54-179">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="14b54-180">샘플 및 자습서</span><span class="sxs-lookup"><span data-stu-id="14b54-180">Samples and tutorials</span></span>](../../../samples-and-tutorials/index.md)
- [<span data-ttu-id="14b54-181">Main()과 명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="14b54-181">Main() and Command-Line Arguments</span></span>](../main-and-command-args/index.md)
- [<span data-ttu-id="14b54-182">Visual C# 시작</span><span class="sxs-lookup"><span data-stu-id="14b54-182">Getting Started with Visual C#</span></span>](/visualstudio/ide/quickstart-csharp-console)
