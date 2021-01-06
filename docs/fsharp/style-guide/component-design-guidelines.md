---
title: F# 구성 요소 디자인 지침
description: '다른 호출자가 사용 하기 위한 F # 구성 요소를 작성 하기 위한 지침에 대해 알아봅니다.'
ms.date: 05/14/2018
ms.openlocfilehash: 24be2a422c97b9334f749e3d9dfcccd0feec219b
ms.sourcegitcommit: e395fabeeea5c705d243d246fa64446839ac85b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2021
ms.locfileid: "97856109"
---
# <a name="f-component-design-guidelines"></a>F# 구성 요소 디자인 지침

이 문서는 f # 구성 요소 디자인 지침, v14, Microsoft Research 및 F # Software Foundation에서 원래 큐 레이트 및 유지 관리 된 버전을 기반으로 하는 F # 프로그래밍에 대 한 구성 요소 디자인 지침의 집합입니다.

이 문서에서는 F # 프로그래밍에 대해 잘 알고 있다고 가정 합니다. 이 가이드의 다양 한 버전에 대 한 유용한 피드백 및 유용한 피드백을 위해 F # 커뮤니티에 감사 드립니다.

## <a name="overview"></a>개요

이 문서에서는 F # 구성 요소 디자인 및 코딩 관련 문제 중 일부를 살펴봅니다. 구성 요소는 다음 중 하나를 의미할 수 있습니다.

