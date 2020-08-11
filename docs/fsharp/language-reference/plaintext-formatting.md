---
title: 일반 텍스트 형식
description: 'F # 응용 프로그램 및 스크립트에서 printf 및 기타 일반 텍스트 서식 지정을 사용 하는 방법에 대해 알아봅니다.'
ms.date: 07/22/2020
ms.openlocfilehash: 90a861736dae69dfbc199a19e24f587c42404737
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063785"
---
# <a name="plain-text-formatting"></a>일반 텍스트 서식 지정

F # `printf` 에서는,, 및 관련 함수를 사용 하 여 일반 텍스트의 형식 선택 형식을 지원 `printfn` `sprintf` 합니다.
예를 들면 다음과 같습니다.

```console
dotnet fsi

> printfn "Hello %s, %d + %d is %d" "world" 2 2 (2+2);;
```

출력을 제공 합니다.

```fsharp
Hello world, 2 + 2 is 4
```

또한 F #에서는 구조적 값을 일반 텍스트로 서식 지정할 수 있습니다.
예를 들어 다음 예제에서는 출력을 매트릭스와 유사한 튜플 표시로 지정 합니다.

```console
dotnet fsi

> printfn "%A" [ for i in 1 .. 5 -> [ for j in 1 .. 5 -> (i, j) ] ];;

[[(1, 1); (1, 2); (1, 3); (1, 4); (1, 5)];
 [(2, 1); (2, 2); (2, 3); (2, 4); (2, 5)];
 [(3, 1); (3, 2); (3, 3); (3, 4); (3, 5)];
 [(4, 1); (4, 2); (4, 3); (4, 4); (4, 5)];
 [(5, 1); (5, 2); (5, 3); (5, 4); (5, 5)]]
```

`%A`서식 문자열에 형식을 사용 하는 경우 구조적 일반 텍스트 형식이 활성화 됩니다 `printf` .
또한 F # interactive에서 값 출력의 서식을 지정할 때 활성화 됩니다. 여기에서 출력에는 추가 정보가 포함 되 고 추가로 사용자 지정이 가능 합니다.
일반 텍스트 서식 지정은 `x.ToString()` 디버깅, 로깅 및 기타 도구에서 암시적으로 발생 하는 값을 포함 하 여 F # 공용 구조체 및 레코드 값에 대 한 모든 호출을 통해 관찰할 수 있습니다.

## <a name="checking-of-printf-format-strings"></a>형식 문자열을 확인 하는 중 `printf`

`printf`형식 문자열의 printf 형식 지정자와 일치 하지 않는 인수와 함께 서식 함수를 사용 하는 경우 컴파일 시간 오류가 보고 됩니다.  예를 들면 다음과 같습니다.

```fsharp
sprintf "Hello %s" (2+2)
```

출력을 제공 합니다.

```console
  sprintf "Hello %s" (2+2)
  ----------------------^

stdin(3,25): error FS0001: The type 'string' does not match the type 'int'
```

기술적으로 말하면 `printf` 및 기타 관련 된 함수를 사용 하는 경우 F # 컴파일러의 특별 한 규칙은 형식 문자열로 전달 된 문자열 리터럴을 검사 하 여, 적용 되는 후속 인수가 사용 되는 형식 지정자와 일치 하는지 확인 하는 올바른 형식 인지 확인 합니다.

## <a name="format-specifiers-for-printf"></a>형식 지정자`printf`

형식에 대 한 형식 지정 `printf` 은 `%` 형식을 나타내는 표식을 사용 하는 문자열입니다. 형식 자리 표시자는 `%[flags][width][.precision][type]` 형식이 다음과 같이 해석 되는 위치로 구성 됩니다.

