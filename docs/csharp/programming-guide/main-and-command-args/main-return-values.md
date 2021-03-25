---
title: Main() 반환 값 - C# 프로그래밍 가이드
description: Main() 반환 값에 대해 알아봅니다. 코드 예제, 컴파일러 생성 코드를 살펴보고 사용 가능한 추가 리소스를 확인합니다.
ms.date: 03/11/2021
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
ms.openlocfilehash: 6f4001ecd490d5627d3a1ec74ecf7d593451e104
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190361"
---
# <a name="main-return-values-c-programming-guide"></a><span data-ttu-id="6707e-104">Main() 반환 값(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="6707e-104">Main() return values (C# Programming Guide)</span></span>

<span data-ttu-id="6707e-105">다음 방법 중 하나로 메서드를 정의하여 `Main` 메서드에서 `int`를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-105">You can return an `int` from the `Main` method by defining the method in one of the following ways:</span></span>

| <span data-ttu-id="6707e-106">`Main` 메서드 코드</span><span class="sxs-lookup"><span data-stu-id="6707e-106">`Main` method code</span></span>             | <span data-ttu-id="6707e-107">`Main` 서명</span><span class="sxs-lookup"><span data-stu-id="6707e-107">`Main` signature</span></span>                             |
|--------------------------------|----------------------------------------------|
| <span data-ttu-id="6707e-108">`args` 또는 `await` 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6707e-108">No use of `args` or `await`</span></span>    | `static int Main()`                          |
| <span data-ttu-id="6707e-109">`args` 사용, `await` 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6707e-109">Uses `args`, no use of `await`</span></span> | `static int Main(string[] args)`             |
| <span data-ttu-id="6707e-110">`args` 사용 안 함 , `await` 사용</span><span class="sxs-lookup"><span data-stu-id="6707e-110">No use of `args`, uses `await`</span></span> | `static async Task<int> Main()`              |
| <span data-ttu-id="6707e-111">`args` 및 `await` 사용</span><span class="sxs-lookup"><span data-stu-id="6707e-111">Uses `args` and `await`</span></span>        | `static async Task<int> Main(string[] args)` |

<span data-ttu-id="6707e-112">`Main`의 반환 값을 사용하지 않는 경우 `void` 또는 `Task`를 반환하면 코드가 다소 단순해집니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-112">If the return value from `Main` is not used, returning `void` or `Task` allows for slightly simpler code.</span></span>

| <span data-ttu-id="6707e-113">`Main` 메서드 코드</span><span class="sxs-lookup"><span data-stu-id="6707e-113">`Main` method code</span></span>             | <span data-ttu-id="6707e-114">`Main` 서명</span><span class="sxs-lookup"><span data-stu-id="6707e-114">`Main` signature</span></span>                        |
|--------------------------------|-----------------------------------------|
| <span data-ttu-id="6707e-115">`args` 또는 `await` 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6707e-115">No use of `args` or `await`</span></span>    | `static void Main()`                    |
| <span data-ttu-id="6707e-116">`args` 사용, `await` 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6707e-116">Uses `args`, no use of `await`</span></span> | `static void Main(string[] args)`       |
| <span data-ttu-id="6707e-117">`args` 사용 안 함 , `await` 사용</span><span class="sxs-lookup"><span data-stu-id="6707e-117">No use of `args`, uses `await`</span></span> | `static async Task Main()`              |
| <span data-ttu-id="6707e-118">`args` 및 `await` 사용</span><span class="sxs-lookup"><span data-stu-id="6707e-118">Uses `args` and `await`</span></span>        | `static async Task Main(string[] args)` |

<span data-ttu-id="6707e-119">그러나 `int` 또는 `Task<int>`를 반환하면 프로그램이 실행 파일을 호출하는 다른 프로그램이나 스크립트에 상태 정보를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-119">However, returning `int` or `Task<int>` enables the program to communicate status information to other programs or scripts that invoke the executable file.</span></span>

<span data-ttu-id="6707e-120">다음 예제에서는 프로세스의 종료 코드에 액세스할 수 있는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-120">The following example shows how the exit code for the process can be accessed.</span></span>

## <a name="example"></a><span data-ttu-id="6707e-121">예제</span><span class="sxs-lookup"><span data-stu-id="6707e-121">Example</span></span>

<span data-ttu-id="6707e-122">이 예제에서는 [.NET Core](../../../core/introduction.md) 명령줄 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-122">This example uses [.NET Core](../../../core/introduction.md) command-line tools.</span></span> <span data-ttu-id="6707e-123">.NET Core 명령줄 도구에 대해 잘 모르는 경우 이 [시작 문서](../../../core/tutorials/with-visual-studio-code.md)에서 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-123">If you are unfamiliar with .NET Core command-line tools, you can learn about them in this [get-started article](../../../core/tutorials/with-visual-studio-code.md).</span></span>