* 해당 프로젝트 내에 외부 소비자가 있는 F # 프로젝트의 계층입니다.
* 어셈블리 경계에서 F # 코드를 사용 하기 위한 라이브러리입니다.
* 어셈블리 경계 전체에서 .NET 언어를 사용 하기 위한 라이브러리입니다.
* [NuGet](https://nuget.org)과 같은 패키지 리포지토리를 통해 배포 하기 위한 라이브러리입니다.

이 문서에서 설명 하는 기술은 [좋은 F # 코드의 5 가지 원칙](index.md#five-principles-of-good-f-code)을 따르고 기능 및 개체 프로그래밍을 모두 적절 하 게 활용 합니다.

방법론에 관계 없이 구성 요소 및 라이브러리 디자이너는 개발자가 가장 쉽게 사용할 수 있는 API를 작성 하려고 할 때 많은 실용적이 고 prosaic 문제가 발생 합니다. [.Net 라이브러리 디자인 지침](../../standard/design-guidelines/index.md) 의 Conscientious 응용 프로그램은 사용이 편리한 일관 된 api 집합을 만드는 과정을 안내 합니다.

## <a name="general-guidelines"></a>일반 지침

라이브러리에 대 한 의도 된 대상에 관계 없이 F # 라이브러리에 적용 되는 몇 가지 범용 지침이 있습니다.

### <a name="learn-the-net-library-design-guidelines"></a>.NET 라이브러리 디자인 지침 알아보기

수행 중인 F # 코딩의 종류에 관계 없이 [.Net 라이브러리 디자인 지침](../../standard/design-guidelines/index.md)에 대 한 실무 지식을 보유 하는 것이 중요 합니다. 대부분의 다른 F # 및 .NET 프로그래머는 이러한 지침에 익숙하고 .NET 코드가 이러한 지침을 준수 하는 것으로 간주 합니다.

.NET 라이브러리 디자인 지침은 이름 지정, 클래스 및 인터페이스 디자인, 멤버 디자인 (속성, 메서드, 이벤트 등) 등을 위한 일반적인 지침을 제공 하며, 다양 한 디자인 지침에 대 한 첫 번째 참조 지점입니다.

### <a name="add-xml-documentation-comments-to-your-code"></a>코드에 XML 문서 주석 추가

공용 Api에 대 한 XML 문서를 통해 사용자는 이러한 형식과 멤버를 사용할 때 뛰어난 Intellisense 및 Quickinfo을 얻을 수 있으며 라이브러리의 문서 파일을 빌드할 수 있습니다. Xmldoc 주석의 주석 내에서 추가 태그에 사용할 수 있는 다양 한 xml 태그에 대 한 [Xml 문서](../language-reference/xml-documentation.md) 를 참조 하세요.

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo: otherPoint:Point -> float
```

약식 XML 주석 ( `/// comment` ) 또는 표준 xml 주석 () 중 하나를 사용할 수 있습니다 `///<summary>comment</summary>` .

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a>안정적인 라이브러리 및 구성 요소 Api에 대 한 명시적 서명 파일 (. fsi.exe)을 사용 하는 것이 좋습니다.

F # 라이브러리의 명시적 서명 파일을 사용 하면 공용 API에 대 한 간결한 요약을 제공 하 여 라이브러리의 전체 공개 화면을 파악 하 고 공용 설명서와 내부 구현 세부 정보를 명확 하 게 구분할 수 있습니다. 서명 파일은 구현 및 서명 파일에서 변경 내용을 적용 하도록 요구 하 여 공용 API를 변경 하는 것을 추가 합니다. 따라서 일반적으로 API가 solidified 되 고 더 이상 변경 될 것으로 예상 되지 않는 경우에만 서명 파일이 도입 되어야 합니다.

### <a name="always-follow-best-practices-for-using-strings-in-net"></a>.NET에서 문자열 사용에 대 한 모범 사례 항상 따르기

[.Net 지침에서 문자열 사용에 대 한 모범 사례](../../standard/base-types/best-practices-strings.md) 를 따릅니다. 특히 문자열 (해당 하는 경우)의 변환과 비교 시 항상 *문화권* 을 명시적으로 명시 합니다.

## <a name="guidelines-for-f-facing-libraries"></a>F # 연결 라이브러리에 대 한 지침

이 섹션에서는 공용 F # 연결 라이브러리를 개발 하기 위한 권장 사항을 제공 합니다. 즉, F # 개발자가 사용 하기 위한 공용 Api를 노출 하는 라이브러리입니다. F #에 적용할 수 있는 다양 한 라이브러리 디자인 권장 사항이 있습니다. 다음에 나오는 특정 권장 사항이 없으면 .NET 라이브러리 디자인 지침을 대체 지침으로 사용할 수 있습니다.

### <a name="naming-conventions"></a>명명 규칙

#### <a name="use-net-naming-and-capitalization-conventions"></a>.NET 명명 및 대문자화 규칙 사용

다음 표에서는 .NET 명명 및 대문자화 규칙을 따릅니다. F # 구문을 포함 하는 데에는 약간의 추가 항목이 있습니다.

| 구문 | 사례 | 파트 | 예 | 메모 |
|-----------|------|------|----------|-------|
| 구체적 형식 | PascalCase | 명사/형용사 | 목록, Double, 복합 | 구체적 형식은 구조체, 클래스, 열거형, 대리자, 레코드 및 공용 구조체입니다. 형식 이름은 일반적으로 OCaml에서 소문자 이지만 F #은 형식에 대 한 .NET 명명 스키마를 채택 했습니다.
| DLL           | PascalCase |                 | Fabrikam.Core.dll |  |
| 공용 구조체 태그     | PascalCase | 명사 | 일부, 추가, 성공 | 공용 Api에는 접두사를 사용 하지 마십시오. 필요에 따라 internal 인 경우 접두사를 사용 합니다 (예:). `type Teams = TAlpha | TBeta | TDelta.` |
| 이벤트          | PascalCase | 동사 | ValueChanged/ValueChanging |  |
| 예외     | PascalCase |      | WebException | 이름은 "Exception"으로 끝나야 합니다. |
| 필드          | PascalCase | 명사 | CurrentName  | |
| 인터페이스 형식 |  PascalCase | 명사/형용사 | IDisposable | 이름은 "I"로 시작 해야 합니다. |
| 메서드 |  PascalCase |  동사 | ToString | |
| 네임스페이스 | PascalCase | | Fsharp.core | 일반적으로는 `<Organization>.<Technology>[.<Subnamespace>]` 기술이 조직과 독립적인 경우 조직을 삭제 하지만는 사용 하지 않습니다. |
| 매개 변수 | camelCase | 명사 |  typeName, transform, range | |
| 값 허용 (내부) | camelCase 또는-Calcase | 명사/동사 |  getValue, myTable |
| 값 허용 (외부) | camelCase 또는-Calcase | 명사/동사  | 목록. 지도, 날짜. 오늘 | let 바인딩 값은 일반적인 기능 디자인 패턴을 수행 하는 경우 일반적으로 public입니다. 그러나는 다른 .NET 언어에서 식별자를 사용할 수 있는 경우 일반적으로가와 같은 경우를 사용 합니다. |
| 속성  | PascalCase  | 명사/형용사  | IsEndOfFile, 배경색  | 일반적으로 사용 되는 부울 속성은 IsNotEndOfFile가 아니라 IsEndOfFile에서와 같이 찬성 수 있습니다.

#### <a name="avoid-abbreviations"></a>약어 사용 안 합니다.

.NET 지침은 약어를 사용 하지 않습니다 (예: "이 아닌 사용 `OnButtonClick` `OnBtnClick` "). "비동기"와 같은 일반적인 약어를 `Async` 사용할 수 있습니다. 이 지침은 종종 함수형 프로그래밍에 대해 무시 됩니다. 예를 들어는 `List.iter` "반복"에 약어를 사용 합니다. 이러한 이유로, 약어를 사용 하는 것은 F #-F # 프로그래밍에서 더 높은 수준으로 허용 되지만 일반적으로 공용 구성 요소 디자인에서는 사용 하지 않는 것이 좋습니다.

#### <a name="avoid-casing-name-collisions"></a>대/소문자 이름 충돌 방지

일부 클라이언트 언어 (예: Visual Basic)는 대/소문자를 구분 하지 않으므로 .NET 지침에서는 이름 충돌을 명확 하 게 구분 하는 데 대/소문자만 사용할 수 있습니다.

#### <a name="use-acronyms-where-appropriate"></a>적절 한 경우 머리글자어 사용

XML과 같은 머리글자어는 약어가 아니며 Xml (uncapitalized form)의 .NET 라이브러리에서 널리 사용 됩니다. 잘 알려진 널리 알려진 머리글자어만 사용 해야 합니다.

#### <a name="use-pascalcase-for-generic-parameter-names"></a>제네릭 매개 변수 이름에 대 한 대/소문자를 사용 합니다.

F # 연결 라이브러리를 비롯 하 여 공용 Api에서 제네릭 매개 변수 이름에 대해 대/소문자를 사용 합니다. 특히,,, `T` 임의의 제네릭 매개 변수에 대해,,와 같은 이름을 사용 하 `U` `T1` `T2` 고 특정 이름이 적합 한 경우 F # 연결 라이브러리에 대해,,와 같은 이름을 사용 `Key` `Value` `Arg` 합니다. 예를 들어는 그렇지 않습니다 `TKey` .

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a>F # 모듈에서 public 함수 및 값에 대해 camelCase를 사용 합니다.

camelCase는 정규화 되지 않은 (예: `invalidArg` )와 "표준 컬렉션 함수" (예: .map)에 대해 사용 하도록 디자인 된 공용 함수에 사용 됩니다. 이러한 두 경우 모두 함수 이름은 언어의 키워드와 매우 유사 하 게 작동 합니다.

### <a name="object-type-and-module-design"></a>개체, 형식 및 모듈 디자인

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a>네임 스페이스 또는 모듈을 사용 하 여 형식 및 모듈 포함

구성 요소의 각 F # 파일은 네임 스페이스 선언 또는 모듈 선언으로 시작 해야 합니다.

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

또는

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

모듈 및 네임 스페이스를 사용 하 여 최상위 수준에서 코드를 구성 하는 경우의 차이점은 다음과 같습니다.

* 네임 스페이스는 여러 파일에 걸쳐 있을 수 있습니다.
* 네임 스페이스는 내부 모듈 내에 있지 않은 경우 F # 함수를 포함할 수 없습니다.
* 지정 된 모듈의 코드는 단일 파일 내에 포함 되어야 합니다.
* 최상위 모듈은 내부 모듈이 없어도 F # 함수를 포함할 수 있습니다.

최상위 네임 스페이스 또는 모듈 중에서 선택한 항목은 컴파일된 코드 형식에 영향을 주므로 다른 .NET 언어의 뷰에 영향을 줍니다. 그러면 API가 F # 코드 외부에서 사용 됩니다.

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a>개체 형식에 대 한 기본 작업에 대 한 메서드 및 속성 사용

개체를 사용할 때 사용할 수 있는 기능이 해당 형식에 대 한 메서드 및 속성으로 구현 되는지 확인 하는 것이 가장 좋습니다.

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

지정 된 멤버에 대 한 대부분의 기능은 반드시 해당 멤버에 구현 해야 하는 것은 아니지만 해당 기능을 사용할 수 있는 부분은 여야 합니다.

#### <a name="use-classes-to-encapsulate-mutable-state"></a>클래스를 사용 하 여 변경 가능한 상태 캡슐화

F #에서는 클로저, 시퀀스 식 또는 비동기 계산과 같은 다른 언어 구문으로 해당 상태가 아직 캡슐화 되지 않은 경우에만이 작업을 수행 해야 합니다.

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a>인터페이스를 사용 하 여 관련 작업 그룹화

인터페이스 형식을 사용 하 여 일련의 작업을 나타냅니다. 함수 튜플 또는 함수 레코드와 같은 다른 옵션에는이 방법이 선호 됩니다.

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

기본 설정:

```fsharp
type Serializer<'T> = {
    Serialize: bool -> 'T -> string
    Deserialize: bool -> string -> 'T
}
```

인터페이스는 일반적으로 함수에서 제공 하는 기능을 얻기 위해 사용할 수 있는 .NET의 최고 수준의 개념입니다. 또한 함수 레코드를 사용 하 여 존재 형식을 프로그램으로 인코딩할 수 없습니다.

#### <a name="use-a-module-to-group-functions-that-act-on-collections"></a>모듈을 사용 하 여 컬렉션에 대해 작동 하는 함수 그룹화

컬렉션 형식을 정의할 때 `CollectionType.map` `CollectionType.iter` 새 컬렉션 형식에 대해 및와 같은 표준 작업 집합을 제공 하는 것이 좋습니다.

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

이러한 모듈을 포함 하는 경우 Fsharp.core에 있는 함수에 대 한 표준 명명 규칙을 따르세요.

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a>모듈을 사용 하 여 일반적인 정식 함수에 대 한 함수를 그룹화 합니다. 특히 수학 및 DSL 라이브러리에서 사용할 수 있습니다.

예를 들어 `Microsoft.FSharp.Core.Operators` 는 `abs` FSharp.Core.dll에서 제공 하는 자동으로 열린 최상위 함수 (예: 및)의 컬렉션입니다 `sin` .

마찬가지로, 통계 라이브러리에는 함수 및가 포함 된 모듈이 포함 될 수 있습니다 `erf` `erfc` . 여기서이 모듈은 명시적 또는 자동으로 열립니다.

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a>RequireQualifiedAccess 사용을 고려 하 고 AutoOpen 특성을 신중 하 게 적용 합니다.

모듈에 특성을 추가 하면 모듈이 `[<RequireQualifiedAccess>]` 열리지 않을 수 있으며 모듈의 요소에 대 한 참조에 명시적으로 정규화 된 액세스가 필요 함을 나타냅니다. 예를 들어 `Microsoft.FSharp.Collections.List` 모듈에이 특성이 있습니다.

이는 모듈의 함수 및 값에 다른 모듈의 이름과 충돌할 가능성이 있는 이름이 있는 경우에 유용 합니다. 정규화 된 액세스를 요구 하면 라이브러리의 장기 유지 관리 및 진화 크게 증가 합니다.

특성을 `[<AutoOpen>]` 모듈에 추가 하면 포함 하는 네임 스페이스를 열 때 모듈이 열립니다. 어셈블리 `[<AutoOpen>]` 에 특성을 적용 하 여 어셈블리를 참조할 때 자동으로 열리는 모듈을 나타낼 수도 있습니다.

예를 들어, 통계 라이브러리 **MathsHeaven** 에는 포함 하는 `module MathsHeaven.Statistics.Operators` 함수 `erf` 및가 포함 될 수 있습니다. `erfc` 이 모듈을로 표시 하는 것이 합리적입니다 `[<AutoOpen>]` . 즉, `open MathsHeaven.Statistics` 이 모듈을 열고 이름과 범위를 가져옵니다 `erf` `erfc` . 의 또 다른 용도 `[<AutoOpen>]` 는 확장 메서드를 포함 하는 모듈에 대 한 것입니다.

를 과도 `[<AutoOpen>]` 하 게 사용 하면 충돌 하는 네임 스페이스로 이어질 수 있으며 특성은 주의 해 서 사용 해야 합니다. 특정 도메인의 특정 라이브러리에 대해를 적절히 사용 하면 `[<AutoOpen>]` 유용성이 향상 될 수 있습니다.

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a>잘 알려진 연산자를 사용 하는 경우 클래스에서 연산자 멤버를 정의 하는 것이 좋습니다.

때로는 클래스를 사용 하 여 벡터와 같은 수학적 구문을 모델링할 수 있습니다. 모델링 되는 도메인에 잘 알려진 연산자가 있는 경우 클래스의 내장 멤버로 정의 하는 것이 좋습니다.

```fsharp
type Vector(x: float) =

    member v.X = x

    static member (*) (vector: Vector, scalar: float) = Vector(vector.X * scalar)

    static member (+) (vector1: Vector, vector2: Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

이 지침은 이러한 유형에 대 한 일반 .NET 지침에 해당 합니다. 그러나 F # 코딩에서는 이러한 형식을 F # 함수 및 멤버 제약 조건이 있는 메서드 (예: sumBy)와 함께 사용할 수 있기 때문에이를 추가로 중요할 수 있습니다.

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a>CompiledName를 사용 하 여를 제공 하는 것이 좋습니다. 다른 .NET 언어 소비자의 순 이름

경우에 따라 F # 소비자에 대해 한 가지 스타일로 이름을 바꿀 수 있습니다. 예를 들어 소문자가 모듈 바인딩 함수인 것 처럼 표시 되도록 하는 경우에는이 클래스를 어셈블리에 컴파일할 때 이름에 대 한 다른 스타일을 사용할 수 있습니다. 특성을 사용 `[<CompiledName>]` 하 여 어셈블리를 사용 하는 F # 코드가 아닌 다른 스타일을 제공할 수 있습니다.

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

를 사용 하면 `[<CompiledName>]` 어셈블리의 비 F # 소비자에 대해 .net 명명 규칙을 사용할 수 있습니다.

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a>멤버 함수에 대 한 메서드 오버 로드를 사용 합니다 .이 경우 더 간단한 API를 제공 합니다.

메서드 오버 로드는 다른 옵션 또는 인수를 사용 하 여 유사한 기능을 수행 해야 할 수 있는 API를 단순화 하는 강력한 도구입니다.

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

F #에서는 인수 형식이 아닌 인수 수에 대 한 오버 로드에 더 일반적입니다.

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a>이러한 형식의 디자인이 개선 될 가능성이 있는 경우 record 및 union 형식의 표현을 숨깁니다.

개체의 구체적인 표현은 노출 하지 마십시오. 예를 들어, 값의 구체적인 표현은 <xref:System.DateTime> .net 라이브러리 디자인의 외부 공용 API에 의해 노출 되지 않습니다. 런타임에 공용 언어 런타임은 실행 전체에서 사용 되는 커밋된 구현을 알고 있습니다. 그러나 컴파일된 코드 자체가 구체적 표현에 대 한 종속성을 선택 하는 것은 아닙니다.

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a>확장성을 위한 구현 상속 사용 방지

F #에서 구현 상속은 거의 사용 되지 않습니다. 또한 상속 계층 구조는 복잡 하 고 새로운 요구 사항이 도착할 때 변경 하기 어렵습니다. 상속 구현은 여전히 F #에서 문제에 대 한 최상의 솔루션인 경우 이지만, 인터페이스 구현과 같이 다형성을 디자인할 때 F # 프로그램에서 대체 기술을 찾아야 합니다.

### <a name="function-and-member-signatures"></a>함수 및 멤버 시그니처

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a>여러 개의 관련 없는 값을 반환 하는 경우 반환 값에 튜플 사용

반환 형식에서 튜플을 사용 하는 좋은 예는 다음과 같습니다.

```fsharp
val divrem: BigInteger -> BigInteger -> BigInteger * BigInteger
```

많은 구성 요소를 포함 하는 반환 형식 또는 구성 요소가 식별 가능한 단일 엔터티와 관련 된 경우 튜플 대신 명명 된 형식을 사용 하는 것이 좋습니다.

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a>`Async<T>`F # API 경계에서 비동기 프로그래밍에 사용

을 반환 하는 라는 해당 동기 작업이 있는 경우 비동기 작업은를 반환 하거나를 반환 하면 `Operation` `T` 이름을 지정 해야 합니다 `AsyncOperation` `Async<T>` `OperationAsync` `Task<T>` . Begin/End 메서드를 노출 하는 일반적으로 사용 되는 .NET 형식의 경우를 사용 하 여 `Async.FromBeginEnd` 확장 메서드를 외관으로 작성 하 여 해당 .Net api에 F # 비동기 프로그래밍 모델을 제공 하는 것이 좋습니다.

```fsharp
type SomeType =
    member this.Compute(x:int): int =
        ...
    member this.AsyncCompute(x:int): Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a>예외

예외, 결과 및 옵션의 적절 한 사용에 대 한 자세한 내용은 [오류 관리](conventions.md#error-management) 를 참조 하세요.

### <a name="extension-members"></a>확장 멤버

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a>F #-F # 구성 요소에서 F # 확장 멤버를 신중 하 게 적용

F # 확장 멤버는 일반적으로 대부분의 사용 모드에서 형식과 연결 된 내장 작업을 종료 하는 작업에만 사용 해야 합니다. 일반적인 한 가지 용도는 다양 한 .NET 형식의 F #에 더 자연 스러운 Api를 제공 하는 것입니다.

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a>공용 구조체 형식

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a>트리 구조 데이터에 대 한 클래스 계층 구조 대신 구별 된 공용 구조체 사용

트리 형태의 구조는 재귀적으로 정의 됩니다. 이는 상속에는 적합 하지 않지만 구별 된 공용 구조체에는 세련 된 방법입니다.

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

구별 된 공용 구조체를 사용 하 여 트리 형태의 데이터를 표시 하면 패턴 일치에 exhaustiveness의 이점을 누릴 수 있습니다.

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a>`[<RequireQualifiedAccess>]`대/소문자 이름이 충분히 고유 하지 않은 공용 구조체 형식에 사용

동일한 이름이 구별 된 공용 구조체 케이스와 같은 다른 항목에 대 한 최상의 이름인 도메인에서 사용자를 찾을 수 있습니다. 를 사용 하 여 `[<RequireQualifiedAccess>]` 문의 순서에 따라 발생 하는 섀도잉으로 인 한 혼동을 방지 하기 위해를 사용 하 여 대/소문자 이름을 구분할 수 있습니다. `open`

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a>이러한 형식의 디자인이 개선 될 가능성이 있는 경우 이진 호환 Api에 대 한 구별 된 공용 구조체의 표현을 숨깁니다.

공용 구조체 형식은 간결한 프로그래밍 모델에 대 한 F # 패턴 일치 형식을 사용 합니다. 앞에서 설명한 것 처럼 이러한 형식의 디자인이 발전 될 가능성이 있는 경우 구체적인 데이터 표현을 노출 하지 않아야 합니다.

예를 들어, private 또는 internal 선언을 사용 하거나 서명 파일을 사용 하 여 구별 된 공용 구조체의 표현을 숨길 수 있습니다.

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

구별 된 공용 구조체 무제한 증가할을 표시 하는 경우 사용자 코드를 손상 시 키 지 않고 라이브러리의 버전을 확인 하는 것이 어려울 수 있습니다. 대신, 형식의 값에 대 한 패턴 일치를 허용 하는 하나 이상의 활성 패턴을 노출 하는 것이 좋습니다.

활성 패턴은 F # 공용 구조체 형식을 직접 노출 하지 않고 F # 소비자에 게 패턴 일치를 제공 하는 대체 방법을 제공 합니다.

### <a name="inline-functions-and-member-constraints"></a>인라인 함수 및 멤버 제약 조건

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a>암시적 멤버 제약 조건 및 정적으로 확인 된 제네릭 형식으로 인라인 함수를 사용 하 여 제네릭 숫자 알고리즘 정의

산술 멤버 제약 조건 및 F # 비교 제약 조건은 F # 프로그래밍에 대 한 표준입니다. 예를 들어, 다음 코드를 고려하세요.

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

이 함수의 형식은 다음과 같습니다.

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

이는 수학적 라이브러리의 공용 API에 적합 한 함수입니다.

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a>멤버 제약 조건을 사용 하 여 형식 클래스 및 오리 형식화를 시뮬레이션 하지 않습니다.

F # 멤버 제약 조건을 사용 하 여 "오리 입력"을 시뮬레이션할 수 있습니다. 그러나이를 사용 하는 멤버는 일반적으로 F #-F # 라이브러리 디자인에서 사용 하면 안 됩니다. 이는 익숙하지 않은 암시적 또는 비표준 암시적 제약 조건을 기반으로 하는 라이브러리 디자인이 사용자 코드를 특정 한 프레임 워크 패턴에 연결 하는 경향이 있기 때문입니다.

또한 이러한 방식으로 멤버 제약 조건을 많이 사용 하면 컴파일 시간이 길어질 수 있습니다.

### <a name="operator-definitions"></a>연산자 정의

#### <a name="avoid-defining-custom-symbolic-operators"></a>사용자 지정 기호화 된 연산자 정의 방지

사용자 지정 연산자는 일부 상황에서 필수적 이며, 구현 코드의 큰 본문 내에서 매우 유용한 표기법 밑수 장치입니다. 라이브러리의 새 사용자의 경우 명명 된 함수를 사용 하는 것이 더 쉽습니다. 또한 사용자 지정 기호화 된 연산자는 문서화 하기 어려울 수 있으며, 사용자는 IDE와 검색 엔진의 기존 제한 사항으로 인해 운영자에 대 한 도움말을 조회 하는 것이 더 어려워집니다.

따라서 기능을 명명 된 함수 및 멤버와 함께 게시 하는 것이 가장 좋지만,이 기능에 대 한 표기법 밑수 혜택을 통해 설명서 및 인식 비용 보다 더 큰 경우에만이 기능에 대 한 연산자를 추가로 제공 합니다.

### <a name="units-of-measure"></a>측정 단위

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a>F # 코드에서 추가 형식 안전을 위해 측정 단위를 신중히 사용

측정 단위에 대 한 추가 정보 입력 정보는 다른 .NET 언어에서 볼 때 지워집니다. .NET 구성 요소, 도구 및 리플렉션에서는 형식-san을 볼 수 있습니다. 예를 들어 c # 소비자는가 아닌를 표시 합니다 `float` `float<kg>` .

### <a name="type-abbreviations"></a>형식 약어

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a>신중 하 게 형식 약어를 사용 하 여 F # 코드 간소화

.NET 구성 요소, 도구 및 리플렉션에서는 형식에 대 한 약식 이름이 표시 되지 않습니다. 형식 약어의 중요 한 사용으로 인해 실제로는 도메인 보다 더 복잡 하 게 표시 되어 소비자를 혼동할 수 있습니다.

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a>해당 멤버 및 속성이 약식으로 사용 가능한 형식에 대해 사용 가능한 멤버와 속성이 본질적으로 다른 공용 형식에 대 한 형식 약어를 사용 하지 않습니다.

이 경우 약식으로 표시 되는 형식은 정의할 실제 형식의 표현에 대해 너무 많이 표시 됩니다. 대신 클래스 형식 또는 단일 대/소문자 구분 된 공용 구조체에 약어를 래핑하는 것이 좋습니다. 또는 성능이 중요 한 경우에는 구조체 형식을 사용 하 여 약어를 래핑하는 것이 좋습니다.

예를 들어 F # 맵의 특수 한 경우에 다중 맵을 정의 하는 것이 좋습니다. 예를 들면 다음과 같습니다.

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

그러나이 형식에 대 한 논리 점 표기법 연산은 맵의 작업과 동일 하지 않습니다. 예를 들어 조회 연산자가 매핑됩니다. [key] 키가 사전에 없는 경우 예외를 발생 시 키 지 않고 빈 목록을 반환 합니다.

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a>다른 .NET 언어에서 사용 하는 라이브러리에 대 한 지침

다른 .NET 언어에서 사용할 라이브러리를 디자인할 때는 [.Net 라이브러리 디자인 지침](../../standard/design-guidelines/index.md)을 준수 해야 합니다. 이 문서에서 이러한 라이브러리는 제한 없이 F # 구문을 사용 하는 F # 연결 라이브러리와는 달리 바닐라 .NET 라이브러리로 레이블이 지정 됩니다. 바닐라 .NET 라이브러리 디자인은 공용 API에서 F # 관련 구문의 사용을 최소화 하 여 친숙 하 고 자연 스러운 Api를 나머지 .NET Framework와 일치 하는 것을 의미 합니다. 규칙은 다음 섹션에 설명 되어 있습니다.

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a>네임 스페이스 및 형식 디자인 (다른 .NET 언어에서 사용 하는 라이브러리의 경우)

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a>구성 요소의 공용 API에 .NET 명명 규칙을 적용 합니다.

약식 이름 및 .NET 대문자화 지침 사용에 특히 주의 해야 합니다.

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a>네임 스페이스, 형식 및 멤버를 구성 요소의 기본 조직 구조로 사용

Public 기능을 포함 하는 모든 파일은 선언으로 시작 해야 `namespace` 하며 네임 스페이스의 공용 엔터티는 형식 이어야 합니다. F # 모듈은 사용 하지 마십시오.

공용이 아닌 모듈을 사용 하 여 구현 코드, 유틸리티 형식 및 유틸리티 함수를 저장 합니다.

정적 형식은 F # 모듈 내에서 사용할 수 없는 오버 로드 및 기타 .NET API 디자인 개념을 사용 하기 위해 나중에 API를 발전 시킬 수 있으므로 모듈 보다 우선적으로 사용 해야 합니다.

예를 들어 다음과 같은 공용 API 대신

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

대신 다음을 고려 하십시오.

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a>형식의 디자인이 진화 하지 않는 경우 바닐라 .NET Api에서 F # 레코드 형식을 사용 합니다.

F # 레코드 형식은 간단한 .NET 클래스로 컴파일됩니다. 이는 Api의 몇 가지 단순 하 고 안정적인 형식에 적합 합니다. `[<NoEquality>]` `[<NoComparison>]` 인터페이스의 자동 생성을 억제 하려면 및 특성을 사용 하는 것이 좋습니다. 또한 바닐라 .NET Api에서 변경 가능한 레코드 필드를 사용 하지 마십시오. 이러한 필드는 public 필드를 노출 합니다. 항상 클래스가 향후 API의 진화에 보다 유연한 옵션을 제공 하는지 여부를 고려해 야 합니다.

예를 들어 다음 F # 코드는 c # 소비자에 게 공용 API를 노출 합니다.

F#:

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing: int
        SecondThing: string }
```

C#:

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a>바닐라 .NET Api에서 F # 공용 구조체 형식의 표현을 숨깁니다.

F # 공용 구조체 형식은 F #-F # 코딩에도 불구 하 고 일반적으로 구성 요소 경계에서 사용 되지 않습니다. 구성 요소와 라이브러리 내에서 내부적으로 사용 되는 경우에는 뛰어난 구현 장치입니다.

바닐라 .NET API를 디자인할 때 전용 선언이 나 서명 파일을 사용 하 여 공용 구조체 형식의 표현을 숨기는 것이 좋습니다.

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

또한 멤버와 내부적으로 공용 구조체 표현을 사용 하는 형식을 보강 하 여 원하는를 제공할 수 있습니다. 네트워크 연결 API.

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True

    /// A public member for use from C#
    member x.Evaluate =
        match x with
        | And(a,b) -> a.Evaluate && b.Evaluate
        | Not a -> not a.Evaluate
        | True -> true

    /// A public member for use from C#
    static member CreateAnd(a,b) = And(a,b)
```

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a>프레임 워크의 디자인 패턴을 사용 하 여 GUI 및 기타 구성 요소 디자인

.NET 내에서는 WinForms, WPF, ASP.NET 등 다양 한 프레임 워크를 사용할 수 있습니다. 이러한 프레임 워크에 사용할 구성 요소를 디자인 하는 경우 각각에 대 한 명명 및 디자인 규칙을 사용 해야 합니다. 예를 들어 WPF 프로그래밍의 경우 디자인 중인 클래스에 대해 WPF 디자인 패턴을 채택 합니다. 사용자 인터페이스 프로그래밍의 모델의 경우 이벤트 및 알림 기반 컬렉션과 같은 디자인 패턴 (예:)을 사용 <xref:System.Collections.ObjectModel> 합니다.

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a>개체 및 멤버 디자인 (다른 .NET 언어에서 사용 하는 라이브러리의 경우)

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a>CLIEvent 특성을 사용 하 여 .NET 이벤트 노출

`DelegateEvent` `EventArgs` `Event` `FSharpHandler` 이벤트가 다른 .net 언어에 익숙한 방식으로 게시 되도록 개체와 (기본적으로 형식을 사용 하는)를 사용 하는 특정 .net 대리자 형식을 사용 하 여를 생성 합니다.

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x: int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-that-return-net-tasks"></a>.NET 작업을 반환 하는 메서드로 비동기 작업 노출

작업은 활성 비동기 계산을 나타내기 위해 .NET에서 사용 됩니다. 작업은 `Async<T>` "이미 실행 중인" 작업을 나타내지만 병렬 컴퍼지션을 수행 하는 방식으로 함께 구성 될 수 없거나 취소 신호 및 기타 컨텍스트 매개 변수의 전파를 숨기 므로 F # 개체 보다 일반적으로 compositional.

그러나이 경우에도 작업을 반환 하는 메서드는 .NET의 비동기 프로그래밍에 대 한 표준 표현입니다.

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int): Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

또한 명시적 취소 토큰을 허용 하는 것이 좋습니다.

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x: int): Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a>F # 함수 형식 대신 .NET 대리자 형식을 사용 합니다.

