---
title: F# 코드 서식 지정 지침
description: 'F # 코드의 서식을 지정 하기 위한 지침을 알아봅니다.'
ms.date: 11/04/2019
ms.openlocfilehash: fe8da6070e1c92bb5205e9cb408b8ac75372b061
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558311"
---
# <a name="f-code-formatting-guidelines"></a>F# 코드 서식 지정 지침

이 문서에서는 F # 코드가 다음과 같이 되도록 코드의 형식을 지정 하는 방법에 대 한 지침을 제공 합니다.

* 보다 읽기 쉬운
* Visual Studio 및 기타 편집기의 서식 도구에서 적용 하는 규칙에 따라
* 온라인에서 다른 코드와 유사

이러한 지침은 [Anh-Ahn-dung Phan](https://github.com/dungpa)에서 [F # 형식 지정 규칙에 대 한 포괄적인 가이드](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) 를 기반으로 합니다.

## <a name="general-rules-for-indentation"></a>들여쓰기에 대 한 일반 규칙

F #은 기본적으로 유효 공백을 사용 합니다. 다음 지침은이에서 적용할 수 있는 몇 가지 문제를 따를 하는 방법에 대 한 지침을 제공 하기 위한 것입니다.

### <a name="using-spaces"></a>공백 사용

들여쓰기가 필요한 경우 탭이 아닌 공백을 사용 해야 합니다. 공간이 하나 이상 필요 합니다. 조직에서 들여쓰기에 사용할 공백 수를 지정 하는 코딩 표준을 만들 수 있습니다. 들여쓰기가 발생 하는 각 수준에서 두 개, 세 개 또는 네 개의 들여쓰기 공간이 일반적입니다.

**들여쓰기 당 4 개의 공백을 권장 합니다.**

즉, 프로그램의 들여쓰기는 주관적인 문제입니다. 변형이 양호 하지만 따라야 하는 첫 번째 규칙은 *들여쓰기의 일관성*입니다. 일반적으로 허용 되는 들여쓰기 스타일을 선택 하 고 코드 베이스 전체에서 체계적으로 사용 합니다.

## <a name="formatting-white-space"></a>공백 서식 지정

F #은 공백으로 구분 됩니다. 공백에서 대부분의 의미 체계는 적절 한 들여쓰기가 적용 되지만 몇 가지 사항을 고려해 야 합니다.

### <a name="formatting-operators-in-arithmetic-expressions"></a>산술 식의 형식 지정 연산자

항상 이진 산술 식 주위의 공백을 사용 합니다.

```fsharp
let subtractThenAdd x = x - 1 + 3
```

단항 `-` 연산자는 부정 하는 값이 항상 뒤에와 야 합니다.

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

연산자 뒤에 공백 문자를 추가 `-` 하면 다른 사람이 혼동을 일으킬 수 있습니다.

요약 하자면, 항상 다음을 고려해 야 합니다.

* 공백을 사용 하 여 이항 연산자를 묶습니다.
* 단항 연산자 뒤에 후행 공백이 없어야 합니다.

이항 산술 연산자 지침은 특히 중요 합니다. `-`특정 형식 선택 항목과 함께 사용할 경우 이항 연산자를 감쌀 수 없으면 단항로 해석 될 수 있습니다 `-` .

### <a name="surround-a-custom-operator-definition-with-white-space"></a>공백을 사용 하 여 사용자 지정 연산자 정의 감싸기

항상 공백을 사용 하 여 연산자 정의를 둘러쌉니다.

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

로 시작 하 고 둘 이상의 문자를 포함 하는 사용자 지정 연산자의 경우 `*` 컴파일러 모호성을 방지 하기 위해 정의의 시작 부분에 공백을 추가 해야 합니다. 따라서 모든 연산자의 정의를 단일 공백 문자로 묶는 것이 좋습니다.

### <a name="surround-function-parameter-arrows-with-white-space"></a>공백을 사용 하 여 함수 매개 변수 화살표 감싸기

함수의 시그니처를 정의 하는 경우 기호 주위의 공백을 사용 합니다 `->` .

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a>공백을 사용 하 여 함수 인수를 묶습니다.

함수를 정의 하는 경우 각 인수 주위에 공백을 사용 합니다.

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-long-definitions"></a>긴 정의를 위해 새 줄에 매개 변수를 추가 합니다.

함수 정의가 매우 긴 경우 새 줄에 매개 변수를 추가 하 고 다음 매개 변수의 들여쓰기 수준에 맞게 들여씁니다.

```fsharp
module M =
    let LongFunctionWithLotsOfParameters(aVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                        (aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                        (aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                        =
        // ... the body of the method follows
```

이는 튜플을 사용 하 여 멤버, 생성자 및 매개 변수에도 적용 됩니다.

```fsharp
type TM() =
    member _.LongMethodWithLotsOfParameters(aVeryLongParam: AVeryLongTypeThatYouNeedToUse,
                                            aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse,
                                            aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method

type TC(aVeryLongCtorParam: AVeryLongTypeThatYouNeedToUse,
        aSecondVeryLongCtorParam: AVeryLongTypeThatYouNeedToUse,
        aThirdVeryLongCtorParam: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

매개 변수가 비어 있는 경우 또는 명시적 반환 형식 주석이 있으면 `=` 새 줄에 문자를 추가 하는 것이 좋습니다.

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(aVeryLongParam: AVeryLongTypeThatYouNeedToUse,
                                            aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse,
                                            aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                            : AReturnType =
        // ... the body of the method
    member _.LongMethodWithLotsOfCurrifiedParams(aVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                                (aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                                (aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                                =
        // ... the body of the method
```

이 방법으로 너무 긴 줄을 방지 하는 방법 (반환 형식에 긴 이름이 있을 수 있음) 및 매개 변수를 추가할 때 줄 손상이 줄어듭니다.

### <a name="type-annotations"></a>형식 주석

#### <a name="right-pad-function-argument-type-annotations"></a>오른쪽 패드 함수 인수 형식 주석

형식 주석을 사용 하 여 인수를 정의 하는 경우 기호 뒤에 공백을 사용 합니다 `:` .

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a>공백을 사용 하 여 반환 형식 주석 감싸기

Let 바인딩 함수 또는 값 형식 주석 (함수의 경우 반환 형식)에서 기호 앞뒤에 공백을 사용 합니다 `:` .

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a>빈 줄 서식 지정

* 두 개의 빈 줄로 최상위 함수와 클래스 정의를 구분 합니다.
* 클래스 내의 메서드 정의는 한 개의 빈 줄로 구분 됩니다.
* 별도의 빈 줄을 사용 하 여 관련 함수 그룹을 구분할 수 있습니다. 관련 된 한 줄 (예: 더미 구현 집합) 간에 빈 줄이 생략 될 수 있습니다.
* 함수에서 빈 줄을 사용 하 여 논리적 섹션을 나타낼 수 있습니다.

## <a name="formatting-comments"></a>주석 서식 지정

일반적으로 ML 스타일 블록 주석에 대해 여러 개의 이중 슬래시 주석을 사용 합니다.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

인라인 주석은 첫 문자를 대문자로 표기 해야 합니다.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>명명 규칙

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>클래스 바인딩, 식 바인딩 및 패턴 바인딩된 값과 함수에 camelCase 사용

지역 변수 또는 패턴 일치 및 함수 정의로 바인딩된 모든 이름에 camelCase를 사용 하는 것은 일반적이 고 허용 되는 F # 스타일입니다.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

클래스의 로컬 바인딩 함수는 camelCase도 사용 해야 합니다.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a>모듈 바인딩 public 함수에 camelCase 사용

모듈 바인딩 함수는 공용 API의 일부인 경우 camelCase를 사용 해야 합니다.

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>내부 및 전용 모듈 바인딩된 값 및 함수에 대해 camelCase 사용

다음을 포함 하 여 전용 모듈 바인딩 값에 camelCase를 사용 합니다.

* 스크립트의 임시 함수

* 모듈 또는 형식의 내부 구현을 구성 하는 값

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a>매개 변수에 camelCase 사용

모든 매개 변수는 .NET 명명 규칙에 따라 camelCase을 사용 해야 합니다.

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a>모듈에 대 한 고 Calcase 사용

모든 모듈 (최상위, 내부, 전용, 중첩)은가는 대/소문자를 사용 해야 합니다.

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a>형식 선언, 멤버 및 레이블에 대 한 대/소문자를 사용 합니다.

클래스, 인터페이스, 구조체, 열거형, 대리자, 레코드 및 구분 된 공용 구조체는 모두 라는 이름으로 지정 되어야 합니다. 레코드 및 구분 된 공용 구조체에 대 한 형식 및 레이블 내의 멤버는 같은 경우에도 사용 해야 합니다.

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a>.NET에 내장 되어 있는 구문에 대 한 대/소문자를 사용 합니다.

네임 스페이스, 예외, 이벤트 및 프로젝트/ `.dll` 이름에는 대/소문자를 사용 해야 합니다. 다른 .NET 언어를 사용 하 여 소비자에 게 더 자연스럽 게 사용할 수 있을 뿐만 아니라 발생할 수 있는 .NET 명명 규칙도 일치 합니다.

### <a name="avoid-underscores-in-names"></a>이름에 밑줄을 사용 하지 마십시오.

지금까지 일부 F # 라이브러리는 이름에 밑줄을 사용 했습니다. 그러나 .NET 명명 규칙과 충돌 하기 때문에이는 더 이상 광범위 하 게 허용 되지 않습니다. 즉, 일부 F # 프로그래머는 자주 사용 되는 밑줄을 사용 하 고, 일부는 기록 하기 위해 부분적으로 사용 되며, 허용 오차 및 존중은 중요 합니다 그러나 스타일을 사용할지 여부를 선택 하는 다른 사용자가 스타일을 선호 하는 경우가 많습니다.

한 가지 예외는 기본 구성 요소와의 상호 운용을 포함 하며, 여기서 밑줄은 일반적입니다.

### <a name="use-standard-f-operators"></a>표준 F # 연산자 사용

다음 연산자는 F # 표준 라이브러리에서 정의 되며, 해당 연산자를 정의 하는 대신 사용 해야 합니다. 이러한 연산자를 사용 하는 것은 코드를 더 읽기 쉽고 자연 스러운 하는 경향이 있기 때문에 권장 됩니다. OCaml 또는 기타 함수형 프로그래밍 언어의 배경이 있는 개발자는 다른 관용구에 익숙할 수 있습니다. 다음 목록에서는 권장 되는 F # 연산자를 요약 합니다.

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Discard away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>`Foo<T>`후 위 구문 ()에 대 한 기본 설정에서 제네릭 ()에 전위 구문을 사용 합니다. `T Foo`

F #은 이름 지정 제네릭 형식의 후 위 ML 스타일 (예: `int list` ) 및 접두사 .net 스타일 (예:)을 모두 상속 합니다 `list<int>` . 다음 5 가지 특정 형식을 제외 하 고 .NET 스타일을 사용 하는 것이 좋습니다.

1. F # 목록의 경우 대신 후 위 형태를 사용 `int list` `list<int>` 합니다.
2. F # 옵션의 경우 대신 후 위 형태를 사용 `int option` `option<int>` 합니다.
3. F # 값 옵션의 경우 대신 후 위 형태를 사용 `int voption` `voption<int>` 합니다.
4. F # 배열의 경우 또는 대신 구문 이름을 사용 합니다 `int[]` `int array` `array<int>` .
5. 참조 셀의 경우 또는 대신을 사용 `int ref` `ref<int>` `Ref<int>` 합니다.

다른 모든 형식의 경우 접두사 형식을 사용 합니다.

## <a name="formatting-tuples"></a>튜플 서식 지정

튜플 인스턴스화는 괄호로 묶어야 하며 그 안에 있는 구분 쉼표 뒤에는 단일 공백이와 야 합니다 (예:) `(1, 2)` `(x, y, z)` .

일반적으로 튜플의 패턴 일치에서 괄호를 생략 하는 것이 허용 됩니다.

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

튜플이 함수의 반환 값인 경우에도 일반적으로 괄호를 생략 하는 것이 허용 됩니다.

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

요약 하자면 괄호로 묶은 튜플 인스턴스화를 선호 하지만 패턴 일치 또는 반환 값에 튜플을 사용 하는 경우 괄호를 사용 하지 않는 것으로 간주 됩니다.

## <a name="formatting-discriminated-union-declarations"></a>구별 된 공용 구조체 선언 서식 지정

`|`형식 정의에서 네 개의 공백으로 들여쓰기:

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

## <a name="formatting-discriminated-unions"></a>구별 된 공용 구조체 서식 지정

여러 줄로 분할 된, 인스턴스화된 구별 된 공용 구조체는 포함 된 데이터에 들여쓰기를 사용 하 여 새 범위를 제공 해야 합니다.

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

또한 닫는 괄호는 새 줄에 있을 수 있습니다.

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a>레코드 선언 서식 지정

`{`형식 정의에서 네 개의 공백으로 들여쓰기 하 고 같은 줄에서 필드 목록을 시작 합니다.

```fsharp
// OK
type PostalAddress =
    { Address: string
      City: string
      Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address: string
    City: string
    Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Unusual in F#
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
```

레코드에서 인터페이스 구현이 나 멤버를 선언 하는 경우에는 여는 토큰을 새 줄에 배치 하 고 닫는 토큰을 새 줄에 배치 하는 것이 좋습니다.

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a>레코드 서식 지정

짧은 레코드는 한 줄로 작성 될 수 있습니다.

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

더 긴 레코드는 레이블에 새 줄을 사용 해야 합니다.

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

여는 토큰을 새 줄에 배치 하 고, 콘텐츠를 한 범위 위로 탭 하 고, 다음을 수행 하는 경우 새 줄에 닫는 토큰을 추가 하는 것이 좋습니다.

* 다른 들여쓰기 범위를 사용 하 여 코드에서 레코드 이동
* 함수에 파이핑

```fsharp
let rainbow =
    {
        Boss1 = "Jeffrey"
        Boss2 = "Jeffrey"
        Boss3 = "Jeffrey"
        Boss4 = "Jeffrey"
        Boss5 = "Jeffrey"
        Boss6 = "Jeffrey"
        Boss7 = "Jeffrey"
        Boss8 = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"]
    }

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface

let foo a =
    a
    |> Option.map (fun x ->
        {
            MyField = x
        })
```

목록 및 배열 요소에도 동일한 규칙이 적용 됩니다.

## <a name="formatting-copy-and-update-record-expressions"></a>복사 및 업데이트 레코드 식 서식 지정

복사 및 업데이트 레코드 식은 여전히 레코드 이므로 비슷한 지침이 적용 됩니다.

짧은 식은 한 줄에 맞출 수 있습니다.

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

더 긴 식은 새 줄을 사용 해야 합니다.

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = [ "Zippy"; "George"; "Bungle" ] }
```

레코드 지침과 마찬가지로 중괄호에 대 한 별도의 줄을 사용 하 고 식을 사용 하 여 하나의 범위를 오른쪽으로 들여쓸 수 있습니다. 괄호 없이 선택적으로 값을 래핑하는 것과 같은 일부 특수 한 경우에는 중괄호를 한 줄에 유지 해야 할 수 있습니다.

```fsharp
type S = { F1: int; F2: string }
type State = { F:  S option }