<span data-ttu-id="6707e-124">*program.cs* 에서 `Main` 메서드를 다음과 같이 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-124">Modify the `Main` method in *program.cs* as follows:</span></span>

 [!code-csharp[csProgGuideMain#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#14)]

<span data-ttu-id="6707e-125">Windows에서 프로그램을 실행하는 경우 `Main` 함수에서 반환된 값은 환경 변수에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-125">When a program is executed in Windows, any value returned from the `Main` function is stored in an environment variable.</span></span> <span data-ttu-id="6707e-126">이 환경 변수는 배치 파일에서 `ERRORLEVEL`을 사용하거나 PowerShell에서 `$LastExitCode`를 사용하여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-126">This environment variable can be retrieved using `ERRORLEVEL` from a batch file, or `$LastExitCode` from PowerShell.</span></span>

<span data-ttu-id="6707e-127">[dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` 명령을 사용하여 애플리케이션을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-127">You can build the application using the [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` command.</span></span>

<span data-ttu-id="6707e-128">다음으로 애플리케이션을 실행하고 결과를 표시하는 PowerShell 스크립트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-128">Next, create a PowerShell script to run the application and display the result.</span></span> <span data-ttu-id="6707e-129">다음 코드를 텍스트 파일에 붙여넣고 이 파일을 프로젝트가 포함된 폴더에 `test.ps1`로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-129">Paste the following code into a text file and save it as `test.ps1` in the folder that contains the project.</span></span> <span data-ttu-id="6707e-130">PowerShell 프롬프트에 `test.ps1`을 입력하여 PowerShell 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-130">Run the PowerShell script by typing `test.ps1` at the PowerShell prompt.</span></span>

<span data-ttu-id="6707e-131">코드에서 0을 반환하기 때문에 배치 파일이 성공했다고 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-131">Because the code returns zero, the batch file will report success.</span></span> <span data-ttu-id="6707e-132">그러나 0이 아닌 값을 반환하도록 MainReturnValTest.cs를 변경한 다음 프로그램을 다시 컴파일하면 다음에 PowerShell 스크립트를 실행할 때 오류가 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-132">However, if you change MainReturnValTest.cs to return a non-zero value and then recompile the program, subsequent execution of the PowerShell script will report failure.</span></span>

```dotnetcli
dotnet run
```

```powershell
if ($LastExitCode -eq 0) {
    Write-Host "Execution succeeded"
} else
{
    Write-Host "Execution Failed"
}
Write-Host "Return value = " $LastExitCode
```

## <a name="sample-output"></a><span data-ttu-id="6707e-133">샘플 출력</span><span class="sxs-lookup"><span data-stu-id="6707e-133">Sample output</span></span>

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a><span data-ttu-id="6707e-134">비동기 Main 반환 값</span><span class="sxs-lookup"><span data-stu-id="6707e-134">Async Main return values</span></span>

<span data-ttu-id="6707e-135">비동기 Main 반환 값은 `Main`에서 비동기 메서드를 호출하는 데 필요한 상용구 코드를 컴파일러에서 생성하는 코드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-135">Async Main return values move the boilerplate code necessary for calling asynchronous methods in `Main` to code generated by the compiler.</span></span> <span data-ttu-id="6707e-136">기존에는 이 구문을 작성하여 비동기 코드를 호출하고 비동기 작업이 완료될 때까지 프로그램이 실행되는지 확인해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-136">Previously, you would need to write this construct to call asynchronous code and ensure your program ran until the asynchronous operation completed:</span></span>

```csharp
public static void Main()
{
    AsyncConsoleWork().GetAwaiter().GetResult();
}

private static async Task<int> AsyncConsoleWork()
{
    // Main body here
    return 0;
}
```

<span data-ttu-id="6707e-137">이제는 이 구문을 다음으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-137">Now, this can be replaced by:</span></span>

[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]

<span data-ttu-id="6707e-138">새 구문의 장점은 컴파일러에서 항상 올바른 코드를 생성한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-138">The advantage of the new syntax is that the compiler always generates the correct code.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="6707e-139">컴파일러 생성 복사</span><span class="sxs-lookup"><span data-stu-id="6707e-139">Compiler-generated code</span></span>

<span data-ttu-id="6707e-140">애플리케이션 진입점에서 `Task` 또는 `Task<int>`를 반환하는 경우 컴파일러는 애플리케이션 코드에서 선언된 진입점 메서드를 호출하는 새 진입점을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-140">When the application entry point returns a `Task` or `Task<int>`, the compiler generates a new entry point that calls the entry point method declared in the application code.</span></span> <span data-ttu-id="6707e-141">이 진입점이 `$GeneratedMain`이라고 가정하면 컴파일러는 이러한 진입점에 대해 다음 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-141">Assuming that this entry point is called `$GeneratedMain`, the compiler generates the following code for these entry points:</span></span>

- <span data-ttu-id="6707e-142">`static Task Main()` - 컴파일러에서 `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`에 해당하는 코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-142">`static Task Main()` results in the compiler emitting the equivalent of `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="6707e-143">`static Task Main(string[])` - 컴파일러에서 `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`에 해당하는 코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-143">`static Task Main(string[])` results in the compiler emitting the equivalent of `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="6707e-144">`static Task<int> Main()` - 컴파일러에서 `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`에 해당하는 코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-144">`static Task<int> Main()` results in the compiler emitting the equivalent of `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="6707e-145">`static Task<int> Main(string[])` - 컴파일러에서 `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`에 해당하는 코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-145">`static Task<int> Main(string[])` results in the compiler emitting the equivalent of `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>

> [!NOTE]
><span data-ttu-id="6707e-146">예제에서 `Main` 메서드에 `async` 한정자를 사용하더라도 컴파일러는 동일한 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6707e-146">If the examples used `async` modifier on the `Main` method, the compiler would generate the same code.</span></span>

## <a name="see-also"></a><span data-ttu-id="6707e-147">참조</span><span class="sxs-lookup"><span data-stu-id="6707e-147">See also</span></span>

- [<span data-ttu-id="6707e-148">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="6707e-148">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6707e-149">C# 참조</span><span class="sxs-lookup"><span data-stu-id="6707e-149">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="6707e-150">Main()과 명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="6707e-150">Main() and Command-Line Arguments</span></span>](index.md)
- [<span data-ttu-id="6707e-151">명령줄 인수를 표시하는 방법</span><span class="sxs-lookup"><span data-stu-id="6707e-151">How to display command line arguments</span></span>](./how-to-display-command-line-arguments.md)