| 형식 지정자   | 유형        | 설명                      |
|:-------------------|:---------------|:-----------------------------|
| `%b`               | bool      | 또는로 형식이 지정 됨 `true``false`                |
| `%s`               | 문자열    | 이스케이프 되지 않은 콘텐츠로 서식 지정         |
| `%c`               | char      | 문자 리터럴로 형식이 지정 됩니다.  |
| `%d`, `%i`         | 기본 정수 형식 | 기본 정수 형식이 서명 된 경우 부호 있는 10 진수 정수로 형식이 지정 됩니다. |
| `%u`               | 기본 정수 형식 | 부호 없는 10 진수 정수로 형식이 지정 됩니다.   |
| `%x`, `%X`         | 기본 정수 형식 | 부호 없는 16 진수 (각각 16 진수에 대 한 a-f 또는 A-f) 형식으로 표시 됩니다.  |
|  `%o`              | 기본 정수 형식 | 부호 없는 8 진수 숫자로 서식 지정 |
| `%e`, `%E`         | 기본 부동 소수점 형식 | 형식에 부호 있는 값으로 서식이 지정 `[-]d.dddde[sign]ddd` 됩니다. 여기서 d는 단일 10 진수이 고, dddd는 하나 이상의 10 진수이 고, ddd는 정확히 3 자리 10 진수이 고, 부호는 또는입니다. `+``-` |
| `%f`               | 기본 부동 소수점 형식 | 형식을 가진 부호 있는 값으로 형식이 지정 `[-]dddd.dddd` `dddd` 됩니다. 여기서은 하나 이상의 10 진수입니다. 소수점 앞의 자릿수는 수의 크기에 따라 다르며, 소수점 뒤의 자릿수는 요청된 정밀도에 따라 다릅니다. |
| `%g`, `%G` | 기본 부동 소수점 형식 |  또는 형식으로 인쇄 된 부호 있는 값으로를 사용 하 여 서식이 지정 된 `%f` `%e` 값 및 전체 자릿수에 대해 더 간결한 형식으로 표시 됩니다. |
| `%M` | `System.Decimal`값  |    형식 지정자를 사용 하 여 형식이 지정 됩니다. `"G"``System.Decimal.ToString(format)` |
| `%O` | 모든 값  |   개체를 boxing 하 고 메서드를 호출 하 여 형식이 지정 됩니다. `System.Object.ToString()` |
| `%A` | 모든 값  |   기본 레이아웃 설정을 사용 하 여 [구조적 일반 텍스트 서식 지정](plaintext-formatting.md) 을 사용 하 여 서식 지정 |
| `%a` | 모든 값  |   두 개의 인수가 필요 합니다. 형식 지정 함수는 컨텍스트 매개 변수 및 값을 허용 하 고 특정 값은 인쇄 해야 합니다. |
| `%t` | 모든 값  |   하나의 인수가 필요 합니다. 형식 지정 함수는 적절 한 텍스트를 출력 하거나 반환 하는 컨텍스트 매개 변수를 허용 합니다. |
| `%%` | (없음)  |   인수를 사용 하지 않고 일반 백분율 기호를 인쇄 합니다.`%` |

기본 정수 형식은 `byte` ( `System.Byte` ), `sbyte` ( `System.SByte` ), (), (), (), (), (), (), () `int16` `System.Int16` `uint16` `System.UInt16` `int32` `System.Int32` `uint32` `System.UInt32` `int64` `System.Int64` `uint64` `System.UInt64` `nativeint` `System.IntPtr` 및 () `unativeint` `System.UIntPtr` 입니다.
기본 부동 소수점 형식은 `float` ( `System.Double` ) 및 `float32` ( `System.Single` )입니다.

선택적 너비는 결과의 최소 너비를 나타내는 정수입니다. 예를 들어는 `%6d` 정수를 인쇄 하 여 6 자 이상으로 채울 수 있는 공백을 접두사로 사용 합니다. Width가 이면 `*` 추가 정수 인수를 사용 하 여 해당 너비를 지정 합니다.

유효한 플래그는 다음과 같습니다.