let state = { F = Some { F1 = 1; F2 = "Hello" } }
let newState =
    {
        state with
            F = Some {
                    F1 = 0
                    F2 = ""
                }
    }
```

## <a name="formatting-lists-and-arrays"></a>목록 및 배열 서식 지정

`x :: l`연산자 주위에 공백을 사용 하 여 씁니다 `::` `::` .는 중 위 연산자 이므로 공백으로 둘러싸여 있습니다.

한 줄에 선언 된 목록 및 배열에는 여는 대괄호 뒤와 닫는 대괄호 앞에 공백을 포함 해야 합니다.

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

두 개의 서로 다른 중괄호와 비슷한 연산자 사이에는 항상 하나 이상의 공백을 사용 합니다. 예를 들어와 사이에 공백을 둡니다 `[` `{` .

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

튜플 목록 또는 배열에도 동일한 지침이 적용 됩니다.

여러 줄에 걸쳐 분할 된 목록 및 배열은 레코드와 비슷한 규칙을 따릅니다.

```fsharp
let pascalsTriangle =
    [|
        [| 1 |]
        [| 1; 1 |]
        [| 1; 2; 1 |]
        [| 1; 3; 3; 1 |]
        [| 1; 4; 6; 4; 1 |]
        [| 1; 5; 10; 10; 5; 1 |]
        [| 1; 6; 15; 20; 15; 6; 1 |]
        [| 1; 7; 21; 35; 35; 21; 7; 1 |]
        [| 1; 8; 28; 56; 70; 56; 28; 8; 1 |]
    |]
```

레코드와 마찬가지로, 여는 대괄호와 닫는 대괄호를 자체 줄에 선언 하면 코드를 더 쉽게 이동 하 고 파이프로 파이프 합니다.

프로그래밍 방식으로 배열과 목록을 생성 하는 `->` 경우 `do ... yield` 값이 항상 생성 되는 경우를 대신 사용 합니다.

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x * x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x * x ]
```

이전 버전의 F # 언어는 `yield` 데이터가 조건부로 생성 될 수 있는 경우를 지정 해야 하며, 그렇지 않은 경우에는 계산 될 연속 식이 있을 수 있습니다. `yield`이전 F # 언어 버전으로 컴파일하지 않아야 하는 경우를 제외 하 고 이러한 키워드를 생략 하는 것이 좋습니다.

```fsharp
// Preferred
let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]

// Not preferred
let daysOfWeek' includeWeekend =
    [
        yield "Monday"
        yield "Tuesday"
        yield "Wednesday"
        yield "Thursday"
        yield "Friday"
        if includeWeekend then
            yield "Saturday"
            yield "Sunday"
    ]
```

경우에 따라에서 `do...yield` 가독성을 향상 시킬 수 있습니다. 이러한 경우에는 주관적인을 고려해 야 합니다.

## <a name="formatting-if-expressions"></a>If 식 서식 지정

조건 들여쓰기는 구성 하는 식의 크기에 따라 달라 집니다. `cond` `e1` 및 `e2` 가 짧으면 한 줄에 작성 하면 됩니다.

```fsharp
if cond then e1 else e2
```

또는 중 `cond` 하나 `e1` 이상이 `e2` 긴 하지만 여러 줄이 아닌 경우:

```fsharp
if cond
then e1
else e2
```

식이 여러 줄 인 경우:

```fsharp
if cond then
    e1
else
    e2
```

및를 사용 하는 여러 `elif` `else` 조건이와 동일한 범위에서 들여쓰기 됩니다 `if` .

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>패턴 일치 구문

`|`들여쓰기가 없는 일치 항목의 for each 절을 사용 합니다. 식이 짧으면 각 하위 식이 simple 인 경우 한 줄을 사용 하는 것을 고려할 수 있습니다.

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> x
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> x
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

패턴 일치 화살표 오른쪽의 식이 너무 크면 다음 줄로 이동 하 여에서 한 단계를 들여씁니다 `match` / `|` .

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

에서 시작 하는 익명 함수의 패턴 일치는 `function` 일반적으로 너무 멀리 들여쓰기 되지 않아야 합니다. 예를 들어 다음과 같이 한 범위를 들여쓰는 것은 괜찮습니다.

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

키워드를 사용 하는 경우에도 또는에서 정의한 함수의 패턴 일치는 `let` `let rec` 를 시작한 후 4 개의 공백으로 들여쓰기 되어야 합니다 `let` `function` .

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

화살표를 정렬 하지 않는 것이 좋습니다.

## <a name="formatting-trywith-expressions"></a>Try/with 식 서식 지정

예외 형식에 대 한 패턴 일치는와 동일한 수준으로 들여쓰기 되어야 합니다 `with` .

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a>형식 지정 함수 매개 변수 응용 프로그램

일반적으로 대부분의 함수 매개 변수 응용 프로그램은 같은 줄에서 수행 됩니다.

새 줄에 함수에 대 한 매개 변수를 적용 하려는 경우 한 범위 만큼 들여씁니다.

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

람다 식에 대 한 동일한 지침이 함수 인수로 적용 됩니다. 람다 식의 본문 인 경우 본문은 한 범위로 들여쓰기 된 다른 줄을 포함할 수 있습니다.

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem -> printfn "%d" (a + elem))
        list1

// OK if lambda body is long enough
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn "%d" (a + elem))
        list1
