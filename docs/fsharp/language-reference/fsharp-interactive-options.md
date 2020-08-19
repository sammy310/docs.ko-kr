---
title: 대화형 옵션
description: F# 대화형 fsi.exe에서 지 원하는 명령줄 옵션에 대해 알아봅니다.
ms.date: 08/15/2020
ms.openlocfilehash: da2251c1d2e57090ed926e501cebf3c53ac58052
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558610"
---
# <a name="f-interactive-options"></a>F# 대화형 옵션

이 문서에서는 F# 대화형에서 지 원하는 명령줄 옵션을 설명 합니다 `fsi.exe` . F# 대화형은 F # 컴파일러와 동일한 명령줄 옵션을 여러 개 사용할 수 있지만 몇 가지 추가 옵션도 허용 합니다.

## <a name="use-f-interactive-for-scripting"></a>스크립팅에 F# 대화형 사용

F# 대화형는 `dotnet fsi` 대화형으로 실행 하거나 명령줄에서 실행 하 여 스크립트를 실행할 수 있습니다. 명령줄 구문은

```dotnetcli
dotnet fsi [options] [ script-file [arguments] ]
```

F # 스크립트 파일의 파일 확장명은 `.fsx` 입니다.

## <a name="table-of-f-interactive-options"></a>F# 대화형 옵션 표

다음 표에서는 F# 대화형에서 지 원하는 옵션을 요약 하 여 보여 줍니다. 이러한 옵션은 명령줄 또는 Visual Studio IDE를 통해 설정할 수 있습니다. Visual Studio IDE에서 이러한 옵션을 설정 하려면 **도구** 메뉴를 열고 **옵션**을 선택한 다음 **F # 도구** 노드를 확장 하 고 **F# 대화형**를 선택 합니다.

목록 요소가 F# 대화형 옵션 인수에 표시 되는 경우 목록 요소는 세미콜론 ()으로 구분 됩니다 `;` .

