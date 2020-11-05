---
title: F# 대화형(dotnet) 참조
description: F# 대화형(dotnet fsi)이 어떻게 콘솔에서 F# 코드를 대화형으로 실행하거나 F# 스크립트를 실행하는 데 사용되는지 알아보세요.
ms.date: 10/31/2020
f1_keywords:
- VS.ToolsOptionsPages.F#_Tools.F#_Interactive
ms.openlocfilehash: ba9111efccceca03fda43ff11c3f111610541595
ms.sourcegitcommit: ffd4d5e824db6c5f0c3521c0e802fd9e8f0edcbe
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "93342685"
---
# <a name="interactive-programming-with-f"></a><span data-ttu-id="fb813-103">F\#을 사용한 대화형 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="fb813-103">Interactive programming with F\#</span></span>

<span data-ttu-id="fb813-104">F# 대화형(dotnet fsi)은 콘솔에서 F# 코드를 대화형으로 실행하거나 F# 스크립트를 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-104">F# Interactive (dotnet fsi) is used to run F# code interactively at the console, or to execute F# scripts.</span></span> <span data-ttu-id="fb813-105">즉, F# Interactive는 F# 언어에 대해 REPL(읽기, 평가, 인쇄 루프)을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-105">In other words, F# interactive executes a REPL (Read, Evaluate, Print Loop) for the F# language.</span></span>

<span data-ttu-id="fb813-106">콘솔에서 F# 대화형을 실행하려면 `dotnet fsi`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-106">To run F# Interactive from the console, run `dotnet fsi`.</span></span> <span data-ttu-id="fb813-107">모든 .NET SDK에서 `dotnet fsi`를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-107">You will find `dotnet fsi` in any .NET SDK.</span></span>

