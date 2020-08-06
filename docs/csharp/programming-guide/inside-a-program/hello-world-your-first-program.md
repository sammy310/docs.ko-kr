---
title: Hello World -- Windows 또는 Mac에서 Visual Studio를 사용하여 프로그램 처음 만들기 - C# 프로그래밍 가이드
description: Visual Studio는 .NET 개발을 위한 다양한 기능을 갖춘 전문적인 개발 환경입니다. Visual Studio를 사용하여 C# 버전의 Hello World를 만드세요.
ms.date: 09/12/2019
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: b78937b8ba1c7d4718bfb6252dac705945336d2a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301829"
---
# <a name="hello-world----your-first-program"></a><span data-ttu-id="3b850-104">Hello World -- 프로그램 처음 만들기</span><span class="sxs-lookup"><span data-stu-id="3b850-104">Hello World -- Your first program</span></span>

<span data-ttu-id="3b850-105">이 문서에서는 Visual Studio를 사용하여 전통적인 "Hello World!" 프로그램을</span><span class="sxs-lookup"><span data-stu-id="3b850-105">In this article, you'll use Visual Studio to create the traditional "Hello World!"</span></span> <span data-ttu-id="3b850-106">만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-106">program.</span></span> <span data-ttu-id="3b850-107">Visual Studio는 .NET 개발용으로 설계된 다양한 기능을 갖춘 전문적인 IDE(통합 개발 환경)입니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-107">Visual Studio is a professional Integrated Development Environment (IDE) with many features designed for .NET development.</span></span> <span data-ttu-id="3b850-108">이 프로그램은 Visual Studio의 일부 기능만 사용하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-108">You'll use only a few of the features in Visual Studio to create this program.</span></span> <span data-ttu-id="3b850-109">Visual Studio에 대해 자세히 알아보려면 [Visual C# 시작](/visualstudio/ide/quickstart-csharp-console)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b850-109">To learn more about Visual Studio, see [Getting Started with Visual C#](/visualstudio/ide/quickstart-csharp-console).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="create-a-new-application"></a><span data-ttu-id="3b850-110">새 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="3b850-110">Create a new application</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[<span data-ttu-id="3b850-111">Windows</span><span class="sxs-lookup"><span data-stu-id="3b850-111">Windows</span></span>](#tab/windows)

<span data-ttu-id="3b850-112">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-112">Start Visual Studio.</span></span> <span data-ttu-id="3b850-113">Windows에 다음 이미지와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-113">You'll see the following image on Windows:</span></span>

![Windows의 Visual Studio 시작 화면](./media/hello-world-your-first-program/visual-studio-windows-start-screen.png)

<span data-ttu-id="3b850-115">이미지 오른쪽 아래 모서리에서 **새 프로젝트 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-115">Select **Create a new project** in the lower right corner of the image.</span></span> <span data-ttu-id="3b850-116">Visual Studio에 **새 프로젝트** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-116">Visual Studio displays the **New Project** dialog:</span></span>

![Windows의 Visual Studio 새 프로젝트 화면](./media/hello-world-your-first-program/visual-studio-windows-new-project.png)

> [!NOTE]
> <span data-ttu-id="3b850-118">Visual Studio를 처음 시작하는 경우 **최근 프로젝트 템플릿** 목록이 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-118">If this is the first time you've started Visual Studio, the **Recent project templates** list is empty.</span></span>

<span data-ttu-id="3b850-119">새 프로젝트 대화 상자에서 "콘솔 앱(.NET Core)"을 선택한 후 **다음**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-119">On the new project dialog, choose "Console App (.NET Core)" and then press **Next**.</span></span> <span data-ttu-id="3b850-120">프로젝트에 "HelloWorld"와 같은 이름을 지정한 다음 **만들기**를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-120">Give your project a name, such as "HelloWorld", then press **Create**.</span></span>

<span data-ttu-id="3b850-121">Visual Studio에서 프로젝트가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-121">Visual Studio opens your project.</span></span> <span data-ttu-id="3b850-122">이미 기본적인 "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="3b850-122">It's already a basic "Hello World!"</span></span> <span data-ttu-id="3b850-123">예가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-123">example.</span></span> <span data-ttu-id="3b850-124">`Ctrl` + `F5`를 눌러 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-124">Press `Ctrl` + `F5` to run your project.</span></span> <span data-ttu-id="3b850-125">Visual Studio가 프로젝트를 빌드하고 소스 코드를 실행 파일로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-125">Visual Studio builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="3b850-126">그런 다음 새 애플리케이션을 실행하는 명령 창이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-126">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="3b850-127">창에 다음 텍스트가 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-127">You should see the following text in the window:</span></span>

```console
Hello World!

C:\Program Files\dotnet\dotnet.exe (process 11964) exited with code 0.
Press any key to close this window . . .
```

<span data-ttu-id="3b850-128">아무 키나 눌러 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-128">Press a key to close the window.</span></span>

# <a name="macos"></a>[<span data-ttu-id="3b850-129">macOS</span><span class="sxs-lookup"><span data-stu-id="3b850-129">macOS</span></span>](#tab/macos)

<span data-ttu-id="3b850-130">Mac용 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-130">Start Visual Studio for Mac.</span></span> <span data-ttu-id="3b850-131">Mac에 다음 이미지와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-131">You'll see the following image on Mac:</span></span>

![Mac의 Visual Studio 시작 화면](./media/hello-world-your-first-program/visual-studio-mac-start-screen.png)

> [!NOTE]
> <span data-ttu-id="3b850-133">Mac용 Visual Studio를 처음 시작하는 경우 **최근 프로젝트** 목록이 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-133">If this is the first time you've started Visual Studio for Mac, the **Recent projects** list is empty.</span></span>

<span data-ttu-id="3b850-134">이미지의 오른쪽 위 모서리에서 **새로 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-134">Select **New** in the upper right corner of the image.</span></span> <span data-ttu-id="3b850-135">Mac용 Visual Studio에 **새 프로젝트** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-135">Visual Studio for Mac displays the **New Project** dialog:</span></span>

![Mac의 Visual Studio 새 프로젝트 화면](./media/hello-world-your-first-program/visual-studio-mac-new-project.png)

<span data-ttu-id="3b850-137">새 프로젝트 대화 상자에서 ".NET Core"와 “콘솔 앱”을 선택한 후 **다음**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-137">On the new project dialog, choose ".NET Core", and "Console App" and then press **Next**.</span></span> <span data-ttu-id="3b850-138">대상 프레임워크를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-138">You'll need to select the target framework.</span></span> <span data-ttu-id="3b850-139">기본값을 사용해도 되므로 다음을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-139">The default is fine, so press next.</span></span> <span data-ttu-id="3b850-140">프로젝트에 "HelloWorld"와 같은 이름을 지정한 다음 **만들기**를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-140">Give your project a name, such as "HelloWorld", then press **Create**.</span></span> <span data-ttu-id="3b850-141">기본 프로젝트 위치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-141">You can use the default project location.</span></span> <span data-ttu-id="3b850-142">소스 제어에 이 프로젝트를 추가하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3b850-142">Don't add this project to source control.</span></span>

<span data-ttu-id="3b850-143">Mac용 Visual Studio에서 프로젝트가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-143">Visual Studio for Mac opens your project.</span></span> <span data-ttu-id="3b850-144">이미 기본적인 "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="3b850-144">It's already a basic "Hello World!"</span></span> <span data-ttu-id="3b850-145">예가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-145">example.</span></span> <span data-ttu-id="3b850-146">`Ctrl` + `Fn` + `F5`를 눌러 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-146">Press `Ctrl` + `Fn` + `F5` to run your project.</span></span> <span data-ttu-id="3b850-147">Mac용 Visual Studio가 프로젝트를 빌드하고 소스 코드를 실행 파일로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-147">Visual Studio for Mac builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="3b850-148">그런 다음 새 애플리케이션을 실행하는 명령 창이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-148">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="3b850-149">창에 다음 텍스트가 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-149">You should see the following text in the window:</span></span>

```console
Hello World!

Press any key to close this window . . .
```

<span data-ttu-id="3b850-150">세션을 종료하려면 아무 키나 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-150">Press a key to end the session.</span></span>

---

## <a name="elements-of-a-c-program"></a><span data-ttu-id="3b850-151">C# 프로그램의 요소</span><span class="sxs-lookup"><span data-stu-id="3b850-151">Elements of a C# program</span></span>

<span data-ttu-id="3b850-152">이 프로그램의 중요한 부분을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-152">Let's examine the important parts of this program.</span></span> <span data-ttu-id="3b850-153">첫 번째 줄에는 설명이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-153">The first line contains a comment.</span></span> <span data-ttu-id="3b850-154">`//` 문자는 줄의 나머지 부분을 설명으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-154">The characters `//` convert the rest of the line to a comment.</span></span>

[!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

<span data-ttu-id="3b850-155">텍스트 블록을 `/*` 및 `*/` 문자 사이에 포함하여 주석으로 처리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-155">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="3b850-156">다음 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-156">This is shown in the following example.</span></span>

[!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

<span data-ttu-id="3b850-157">C# 콘솔 애플리케이션에는 시작 및 끝을 제어하는 `Main` 메서드가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-157">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="3b850-158">`Main` 메서드에서 개체를 만들고 다른 메서드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-158">The `Main` method is where you create objects and execute other methods.</span></span>

<span data-ttu-id="3b850-159">`Main` 메서드는 클래스나 구조체 내부에 있는 [정적](../../language-reference/keywords/static.md) 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-159">The `Main` method is a [static](../../language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="3b850-160">이전 "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="3b850-160">In the previous "Hello World!"</span></span> <span data-ttu-id="3b850-161">예제에서 이 메서드는 `Hello` 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-161">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="3b850-162">다음 방법 중 하나로 `Main` 메서드를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-162">You can declare the `Main` method in one of the following ways:</span></span>

- <span data-ttu-id="3b850-163">이 메서드는 `void`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-163">It can return `void`.</span></span> <span data-ttu-id="3b850-164">즉, 프로그램에서 값을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-164">That means your program doesn't return a value.</span></span>

[!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- <span data-ttu-id="3b850-165">정수를 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-165">It can also return an integer.</span></span> <span data-ttu-id="3b850-166">이 정수는 애플리케이션의 **종료 코드**입니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-166">The integer is the **exit code** for your application.</span></span>

[!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- <span data-ttu-id="3b850-167">반환 형식은 각각 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-167">With either of the return types, it can take arguments.</span></span>

[!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

<span data-ttu-id="3b850-168">또는</span><span class="sxs-lookup"><span data-stu-id="3b850-168">-or-</span></span>

[!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

<span data-ttu-id="3b850-169">`Main` 메서드의 매개 변수 `args`는 프로그램을 호출하는 데 사용된 명령줄 인수가 포함된 `string` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-169">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span>

<span data-ttu-id="3b850-170">명령줄 인수를 사용하는 방법에 대한 자세한 내용은 [Main() 및 명령줄 인수](../main-and-command-args/index.md)의 예를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b850-170">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../main-and-command-args/index.md).</span></span>

## <a name="input-and-output"></a><span data-ttu-id="3b850-171">입력 및 출력</span><span class="sxs-lookup"><span data-stu-id="3b850-171">Input and output</span></span>

<span data-ttu-id="3b850-172">일반적으로 C# 프로그램에서는 .NET의 런타임 라이브러리에서 제공되는 입출력 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-172">C# programs generally use the input/output services provided by the run-time library of .NET.</span></span> <span data-ttu-id="3b850-173">`System.Console.WriteLine("Hello World!");` 문은 <xref:System.Console.WriteLine%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-173">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="3b850-174">이 메서드는 런타임 라이브러리에 있는 <xref:System.Console> 클래스의 출력 메서드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-174">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="3b850-175">이 메서드는 표준 출력 스트림에 문자열 매개 변수를 표시하고 이어서 새 줄을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-175">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="3b850-176">기타 <xref:System.Console> 메서드는 다양한 입력 및 출력 작업에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-176">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="3b850-177">프로그램 시작 부분에 `using System;` 지시문을 포함하면 <xref:System> 클래스 및 메서드를 정규화하지 않고 바로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-177">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="3b850-178">예를 들어 `System.Console.WriteLine` 대신 `Console.WriteLine`을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b850-178">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="3b850-179">입출력 메서드에 대한 자세한 내용은 <xref:System.IO>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b850-179">For more information about input/output methods, see <xref:System.IO>.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b850-180">참조</span><span class="sxs-lookup"><span data-stu-id="3b850-180">See also</span></span>

- [<span data-ttu-id="3b850-181">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="3b850-181">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3b850-182">샘플 및 자습서</span><span class="sxs-lookup"><span data-stu-id="3b850-182">Samples and tutorials</span></span>](../../../samples-and-tutorials/index.md)
- [<span data-ttu-id="3b850-183">Main()과 명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="3b850-183">Main() and Command-Line Arguments</span></span>](../main-and-command-args/index.md)
- [<span data-ttu-id="3b850-184">Visual C# 시작</span><span class="sxs-lookup"><span data-stu-id="3b850-184">Getting Started with Visual C#</span></span>](/visualstudio/ide/quickstart-csharp-console)