|옵션|Description|
|------|-----------|
|**--**|**Fsi.exe my.application.commandlineargs**를 사용 하 여 코드에서 액세스할 수 있는 F # 프로그램 또는 스크립트에 대 한 명령줄 인수로 나머지 인수를 처리 하도록 F# 대화형에 지시 하는 데 사용 됩니다.|
|**--확인**됨 [ **+**&#124;**-** ]|**fsc.exe** 컴파일러 옵션과 동일 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.|
|**--codepage: &lt; int&gt;**|**fsc.exe** 컴파일러 옵션과 동일 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.|
|**--consolecolors**[ **+**&#124;**-** ]|경고 및 오류 메시지를 색으로 출력 합니다.|
|**--교차 최적화**[ **+**&#124;**-** ]|크로스 모듈 최적화를 사용 하거나 사용 하지 않도록 설정 합니다.|
|**--debug**[ **+**&#124;**-** ]<br /><br />**--debug:**[**full**&#124;**pdbonly**&#124;**이식 가능한**&#124;**포함**]<br /><br />**-g**[ **+**&#124;**-** ]<br /><br />**-g:**[**full**&#124;**pdbonly**&#124;**이식 가능한**&#124;**포함**]|**fsc.exe** 컴파일러 옵션과 동일 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.|
|**--define: &lt; 문자열&gt;**|**fsc.exe** 컴파일러 옵션과 동일 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.|
|**--결정적**[ **+**&#124;**-** ]|결정적 어셈블리 (모듈 버전 GUID 및 타임 스탬프 포함)를 생성 합니다.|
|**--exec**|파일을 로드 하거나 명령줄에 지정 된 스크립트 파일을 실행 한 후 F # interactive를 종료 하도록 지시 합니다.|
|**--fullpaths**|**fsc.exe** 컴파일러 옵션과 동일 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.|
|**--gui**[ **+**&#124;**-** ]|Windows Forms 이벤트 루프를 사용 하거나 사용 하지 않도록 설정 합니다. 기본값을 사용합니다.|
|**--도움말**<br /><br />**-?**|각 옵션에 대 한 간단한 설명 및 명령줄 구문을 표시 하는 데 사용 됩니다.|
|**--lib: &lt; 폴더-목록&gt;**<br /><br />**-I: &lt; 폴더-목록&gt;**|**fsc.exe** 컴파일러 옵션과 동일 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.|
|**--load: &lt; filename&gt;**|시작 시 지정 된 소스 코드를 컴파일하고 컴파일된 F # 구문을 세션에 로드 합니다.|
|**--mlcompatibility**|**fsc.exe** 컴파일러 옵션과 동일 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.|
|**--noframework**|**fsc.exe** 컴파일러 옵션과 동일 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md) 을 참조 하세요.|
|**--nologo**|**fsc.exe** 컴파일러 옵션과 동일 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.|
|**--nowarn: &lt; warning-list&gt;**|**fsc.exe** 컴파일러 옵션과 동일 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.|
|**--optimize**[ **+**&#124;**-** ]|**fsc.exe** 컴파일러 옵션과 동일 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.|
|**--preferreduilang: &lt; lang&gt;**| 기본 출력 언어 문화권 이름 (예: es, ja-jp)을 지정 합니다. |
|**--quiet**|**Stdout** 스트림에 대 한 F# 대화형 출력을 표시 하지 않습니다.|
|**--인용구-debug**|F # 인용 리터럴에서 파생 된 정의와 리플렉션 정의에서 파생 된 식에 대 한 추가 디버깅 정보를 내보내도록 지정 합니다. 디버그 정보는 F # 식 트리 노드의 사용자 지정 특성에 추가 됩니다. [코드 인용](code-quotations.md) 및 [Expr. customattributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3)를 참조 하세요.|
|**--readline**[ **+**&#124;**-** ]|대화형 모드에서 탭 완성 기능을 사용 하거나 사용 하지 않도록 설정 합니다.|
|**--참조: &lt; 파일 이름&gt;**<br /><br />**-r: &lt; 파일 이름&gt;**|**fsc.exe** 컴파일러 옵션과 동일 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.|
|**--tailcalls**[ **+**&#124;**-** ]|Tail IL 명령을 사용 하거나 사용 하지 않도록 설정 하 여 tail 재귀 함수에 스택 프레임을 다시 사용 하도록 합니다. 기본적으로 이 옵션은 사용하도록 설정됩니다.|
|**--targetprofile: &lt; 문자열&gt;**|이 어셈블리의 대상 프레임 워크 프로필을 지정 합니다. 유효한 값은 `mscorlib`, `netcore` 또는 `netstandard`입니다. 기본값은 `mscorlib`입니다.|
|**--사용: &lt; 파일 이름&gt;**|시작 시 지정 된 파일을 초기 입력으로 사용 하도록 인터프리터에 지시 합니다.|
|**--utf8output**|fsc.exe 컴파일러 옵션과 동일 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.|
|**--경고: &lt; 경고 수준&gt;**|**fsc.exe** 컴파일러 옵션과 동일 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.|
|**--warnaserror**[ **+**&#124;**-** ]|**fsc.exe** 컴파일러 옵션과 동일 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.|
|**--warnaserror**[ **+**&#124;**-** ]:** &lt; int 목록 &gt; **|**fsc.exe** 컴파일러 옵션과 동일 합니다. 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.|

## <a name="f-interactive-structured-printing"></a>F# 대화형 구조적 인쇄

F# 대화형 ( `dotnet fsi` )는 보고서 값에 대 한 [구조적 일반 텍스트 서식](plaintext-formatting.md) 의 확장 된 버전을 사용 합니다.

1. `%A`일반 텍스트 서식의 모든 기능이 지원 되며 일부는 추가로 사용자 지정이 가능 합니다.

2. 출력 콘솔에서 색을 지 원하는 경우 인쇄는 색이 있습니다.

3. 해당 문자열을 명시적으로 평가 하지 않으면 표시 되는 문자열의 길이에 제한이 적용 됩니다.

4. 개체를 통해 사용자 정의 가능한 설정 집합을 사용할 수 있습니다 `fsi` .

보고 된 값에 대해 일반 텍스트 인쇄를 사용자 지정 하는 데 사용할 수 있는 설정은 다음과 같습니다.

```fsharp
open System.Globalization

fsi.FormatProvider <- CultureInfo("de-DE")  // control the default culture for primitives

fsi.PrintWidth <- 120        // Control the width used for structured printing

fsi.PrintDepth <- 10         // Control the maximum depth of nested printing

fsi.PrintLength <- 10        // Control the length of lists and arrays

fsi.PrintSize <- 100         // Control the maximum overall object count

fsi.ShowProperties <- false  // Control whether properties of .NET objects are shown by default

fsi.ShowIEnumerable <- false // Control whether sequence values are expanded by default

fsi.ShowDeclarationValues <- false // Control whether values are shown for declaration outputs
```

### <a name="customize-with-addprinter-and-addprinttransformer"></a>및를 사용 하 여 사용자 지정 `AddPrinter``AddPrintTransformer`

및를 사용 하 여 F# 대화형 출력의 인쇄를 사용자 지정할 수 있습니다 `fsi.AddPrinter` `fsi.AddPrintTransformer` .
첫 번째 함수는 개체의 인쇄를 바꿀 텍스트를 제공 합니다. 두 번째 함수는 대신 표시할 서로게이트 개체를 반환 합니다. 예를 들어 다음 F # 코드를 살펴보세요.

```fsharp
open System

fsi.AddPrinter<DateTime>(fun dt -> dt.ToString("s"))

type DateAndLabel =
    { Date: DateTime
      Label: string  }

let newYearsDay1999 =
    { Date = DateTime(1999, 1, 1)
      Label = "New Year" }
```

F# 대화형에서 예제를 실행 하는 경우 형식 지정 옵션 집합을 기반으로 출력 됩니다. 이 경우 날짜 및 시간의 형식에 영향을 줍니다.

```console
type DateAndLabel =
  { Date: DateTime
    Label: string }
val newYearsDay1999 : DateAndLabel = { Date = 1999-01-01T00:00:00
                                       Label = "New Year" }
```

`fsi.AddPrintTransformer` 를 사용 하 여 인쇄를 위한 서로게이트 개체를 제공할 수 있습니다.

```fsharp
type MyList(values: int list) =
    member _.Values = values

fsi.AddPrintTransformer(fun (x:MyList) -> box x.Values)

let x = MyList([1..10])
```

출력은 다음과 같습니다.

```console
val x : MyList = [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
```

에 전달 된 변환기 함수가를 반환 하는 경우 `fsi.AddPrintTransformer` `null` 인쇄 변환기는 무시 됩니다.
형식으로 시작 하 여 입력 값을 필터링 하는 데 사용할 수 있습니다 `obj` .  예를 들면 다음과 같습니다.

```fsharp
fsi.AddPrintTransformer(fun (x:obj) ->
    match x with
    | :? string as s when s = "beep" -> box ["quack"; "quack"; "quack"]
    | _ -> null)

let y = "beep"
```

출력은 다음과 같습니다.

```console
val y : string = ["quack"; "quack"; "quack"]
```

## <a name="related-topics"></a>관련 항목

|제목|Description|
|-----|-----------|
|[컴파일러 옵션](compiler-options.md)|**fsc.exe**F # 컴파일러에 사용할 수 있는 명령줄 옵션에 대해 설명 합니다.|