<span data-ttu-id="fb813-108">사용 가능한 명령줄 옵션에 대한 정보는 [F# Interactive Options](../../language-reference/fsharp-interactive-options.md)(F# Interactive 옵션)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb813-108">For information about command line options available, see [F# Interactive Options](../../language-reference/fsharp-interactive-options.md).</span></span>

## <a name="executing-code-directly-in-f-interactive"></a><span data-ttu-id="fb813-109">F# 대화형에서 직접 코드 실행</span><span class="sxs-lookup"><span data-stu-id="fb813-109">Executing code directly in F# Interactive</span></span>

<span data-ttu-id="fb813-110">F# 대화형은 REPL(read-eval-print loop)이므로 대화형으로 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-110">Because F# Interactive is a REPL (read-eval-print loop), you can execute code interactively in it.</span></span> <span data-ttu-id="fb813-111">다음은 명령줄에서 `dotnet fsi`를 실행한 후의 대화형 세션 예입니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-111">Here is an example of an interactive session after executing `dotnet fsi` from the command line:</span></span>

```console
Microsoft (R) F# Interactive version 11.0.0.0 for F# 5.0
Copyright (c) Microsoft Corporation. All Rights Reserved.

For help type #help;;

> let square x = x *  x;;
val square : x:int -> int

> square 12;;
val it : int = 144

> printfn "Hello, FSI!"
- ;;
Hello, FSI!
val it : unit = ()
```

<span data-ttu-id="fb813-112">두 가지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-112">You'll notice two main things:</span></span>

1. <span data-ttu-id="fb813-113">모든 코드는 두 개의 세미콜론(`;;`)으로 끝나야 평가 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-113">All code must be terminated with a double semicolon (`;;`) to be evaluated</span></span>
2. <span data-ttu-id="fb813-114">코드는 평가되고 `it` 값에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-114">Code is evaluated and stored in an `it` value.</span></span> <span data-ttu-id="fb813-115">`it`을 대화형으로 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-115">You can reference `it` interactively.</span></span>

<span data-ttu-id="fb813-116">F# 대화형은 여러 줄 입력도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-116">F# Interactive also supports multi-line input.</span></span> <span data-ttu-id="fb813-117">이중 세미콜론(`;;`)으로 제출을 종료하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-117">You just need to terminate your submission with a double semicolon (`;;`).</span></span> <span data-ttu-id="fb813-118">F# 대화형으로 붙여 넣고 평가된 다음 코드 조각을 살펴보십시오.</span><span class="sxs-lookup"><span data-stu-id="fb813-118">Consider the following snippet that has been pasted into and evaluated by F# Interactive:</span></span>

```console
> let getOddSquares xs =
-     xs
-     |> List.filter (fun x -> x % 2 <> 0)
-     |> List.map (fun x -> x * x)
-
- printfn "%A" (getOddSquares [1..10]);;
[1; 9; 25; 49; 81]
val getOddSquares : xs:int list -> int list
val it : unit = ()

>
```

<span data-ttu-id="fb813-119">코드의 형식이 유지되며 입력을 종료하는 이중 세미콜론(`;;`)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-119">The code's formatting is preserved, and there is a double semiclon (`;;`) terminating the input.</span></span> <span data-ttu-id="fb813-120">그런 다음 F# 대화형으로 코드를 평가하고 결과를 출력했습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-120">F# Interactive then evaluated the code and printed the results!</span></span>

## <a name="scripting-with-f"></a><span data-ttu-id="fb813-121">F\#을 사용한 스크립팅</span><span class="sxs-lookup"><span data-stu-id="fb813-121">Scripting with F\#</span></span>

<span data-ttu-id="fb813-122">F# 대화형으로 코드를 평가하는 것은 좋은 학습 도구일 수 있지만 일반적인 편집기에서 코드를 작성하는 것만큼 생산적이지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-122">Evaluating code interactively in F# Interactive can be a great learning tool, but you'll quickly find that it's not as productive as writing code in a normal editor.</span></span> <span data-ttu-id="fb813-123">일반 코드 편집을 지원하기 위해 F# 스크립트를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-123">To support normal code editing, you can write F# scripts.</span></span>

<span data-ttu-id="fb813-124">스크립트는 **.fsx** 파일 확장명을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-124">Scripts use the file extension **.fsx**.</span></span> <span data-ttu-id="fb813-125">소스 코드를 컴파일한 다음 나중에 컴파일된 어셈블리를 실행하는 대신 **dotnet fsi** 를 실행하고 F# 소스 코드의 스크립트 파일 이름을 지정하면 F# 대화형이 실시간으로 코드를 읽고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-125">Instead of compiling source code and then later running the compiled assembly, you can just run **dotnet fsi** and specify the filename of the script of F# source code, and F# interactive reads the code and executes it in real time.</span></span> <span data-ttu-id="fb813-126">예를 들어, `Script.fsx`라는 스크립트를 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="fb813-126">For example, consider the following script called `Script.fsx`:</span></span>

```fsharp
let getOddSquares xs =
    xs
    |> List.filter (fun x -> x % 2 <> 0)
    |> List.map (fun x -> x * x)

getOddSquares [1..10]
```

<span data-ttu-id="fb813-127">컴퓨터에서 이 파일을 만들 때 `dotnet fsi`를 사용하여 실행하고 터미널 창에서 출력을 직접 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-127">When this file is created in your machine, you can run it with `dotnet fsi` and see the output directly in your terminal window:</span></span>

```console
dotnet fsi Script.fsx
[1; 9; 25; 49; 81]
```

<span data-ttu-id="fb813-128">F# 스크립팅은 기본적으로 [Visual Studio](../../get-started/get-started-visual-studio.md), [Visual Studio Code](../../get-started/get-started-vscode.md) 및 [Mac용 Visual Studio](../../get-started/get-started-with-visual-studio-for-mac.md)에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-128">F# scripting is natively supported in [Visual Studio](../../get-started/get-started-visual-studio.md), [Visual Studio Code](../../get-started/get-started-vscode.md), and [Visual Studio for Mac](../../get-started/get-started-with-visual-studio-for-mac.md).</span></span>

## <a name="referencing-packages-in-f-interactive"></a><span data-ttu-id="fb813-129">F# 대화형에서 패키지 참조</span><span class="sxs-lookup"><span data-stu-id="fb813-129">Referencing packages in F# Interactive</span></span>

> [!NOTE]
> <span data-ttu-id="fb813-130">패키지 관리는 F# 5 기능이며 현재 최신 .NET 5 SDK로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-130">Package management is an F# 5 feature and is currently available using the latest .NET 5 SDK.</span></span>

<span data-ttu-id="fb813-131">F# 대화형에서는 `#r "nuget:"` 구문 및 특정 버전으로 NuGet 패키지를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-131">F# Interactive supports referencing NuGet packages with the `#r "nuget:"` syntax and an optional version:</span></span>

```fsharp
#r "nuget: Newtonsoft.Json"
open Newtonsoft.Json

let data = {| Name = "Don Syme"; Occupation = "F# Creator" |}
JsonConvert.SerializeObject(data)
```

<span data-ttu-id="fb813-132">버전을 지정하지 않으면 사용 가능한 최상위 패키지(미리 보기 아님)가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-132">If a version is not specified, the highest available non-preview package is taken.</span></span> <span data-ttu-id="fb813-133">특정 버전을 참조하려면 쉼표를 사용하여 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-133">To reference a specific version, introduce the version via a comma.</span></span> <span data-ttu-id="fb813-134">이는 패키지의 미리 보기 버전을 참조하는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-134">This can be handy when referencing a preview version of a package.</span></span> <span data-ttu-id="fb813-135">예를 들어 [DiffSharp](https://diffsharp.github.io/)의 미리 보기 버전을 사용하여 이 스크립트를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-135">For example, consider this script using a preview version of [DiffSharp](https://diffsharp.github.io/):</span></span>

```fsharp
#r "nuget: DiffSharp-lite,1.0.0-preview-328097867"
open DiffSharp

// A 1D tensor
let t1 = dsharp.tensor [ 0.0 .. 0.2 .. 1.0 ]

// A 2x2 tensor
let t2 = dsharp.tensor [ [ 0; 1 ]; [ 2; 2 ] ]

// Define a scalar-to-scalar function
let f (x: Tensor) = sin (sqrt x)

printfn "%A" (f (dsharp.tensor 1.2))
```

<span data-ttu-id="fb813-136">스크립트에서 패키지 참조를 원하는 만큼 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-136">You can specify as many package references as you like in a script.</span></span>

## <a name="referencing-assemblies-on-disk-with-f-interactive"></a><span data-ttu-id="fb813-137">F# 대화형으로 디스크에서 어셈블리 참조</span><span class="sxs-lookup"><span data-stu-id="fb813-137">Referencing assemblies on disk with F# interactive</span></span>

<span data-ttu-id="fb813-138">또는 디스크에 어셈블리가 있고 스크립트에서 이를 참조하려는 경우 `#r` 구문을 사용하여 어셈블리를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-138">Alternatively, if you have an assembly on disk and wish to reference that in a script, you can use the `#r` syntax to specify an assembly.</span></span> <span data-ttu-id="fb813-139">`MyAssembly.dll`로 컴파일된 프로젝트에서 다음 코드를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="fb813-139">Consider the following code in a project compiled into `MyAssembly.dll`:</span></span>

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

<span data-ttu-id="fb813-140">컴파일 된 후에는 다음과 같이 `Script.fsx`라는 파일에서 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-140">One compiled, you can reference it in a file called `Script.fsx` like so:</span></span>

```fsharp
#r "path/to/MyAssembly.dll"

printfn "%A" (MyAssembly.myFunction 10 40)
```

<span data-ttu-id="fb813-141">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-141">The output is as follows:</span></span>

```console
dotnet fsi Script.fsx
90
```

<span data-ttu-id="fb813-142">스크립트에서 어셈블리 참조를 원하는 만큼 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-142">You can specify as many assembly references as you like in a script.</span></span>

## <a name="loading-other-scripts"></a><span data-ttu-id="fb813-143">다른 스크립트 로드</span><span class="sxs-lookup"><span data-stu-id="fb813-143">Loading other scripts</span></span>

<span data-ttu-id="fb813-144">스크립팅할 때 작업마다 다른 스크립트를 사용하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-144">When scripting, it can often be helpful to use different scripts for different tasks.</span></span> <span data-ttu-id="fb813-145">다른 스크립트에서 코드를 다시 사용하고자 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-145">Sometimes you may want to re-use code from on script in another.</span></span> <span data-ttu-id="fb813-146">콘텐츠를 복사하여 파일에 붙여 넣는 대신 `#load`를 사용하여 쉽게 로드하고 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-146">Rather than copy-pasting its contents into your file, you can simple load and evaluate it with `#load`.</span></span>

<span data-ttu-id="fb813-147">다음 `Script1.fsx`를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-147">Consider the following `Script1.fsx`:</span></span>

```fsharp
let square x = x * x
```

<span data-ttu-id="fb813-148">사용하는 파일은 `Script2.fsx`입니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-148">And the consuming file, `Script2.fsx`:</span></span>

```fsharp
#load "Script1.fsx"
open Script1

printfn "%d" (square 12)
```

<span data-ttu-id="fb813-149">`open Script1` 선언은 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-149">Note that the `open Script1` declaration is required.</span></span> <span data-ttu-id="fb813-150">F# 스크립트의 구문이 해당 스크립트 파일의 이름인 최상위 모듈로 컴파일되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-150">This is because constructs in an F# script are compiled into a top-level module that is the name of the script file it is in.</span></span>

<span data-ttu-id="fb813-151">다음과 같이 `Script2.fsx`를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-151">You can evaluate `Script2.fsx` like so:</span></span>

```console
dotnet fsi Script2.fsx
144
```

<span data-ttu-id="fb813-152">스크립트에서 `#load` 지시문을 원하는 만큼 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-152">You can specify as many `#load` directives as you like in a script.</span></span>

## <a name="using-the-fsi-object-in-f-code"></a><span data-ttu-id="fb813-153">F# 코드에서 `fsi` 개체 사용</span><span class="sxs-lookup"><span data-stu-id="fb813-153">Using the `fsi` object in F# code</span></span>

<span data-ttu-id="fb813-154">F# 스크립트는 F# 대화형 세션을 나타내는 사용자 지정 `fsi` 개체에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-154">F# scripts have access to a custom `fsi` object that represents the F# Interactive session.</span></span> <span data-ttu-id="fb813-155">출력 서식과 같은 항목을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-155">It allows you to customize things like output formatting.</span></span> <span data-ttu-id="fb813-156">또한 명령줄 인수에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-156">It is also how you can access command-line arguments.</span></span>

<span data-ttu-id="fb813-157">다음 예제에서는 명령줄 인수를 가져오고 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-157">The following example shows how to get and use command-line arguments:</span></span>

```fsharp
let args = fsi.CommandLineArgs

for arg in args do
    printfn "%s" arg
```

<span data-ttu-id="fb813-158">평가될 때 모든 인수를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-158">When evaluated, it prints all arguments.</span></span> <span data-ttu-id="fb813-159">첫 번째 인수는 항상 평가되는 스크립트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-159">The first argument is always the name of the script that is evaluated:</span></span>

```dotnet
dotnet fsi Script1.fsx hello world from fsi
Script1.fsx
hello
world
from
fsi
```

<span data-ttu-id="fb813-160">또한 `System.Environment.GetCommandLineArgs()`를 사용하여 동일한 인수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-160">Note that you can also use `System.Environment.GetCommandLineArgs()` to access the same arguments.</span></span>

## <a name="f-interactive-directive-reference"></a><span data-ttu-id="fb813-161">F# 대화형 지시문 참조</span><span class="sxs-lookup"><span data-stu-id="fb813-161">F# Interactive directive reference</span></span>

<span data-ttu-id="fb813-162">이전에 살펴본 `#r` 및 `#load` 지시문은 F# 대화형으로만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-162">The `#r` and `#load` directives seen previously are only available in F# Interactive.</span></span> <span data-ttu-id="fb813-163">F# 대화형으로만 사용할 수 있는 몇 가지 지시문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-163">There are several directives only available in F# Interactive:</span></span>

|<span data-ttu-id="fb813-164">지시문</span><span class="sxs-lookup"><span data-stu-id="fb813-164">Directive</span></span>|<span data-ttu-id="fb813-165">설명</span><span class="sxs-lookup"><span data-stu-id="fb813-165">Description</span></span>|
|---------|-----------|
|`#r "nuget:..."`|<span data-ttu-id="fb813-166">Nuget에서 패키지를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-166">References a package from Nuget</span></span>|
|`#r "assembly-name.dll"`|<span data-ttu-id="fb813-167">디스크에서 어셈블리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-167">References an assembly on disk</span></span>|
|`#load "file-name.fsx"`|<span data-ttu-id="fb813-168">소스 파일을 읽고 컴파일한 다음 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-168">Reads a source file, compiles it, and runs it.</span></span>|
|`#help`|<span data-ttu-id="fb813-169">사용 가능한 지시문에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-169">Displays information about available directives.</span></span>|
|`#I`|<span data-ttu-id="fb813-170">어셈블리 검색 경로를 따옴표로 묶어 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-170">Specifies an assembly search path in quotation marks.</span></span>|
|`#quit`|<span data-ttu-id="fb813-171">F# Interactive 세션을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-171">Terminates an F# Interactive session.</span></span>|
|<span data-ttu-id="fb813-172">`#time "on"` 또는 `#time "off"`</span><span class="sxs-lookup"><span data-stu-id="fb813-172">`#time "on"` or `#time "off"`</span></span>|<span data-ttu-id="fb813-173">`#time` 자체는 성능 정보 표시 여부를 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-173">By itself, `#time` toggles whether to display performance information.</span></span> <span data-ttu-id="fb813-174">`"on"`으로 설정하면 F# 대화형이 해석 및 실행되는 각 코드 섹션에 대해 실제 시간, CPU 시간 및 가비지 수집 정보를 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-174">When it is `"on"`, F# Interactive measures real time, CPU time, and garbage collection information for each section of code that is interpreted and executed.</span></span>|

<span data-ttu-id="fb813-175">F# Interactive에서 파일 또는 경로를 지정할 때는 문자열 리터럴이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-175">When you specify files or paths in F# Interactive, a string literal is expected.</span></span> <span data-ttu-id="fb813-176">따라서 파일 및 경로를 따옴표로 묶어야 하며, 일반적인 이스케이프 문자가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-176">Therefore, files and paths must be in quotation marks, and the usual escape characters apply.</span></span> <span data-ttu-id="fb813-177">`@` 문자를 사용하여 F# 대화형이 경로를 포함하는 문자열을 축자 문자열로 해석하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-177">You can use the `@` character to cause F# Interactive to interpret a string that contains a path as a verbatim string.</span></span> <span data-ttu-id="fb813-178">그러면 F# Interactive에서 이스케이프 문자를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-178">This causes F# Interactive to ignore any escape characters.</span></span>

## <a name="interactive-and-compiled-preprocessor-directives"></a><span data-ttu-id="fb813-179">대화형 및 컴파일된 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="fb813-179">Interactive and compiled preprocessor directives</span></span>

<span data-ttu-id="fb813-180">F# 대화형에서 코드를 컴파일할 때는 대화형으로 실행하든 스크립트를 실행하든 관계없이 **INTERACTIVE** 기호가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-180">When you compile code in F# Interactive, whether you are running interactively or running a script, the symbol **INTERACTIVE** is defined.</span></span> <span data-ttu-id="fb813-181">컴파일러에서 코드를 컴파일할 때는 **COMPILED** 기호가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-181">When you compile code in the compiler, the symbol **COMPILED** is defined.</span></span> <span data-ttu-id="fb813-182">따라서 컴파일된 모드와 대화형 모드에서 코드가 달라야 하는 경우 이러한 조건부 컴파일용 전처리기 지시문을 통해 사용할 코드를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-182">Thus, if code needs to be different in compiled and interactive modes, you can use these preprocessor directives for conditional compilation to determine which to use.</span></span> <span data-ttu-id="fb813-183">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-183">For example:</span></span>

```fsharp
#if INTERACTIVE
// Some code that executes only in FSI
// ...
#endif
```

## <a name="using-f-interactive-in-visual-studio"></a><span data-ttu-id="fb813-184">Visual Studio에서 F# 대화형 사용</span><span class="sxs-lookup"><span data-stu-id="fb813-184">Using F# Interactive in Visual Studio</span></span>

<span data-ttu-id="fb813-185">Visual Studio를 통해 F# Interactive를 실행하려면 **F# Interactive** 라는 레이블이 있는 적절한 도구 모음 단추를 클릭하거나 **Ctrl+Alt+F** 키를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-185">To run F# Interactive through Visual Studio, you can click the appropriate toolbar button labeled **F# Interactive** , or use the keys **Ctrl+Alt+F**.</span></span> <span data-ttu-id="fb813-186">이렇게 하면 대화형 창(F# Interactive 세션을 실행하는 도구 창)이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-186">Doing this will open the interactive window, a tool window running an F# Interactive session.</span></span> <span data-ttu-id="fb813-187">대화형 창에서 실행할 코드를 선택하고 **Alt+Enter** 키 조합을 눌러도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-187">You can also select some code that you want to run in the interactive window and hit the key combination **Alt+Enter**.</span></span> <span data-ttu-id="fb813-188">그러면 레이블이 **F# Interactive** 인 도구 창에서 F# Interactive가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-188">F# Interactive starts in a tool window labeled **F# Interactive**.</span></span> <span data-ttu-id="fb813-189">이 키 조합을 사용할 때 편집기 창에 포커스가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-189">When you use this key combination, make sure that the editor window has the focus.</span></span>

<span data-ttu-id="fb813-190">콘솔을 사용하든 Visual Studio를 사용하든 상관없이 명령 프롬프트가 나타납니다. 해석기를 실행하려면 사용자가 이 명령 프롬프트에 필요한 사항을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-190">Whether you are using the console or Visual Studio, a command prompt appears and the interpreter awaits your input.</span></span> <span data-ttu-id="fb813-191">코드 파일에서와 같은 방법으로 코드를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-191">You can enter code just as you would in a code file.</span></span> <span data-ttu-id="fb813-192">코드를 컴파일하고 실행하려면 세미콜론 두 개( **;;** )를 입력하여 입력 줄 하나 또는 여러 개를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-192">To compile and execute the code, enter two semicolons ( **;;** ) to terminate a line or several lines of input.</span></span>

<span data-ttu-id="fb813-193">F# Interactive가 코드 컴파일을 시도하며, 컴파일이 성공하면 코드를 실행하고 컴파일된 형식과 값의 서명을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-193">F# Interactive attempts to compile the code and, if successful, it executes the code and prints the signature of the types and values that it compiled.</span></span> <span data-ttu-id="fb813-194">오류가 발생하면 해석기에 오류 메시지가 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-194">If errors occur, the interpreter prints the error messages.</span></span>

<span data-ttu-id="fb813-195">프로그램을 빌드할 수 있도록 동일한 세션에서 입력한 코드는 이전에 입력된 모든 구문에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-195">Code entered in the same session has access to any constructs entered previously, so you can build up programs.</span></span> <span data-ttu-id="fb813-196">도구 창에서는 확장 버퍼가 제공되므로 필요한 경우 파일에 코드를 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-196">An extensive buffer in the tool window allows you to copy the code into a file if needed.</span></span>

<span data-ttu-id="fb813-197">F# Interactive는 Visual Studio에서 실행할 때 프로젝트와 독립적으로 실행되므로 예를 들어 함수의 코드를 대화형 창에 복사하지 않으면 프로젝트에 정의한 구문을 F# Interactive에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-197">When run in Visual Studio, F# Interactive runs independently of your project, so, for example, you cannot use constructs defined in your project in F# Interactive unless you copy the code for the function into the interactive window.</span></span>

<span data-ttu-id="fb813-198">설정을 조정하여 F# Interactive 명령줄 인수(옵션)를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-198">You can control the F# Interactive command line arguments (options) by adjusting the settings.</span></span> <span data-ttu-id="fb813-199">이렇게 하려면 **도구** 메뉴에서 **옵션...** 을 선택하고 **F# 도구** 를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-199">On the **Tools** menu, select **Options...** , and then expand **F# Tools**.</span></span> <span data-ttu-id="fb813-200">변경 가능한 두 가지 설정은 F# Interactive 옵션과 **64비트 F# Interactive** 설정(F# Interactive를 64비트 컴퓨터에서 실행하는 경우만 해당)입니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-200">The two settings that you can change are the F# Interactive options and the **64-bit F# Interactive** setting, which is relevant only if you are running F# Interactive on a 64-bit machine.</span></span> <span data-ttu-id="fb813-201">이 설정은 전용 64비트 버전의 **fsi.exe** 또는 **fsianycpu.exe** (컴퓨터 아키텍처를 사용하여 32비트 또는 64비트 프로세스로 실행할지 여부를 결정)를 실행할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-201">This setting determines whether you want to run the dedicated 64-bit version of **fsi.exe** or **fsianycpu.exe** , which uses the machine architecture to determine whether to run as a 32-bit or 64-bit process.</span></span>

## <a name="related-articles"></a><span data-ttu-id="fb813-202">관련 문서</span><span class="sxs-lookup"><span data-stu-id="fb813-202">Related articles</span></span>

|<span data-ttu-id="fb813-203">제목</span><span class="sxs-lookup"><span data-stu-id="fb813-203">Title</span></span>|<span data-ttu-id="fb813-204">Description</span><span class="sxs-lookup"><span data-stu-id="fb813-204">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="fb813-205">F# Interactive 옵션</span><span class="sxs-lookup"><span data-stu-id="fb813-205">F# Interactive Options</span></span>](../../language-reference/fsharp-interactive-options.md)|<span data-ttu-id="fb813-206">F# 대화형(fsi.exe)의 명령줄 구문 및 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fb813-206">Describes command-line syntax and options for the F# Interactive, fsi.exe.</span></span>|