| 플래그   | 효과        | 설명                      |
|:-------------------|:---------------|:-----------------------------|
| `0`  | 필요한 너비를 구성 하려면 공백 대신 0을 추가 합니다. |    |
| `-` |  지정 된 너비 내에서 결과를 왼쪽에 맞춥니다. |   |
| `+`  | `+`숫자가 양수 이면 문자를 추가 합니다 (부정 부호와 일치 하는 경우 `-` ). |   |
| 공백 문자 | 숫자가 양수 이면 추가 공백을 추가 합니다 (부정의 '-' 부호와 일치). |

Printf `#` 플래그가 잘못 되었으며 사용 되는 경우 컴파일 타임 오류가 보고 됩니다.

값은 고정 문화권을 사용 하 여 형식이 지정 됩니다. 문화권 설정은 `printf` 및 형식 지정의 결과에 영향을 주는 경우를 제외 하 고는 서식 지정 `%O` 과 관련이 `%A` 없습니다. 자세한 내용은 [구조적 일반 텍스트 서식 지정](plaintext-formatting.md)을 참조 하세요.

## <a name="a-formatting"></a>`%A`서식 지정

`%A`형식 지정자는 사람이 읽을 수 있는 방식으로 값의 형식을 지정 하는 데 사용 되며 진단 정보를 보고 하는 데에도 유용할 수 있습니다.

### <a name="primitive-values"></a>기본 값

지정자를 사용 하 여 일반 텍스트의 서식을 지정 하는 경우 `%A` F # 숫자 값은 접미사와 고정 문화권으로 서식이 지정 됩니다. 부동 소수점 값은 부동 소수점 전체 자릿수 10 개를 사용 하 여 서식이 지정 됩니다. 예를 들면 다음과 같습니다.

```fsharp
printfn "%A" (1L, 3n, 5u, 7, 4.03f, 5.000000001, 5.0000000001)
```

예제의

```console
(1L, 3n, 5u, 7, 4.03000021f, 5.000000001, 5.0)
```

지정자를 사용 하는 경우 `%A` 따옴표를 사용 하 여 문자열의 서식을 지정 합니다. 이스케이프 코드는 추가 되지 않고 대신 원시 문자를 출력 합니다. 예를 들면 다음과 같습니다.

```fsharp
printfn "%A" ("abc", "a\tb\nc\"d")

```

예제의

```console
("abc", "a      b
c"d")
```

### <a name="net-values"></a>.NET 값

지정자를 사용 하 여 일반 텍스트의 서식을 지정 하는 경우 `%A` `x.ToString()` 및에서 제공 하는 .net의 기본 설정을 사용 하 여 비 F # .net 개체의 형식을 지정 합니다 `System.Globalization.CultureInfo.CurrentCulture` `System.Globalization.CultureInfo.CurrentUICulture` .  예를 들면 다음과 같습니다.

```fsharp
open System.Globalization

let date = System.DateTime(1999, 12, 31)

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("de-DE")
printfn "Culture 1: %A" date

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("en-US")
printfn "Culture 2: %A" date
```

예제의

```console
Culture 1: 31.12.1999 00:00:00
Culture 2: 12/31/1999 12:00:00 AM
```

### <a name="structured-values"></a>구조적 값

지정자를 사용 하 여 일반 텍스트의 서식을 지정 하는 경우 `%A` F # 목록 및 튜플에 대해 블록 들여쓰기가 사용 됩니다. 이전 예제에 표시 된 것입니다.
다차원 배열을 비롯 한 배열의 구조도 사용 됩니다.  1 차원 배열에는 구문이 표시 됩니다 `[| ... |]` . 예를 들면 다음과 같습니다.

```fsharp
printfn "%A" [| for i in 1 .. 20 -> (i, i*i) |]
```

예제의

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25); (6, 36); (7, 49); (8, 64); (9, 81);
  (10, 100); (11, 121); (12, 144); (13, 169); (14, 196); (15, 225); (16, 256);
  (17, 289); (18, 324); (19, 361); (20, 400)|]