여기에서 "F # 함수 형식"은와 같은 "화살표" 형식을 의미 `int -> int` 합니다.

대신 다음을 수행 합니다.

```fsharp
member this.Transform(f: int->int) =
    ...
```

방법:

```fsharp
member this.Transform(f: Func<int,int>) =
    ...
```

F # 함수 형식은 `class FSharpFunc<T,U>` 다른 .net 언어에 표시 되며, 대리자 형식을 이해 하는 언어 기능 및 도구에는 적합 하지 않습니다. .NET Framework 3.5 이상을 대상으로 하는 고차 메서드를 작성 하는 경우, `System.Func` 및 `System.Action` 대리자는 .net 개발자가 이러한 api를 낮은 수준으로 사용할 수 있도록 게시 하는 데 적합 한 api입니다. .NET Framework 2.0를 대상으로 지정 하는 경우 시스템 정의 대리자 형식이 더 제한적입니다. 또는와 같은 미리 정의 된 대리자 형식을 사용 `System.Converter<T,U>` 하거나 특정 대리자 형식을 정의 하는 것이 좋습니다.

대칭 이동 측면에서 .NET 대리자는 F # 연결 라이브러리에 대해 자연스럽 게 되지 않습니다 (F # 연결 라이브러리의 다음 섹션 참조). 결과적으로 바닐라 .NET 라이브러리에 대해 고차 메서드를 개발할 때 일반적인 구현 전략은 F # 함수 형식을 사용 하 여 모든 구현을 작성 한 다음 실제 F # 구현에서 가장 왼쪽에 있는 씬 외관으로 대리자를 사용 하 여 공용 API를 만드는 것입니다.

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a>F # 옵션 값을 반환 하는 대신 TryGetValue 패턴을 사용 하 고 F # 옵션 값을 인수로 사용 하는 메서드 오버 로드를 선호 합니다.

