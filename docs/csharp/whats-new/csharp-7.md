---
title: C# 7.0의 새로운 기능 - C# 가이드
description: C# 언어 버전 7.0의 새로운 기능을 살펴봅니다.
ms.date: 10/02/2020
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: 897729022e45e96d0f54057ef4dad1a4fc0d6799
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103480855"
---
# <a name="whats-new-in-c-70-through-c-73"></a>C# 7.0~C# 7.3의 새로운 기능

C# 7.0~C# 7.3에서는 C#을 사용한 개발 환경에 다양한 기능과 증분 개선 사항을 도입했습니다. 이 문서에서는 새로운 언어 기능과 컴파일러 옵션에 대해 간략하게 설명합니다. .NET Framework 기반 애플리케이션에 대해 지원되는 최신 버전인 C# 7.3의 동작을 설명합니다.

C# 7.1에 추가된 [언어 버전 선택](../language-reference/configure-language-version.md) 구성 요소를 사용하면 프로젝트 파일에서 컴파일러 언어 버전을 지정할 수 있습니다.

C# 7.0~7.3에서는 C# 언어에 다음 기능과 테마를 추가합니다.

- [튜플 및 무시 항목](#tuples-and-discards)
  - 여러 public 필드가 포함된 간단한 명명되지 않은 형식을 만들 수 있습니다. 컴파일러 및 IDE 도구는 이러한 형식의 의미 체계를 이해합니다.
  - 삭제는 할당된 값에 신경 쓰지 않을 때 할당에서 사용되는 임시 쓰기 전용 변수입니다. 매개 변수는 `out` 매개 변수를 사용하여 메서드를 호출할 때뿐만 아니라 튜플 및 사용자 정의 형식을 분해할 때 특히 유용합니다.
- [패턴 일치](#pattern-matching)
  - 임의 형식 및 해당 형식의 멤버 값에 따라 분기 논리를 만들 수 있습니다.
- [`async` `Main` 메서드](#async-main)
  - 애플리케이션에 대한 진입점은 `async` 한정자를 가질 수 있습니다.
- [로컬 함수](#local-functions)
  - 함수를 다른 함수 내부에 중첩하여 범위와 표시 여부를 제한할 수 있습니다.
- [추가 식 본문 멤버](#more-expression-bodied-members)
  - 식을 사용하여 작성할 수 있는 멤버 목록이 증가했습니다.
- [`throw` 식](#throw-expressions)
  - `throw` 문이었기 때문에 이전에 허용되지 않은 코드 구문에서 예외를 throw할 수 있습니다.
- [`default` 리터럴 식](#default-literal-expressions)
  - 대상 형식을 유추할 수 있는 경우 기본 값 식에서 기본 리터럴 식을 사용할 수 있습니다.
- [숫자 리터럴 구문 개선 사항](#numeric-literal-syntax-improvements)
  - 새로운 토큰으로 숫자 상수의 가독성이 향상됩니다.
- [`out` 변수](#out-variables)
  - `out` 값을 사용되는 메서드에 대한 인수로 인라인으로 선언할 수 있습니다.
- [뒤에 오지 않는 명명된 인수](#non-trailing-named-arguments)
  - 명명된 인수 뒤에는 위치 인수가 올 수 있습니다.
- [`private protected` 액세스 한정자](#private-protected-access-modifier)
  - `private protected` 액세스 한정자는 동일한 어셈블리의 파생된 클래스에 대해 액세스를 사용합니다.
- [향상된 오버로드 확인](#improved-overload-candidates)
  - 오버로드 확인 모호성을 해결하는 새로운 규칙
- [안전하고 효율적인 코드를 작성하는 방법](#enabling-more-efficient-safe-code)
  - 참조 의미 체계를 사용하는 값 유형으로 작동할 수 있는 구문 개선의 조합입니다.

마지막으로, 컴파일러에는 다음과 같은 새 옵션이 있습니다.

- `-refout` 및 `-refonly` - [참조 어셈블리 생성](#reference-assembly-generation)을 제어합니다.
- `-publicsign` - OSS(오픈 소스 소프트웨어) 시그니처를 사용하도록 설정합니다.
- `-pathmap` - 소스 디렉터리에 대한 매핑을 제공합니다.

이 문서의 나머지 부분에서는 해당 기능에 대한 개요를 제공합니다. 각 기능의 논리적 근거와 구문을 알아봅니다. `dotnet try` 글로벌 도구를 사용하여 환경에서 다음과 같은 기능을 탐색할 수 있습니다.

1. [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) 글로벌 도구를 설치합니다.
1. [dotnet/try-samples](https://github.com/dotnet/try-samples) 리포지토리를 복제합니다.
1. 현재 디렉터리를 *try-samples* 리포지토리의 *csharp7* 하위 디렉터리로 설정합니다.
1. `dotnet try`를 실행합니다.

## <a name="tuples-and-discards"></a>튜플 및 무시 항목

C#에서는 디자인 의도를 설명하는 데 사용되는 클래스 및 구조체에 대한 다양한 구문을 제공합니다. 하지만 다양한 구문에는 이점이 거의 없는데 추가 작업이 필요한 경우가 있습니다. 일반적으로 두 개 이상의 데이터 요소가 포함된 간단한 구조체가 필요한 메서드를 작성할 수 있습니다. 이러한 시나리오를 지원하기 위해 *튜플* 이 C#에 추가되었습니다. 튜플은 데이터 멤버를 나타내는 여러 필드가 포함된 간단한 데이터 구조입니다. 필드의 유효성이 검사되지 않고 고유한 메서드를 정의할 수 없습니다. C# 튜플 형식은 `==` 및 `!=`를 지원합니다. 자세한 내용은

> [!NOTE]
> 튜플은 C# 7.0 이전부터 사용할 수 있었지만 비효율적이었고 언어 지원이 없었습니다. 즉, 튜플 요소는 `Item1`, `Item2` 등으로만 참조될 수 있었습니다. C# 7.0은 새롭고 보다 효율적인 튜플 유형을 사용하여 튜플의 필드에 대해 의미론적 이름을 사용할 수 있는 튜플에 대한 언어 지원을 소개합니다.

각 멤버에 값을 할당하고 필요에 따라 튜플의 각 멤버에 의미 체계 이름을 입력하여 튜플을 만들 수 있습니다.

[!code-csharp[NamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#NamedTuple "Named tuple")]

`namedLetters` 튜플에는 `Alpha` 및 `Beta`라는 필드가 포함됩니다. 이러한 이름은 컴파일 시간에만 존재하며 런타임 시 리플렉션을 통해 튜플을 검사하는 경우 보존되지 않습니다.

튜플 할당에서 할당의 오른쪽에 필드의 이름을 지정할 수도 있습니다.

[!code-csharp[ImplicitNamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#ImplicitNamedTuple "Implicitly named tuple")]

메서드에서 반환된 튜플의 멤버를 패키지 해제하려는 경우가 있을 수 있습니다.  이 작업을 수행하려면 튜플에서 각 값에 대한 개별 변수를 선언합니다. 이 패키지 해제 작업을 튜플 *분해* 라고 합니다.

[!code-csharp[CallingWithDeconstructor](~/samples/snippets/csharp/new-in-7/program.cs#CallingWithDeconstructor "Deconstructing a tuple")]

.NET에 있는 형식에 대한 비슷한 분해를 제공할 수도 있습니다. `Deconstruct` 메서드를 클래스의 멤버로 작성합니다. 해당 `Deconstruct` 메서드는 추출하려는 각 속성에 대한 `out` 인수 집합을 제공합니다. `X` 및 `Y` 좌표를 추출하는 분해자 메서드를 제공하는 이 `Point` 클래스를 살펴봅니다.

[!code-csharp[PointWithDeconstruction](~/samples/snippets/csharp/new-in-7/point.cs#PointWithDeconstruction "Point with deconstruction method")]

튜플에 `Point`을 할당하여 개별 필드를 추출할 수 있습니다.

[!code-csharp[DeconstructPoint](~/samples/snippets/csharp/new-in-7/program.cs#DeconstructPoint "Deconstruct a point")]

여러 번 튜플을 초기화할 때 할당의 오른쪽에 사용되는 변수는 튜플 요소에 대해 원하는 이름과 동일합니다. 튜플 요소의 이름은 튜플을 초기화하는 데 사용된 변수를 통해 유추할 수 있습니다.

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

[튜플 형식](../language-reference/builtin-types/value-tuples.md) 문서에서 해당 기능을 자세히 알아볼 수 있습니다.

종종 튜플을 분해하거나 `out` 매개 변수로 메서드를 호출할 때 값을 신경 쓰지 않고 사용하지 않을 변수를 정의해야 합니다. C#은 *버림* 에 대한 지원을 추가하여 이 시나리오를 처리합니다. 무시는 이름이 `_`(밑줄 문자)인 쓰기 전용 변수입니다. 단일 변수에 버리려는 모든 값을 할당할 수 있습니다. 버림은 할당 문과 별도로 분리되는 할당되지 않은 변수와 같습니다. 코드에서 버림을 사용할 수 없습니다.

다음 시나리오에서는 버림이 지원되지 않습니다.

- 튜플이나 사용자 정의 형식을 분해할 때.
- [out](../language-reference/keywords/out-parameter-modifier.md) 매개 변수로 메서드를 호출할 때.
- [is](../language-reference/keywords/is.md) 및 [switch](../language-reference/keywords/switch.md) 문을 사용한 패턴 일치 작업에서.
- 할당 값을 버림으로 명시적으로 지정할 때 독립 실행형 식별자인 경우.

다음 예제에서는 서로 다른 2년간의 도시 데이터가 포함된 6 튜플을 반환하는 `QueryCityDataForYears` 메서드를 정의합니다. 예제의 메서드 호출은 메서드에 의해 반환된 두 개의 채우기 값에만 관련되어 있으므로 튜플을 해체할 때 튜플의 나머지 값을 버림으로 처리합니다.

[!code-csharp[Tuple-discard](~/samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

자세한 내용은 [버림](../discards.md)을 참조하세요.

## <a name="pattern-matching"></a>패턴 일치

‘패턴 일치’는 코드에서 제어 흐름을 표현하는 새로운 방법을 제공하는 기능 세트입니다. 형식, 값 또는 속성 값에 대해 변수를 테스트할 수 있습니다. 해당 기술은 좀 더 읽기 쉬운 코드 흐름을 만듭니다.

패턴 일치는 `is` 식과 `switch` 식을 지원합니다. 각 식을 통해 개체 및 관련 속성을 검사하여 해당 개체가 검색된 패턴을 충족하는지 확인할 수 있습니다. `when` 키워드를 사용하여 패턴에 대한 추가 규칙을 지정합니다.

`is` 패턴 식은 친숙한 [`is` 연산자](../language-reference/keywords/is.md#pattern-matching-with-is)를 확장하여 해당 형식에 대한 개체를 쿼리하고 하나의 명령에서 결과를 할당합니다. 다음 코드는 변수가 `int`인지 검사하고, 그럴 경우 현재 합계에 추가합니다.

```csharp
if (input is int count)
    sum += count;
```

앞서 간단한 예제에서는 `is` 식의 개선 사항을 보여줍니다. 참조 형식뿐만 아니라 값 형식에 대해 테스트할 수 있고, 올바른 형식의 새로운 변수에 성공적인 결과를 할당할 수 있습니다.

switch 일치 식에는 이미 C# 언어의 일부인 `switch` 문에 기반을 둔 친숙한 구문이 있습니다. 업데이트된 switch 문에는 몇 가지 새로운 구문이 포함됩니다.

- `switch` 식의 관리 형식은 더 이상 정수 형식, `Enum` 형식, `string` 또는 해당 형식 중 하나에 해당하는 nullable 형식으로 제한되지 않습니다. 모든 형식을 사용할 수 있습니다.
- 각 `case` 레이블에서 `switch` 식 형식을 테스트할 수 있습니다. `is` 식과 마찬가지로 해당 형식에 새 변수를 할당할 수 있습니다.
- `when` 절을 해당 변수의 추가 테스트 조건에 추가할 수 있습니다.
- 이제 `case` 레이블의 순서가 중요합니다. 일치하는 첫 번째 분기가 실행됩니다. 다른 분기는 건너뜁니다.

다음 코드에서는 이 새로운 기능을 보여줍니다.

```csharp
public static int SumPositiveNumbers(IEnumerable<object> sequence)
{
    int sum = 0;
    foreach (var i in sequence)
    {
        switch (i)
        {
            case 0:
                break;
            case IEnumerable<int> childSequence:
            {
                foreach(var item in childSequence)
                    sum += (item > 0) ? item : 0;
                break;
            }
            case int n when n > 0:
                sum += n;
                break;
            case null:
                throw new NullReferenceException("Null found in sequence");
            default:
                throw new InvalidOperationException("Unrecognized type");
        }
    }
    return sum;
}
```

- `case 0:`은 친숙한 상수 패턴입니다.
- `case IEnumerable<int> childSequence:`는 형식 패턴입니다.
- `case int n when n > 0:`은 추가 `when` 조건을 포함한 형식 패턴입니다.
- `case null:`은 null 패턴입니다.
- `default:`는 친숙한 기본 사례입니다.

C# 7.1부터 `is` 및 `switch` 형식 패턴의 패턴 식에는 제네릭 형식 매개 변수의 형식이 포함될 수 있습니다. 이 방법은 `struct` 또는 `class` 형식 중 하나일 수 있는 형식을 확인하고 boxing을 방지하려는 경우에 가장 유용합니다.

[C#의 패턴 일치](../pattern-matching.md)에서 패턴 일치에 대해 자세히 알아볼 수 있습니다.

## <a name="async-main"></a>비동기 기본

*비동기 기본* 메서드를 통해 `Main` 메서드에서 `await`를 사용할 수 있습니다. 이전에 다음을 작성해야 했습니다.

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

이제 다음을 작성할 수 있습니다.

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

프로그램이 종료 코드를 반환하지 않는 경우 <xref:System.Threading.Tasks.Task>를 반환하는 `Main` 메서드를 선언할 수 있습니다.

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

프로그래밍 가이드의 [비동기 기본](../programming-guide/main-and-command-args/index.md) 문서에서 세부 정보에 대해 자세히 읽어볼 수 있습니다.

## <a name="local-functions"></a>로컬 함수

클래스에 대한 대부분의 디자인에는 한 위치에서만 호출되는 메서드가 포함됩니다. 이러한 추가 private 메서드는 각 메서드를 작고 집중되게 유지합니다. *로컬 함수* 를 사용하면 다른 메서드의 컨텍스트 내부에서 메서드를 선언할 수 있습니다. 로컬 함수를 통해 클래스 readers는 로컬 메서드가 선언된 컨텍스트에서만 호출된다는 것을 더 쉽게 알 수 있습니다.

로컬 함수는 일반적으로 공용 반복기 메서드 및 공용 비동기 메서드에 사용됩니다. 두 메서드 형식 모두 프로그래머가 예상한 것보다 늦게 오류를 보고하는 코드를 생성합니다. 반복기 메서드에서 모든 예외는 반환된 시퀀스를 열거하는 코드를 호출할 경우에만 관찰됩니다. 비동기 메서드에서 모든 예외는 반환된 `Task`가 대기 상태일 경우에만 관찰됩니다. 다음 예제에서는 로컬 함수를 사용하여 반복기 구현으로부터 매개 변수 유효성 검사를 분리하는 방법을 보여줍니다.

[!code-csharp[22_IteratorMethodLocal](~/samples/snippets/csharp/new-in-7/Iterator.cs#IteratorMethodLocal "Iterator method with local function")]

`async` 메서드에서 같은 방법을 사용하면 인수 유효성 검사에서 발생하는 예외가 비동기 작업이 시작되기 전에 throw됩니다.

[!code-csharp[TaskExample](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

이제 다음 구문이 지원됩니다.

```csharp
[field: SomeThingAboutFieldAttribute]
public int SomeProperty { get; set; }
```

`SomeThingAboutFieldAttribute` 특성은 `SomeProperty`에 대한 컴파일러 생성 지원 필드에 적용됩니다. 자세한 내용은 C# 프로그래밍 가이드의 [특성](../programming-guide/concepts/attributes/index.md)을 참조하세요.

> [!NOTE]
> 로컬 함수가 지원하는 일부 디자인은 *람다 식* 을 사용하여 수행할 수도 있습니다. 자세한 내용은 [로컬 함수와 람다 식 비교](../programming-guide/classes-and-structs/local-functions.md#local-functions-vs-lambda-expressions)를 참조하세요.

## <a name="more-expression-bodied-members"></a>추가 식 본문 멤버

C# 6에서는 멤버 함수의 식 본문 멤버 및 읽기 전용 속성을 추가했습니다. C# 7.0에서는 식으로 구현될 수 있는 허용 멤버를 확장합니다. C# 7.0에서는 *속성* 및 *인덱서* 에 대한 *생성자*, *종료자* 및 `get`/`set` 접근자를 구현할 수 있습니다. 다음 코드는 각각에 대한 예제를 보여 줍니다.

[!code-csharp[ExpressionBodiedMembers](~/samples/snippets/csharp/new-in-7/expressionmembers.cs#ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> 이 예제에는 종료자가 필요하지 않지만 구문을 보여 주기 위해 표시됩니다. 관리되지 않는 리소스를 릴리스해야 하는 경우가 아니면 클래스에서 종료자를 구현하면 안 됩니다. 관리되지 않는 리소스를 직접 관리하지 않고 <xref:System.Runtime.InteropServices.SafeHandle> 클래스를 사용하는 것도 고려해야 합니다.

식 본문 멤버의 새 위치는 C# 언어의 중요한 마일스톤을 나타냅니다. 이러한 기능은 오픈 소스 [Roslyn](https://github.com/dotnet/Roslyn) 프로젝트에서 작업하는 커뮤니티 멤버에 의해 구현되었습니다.

메서드를 식 본문 멤버로 변경하는 것은 [이진 호환 가능 변경](version-update-considerations.md#binary-compatible-changes)입니다.

## <a name="throw-expressions"></a>Throw 식

C#에서 `throw`는 항상 문이었습니다. `throw`는 식이 아닌 명령문이므로 이 명령문을 사용할 수 없는 C# 구문이 있었습니다. 이러한 구문에는 조건식, null 병합 식 및 몇몇 람다 식이 포함되었습니다. 식 본문 멤버가 추가됨에 따라 `throw` 식이 유용할 수 있는 추가 위치도 추가됩니다. 이러한 구문을 작성할 수 있도록 C# 7.0에서는 [*throw 식*](../language-reference/keywords/throw.md#the-throw-expression)을 추가합니다.

이렇게 추가하면 자세한 식 기반 코드를 쉽게 작성할 수 있습니다. 오류 검사를 위해 명령문을 추가할 필요는 없습니다.

## <a name="default-literal-expressions"></a>기본 리터럴 식

기본 리터럴 식은 기본값 식에 대한 향상된 기능입니다. 이러한 식은 변수를 기본 값으로 초기화합니다. 여기서 이전에 다음을 작성했습니다.

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

이제 초기화의 오른쪽에서 형식을 생략할 수 있습니다.

```csharp
Func<string, bool> whereClause = default;
```

자세한 내용은 [기본 연산자](../language-reference/operators/default.md) 문서의 [기본 리터럴](../language-reference/operators/default.md#default-literal) 섹션을 참조하세요.

## <a name="numeric-literal-syntax-improvements"></a>숫자 리터럴 구문 개선 사항

숫자 상수를 잘못 읽으면 코드를 처음 읽을 때 이해하기가 더 어려울 수 있습니다. 비트 마스크 또는 다른 기호 값은 잘못 이해하기 쉽습니다. C# 7.0에는 의도한 용도에 맞게 가장 읽기 쉬운 방식으로 숫자를 작성할 수 있는 *이진 리터럴* 및 *숫자 구분 기호* 라는 두 가지 새로운 기능이 포함됩니다.

비트 마스크를 만들 때 또는 숫자의 이진 표현이 가장 읽기 쉬운 코드를 만들 때마다 해당 숫자를 이진으로 작성하세요.

[!code-csharp[ThousandSeparators](~/samples/snippets/csharp/new-in-7/Program.cs#ThousandSeparators "Thousands separators")]

상수의 시작 부분에 있는 `0b`는 숫자가 이진 숫자로 작성되었음을 나타냅니다. 이진 숫자는 길어질 수 있으므로, 이전 예제의 이진 상수와 같이 `_`을 숫자 구분 기호로 추가하면 일반적으로 비트 패턴을 더 쉽게 확인할 수 있습니다. 숫자 구분 기호는 상수 내의 어디에나 나타날 수 있습니다. 10진수 숫자의 경우 숫자 구분 기호를 천 단위 구분 기호로 사용하는 것이 일반적입니다. 16진수 및 이진 숫자 리터럴은 `_`로 시작할 수도 있습니다.

[!code-csharp[LargeIntegers](~/samples/snippets/csharp/new-in-7/Program.cs#LargeIntegers "Large integer")]

숫자 구분 기호는 `decimal`, `float` 및 `double` 형식에서도 사용할 수 있습니다.

[!code-csharp[OtherConstants](~/samples/snippets/csharp/new-in-7/Program.cs#OtherConstants "non-integral constants")]

함께 사용하면 숫자 상수를 훨씬 더 읽기 쉽게 선언할 수 있습니다.

## <a name="out-variables"></a>`out` 변수

`out` 매개 변수를 지원하는 기존 구문이 C# 7에서 개선되었습니다. 이제 개별 선언 문을 작성하는 대신 메서드 호출의 인수 목록에서 `out` 변수를 선언할 수 있습니다.

[!code-csharp[OutVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVariableDeclarations "Out variable declarations")]

이전 예제와 같이 `out` 변수의 형식을 명확하게 지정하는 것이 좋습니다. 그러나 이 언어는 암시적 형식 지역 변수를 지원하지 않습니다.

[!code-csharp[OutVarVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVarVariableDeclarations "Implicitly typed Out variable")]

- 코드를 읽기가 더 쉽습니다.
  - out 변수는 앞의 코드 줄이 아니라 변수를 사용하는 곳에서 선언합니다.
- 초기 값을 할당할 필요가 없습니다.
  - 메서드 호출에서 사용되는 위치에 `out` 변수를 선언하여 변수가 할당되기 전에 실수로 사용할 수 없습니다.

`out` 변수 선언이 허용하기 위해 C# 7.0에 추가된 구문은 필드 이니셜라이저, 속성 이니셜라이저, 생성자 이니셜라이저 및 쿼리 절을 포함하도록 확장되었습니다. 이를 통해 다음 예제와 같은 코드를 사용할 수 있습니다.

```csharp
public class B
{
   public B(int i, out int j)
   {
      j = i;
   }
}

public class D : B
{
   public D(int i) : base(i, out var j)
   {
      Console.WriteLine($"The value of 'j' is {j}");
   }
}
```

## <a name="non-trailing-named-arguments"></a>뒤에 오지 않는 명명된 인수

명명된 인수가 올바른 위치에 있을 때 메서드 호출은 이제 위치 인수보다 앞에 있는 명명된 인수를 사용할 수 있습니다. 자세한 내용은 [명명된 인수 및 선택적 인수](../programming-guide/classes-and-structs/named-and-optional-arguments.md)를 참조하세요.

## <a name="private-protected-access-modifier"></a>*private protected* 액세스 한정자

새로운 복합 액세스 한정자인 `private protected`는 동일한 어셈블리에 선언된 클래스 또는 파생 클래스를 포함하여 멤버에 액세스할 수 있음을 나타냅니다. `protected internal`은 동일한 어셈블리에 있는 파생 클래스나 클래스에 의한 액세스를 허용하지만 `private protected`는 동일한 어셈블리에서 선언된 파생 유형에 대한 액세스를 제한합니다.

자세한 내용은 언어 참조에서 [액세스 한정자](../language-reference/keywords/access-modifiers.md)를 참조하세요.

## <a name="improved-overload-candidates"></a>향상된 오버로드 후보

모든 릴리스에서 오버로드 해결 규칙은 모호한 메서드 호출에 “분명한” 선택이 있는 상황을 해결하도록 업데이트됩니다. 이 릴리스는 컴파일러가 분명한 선택 항목을 선택하도록 도와주는 세 가지 새로운 규칙을 추가합니다.

1. 메서드 그룹에 인스턴스와 정적 멤버가 둘 다 포함되어 있으면 인스턴스 수신기 또는 컨텍스트 없이 호출되는 경우 컴파일러는 인스턴스 멤버를 버립니다. 메서드가 인스턴스 수신기를 통해 호출된 경우 컴파일러는 정적 멤버를 버립니다. 수신기가 없는 경우 컴파일러는 정적 컨텍스트에 정적 멤버만 포함하고, 이외의 경우에는 정적 및 인스턴스 멤버를 둘 다 포함합니다. 수신기가 모호하게 인스턴스 또는 형식인 경우에는 컴파일러가 둘 다 포함합니다. 암시적 `this` 인스턴스 수신기를 사용할 수 없는 정적 컨텍스트에는 정적 멤버와 같이 `this`가 정의되지 않은 멤버의 본문과 필드 이니셜라이저 및 생성자 이니셜라이저와 같이 `this`를 사용할 수 없는 위치가 포함됩니다.
1. 형식 인수가 해당 제약 조건을 충족하지 않는 제네릭 메서드가 메서드 그룹에 포함된 경우 이러한 멤버는 후보 집합에서 제거됩니다.
1. 메서드 그룹 변환의 경우 반환 형식이 대리자의 반환 형식과 일치하지 않는 후보 메서드가 집합에서 제거됩니다.

어떤 메서드가 더 나은지 알고 있으면 모호한 메서드 오버로드에 대한 컴파일러 오류가 감소하므로 이 변경을 알 수 있습니다.

## <a name="enabling-more-efficient-safe-code"></a>좀 더 효율적인 안전한 코드 사용

안전하게 실행할 C# 코드 및 안전하지 않은 코드를 작성할 수 있어야 합니다. 안전한 코드를 사용하면 버퍼 오버런, 이상 포인터 및 기타 메모리 액세스 오류와 같은 오류 클래스를 피할 수 있습니다. 이러한 새 기능은 확인 가능한 안전한 코드의 기능을 확장합니다. 안전한 구문을 사용하여 더 많은 코드를 작성하도록 노력하세요. 이러한 기능을 사용하면 이 작업이 더 쉬워집니다.

다음 새로운 기능은 안전한 코드에 대해 향상된 성능의 테마를 지원합니다.

- 고정하지 않고 고정 필드에 액세스할 수 있습니다.
- `ref` 지역 변수를 다시 할당할 수 있습니다.
- `stackalloc` 배열에서 이니셜라이저를 사용할 수 있습니다.
- 패턴을 지원하는 모든 형식과 함께 `fixed` 문을 사용할 수 있습니다.
- 추가적인 제네릭 제약 조건을 사용할 수 있습니다.
- 매개 변수의 `in` 한정자는 인수가 참조에 의해 전달되지만 호출된 메서드에 의해 수정되지 않도록 지정합니다. `in` 한정자를 인수에 추가하는 것은 [소스 호환 가능 변경](version-update-considerations.md#source-compatible-changes)입니다.
- 메서드의 `ref readonly` 한정자는 메서드가 참조별 값을 반환하지만 해당 개체에 대한 쓰기를 허용하지 않음을 나타내기 위해 반환합니다. 반환이 값에 할당되는 경우 `ref readonly` 한정자를 추가하는 것은 [소스 호환 가능 변경](version-update-considerations.md#source-compatible-changes)입니다. 기존 `ref` 반환 문에 `readonly` 한정자를 추가하는 것은 [호환되지 않는 변경](version-update-considerations.md#incompatible-changes)입니다. 호출자가 `readonly` 한정자를 포함하도록 `ref` 지역 변수의 선언을 업데이트하도록 합니다.
- `readonly struct` 선언은 구조체가 변경 가능하지 않으며 `in` 매개 변수로서 멤버 메서드로 전달되어야 함을 나타냅니다. 기존 구조체 선언에 `readonly` 한정자를 추가하는 것은 [이진 호환 가능 변경](version-update-considerations.md#binary-compatible-changes)입니다.
- `ref struct` 선언은 구조체 유형이 관리되는 메모리에 직접 액세스하고 항상 스택에 할당되어야 함을 나타냅니다. 기존 `struct` 선언에 `ref` 한정자를 추가하는 것은 [호환되지 않는 변경](version-update-considerations.md#incompatible-changes)입니다. `ref struct`는 클래스의 멤버가 되거나 힙에 할당될 수 있는 다른 위치에서 사용될 수 없습니다.

[안전하고 효율적인 코드 작성](../write-safe-efficient-code.md)에서 모든 변경 내용을 자세히 읽을 수 있습니다.

### <a name="ref-locals-and-returns"></a>Ref local 및 return

이 기능을 통해 다른 곳에 정의된 변수에 대한 참조를 사용 및 반환하는 알고리즘이 가능해집니다. 한 가지 예는 큰 매트릭스를 사용하고 특정 특징을 가진 하나의 위치를 찾는 것입니다. 다음 메서드는 **참조** 를 행렬의 해당 스토리지에 반환합니다.

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

다음 코드에서처럼 반환 값을 `ref`로 선언하고 행렬에서 해당 값을 수정할 수 있습니다.

[!code-csharp[AssignRefReturn](~/samples/snippets/csharp/new-in-7/Program.cs#AssignRefReturn "Assign ref return")]

C# 언어에는 `ref` 로컬 및 반환을 잘못 사용하지 않도록 방지하는 몇 가지 규칙이 있습니다.

- `ref` 키워드를 메서드 서명 및 메서드의 모든 `return` 문에 추가해야 합니다.
  - 그러면 메서드가 메서드 전체에서 참조별로 반환되도록 합니다.
- `ref return`은 값 변수 또는 `ref` 변수에 할당될 수 있습니다.
  - 호출자는 반환 값을 복사할지 여부를 제어합니다. 반환 값을 할당할 때 `ref` 한정자를 생략하면 호출자가 스토리지에 대한 참조가 아닌 값의 복사본을 요청한다는 것을 나타냅니다.
- 표준 메서드 반환 값을 `ref` 로컬 변수에 할당할 수 없습니다.
  - 이로 인해 `ref int i = sequence.Count();` 같은 문이 허용되지 않습니다.
- 메서드 실행보다 길게 수명이 연장되지 않는 변수에 `ref`를 반환할 수 없습니다.
  - 즉, 로컬 변수 또는 비슷한 범위의 변수에 참조를 반환할 수 없습니다.
- `ref` local 및 return은 비동기 메서드와 함께 사용할 수 없습니다.
  - 컴파일러는 비동기 메서드가 반환될 때 참조된 변수가 최종 값으로 설정되었는지 여부를 알 수 없습니다.

ref local 및 ref return을 추가하면 값을 복사하거나 역참조 작업을 여러 번 수행하는 경우를 방지하여 더 효율적인 알고리즘이 가능해집니다.

`ref`를 반환 값에 추가하는 것은 [소스 호환 가능 변경](version-update-considerations.md#source-compatible-changes)입니다. 기존 코드는 컴파일되지만, 참조 반환 값은 할당 시 복사됩니다. 호출자는 반환 값 스토리지를 `ref` 지역 변수로 업데이트하여 반환을 참조로 저장해야 합니다.

이제 `ref` 지역 변수를 다시 할당하여 초기화된 후 다른 인스턴스를 참조할 수 있습니다. 이제 다음 코드가 컴파일됩니다.

```csharp
ref VeryLargeStruct refLocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

자세한 내용은 [`ref` 반환 및 `ref` 지역](../programming-guide/classes-and-structs/ref-returns.md)에 대한 아티클 및 [`foreach`](../language-reference/keywords/foreach-in.md)에 대한 아티클을 참조하세요.

자세한 내용은 [ref 키워드](../language-reference/keywords/ref.md) 문서를 참조하세요.

### <a name="conditional-ref-expressions"></a>조건부 `ref` 식

마지막으로, 조건식은 값 결과 대신 참조 결과를 생성할 수 있습니다. 예를 들어 다음을 작성하여 두 배열 중 하나의 첫 번째 요소에 대한 참조를 검색합니다.

```csharp
ref var r = ref (arr != null ? ref arr[0] : ref otherArr[0]);
```

`r` 변수는 `arr` 또는 `otherArr`의 첫 번째 값에 대한 참조입니다.

자세한 내용은 언어 참조에서 [조건부 연산자(?:)](../language-reference/operators/conditional-operator.md)를 참조하세요.

### <a name="in-parameter-modifier"></a>`in` 매개 변수 한정자

`in` 키워드는 기존 ref 및 out 키워드를 보완하여 참조로 인수를 전달합니다. `in` 키워드는 인수를 참조로 전달하도록 지정하지만 호출된 메서드는 값을 수정하지 않습니다.

다음 코드와 같이 값 또는 읽기 전용 참조로 전달되는 오버로드를 선언할 수 있습니다.

```csharp
static void M(S arg);
static void M(in S arg);
```

값으로 전달(이전 예제의 첫 번째 경우) 오버로드가 읽기 전용 참조로 전달 버전보다 더 효율적입니다. 읽기 전용 참조 인수를 사용하여 버전을 호출하려면 메서드를 호출할 때 `in` 한정자를 포함해야 합니다.

자세한 내용은 [`in` 매개 변수 한정자](../language-reference/keywords/in-parameter-modifier.md)에 대한 문서를 참조하세요.

### <a name="more-types-support-the-fixed-statement"></a>더 많은 형식이 `fixed` 문을 지원함

`fixed` 문은 제한된 형식 집합을 지원했습니다. C# 7.3부터 `ref T` 또는 `ref readonly T`를 반환하는 `GetPinnableReference()` 메서드를 포함하는 모든 형식이 `fixed`일 수 있습니다. 이 기능을 추가하면 `fixed`를 <xref:System.Span%601?displayProperty=nameWithType> 및 관련 형식과 함께 사용할 수 있습니다.

자세한 내용은 언어 참조에서 [`fixed` 문](../language-reference/keywords/fixed-statement.md) 문서를 참조하세요.

### <a name="indexing-fixed-fields-does-not-require-pinning"></a>`fixed` 필드 인덱싱에 고정이 필요하지 않음

다음 구조체를 고려합니다.

```csharp
unsafe struct S
{
    public fixed int myFixedField[10];
}
```

이전 버전의 C#에서는 `myFixedField`의 일부인 정수 중 하나에 액세스하려면 변수를 고정해야 했습니다. 이제 다음 코드는 별도의 `fixed` 문 안에 `p` 변수를 고정하지 않고 컴파일됩니다.

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        int p = s.myFixedField[5];
    }
}
```

`p` 변수는 `myFixedField`의 한 요소에 액세스합니다. 별도의 `int*` 변수를 선언할 필요가 없습니다. `unsafe` 컨텍스트는 여전히 필요합니다. 이전 버전의 C#에서는 두 번째 고정된 포인터를 선언해야 합니다.

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        fixed (int* ptr = s.myFixedField)
        {
            int p = ptr[5];
        }
    }
}
```

자세한 내용은 [`fixed` 문](../language-reference/keywords/fixed-statement.md)에 대한 문서를 참조하세요.

### <a name="stackalloc-arrays-support-initializers"></a>`stackalloc` 배열이 이니셜라이저를 지원함

초기화할 때 배열의 요소 값을 지정할 수 있었습니다.

```csharp
var arr = new int[3] {1, 2, 3};
var arr2 = new int[] {1, 2, 3};
```

이제 `stackalloc`로 선언된 배열에 동일한 구문을 적용할 수 있습니다.

```csharp
int* pArr = stackalloc int[3] {1, 2, 3};
int* pArr2 = stackalloc int[] {1, 2, 3};
Span<int> arr = stackalloc [] {1, 2, 3};
```

자세한 내용은 [`stackalloc` 연산자](../language-reference/operators/stackalloc.md) 문서를 참조하세요.

### <a name="enhanced-generic-constraints"></a>향상된 제네릭 제약 조건

이제 형식 매개 변수에 대한 기본 클래스 제약 조건으로 <xref:System.Enum?displayProperty=nameWithType> 또는 <xref:System.Delegate?displayProperty=nameWithType> 형식을 지정할 수 있습니다.

또한 새 `unmanaged` 제약 조건을 사용하여 형식 매개 변수가 nullable이 아닌 [비관리형 형식](../language-reference/builtin-types/unmanaged-types.md)이 되도록 지정할 수 있습니다.

자세한 내용은 [`where` 제네릭 제약 조건](../language-reference/keywords/where-generic-type-constraint.md) 및 [형식 매개 변수 제약 조건](../programming-guide/generics/constraints-on-type-parameters.md)에 대한 문서를 참조하세요.

기존 형식에 이러한 제약 조건을 추가하는 것은 [호환되지 않는 변경](version-update-considerations.md#incompatible-changes)입니다. 폐쇄형 제네릭 형식은 더 이상 이러한 새 제약 조건을 충족할 수 없습니다.

### <a name="generalized-async-return-types"></a>일반화된 비동기 반환 형식

비동기 메서드에서 `Task` 개체를 반환하면 특정 경로에 성능 병목 현상이 발생할 수 있습니다. `Task`는 참조 형식이므로 이를 사용하는 것은 개체 할당을 의미합니다. `async` 한정자로 선언된 메서드가 캐시된 결과를 반환하거나 동기적으로 완료된 경우 코드의 성능이 중요한 섹션에서 추가 할당에 상당한 시간이 소요될 수 있습니다. 연속 루프에서 이러한 할당이 발생하면 부담이 될 수 있습니다.

새로운 언어 기능을 통해 비동기 메서드 반환 형식이 `Task`, `Task<T>` 및 `void`에 제한되지 않게 되었습니다. 반환된 형식은 비동기 패턴을 충족해야 합니다. 즉, `GetAwaiter` 메서드에 액세스할 수 있어야 합니다. 한 가지 구체적인 예로 이 새로운 언어 기능을 사용할 수 있도록 `ValueTask` 형식이 .NET에 추가되었습니다.

[!code-csharp[UsingValueTask](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#UsingValueTask "Using ValueTask")]

> [!NOTE]
> <xref:System.Threading.Tasks.ValueTask%601> 형식을 사용하려면 NuGet 패키지 [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/)를 추가해야 합니다.

이 개선 사항은 라이브러리 작성자가 성능이 중요한 코드에서 `Task`를 할당하지 않도록 방지하는 데 유용합니다.

## <a name="new-compiler-options"></a>새로운 컴파일러 옵션

새로운 컴파일러 옵션은 C# 프로그램에 대한 새로운 빌드 및 DevOps 시나리오를 지원합니다.

### <a name="reference-assembly-generation"></a>참조 어셈블리 생성

*참조 전용 어셈블리* 를 생성하는 두 가지 새로운 컴파일러 옵션인 [**ProduceReferenceAssembly**](../language-reference/compiler-options/output.md#producereferenceassembly) 및 [**ProduceOnlyReferenceAssembly**](../language-reference/compiler-options/code-generation.md#produceonlyreferenceassembly)가 있습니다.
연결된 문서에서는 이러한 옵션과 참조 어셈블리를 보다 자세히 설명합니다.

### <a name="public-or-open-source-signing"></a>공개 또는 오픈 소스 서명

**PublicSign** 컴파일러 옵션은 공개 키를 사용하여 어셈블리에 서명하도록 컴파일러에 지시합니다. 어셈블리는 서명됨으로 표시되지만 시그니처는 공개 키에서 가져옵니다. 이 옵션을 사용하면 공개 키를 사용하여 오픈 소스 프로젝트에서 서명된 어셈블리를 빌드할 수 있습니다.

자세한 내용은 [**PublicSign** 컴파일러 옵션](../language-reference/compiler-options/security.md#publicsign) 문서를 참조하세요.

### <a name="pathmap"></a>pathmap

**PathMap** 컴파일러 옵션은 빌드 환경의 소스 경로를 매핑된 소스 경로로 바꾸도록 컴파일러에 지시합니다. **PathMap** 옵션은 컴파일러가 PDB 파일 또는 <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>에 대해 작성한 소스 경로를 제어합니다.

자세한 내용은 [**PathMap** 컴파일러 옵션](../language-reference/compiler-options/advanced.md#pathmap) 문서를 참조하세요.