```

기본 인쇄 너비는 80입니다.  이 너비는 서식 지정자에서 인쇄 너비를 사용 하 여 사용자 지정할 수 있습니다. 예를 들면 다음과 같습니다.

```fsharp
printfn "%10A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%20A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%50A" [| for i in 1 .. 5 -> (i, i*i) |]
```

예제의

```console
[|(1, 1);
  (2, 4);
  (3, 9);
  (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4);
  (3, 9); (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
```

인쇄 너비를 0으로 지정 하면 인쇄 너비가 사용 되지 않습니다. 출력의 포함 된 문자열이 줄 바꿈을 포함 하는 경우를 제외 하 고 한 줄의 텍스트를 반환 합니다.  예

```fsharp
printfn "%0A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%0A" [| for i in 1 .. 5 -> "abc\ndef" |]
```

예제의

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
[|"abc
def"; "abc
def"; "abc
def"; "abc
def"; "abc
def"|]
```

4의 깊이 한도가로 표시 되는 sequence ( `IEnumerable` ) 값에 사용 됩니다 `seq { ...}` . 목록 및 배열 값에는 100의 깊이 제한이 사용 됩니다.
예를 들면 다음과 같습니다.

```fsharp
printfn "%A" (seq { for i in 1 .. 10 -> (i, i*i) })
```

예제의

```console
seq [(1, 1); (2, 4); (3, 9); (4, 16); ...]
```

블록 들여쓰기는 공용 레코드 및 공용 구조체 값의 구조에도 사용 됩니다. 예를 들면 다음과 같습니다.

```fsharp
type R = { X : int list; Y : string list }

printfn "%A" { X =  [ 1;2;3 ]; Y = ["one"; "two"; "three"] }
```

예제의

```console
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

를 사용 하는 경우에는 `%+A` 리플렉션을 사용 하 여 레코드와 공용 구조체의 전용 구조도 표시 됩니다. 예

```fsharp
type internal R =
    { X : int list; Y : string list }
    override _.ToString() = "R"

let internal data = { X = [ 1;2;3 ]; Y = ["one"; "two"; "three"] }

printfn "external view:\n%A" data

printfn "internal view:\n%+A" data

```

예제의

```console
external view:
R

internal view:
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

### <a name="large-cyclic-or-deeply-nested-values"></a>큼, 순환 또는 깊게 중첩 된 값

큰 구조화 된 값은 최대 1만의 전체 개체 노드 수로 형식이 지정 됩니다.
깊이 중첩 된 값의 형식은 100입니다.  두 경우 모두를 `...` 사용 하 여 일부 출력을 elide 합니다.  예를 들면 다음과 같습니다.

```fsharp
type Tree =
    | Tip
    | Node of Tree * Tree

let rec make n =
    if n = 0 then
        Tip
    else
        Node(Tip, make (n-1))

printfn "%A" (make 1000)
```

생략 일부를 사용 하 여 많은 출력을 생성 합니다.

```console
Node(Tip, Node(Tip, ....Node (..., ...)...))
```

주기는 개체 그래프에서 감지 되 고 `...` 사이클이 검색 된 위치에서 사용 됩니다. 예

```fsharp
type R = { mutable Links: R list }
let r = { Links = [] }
r.Links <- [r]
printfn "%A" r
```

예제의

```console
{ Links = [...] }
```

### <a name="lazy-null-and-function-values"></a>Lazy, null 및 함수 값

`Value is not created`값이 아직 계산 되지 않은 경우 지연 값은 또는 동등한 텍스트로 인쇄 됩니다.

Null 값은 `null` 값의 정적 형식이 공용 구조체 형식으로 결정 되는 경우를 제외 하 고는로 출력 됩니다 `null` . 여기서가 허용 되는 표현입니다.

F # 함수 값은 내부적으로 생성 된 클로저 이름으로 인쇄 됩니다 (예:) `<fun:it@43-7>` .

### <a name="customize-plain-text-formatting-with-structuredformatdisplay"></a>일반 텍스트 서식 지정 사용자 지정`StructuredFormatDisplay`

지정자를 사용 하는 경우 `%A` `StructuredFormatDisplay` 형식 선언에 특성이 있는지 여부를 확인 합니다.  서로게이트 텍스트와 속성을 지정 하 여 값을 표시 하는 데 사용할 수 있습니다. 예를 들면 다음과 같습니다.

```fsharp
[<StructuredFormatDisplay("Counts({Clicks})")>]
type Counts = { Clicks:int list}

printfn "%20A" {Clicks=[0..20]}
```

예제의

```console
Counts([0; 1; 2; 3;
        4; 5; 6; 7;
        8; 9; 10; 11;
        12; 13; 14;
        15; 16; 17;
        18; 19; 20])
```

### <a name="customize-plain-text-formatting-by-overriding-tostring"></a>재정의 하 여 일반 텍스트 서식 지정`ToString`

의 기본 구현은 `ToString` F # 프로그래밍에서 관찰 가능 합니다. 기본 결과는 프로그래머 지향 정보 표시 또는 사용자 출력에 사용 하기에 적합 하지 않은 경우가 많으므로 기본 구현을 재정의 하는 것이 일반적입니다.  

기본적으로 F # 레코드 및 공용 구조체 형식은를 `ToString` 사용 하는 구현을 사용 하 여의 구현을 재정의 합니다 `sprintf "%+A"` .  예를 들면 다음과 같습니다.

```fsharp
type Counts = { Clicks:int list }

printfn "%s" ({Clicks=[0..10]}.ToString())
```

예제의

```console
{ Clicks = [0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10] }
```

클래스 형식의 경우의 기본 구현을 제공 하지 `ToString` 않으며 .net 기본값을 사용 하 여 형식의 이름을 보고 합니다. 예를 들면 다음과 같습니다.

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Default structured print gives this:\n%A" data
printfn "Default ToString gives:\n%s" (data.ToString())
```

예제의

```console
Default structured print gives this:
[MyClassType; MyClassType]
Default ToString gives:
[MyClassType; MyClassType]
```

에 대 한 재정의를 추가 `ToString` 하면 서식 지정이 더 적합할 수 있습니다.

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks
   override _.ToString() = sprintf "MyClassType(%0A)" clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Now structured print gives this:\n%A" data
printfn "Now ToString gives:\n%s" (data.ToString())
```

예제의

```console
Now structured print gives this:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
Now ToString gives:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
```

## <a name="f-interactive-structured-printing"></a>F# 대화형 구조적 인쇄

F# 대화형 ( `dotnet fsi` )는 확장 된 버전의 구조적 일반 텍스트 서식을 사용 하 여 값을 보고 하 고 추가 사용자 지정 가능성를 허용 합니다. 자세한 내용은 [F# 대화형](fsharp-interactive-options.md)를 참조 하세요.

## <a name="customize-debug-displays"></a>디버그 표시 사용자 지정

.NET 용 디버거는 및와 같은 특성을 사용 `DebuggerDisplay` `DebuggerTypeProxy` 하며, 이러한 특성은 디버거 검사 창에서 개체의 구조적 표시에 영향을 줍니다.
F # 컴파일러는 구별 된 공용 구조체 및 레코드 형식에 대해 이러한 특성을 자동으로 생성 하지만 클래스, 인터페이스 또는 구조체 형식이 아닙니다.

이러한 특성은 F # 일반 텍스트 서식에서 무시 되지만 F # 형식을 디버그할 때 표시를 향상 시키기 위해 이러한 메서드를 구현 하는 것이 유용할 수 있습니다.

## <a name="see-also"></a>참조

- [문자열](strings.md)
- [레코드](records.md)
- [구별된 공용 구조체](discriminated-unions.md)
- [F# Interactive](fsharp-interactive-options.md)