```

그러나 람다 식의 본문이 두 줄 이상인 경우에는 함수에 단일 인수로 적용 되는 여러 줄 구문을 포함 하지 않고 별도의 함수로 팩터링 하는 것이 좋습니다.

### <a name="formatting-infix-operators"></a>중 위 연산자 서식 지정

연산자를 공백으로 구분 합니다. 이 규칙에 대 한 명백한 예외는 `!` 및 `.` 연산자입니다.

중 위 식은 동일한 열의 목록에 대해 확인 됩니다.

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>파이프라인 연산자 서식 지정

파이프라인 `|>` 연산자는 작동 하는 식 아래로 이동 해야 합니다.

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a>서식 모듈

로컬 모듈의 코드는 모듈을 기준으로 들여쓰기 되어야 하지만 최상위 모듈의 코드는 들여쓰지 않아야 합니다. 네임 스페이스 요소를 들여쓸 필요가 없습니다.

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a * a + b * b

module A2 =
    let function2 a b = a * a - b * b
```

### <a name="formatting-object-expressions-and-interfaces"></a>개체 식 및 인터페이스 서식 지정

개체 식과 인터페이스는 `member` 네 개의 공간 이후에 들여쓰는 것과 같은 방식으로 정렬 되어야 합니다.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a>식의 공백 서식 지정

