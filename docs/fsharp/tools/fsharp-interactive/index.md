---
title: F# 대화형(dotnet) 참조
description: F# 대화형(dotnet fsi)이 어떻게 콘솔에서 F# 코드를 대화형으로 실행하거나 F# 스크립트를 실행하는 데 사용되는지 알아보세요.
ms.date: 10/31/2020
f1_keywords:
- VS.ToolsOptionsPages.F#_Tools.F#_Interactive
ms.openlocfilehash: b535cb03d76909043ca192ed5a9d2078f9343795
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099436"
---
# <a name="interactive-programming-with-f"></a>F\#을 사용한 대화형 프로그래밍

F# 대화형(dotnet fsi)은 콘솔에서 F# 코드를 대화형으로 실행하거나 F# 스크립트를 실행하는 데 사용됩니다. 즉, F# Interactive는 F# 언어에 대해 REPL(읽기, 평가, 인쇄 루프)을 실행합니다.

콘솔에서 F# 대화형을 실행하려면 `dotnet fsi`를 실행합니다. 모든 .NET SDK에서 `dotnet fsi`를 찾을 수 있습니다.

사용 가능한 명령줄 옵션에 대한 정보는 [F# 대화형 옵션](../../language-reference/fsharp-interactive-options.md)을 참조하세요.

## <a name="executing-code-directly-in-f-interactive"></a>F# 대화형에서 직접 코드 실행

F# 대화형은 REPL(read-eval-print loop)이므로 대화형으로 코드를 실행할 수 있습니다. 다음은 명령줄에서 `dotnet fsi`를 실행한 후의 대화형 세션 예입니다.

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

두 가지를 확인할 수 있습니다.

1. 모든 코드는 두 개의 세미콜론(`;;`)으로 끝나야 평가 가능합니다.
2. 코드는 평가되고 `it` 값에 저장됩니다. `it`을 대화형으로 참조할 수 있습니다.

F# 대화형은 여러 줄 입력도 지원합니다. 이중 세미콜론(`;;`)으로 제출을 종료하기만 하면 됩니다. F# 대화형으로 붙여 넣고 평가된 다음 코드 조각을 살펴보십시오.

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

코드의 형식이 유지되며 입력을 종료하는 이중 세미콜론(`;;`)이 있습니다. 그런 다음 F# 대화형으로 코드를 평가하고 결과를 출력했습니다.

## <a name="scripting-with-f"></a>F\#을 사용한 스크립팅

F# 대화형으로 코드를 평가하는 것은 좋은 학습 도구일 수 있지만 일반적인 편집기에서 코드를 작성하는 것만큼 생산적이지는 않습니다. 일반 코드 편집을 지원하기 위해 F# 스크립트를 작성할 수 있습니다.

스크립트는 **.fsx** 파일 확장명을 사용합니다. 소스 코드를 컴파일한 다음 나중에 컴파일된 어셈블리를 실행하는 대신 **dotnet fsi** 를 실행하고 F# 소스 코드의 스크립트 파일 이름을 지정하면 F# 대화형이 실시간으로 코드를 읽고 실행할 수 있습니다. 예를 들어, `Script.fsx`라는 스크립트를 가정해 봅시다.

```fsharp
let getOddSquares xs =
    xs
    |> List.filter (fun x -> x % 2 <> 0)
    |> List.map (fun x -> x * x)

printfn "%A" (getOddSquares [1..10])
```

컴퓨터에서 이 파일을 만들 때 `dotnet fsi`를 사용하여 실행하고 터미널 창에서 출력을 직접 볼 수 있습니다.

```console
dotnet fsi Script.fsx
[1; 9; 25; 49; 81]
```

F# 스크립팅은 기본적으로 [Visual Studio](../../get-started/get-started-visual-studio.md), [Visual Studio Code](../../get-started/get-started-vscode.md) 및 [Mac용 Visual Studio](../../get-started/get-started-with-visual-studio-for-mac.md)에서 지원됩니다.

## <a name="referencing-packages-in-f-interactive"></a>F# 대화형에서 패키지 참조

F# 대화형에서는 `#r "nuget:"` 구문 및 특정 버전으로 NuGet 패키지를 참조할 수 있습니다.

```fsharp
#r "nuget: Newtonsoft.Json"
open Newtonsoft.Json

let data = {| Name = "Don Syme"; Occupation = "F# Creator" |}
JsonConvert.SerializeObject(data)
```

버전을 지정하지 않으면 사용 가능한 최상위 패키지(미리 보기 아님)가 생성됩니다. 특정 버전을 참조하려면 쉼표를 사용하여 버전을 지정합니다. 이는 패키지의 미리 보기 버전을 참조하는 경우에 유용할 수 있습니다. 예를 들어 [DiffSharp](https://diffsharp.github.io/)의 미리 보기 버전을 사용하여 이 스크립트를 살펴보겠습니다.

```fsharp
#r "nuget: DiffSharp-lite, 1.0.0-preview-328097867"
open DiffSharp

// A 1D tensor
let t1 = dsharp.tensor [ 0.0 .. 0.2 .. 1.0 ]

// A 2x2 tensor
let t2 = dsharp.tensor [ [ 0; 1 ]; [ 2; 2 ] ]

// Define a scalar-to-scalar function
let f (x: Tensor) = sin (sqrt x)

printfn "%A" (f (dsharp.tensor 1.2))
```

스크립트에서 패키지 참조를 원하는 만큼 지정할 수 있습니다.

> [!NOTE]
> 현재 프레임워크 참조를 사용하는 스크립트에 대한 제한(예: `Microsoft.NET.Sdk.Web` 또는 `Microsoft.NET.Sdk.WindowsDesktop`)이 있습니다. Saturn, Giraffe, WinForms와 같은 패키지는 사용할 수 없습니다. 이는 [#9417](https://github.com/dotnet/fsharp/issues/9417) 이슈에서 추적되고 있습니다.

## <a name="referencing-assemblies-on-disk-with-f-interactive"></a>F# 대화형으로 디스크에서 어셈블리 참조

또는 디스크에 어셈블리가 있고 스크립트에서 이를 참조하려는 경우 `#r` 구문을 사용하여 어셈블리를 지정할 수 있습니다. `MyAssembly.dll`로 컴파일된 프로젝트에서 다음 코드를 고려하세요.

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

컴파일 된 후에는 다음과 같이 `Script.fsx`라는 파일에서 참조할 수 있습니다.

```fsharp
#r "path/to/MyAssembly.dll"

printfn "%A" (MyAssembly.myFunction 10 40)
```

출력은 다음과 같습니다.

```console
dotnet fsi Script.fsx
90
```

스크립트에서 어셈블리 참조를 원하는 만큼 지정할 수 있습니다.

## <a name="loading-other-scripts"></a>다른 스크립트 로드

스크립팅할 때 작업마다 다른 스크립트를 사용하는 것이 유용할 수 있습니다. 경우에 따라 다른 스크립트에서 코드를 다시 사용하는 것이 좋습니다. 콘텐츠를 복사하여 파일에 붙여 넣는 대신 `#load`를 사용하여 쉽게 로드하고 평가할 수 있습니다.

다음 `Script1.fsx`를 고려합니다.

```fsharp
let square x = x * x
```

사용하는 파일은 `Script2.fsx`입니다.

```fsharp
#load "Script1.fsx"
open Script1

printfn "%d" (square 12)
```

`open Script1` 선언은 필수입니다. F# 스크립트의 구문이 해당 스크립트 파일의 이름인 최상위 모듈로 컴파일되기 때문입니다.

다음과 같이 `Script2.fsx`를 평가할 수 있습니다.

```console
dotnet fsi Script2.fsx
144
```

스크립트에서 `#load` 지시문을 원하는 만큼 지정할 수 있습니다.

## <a name="using-the-fsi-object-in-f-code"></a>F# 코드에서 `fsi` 개체 사용

F# 스크립트는 F# 대화형 세션을 나타내는 사용자 지정 `fsi` 개체에 액세스할 수 있습니다. 출력 서식과 같은 항목을 사용자 지정할 수 있습니다. 또한 명령줄 인수에 액세스할 수도 있습니다.

다음 예제에서는 명령줄 인수를 가져오고 사용하는 방법을 보여 줍니다.

```fsharp
let args = fsi.CommandLineArgs

for arg in args do
    printfn "%s" arg
```

평가될 때 모든 인수를 출력합니다. 첫 번째 인수는 항상 평가되는 스크립트의 이름입니다.

```dotnet
dotnet fsi Script1.fsx hello world from fsi
Script1.fsx
hello
world
from
fsi
```

또한 `System.Environment.GetCommandLineArgs()`를 사용하여 동일한 인수에 액세스할 수 있습니다.

## <a name="f-interactive-directive-reference"></a>F# 대화형 지시문 참조

이전에 살펴본 `#r` 및 `#load` 지시문은 F# 대화형으로만 가능합니다. F# 대화형으로만 사용할 수 있는 몇 가지 지시문은 다음과 같습니다.

|지시문|설명|
|---------|-----------|
|`#r "nuget:..."`|NuGet에서 패키지를 참조합니다.|
|`#r "assembly-name.dll"`|디스크에서 어셈블리를 참조합니다.|
|`#load "file-name.fsx"`|소스 파일을 읽고 컴파일한 다음 실행합니다.|
|`#help`|사용 가능한 지시문에 대한 정보를 표시합니다.|
|`#I`|어셈블리 검색 경로를 따옴표로 묶어 지정합니다.|
|`#quit`|F# Interactive 세션을 종료합니다.|
|`#time "on"` 또는 `#time "off"`|`#time` 자체는 성능 정보 표시 여부를 전환합니다. `"on"`으로 설정하면 F# 대화형이 해석 및 실행되는 각 코드 섹션에 대해 실제 시간, CPU 시간 및 가비지 수집 정보를 측정합니다.|

F# Interactive에서 파일 또는 경로를 지정할 때는 문자열 리터럴이 필요합니다. 따라서 파일 및 경로를 따옴표로 묶어야 하며, 일반적인 이스케이프 문자가 적용됩니다. `@` 문자를 사용하여 F# 대화형이 경로를 포함하는 문자열을 축자 문자열로 해석하도록 할 수 있습니다. 그러면 F# Interactive에서 이스케이프 문자를 무시합니다.

## <a name="interactive-and-compiled-preprocessor-directives"></a>대화형 및 컴파일된 전처리기 지시문

F# 대화형에서 코드를 컴파일할 때는 대화형으로 실행하든 스크립트를 실행하든 관계없이 **INTERACTIVE** 기호가 정의됩니다. 컴파일러에서 코드를 컴파일할 때는 **COMPILED** 기호가 정의됩니다. 따라서 컴파일된 모드와 대화형 모드에서 코드가 달라야 하는 경우 이러한 조건부 컴파일용 전처리기 지시문을 통해 사용할 코드를 결정할 수 있습니다. 예를 들면 다음과 같습니다.

```fsharp
#if INTERACTIVE
// Some code that executes only in FSI
// ...
#endif
```

## <a name="using-f-interactive-in-visual-studio"></a>Visual Studio에서 F# 대화형 사용

Visual Studio를 통해 F# Interactive를 실행하려면 **F# Interactive** 라는 레이블이 있는 적절한 도구 모음 단추를 클릭하거나 **Ctrl+Alt+F** 키를 사용합니다. 이렇게 하면 대화형 창(F# Interactive 세션을 실행하는 도구 창)이 열립니다. 대화형 창에서 실행할 코드를 선택하고 **Alt+Enter** 키 조합을 눌러도 됩니다. 그러면 레이블이 **F# Interactive** 인 도구 창에서 F# Interactive가 시작됩니다. 이 키 조합을 사용할 때 편집기 창에 포커스가 있는지 확인합니다.

콘솔을 사용하든 Visual Studio를 사용하든 상관없이 명령 프롬프트가 나타납니다. 해석기를 실행하려면 사용자가 이 명령 프롬프트에 필요한 사항을 입력해야 합니다. 코드 파일에서와 같은 방법으로 코드를 입력할 수 있습니다. 코드를 컴파일하고 실행하려면 세미콜론 두 개(**;;**)를 입력하여 입력 줄 하나 또는 여러 개를 종료합니다.

F# Interactive가 코드 컴파일을 시도하며, 컴파일이 성공하면 코드를 실행하고 컴파일된 형식과 값의 서명을 인쇄합니다. 오류가 발생하면 해석기에 오류 메시지가 출력됩니다.

프로그램을 빌드할 수 있도록 동일한 세션에서 입력한 코드는 이전에 입력된 모든 구문에 액세스할 수 있습니다. 도구 창에서는 확장 버퍼가 제공되므로 필요한 경우 파일에 코드를 복사할 수 있습니다.

F# Interactive는 Visual Studio에서 실행할 때 프로젝트와 독립적으로 실행되므로 예를 들어 함수의 코드를 대화형 창에 복사하지 않으면 프로젝트에 정의한 구문을 F# Interactive에서 사용할 수 없습니다.

설정을 조정하여 F# 대화형 명령줄 인수(옵션)를 제어할 수 있습니다. 이렇게 하려면 **도구** 메뉴에서 **옵션...** 을 선택하고 **F# 도구** 를 확장합니다. 변경 가능한 두 가지 설정은 F# Interactive 옵션과 **64비트 F# Interactive** 설정(F# Interactive를 64비트 컴퓨터에서 실행하는 경우만 해당)입니다. 이 설정은 전용 64비트 버전의 **fsi.exe** 또는 **fsianycpu.exe**(컴퓨터 아키텍처를 사용하여 32비트 또는 64비트 프로세스로 실행할지 여부를 결정)를 실행할지 여부를 결정합니다.

## <a name="related-articles"></a>관련 문서

|제목|Description|
|-----|-----------|
|[F# Interactive 옵션](../../language-reference/fsharp-interactive-options.md)|F# 대화형(fsi.exe)의 명령줄 구문 및 옵션에 대해 설명합니다.|
