---
title: F# 코드 서식 지정 지침
description: F# 코드 서식 지정에 대한 지침을 알아봅니다.
ms.date: 11/04/2019
ms.openlocfilehash: 2086b515b8ec9b69a44e2e65ca06fb320670dff2
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81278940"
---
# <a name="f-code-formatting-guidelines"></a>F# 코드 서식 지정 지침

이 문서에서는 F# 코드가 다음과 같은지 코드를 포맷하는 방법에 대한 지침을 제공합니다.

* 일반적으로 더 읽기 쉬운 것으로 간주
* Visual Studio 및 기타 편집기의 서식 지정 도구에 의해 적용되는 규칙에 따라
* 온라인의 다른 코드와 유사

이 지침은 [안둥 판에](https://github.com/dungpa)의해 F # 서식 규칙에 대한 [포괄적 인 가이드를 기반으로합니다.](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md)

## <a name="general-rules-for-indentation"></a>들여쓰기에 대한 일반 규칙

F#은 기본적으로 상당한 공백을 사용합니다. 다음 지침은 이로 인해 부과될 수 있는 몇 가지 문제를 저글링하는 방법에 대한 지침을 제공하기 위한 것입니다.

### <a name="using-spaces"></a>공백 사용

들여쓰기가 필요한 경우 탭이 아닌 공백을 사용해야 합니다. 하나 이상의 공간이 필요합니다. 조직에서 는 코딩 표준을 만들어 들여쓰기에 사용할 공백 수를 지정할 수 있습니다. 들여쓰기가 발생하는 각 수준에서 2, 3 개 또는 4 개의 들여 쓰기 공간이 일반적입니다.

**들여쓰기당 4개의 공백을 권장합니다.**

즉, 프로그램의 들여 쓰기는 주관적인 문제입니다. 변형은 괜찮지만 따라야 할 첫 번째 규칙은 *들여쓰기의 일관성입니다.* 일반적으로 허용되는 들여쓰기 스타일을 선택하고 코드베이스 전체에서 체계적으로 사용합니다.

## <a name="formatting-white-space"></a>공백 서식 지정

F#은 공백에 민감합니다. 공백의 대부분의 의미 체계는 적절한 들여쓰기로 덮여 있지만 고려해야 할 몇 가지 다른 사항이 있습니다.

### <a name="formatting-operators-in-arithmetic-expressions"></a>산술 식에서 연산자 서식 지정

항상 이진 산술 식 주위에 공백을 사용합니다.

```fsharp
let subtractThenAdd x = x - 1 + 3
```

Unary `-` 연산자는 항상 부정하는 값이 즉시 따라야 합니다.

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

`-` 연산자 후에 공백 문자를 추가하면 다른 사람에게 혼동을 초래할 수 있습니다.

요약하자면, 항상 다음을 하는 것이 중요합니다.

* 공백으로 이진 연산자 서라운드
* 어설프게 연산자 후 후행 공백이 없는 경우

이진 산술 연산자 지침은 특히 중요합니다. 이진 `-` 연산자 를 둘러싸지 못하면 특정 서식 선택 과 결합하면 이연산자로 해석될 수 `-`있습니다.

### <a name="surround-a-custom-operator-definition-with-white-space"></a>공백으로 사용자 지정 연산자 정의 둘러싸기

항상 공백을 사용하여 연산자 정의를 둘러싸는다.

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

시작되고 `*` 두 개 이상의 문자가 있는 사용자 지정 연산자의 경우 컴파일러 모호성을 피하기 위해 정의의 시작 부분에 공백을 추가해야 합니다. 따라서 모든 연산자의 정의를 단일 공백 문자로 둘러싸는 것이 좋습니다.

### <a name="surround-function-parameter-arrows-with-white-space"></a>공백이 있는 서라운드 기능 매개변수 화살표

함수의 서명을 정의할 때 기호 주위에 `->` 공백을 사용합니다.

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a>공백이 있는 서라운드 함수 인수

함수를 정의할 때 각 인수 주위에 공백을 사용합니다.

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-very-long-member-definitions"></a>매우 긴 멤버 정의를 위해 새 줄에 매개변수 배치

멤버 정의가 매우 긴 경우 새 줄에 매개 변수를 배치하고 하나의 범위를 들여쓰기합니다.

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(
        aVeryLongType: AVeryLongTypeThatYouNeedToUse
        aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
        aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

생성자에도 적용됩니다.

```fsharp
type C(
    aVeryLongType: AVeryLongTypeThatYouNeedToUse
    aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
    aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

### <a name="type-annotations"></a>형식 주석

#### <a name="right-pad-function-argument-type-annotations"></a>오른쪽 패드 함수 인수 형식 주석

형식 주석으로 인수를 정의할 때 기호 다음 `:` 공백을 사용합니다.

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a>공백이 있는 서라운드 리턴 유형 주석

let-bound 함수 또는 값 형식 어노션(함수의 경우 반환 형식)에서 기호 `:` 앞뒤의 공백을 사용합니다.

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

* 최상위 함수와 클래스 정의를 두 개의 빈 줄로 구분합니다.
* 클래스 내의 메서드 정의는 한 줄로 구분됩니다.
* 추가 빈 줄을 (아껴서) 관련 함수 그룹을 분리하는 데 사용할 수 있습니다. 빈 줄은 관련 한 줄(예: 더미 구현 집합)간에 생략될 수 있습니다.
* 함수의 빈 줄을 아껴서 사용하여 논리 섹션을 나타냅니다.

## <a name="formatting-comments"></a>주석 서식 지정

일반적으로 ML 스타일 블록 주석보다 여러 개의 이중 슬래시 주석을 선호합니다.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

인라인 주석은 첫 번째 문자를 대문자로 대문자로 지정해야 합니다.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>명명 규칙

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>클래스 바인딩, 식 바인딩 및 패턴 바인딩 된 값 및 함수에 대 한 camelCase 사용

로컬 변수로 바인딩된 모든 이름또는 패턴 일치 및 함수 정의에 대해 camelCase를 사용하는 것이 일반적이고 허용되는 F# 스타일입니다.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

클래스의 로컬 바인딩된 함수도 camelCase를 사용해야 합니다.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a>모듈 바인딩 된 공용 기능에 대 한 낙 타 케이스를 사용 하 여

모듈 바인딩 된 함수가 공용 API의 일부인 경우 camelCase를 사용해야 합니다.

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>내부 및 개인 모듈 바인딩 값 및 함수에 camelCase 사용

다음을 포함하여 개인 모듈 바인딩 값에 camelCase를 사용합니다.

* 스크립트의 임시 함수

* 모듈 또는 형식의 내부 구현을 구성하는 값

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a>매개 변수에 낙타 케이스 사용

모든 매개 변수는 .NET 명명 규칙에 따라 camelCase를 사용해야 합니다.

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a>모듈에 파스칼 케이스 사용

모든 모듈(최상위, 내부, 개인, 중첩)은 PascalCase를 사용해야 합니다.

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a>형식 선언, 멤버 및 레이블에 PascalCase 사용

클래스, 인터페이스, 구조체, 열거형, 대리자, 레코드 및 구별된 공용 구조체는 모두 PascalCase를 사용하여 이름을 지정해야 합니다. 레코드 및 차별된 공용 구조체에 대한 형식 및 레이블 내의 멤버도 PascalCase를 사용해야 합니다.

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a>.NET에 내재된 구문에 파스칼 케이스 사용

네임스페이스, 예외, 이벤트 및`.dll` 프로젝트/이름도 PascalCase를 사용해야 합니다. 이렇게 하면 다른 .NET 언어의 소비가 소비자에게 더 자연스럽게 느껴질 뿐만 아니라 발생할 가능성이 있는 .NET 명명 규칙과도 일치합니다.

### <a name="avoid-underscores-in-names"></a>이름에 밑줄 을 피하기

역사적으로 일부 F# 라이브러리는 이름에 밑줄을 사용했습니다. 그러나 .NET 명명 규칙과 충돌하기 때문에 더 이상 널리 받아들여지지 않습니다. 즉, 일부 F# 프로그래머는 역사적 이유로 부분적으로 강조를 사용하며 관용과 존중이 중요합니다. 그러나 스타일은 종종 그것을 사용할지 여부에 대한 선택의 여지가 다른 사람에 의해 싫어한다는 것을 유의하십시오.

일부 예외에는 밑줄이 매우 일반적인 네이티브 구성 요소와의 상호 운용이 포함됩니다.

### <a name="use-standard-f-operators"></a>표준 F# 연산자 사용

다음 연산자는 F# 표준 라이브러리에 정의되어 있으며 등가물을 정의하는 대신 사용해야 합니다. 이러한 연산자는 코드를 더 읽기 쉽고 숙어적으로 만드는 경향이 있으므로 사용하는 것이 좋습니다. OCaml 또는 기타 함수형 프로그래밍 언어를 사용한 개발자는 다른 숙어에 익숙할 수 있습니다. 다음 목록에는 권장F# 연산자가 요약됩니다.

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>제네릭 ()`Foo<T>`접두사 구문 ()`T Foo`

F#은 제네릭 형식(예: `int list`)의 이름 지정후부 ML 스타일과 접두사 .NET `list<int>`스타일(예: )을 모두 상속합니다. 다음 다섯 가지 특정 유형을 제외하고 .NET 스타일을 선호합니다.

1. F# 목록의 경우 접두사 `int list` 양식을 `list<int>`사용하십시오.
2. F# 옵션의 경우 다음 값 `int option` 서식 양식을 사용하십시오. `option<int>`
3. F# 값 옵션의 경우 다음 `int voption` 값 `voption<int>`양식을 사용하십시오.
4. F# 배열의 경우 또는 `int[]` `int array` `array<int>`또는 구문 이름을 사용하십시오.
5. 참조 셀의 `int ref` 경우 `ref<int>` 또는 `Ref<int>`을 대신 사용하십시오.

다른 모든 형식의 경우 접두사 양식을 사용합니다.

## <a name="formatting-tuples"></a>tuples 서식 지정

튜플 인스턴스화는 괄호로 만들어야 하며, 내의 구분 쉼표 뒤에는 단일 공간(예: `(1, 2)`. `(x, y, z)`

일반적으로 tuples의 패턴 일치에서 괄호를 생략하는 것이 허용됩니다.

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

또한 튜플이 함수의 반환 값인 경우 괄호를 생략하는 것이 일반적으로 허용됩니다.

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

요약하면 괄호 모양의 튜플 인스턴스화를 선호하지만 패턴 일치 또는 반환 값에 튜플을 사용하는 경우 괄호를 피하는 것이 좋습니다.

## <a name="formatting-discriminated-union-declarations"></a>구별된 공용 구조체 선언 서식 지정

4 `|` 개의 공백에 의한 형식 정의의 들여쓰기:

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

## <a name="formatting-discriminated-unions"></a>구별된 공용 구조체 서식 지정

여러 줄로 분할되는 인스턴스화된 구별된 공용 구조체는 포함된 데이터를 들여쓰기와 함께 새 범위를 제공해야 합니다.

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

닫는 괄호는 새 줄에 있을 수도 있습니다.

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a>레코드 선언 서식 지정

4 `{` 개의 공백으로 형식 정의를 들여쓰기하고 동일한 줄에서 필드 목록을 시작합니다.

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

레코드에서 인터페이스 구현 또는 멤버를 선언하는 경우 새 줄에 여는 토큰과 닫는 토큰을 새 줄에 배치하는 것이 좋습니다.

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

짧은 레코드는 한 줄로 작성할 수 있습니다.

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

더 긴 레코드는 레이블에 새 줄을 사용해야 합니다.

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

다음 경우 열기 토큰을 새 줄에 배치하고 한 범위 위에 탭된 내용과 새 줄의 닫는 토큰을 배치하는 것이 좋습니다.

* 들여쓰기 범위가 다른 코드에서 레코드 이동
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

목록 및 배열 요소에도 동일한 규칙이 적용됩니다.

## <a name="formatting-copy-and-update-record-expressions"></a>복사 및 업데이트 레코드 식 서식 지정

복사 및 업데이트 레코드 표현식은 여전히 레코드이므로 유사한 지침이 적용됩니다.

짧은 표현식은 한 줄에 맞을 수 있습니다.

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

더 긴 표현식은 새 줄을 사용해야 합니다.

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

또한 레코드 지침과 마찬가지로 중괄호에 대해 별도의 줄을 전용으로 지정하고 식을 사용하여 오른쪽에 하나의 범위를 들여쓰기할 수 있습니다. 괄호 없이 선택적 값으로 값을 래핑하는 것과 같은 특별한 경우에는 한 줄에 중괄호를 유지해야 할 수 있습니다.

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

연산자 주위에 `::` 공백을 쓰기`::` `x :: l` (infix 연산자이므로 공백으로 둘러싸여 있음).

단일 줄에 선언된 목록 및 배열은 오프닝 대괄호 뒤와 닫는 대괄호 앞에 공백이 있어야 합니다.

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

항상 두 개의 서로 다른 중괄호와 같은 연산자 사이에 적어도 하나의 공간을 사용합니다. 예를 들어 `[` a와 `{`a 사이에 공백을 둡니다.

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

튜플의 목록 또는 배열에 대해동일한 지침이 적용됩니다.

여러 줄로 분할된 목록 및 배열은 레코드와 마찬가지로 다음과 같은 규칙을 따릅니다.

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

그리고 레코드와 마찬가지로 자체 줄에서 개폐 대괄호를 선언하면 코드를 이동하고 함수로 파이프를 쉽게 변환할 수 있습니다.

프로그래밍 방식으로 배열 및 목록을 생성할 `->` `do ... yield` 때 값이 항상 생성되는 경우보다 선호합니다.

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x*x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x*x ]
```

이전 버전의 F# 언어는 `yield` 데이터를 조건부로 생성할 수 있거나 평가할 연속식이 있을 수 있는 상황에서 지정해야 합니다. 이전 F# `yield` 언어 버전으로 컴파일해야 하지 않는 한 이러한 키워드를 생략하는 것이 좋습니다.

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

경우에 따라 `do...yield` 가독성에 도움이 될 수 있습니다. 이러한 경우는 주관적이지만 고려해야 합니다.

## <a name="formatting-if-expressions"></a>if 표현식서식 서식 지정

조건부 들여쓰기는 이를 구성하는 식의 크기에 따라 달라집니다. 과 `cond` `e1` `e2` 짧은 경우 한 줄에 쓰기만 하면 됩니다.

```fsharp
if cond then e1 else e2
```

의 `cond`경우 `e1` `e2` 중 하나이거나 더 길지만 다중 줄이 아닌 경우:

```fsharp
if cond
then e1
else e2
```

식 중 어느 것이 다중 줄인 경우:

```fsharp
if cond then
    e1
else
    e2
```

다음과 같은 범위에서 `else` 들여쓰기되는 여러 조건부 `elif` `if`

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>패턴 일치 구문

들여쓰기 `|` 없이 일치의 각 절에 대해 a를 사용합니다. 식이 짧은 경우 각 하위 표현식도 간단한 경우 한 줄을 사용하는 것이 좋습니다.

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

패턴 일치 화살표의 오른쪽에 있는 식이 너무 큰 경우 다음 줄로 이동하여 `match` / `|`에서 한 단계 들여쓰기합니다.

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

에서 시작하는 `function`익명 함수의 패턴 일치는 일반적으로 너무 멀리 들여쓰기해서는 안됩니다. 예를 들어 다음과 같이 한 범위를 들여쓰기하는 것은 괜찮습니다.

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

키워드를 사용하는 경우에도 `let` `function` `let rec` `let`를 시작한 후 4개의 공백으로 정의되거나 들여쓰기해야 하는 함수에서 패턴 일치:

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

화살표를 정렬하지 않는 것이 좋습니다.

## <a name="formatting-trywith-expressions"></a>시도 서식 지정/식 사용

예외 형식의 패턴 일치는 `with`와 동일한 수준에서 들여쓰기되어야 합니다.

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

## <a name="formatting-function-parameter-application"></a>함수 매개 변수 응용 프로그램 서식 지정

일반적으로 대부분의 함수 매개 변수 응용 프로그램은 동일한 줄에서 수행됩니다.

새 줄의 함수에 매개 변수를 적용하려면 매개 변수를 하나의 범위로 들여쓰기합니다.

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

람다 식에 함수 인수와 동일한 지침이 적용됩니다. 람다 식의 본문에 한 범위에 의해 들여쓰기된 다른 줄을 가질 수 있는 경우

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

그러나 lambda 식의 본문이 두 줄 이상인 경우 함수에 단일 인수로 적용된 다중 줄 구문이 아니라 별도의 함수로 팩터링하는 것이 좋습니다.

### <a name="formatting-infix-operators"></a>infix 연산자 서식 지정

연산자는 공백으로 구분합니다. 이 규칙에 대한 명백한 `!` 예외는 연산자입니다. `.`

Infix 표현식은 동일한 열에서 라인업해도 됩니다.

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>파이프라인 연산자 서식 지정

파이프라인 `|>` 연산자는 작동식 아래에 있어야 합니다.

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

### <a name="formatting-modules"></a>모듈 서식 지정

로컬 모듈의 코드는 모듈을 기준으로 들여쓰기되어야 하지만 최상위 모듈의 코드는 들여쓰기해서는 안 됩니다. 네임스페이스 요소는 들여쓰기할 필요가 없습니다.

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a*a + b*b

module A2 =
    let function2 a b = a*a - b*b
```

### <a name="formatting-object-expressions-and-interfaces"></a>개체 표현식 및 인터페이스 서식 지정

개체 표현식과 인터페이스는 4개의 공백 이후에 `member` 들여쓰기되는 것과 동일한 방식으로 정렬되어야 합니다.

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

F# 식에서 불필요한 공백을 피하십시오.

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

명명된 인수에는 `=`다음을 둘러싼 공간도 없어야 합니다.

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a>특성 서식 지정

[특성은](../language-reference/attributes.md) 구문 위에 배치됩니다.

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

### <a name="formatting-attributes-on-parameters"></a>매개 변수에 특성 서식 지정

특성은 매개 변수에 배치될 수도 있습니다. 이 경우 매개 변수와 같은 줄에 이름을 배치합니다.

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a>여러 특성 서식 지정

매개 변수가 아닌 구문에 여러 특성이 적용되면 줄당 하나의 특성이 있도록 배치해야 합니다.

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

매개 변수에 적용할 때 동일한 줄에 있어야 하며 `;` 구분 기호로 구분되어야 합니다.

## <a name="formatting-literals"></a>리터럴 서식 지정

특성을 `Literal` 사용하는 [F# 리터럴은](../language-reference/literals.md) 특성을 자체 줄에 배치하고 PascalCase 이름을 지정해야 합니다.

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

값과 동일한 줄에 특성을 배치하지 마십시오.