F # 식에 불필요 한 공백을 사용 하지 마십시오.

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

명명 된 인수에는를 둘러싼 공간이 없어야 합니다 `=` .

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a>서식 특성

[특성](../language-reference/attributes.md) 은 구문 위에 배치 됩니다.

```fsharp
[<SomeAttribute>]
type MyClass() = ...

[<RequireQualifiedAccess>]
module M =
    let f x = x

[<Struct>]
type MyRecord =
    { Label1: int
      Label2: string }
```

### <a name="formatting-attributes-on-parameters"></a>매개 변수의 특성 서식 지정

특성은 매개 변수에도 배치할 수 있습니다. 이 경우 매개 변수와 같은 줄에, 이름 앞에를 놓습니다.

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a>여러 특성 서식 지정

매개 변수가 아닌 구문에 여러 특성을 적용 하는 경우에는 줄 마다 하나의 특성이 있도록 배치 되어야 합니다.

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

매개 변수에 적용 되는 경우 동일한 줄에 있고 구분 기호로 구분 되어야 합니다 `;` .

## <a name="formatting-literals"></a>리터럴 서식 지정

특성을 사용 하는 [F # 리터럴은](../language-reference/literals.md) 해당 `Literal` 줄에 특성을 추가 하 고, 다음을 사용 하 여 대/소문자 이름을 사용 해야 합니다.

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

특성을 값과 같은 줄에 배치 하지 마십시오.