Api에서 F # 옵션 형식에 대 한 일반적인 사용 패턴은 표준 .NET 디자인 기술을 사용 하 여 바닐라 .NET Api에서 구현 하는 것이 더 좋습니다. F # 옵션 값을 반환 하는 대신 bool 반환 형식과 out 매개 변수를 "TryGetValue" 패턴과 함께 사용 하는 것이 좋습니다. F # 옵션 값을 매개 변수로 사용 하는 대신 메서드 오버 로드 또는 선택적 인수를 사용 하는 것이 좋습니다.

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal: byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x: int, y: int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x: int) = x

member this.ParamOverload(x: int, y: int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a>.NET 컬렉션 인터페이스 형식 IEnumerable \<T\> 및 IDictionary \<Key,Value\> 에 매개 변수 및 반환 값 사용

.NET 배열 `T[]` , F # 형식 `list<T>` , 및와 같은 `Map<Key,Value>` `Set<T>` .net 구체적 컬렉션 형식과 `Dictionary<Key,Value>` 같은 구체적인 컬렉션 형식을 사용 하지 마십시오. .NET 라이브러리 디자인 지침에는와 같은 다양 한 컬렉션 형식을 사용 해야 하는 경우에 대 한 적절 한 조언이 있습니다 `IEnumerable<T>` . 일부 경우에는 성능 grounds 일부 배열 ()을 사용할 `T[]` 수 있습니다. 특히 `seq<T>` ,에 대 한 F # 별칭입니다 `IEnumerable<T>` . 따라서 seq는 종종 바닐라 .net API에 적합 한 형식입니다.

F # 목록 대신:

```fsharp
member this.PrintNames(names: string list) =
    ...
```

F # 시퀀스 사용:

```fsharp
member this.PrintNames(names: seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a>0 인수 메서드를 정의 하는 메서드의 유일한 입력 형식으로 단위 형식을 사용 하거나, void 반환 메서드를 정의 하는 유일한 반환 형식으로 사용 합니다.

단위 형식의 다른 용도를 방지 합니다. 이는 다음과 같이 좋습니다.

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x: int) = ()
```

이것은 잘못 된 것입니다.

```fsharp
member this.WrongUnit( x: unit, z: int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a>바닐라 .NET API 경계에서 null 값 확인

F # 구현 코드는 변경 불가능 한 디자인 패턴 및 F # 형식에 대 한 null 리터럴 사용에 대 한 제한으로 인해 null 값이 줄어드는 경향이 있습니다. 다른 .NET 언어에서는 종종 null을 값으로 자주 사용 합니다. 이로 인해 바닐라 .NET API를 노출 하는 F # 코드는 API 경계에서 null에 대 한 매개 변수를 확인 하 고 이러한 값이 F # 구현 코드로 더 심층적으로 이동 하지 않도록 합니다. `isNull`패턴에서 함수 또는 패턴 일치를 `null` 사용할 수 있습니다.

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a>튜플을 반환 값으로 사용 하지 않습니다.

대신 집계 데이터를 포함 하는 명명 된 형식을 반환 하거나 out 매개 변수를 사용 하 여 여러 값을 반환 하는 것이 좋습니다. 튜플 및 구조체 튜플은 .NET에 존재 하지만 (구조체 튜플에 대 한 c # 언어 지원 포함) .NET 개발자에 게 이상적이 고 예상 되는 API를 제공 하지 않는 경우가 많습니다.

#### <a name="avoid-the-use-of-currying-of-parameters"></a>Currying 매개 변수 사용 방지

대신 .NET 호출 규칙을 사용 `Method(arg1,arg2,…,argN)` 합니다.

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

팁: 모든 .NET 언어에서 사용할 수 있도록 라이브러리를 디자인 하는 경우 실제로 이러한 언어에서 "느낌" 라이브러리가 되도록 일부 실험적 c # 및 Visual Basic 프로그래밍을 수행 하는 것은 대체 되지 않습니다. .NET 반영자 및 Visual Studio 개체 브라우저와 같은 도구를 사용 하 여 라이브러리와 해당 설명서가 개발자에 게 예상 대로 표시 되도록 할 수도 있습니다.

## <a name="appendix"></a>부록

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a>다른 .NET 언어에서 사용할 F # 코드를 디자인 하는 종단 간 예제

다음 클래스를 살펴보세요.

```fsharp
open System

type Point1(angle,radius) =
    new() = Point1(angle=0.0, radius=0.0)
    member x.Angle = angle
    member x.Radius = radius
    member x.Stretch(l) = Point1(angle=x.Angle, radius=x.Radius * l)
    member x.Warp(f) = Point1(angle=f(x.Angle), radius=x.Radius)
    static member Circle(n) =
        [ for i in 1..n -> Point1(angle=2.0*Math.PI/float(n), radius=1.0) ]
```

이 클래스의 유추 된 F # 형식은 다음과 같습니다.

```fsharp
type Point1 =
    new : unit -> Point1
    new : angle:double * radius:double -> Point1
    static member Circle : n:int -> Point1 list
    member Stretch : l:double -> Point1
    member Warp : f:(double -> double) -> Point1
    member Angle : double
    member Radius : double
```

이 F # 형식이 다른 .NET 언어를 사용 하 여 프로그래머에 게 표시 되는 방식을 살펴보겠습니다. 예를 들어 대략적인 c # "signature"는 다음과 같습니다.

```csharp
// C# signature for the unadjusted Point1 class
public class Point1
{
    public Point1();

    public Point1(double angle, double radius);

    public static Microsoft.FSharp.Collections.List<Point1> Circle(int count);

    public Point1 Stretch(double factor);

    public Point1 Warp(Microsoft.FSharp.Core.FastFunc<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

여기에서 F #이 생성 하는 방법에 대 한 몇 가지 중요 한 사항이 있습니다. 예를 들면 다음과 같습니다.

* 인수 이름과 같은 메타 데이터는 유지 되었습니다.

* 두 인수를 사용 하는 F # 메서드는 두 개의 인수를 사용 하는 c # 메서드가 됩니다.

* 함수 및 목록은 F # 라이브러리의 해당 형식에 대 한 참조가 됩니다.

다음 코드에서는 이러한 항목을 고려 하도록이 코드를 조정 하는 방법을 보여 줍니다.

```fsharp
namespace SuperDuperFSharpLibrary.Types

type RadialPoint(angle:double, radius:double) =

    /// Return a point at the origin
    new() = RadialPoint(angle=0.0, radius=0.0)

    /// The angle to the point, from the x-axis
    member x.Angle = angle

    /// The distance to the point, from the origin
    member x.Radius = radius

    /// Return a new point, with radius multiplied by the given factor
    member x.Stretch(factor) =
        RadialPoint(angle=angle, radius=radius * factor)

    /// Return a new point, with angle transformed by the function
    member x.Warp(transform:Func<_,_>) =
        RadialPoint(angle=transform.Invoke angle, radius=radius)

    /// Return a sequence of points describing an approximate circle using
    /// the given count of points
    static member Circle(count) =
        seq { for i in 1..count ->
                RadialPoint(angle=2.0*Math.PI/float(count), radius=1.0) }
```

코드의 유추 된 F # 형식은 다음과 같습니다.

```fsharp
type RadialPoint =
    new : unit -> RadialPoint
    new : angle:double * radius:double -> RadialPoint
    static member Circle : count:int -> seq<RadialPoint>
    member Stretch : factor:double -> RadialPoint
    member Warp : transform:System.Func<double,double> -> RadialPoint
    member Angle : double
    member Radius : double
```

이제 c # 시그니처는 다음과 같습니다.

```csharp
public class RadialPoint
{
    public RadialPoint();

    public RadialPoint(double angle, double radius);

    public static System.Collections.Generic.IEnumerable<RadialPoint> Circle(int count);

    public RadialPoint Stretch(double factor);

    public RadialPoint Warp(System.Func<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

바닐라 .NET 라이브러리의 일부로 사용 하기 위해이 형식을 준비 하는 수정 사항은 다음과 같습니다.

* ,, 및가 각각,, 및로 조정 `Point1` `n` `l` `f` `RadialPoint` `count` `factor` `transform` 되었습니다.

* 를 사용 하 여에서 `seq<RadialPoint>` `RadialPoint list` 시퀀스 생성으로 목록 생성을 변경 하는 대신의 반환 형식을 사용 `[ ... ]` `IEnumerable<RadialPoint>` 했습니다.

* `System.Func`F # 함수 형식 대신 .net 대리자 형식을 사용 했습니다.

이렇게 하면 c # 코드를 사용 하는 것이 훨씬 더 좋은.
