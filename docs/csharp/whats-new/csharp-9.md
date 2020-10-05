---
title: C# 9.0의 새로운 기능 - C# 가이드
description: C# 9.0의 새로운 기능을 살펴봅니다.
ms.date: 09/04/2020
ms.openlocfilehash: 6a0227b408b894fe450c2a6bb6017d9059d229c0
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247620"
---
# <a name="whats-new-in-c-90"></a>C# 9.0의 새로운 기능

C# 9.0은 다음 기능과 개선 사항을 C# 언어에 추가합니다.

- [레코드](#record-types)
- [Init 전용 setter](#init-only-setters)
- [최상위 문](#top-level-statements)
- [패턴 일치 개선 사항](#pattern-matching-enhancements)
- 원시 크기 정수
- 함수 포인터
- localsinit 플래그 내보내기 무시
- 대상으로 형식화된 새 식
- 정적 무명 함수
- 대상으로 형식화된 조건식
- 공변 반환 형식
- `foreach` 루프에 대한 확장 `GetEnumerator` 지원
- 람다 무시 항목 매개 변수
- 로컬 함수의 특성
- 모듈 이니셜라이저
- 부분 메서드에 대한 새로운 기능

C# 9.0은 **.NET 5**에서 지원됩니다. 자세한 내용은 [C# 언어 버전 관리](../language-reference/configure-language-version.md)를 참조하세요.

## <a name="record-types"></a>레코드 유형

C# 9.0에서는 같음에 대한 값 의미 체계를 제공하는 합성 메서드를 포함하는 참조 형식인 ***레코드 종류***가 도입되었습니다. 레코드는 기본적으로 변경할 수 없습니다.

레코드 종류를 사용하면 .NET에서 변경할 수 없는 참조 형식을 쉽게 만들 수 있습니다. 지금까지 .NET 형식은 크게 참조 형식(클래스 및 무명 형식 포함)과 값 형식(구조체 및 튜플 포함)으로 분류되었습니다. 변경할 수 없는 값 형식이 권장되지만, 변경 가능한 값 형식을 사용해도 오류가 자주 발생하지는 않습니다. 값 형식 변수에는 값이 포함되므로 값 형식을 메서드에 전달할 때 원래 데이터의 복사본이 변경됩니다.

변경할 수 없는 참조 형식에도 많은 이점이 있습니다. 이러한 이점은 공유 데이터를 사용하는 동시 프로그램에서 더욱 두드러지게 나타납니다. 아쉽게도 C#에서는 변경할 수 없는 참조 형식을 만들기 위한 상당한 추가 코드를 작성해야 했습니다. 레코드는 같음에 대한 값 의미 체계를 사용하는, 변경할 수 없는 참조 형식의 형식 선언을 제공합니다. 같음 및 해시 코드에 대한 합성 메서드는 해당 속성이 모두 동일한 경우 두 레코드가 같다고 간주합니다. 다음과 같은 정의를 고려해 보세요.

:::code language="csharp" source="snippets/whats-new-csharp9/RecordsExamples.cs" ID="RecordDefinition":::

레코드 정의에서 `FirstName` 및 `LastName`이라는 두 개의 읽기 전용 속성을 포함하는 `Person` 형식을 만듭니다. `Person` 형식은 참조 형식입니다. IL을 확인했다면 이 형식은 클래스입니다. 생성된 후에는 속성을 수정할 수 없다는 점에서 변경할 수 없는 형식입니다. 레코드 종류를 정의하면 컴파일러에서 다른 여러 메서드를 자동으로 합성합니다.

- 값 기반 같음 비교 메서드
- <xref:System.Object.GetHashCode> 재정의
- 멤버 복사 및 복제
- `PrintMembers` 및 <xref:System.Object.ToString>

레코드는 상속을 지원합니다. `Person`에서 파생된 새 레코드를 다음과 같이 선언할 수 있습니다.

:::code language="csharp" source="snippets/whats-new-csharp9/RecordsExamples.cs" ID="InheritedRecord":::

추가 파생을 방지하기 위해 레코드를 봉인할 수도 있습니다.

:::code language="csharp" source="snippets/whats-new-csharp9/RecordsExamples.cs" ID="SealedRecord":::

컴파일러는 위 메서드의 여러 버전을 합성합니다. 메서드 시그니처는 레코드 종류가 sealed인지 여부와 직접 기본 클래스가 object인지 여부에 따라 달라집니다. 레코드에는 다음 기능이 있어야 합니다.

- 같음은 값을 기반으로 하며 형식 일치 검사를 포함합니다. 예를 들어 `Student`는 두 레코드가 동일한 이름을 공유하는 경우에도 `Person`과 같을 수 없습니다.
- 레코드의 문자열 표현이 일관성 있게 자동으로 생성됩니다.
- 레코드에서 복사본 생성을 지원합니다. 올바른 복사본 생성에는 상속 계층 구조와 개발자가 추가한 속성이 포함되어야 합니다.
- 수정 내용과 함께 레코드를 복사할 수 있습니다. 복사 및 수정 작업에서 비파괴적 변경을 지원합니다.

컴파일러는 익숙한 `Equals` 오버로드, `operator ==`, `operator !=` 외에도 새 `EqualityContract` 속성을 합성합니다. 이 속성은 레코드 종류와 일치하는 `Type` 개체를 반환합니다. 기본 형식이 `object`이면 속성은 `virtual`이 됩니다. 기본 형식이 다른 레코드 종류이면 속성은 `override`가 됩니다. 레코드 종류가 `sealed`이면 속성은 `sealed`가 됩니다. 합성된 `GetHashCode`는 기본 형식 및 레코드 종류에 선언된 모든 속성과 필드의 `GetHashCode`를 사용합니다. 해당 합성 메서드는 상속 계층 구조 전체에 값 기반 같음을 적용합니다. 즉, `Student`는 동일한 이름을 가진 `Person`과 같다고 간주하지 않습니다. 레코드 종류 간에 공유되는 모든 속성이 같을 뿐 아니라 두 레코드 종류도 일치해야 합니다.

또한 레코드에는 합성 생성자와 복사본을 만들기 위한 “clone” 메서드가 있습니다. 합성 생성자에는 레코드 종류의 인수가 하나 있습니다. 합성 생성자는 레코드의 모든 속성에 동일한 값을 사용하여 새 레코드를 생성합니다. 레코드가 sealed이면 해당 생성자는 private이 되고, 그렇지 않으면 protected가 됩니다. 합성된 “clone” 메서드는 레코드 계층 구조의 복사본 생성을 지원합니다. 실제 이름이 컴파일러에서 생성되기 때문에 “clone” 용어는 따옴표 안에 표시됩니다. 레코드 종류에 `Clone`이라는 메서드를 만들 수는 없습니다. 합성된 “clone” 메서드는 가상 디스패치를 사용하여 복사되는 레코드 종류를 반환합니다. 컴파일러는 `record`의 액세스 한정자에 따라 “clone” 메서드에 대해 다른 한정자를 추가합니다.

- 레코드 종류가 `abstract`이면 “clone” 메서드도 `abstract`가 됩니다. 기본 형식이 `object`가 아니면 메서드도 `override`가 됩니다.
- 기본 형식이 `object`일 때 `abstract`가 아닌 레코드 종류의 경우:
  - 레코드가 `sealed`이면 “clone” 메서드에 한정자가 추가되지 않습니다(즉, `virtual`이 아님).
  - 레코드가 `sealed`가 아니면 “clone” 메서드는 `virtual`이 됩니다.
- 기본 형식이 `object`가 아닐 때 `abstract`가 아닌 레코드 종류의 경우:
  - 레코드가 `sealed`이면 “clone” 메서드도 `sealed`가 됩니다.
  - 레코드가 `sealed`가 아니면 “clone” 메서드는 `override`가 됩니다.

모든 규칙의 결과로, 모든 레코드 종류 계층 구조에서 같음이 일관되게 구현됩니다. 다음 예제와 같이 해당 속성과 종류가 동일하면 두 레코드는 같습니다.

:::code language="csharp" source="snippets/whats-new-csharp9/RecordsExamples.cs" ID="RecordsEquality":::

컴파일러는 인쇄 출력을 지원하는 두 가지 메서드인 <xref:System.Object.ToString> 재정의와 `PrintMembers`를 합성합니다. `PrintMembers`는 <xref:System.Text.StringBuilder?displayProperty=nameWithType>을 인수로 사용합니다. 레코드 종류의 모든 속성에 대해 쉼표로 구분된 속성 이름 및 값 목록이 추가됩니다. `PrintMembers`는 다른 레코드에서 파생된 모든 레코드에 대해 기본 구현을 호출합니다. <xref:System.Object.ToString> 재정의는 `PrintMembers`에서 생성된 문자열을 `{` 및 `}`로 묶어 반환합니다. 예를 들어 `Student`의 <xref:System.Object.ToString> 메서드는 다음 코드와 같이 `string`을 반환합니다.

```csharp
"Student { LastName = Wagner, FirstName = Bill, Level = 11 }"
```

지금까지 살펴본 예제에서는 일반적인 구문을 사용하여 속성을 선언합니다. ***위치 레코드***라는 보다 간결한 형식이 있습니다.  다음은 앞에서 위치 레코드로 정의된 세 가지 레코드 종류입니다.

:::code language="csharp" source="snippets/whats-new-csharp9/PositionalRecords.cs" ID="PositionalRecords":::

이 선언에서는 이전 버전과 동일한 기능을 만듭니다(다음 섹션에서 설명하는 몇 가지 추가 기능 포함). 레코드에서 메서드를 추가하지 않으므로 이 선언은 대괄호가 아닌 세미콜론으로 끝납니다. 본문을 추가하고 다른 메서드도 포함할 수 있습니다.

:::code language="csharp" source="snippets/whats-new-csharp9/PositionalRecords.cs" ID="RecordsWithMethods":::

컴파일러는 위치 레코드의 `Deconstruct` 메서드를 생성합니다. `Deconstruct` 메서드에는 레코드 종류의 모든 public 속성 이름과 일치하는 매개 변수가 있습니다. `Deconstruct` 메서드를 사용하여 레코드를 구성 요소 속성으로 분해할 수 있습니다.

:::code language="csharp" source="snippets/whats-new-csharp9/PositionalRecords.cs" ID="DeconstructRecord":::

마지막으로, 레코드는 ***with-expression***을 지원합니다. ***with-expression***은 컴파일러에 레코드 복사본을 만들지만 *with*에 지정된 속성을 수정하도록 지시합니다.

:::code language="csharp" source="snippets/whats-new-csharp9/PositionalRecords.cs" ID="Wither":::

위 줄에서는 `LastName` 속성이 `person`의 복사본이고 `FirstName`이 “Paul”인 새 `Person` 레코드를 만듭니다. with-expression에 속성을 원하는 개수만큼 설정할 수 있습니다.  “clone” 메서드를 제외한 모든 합성 멤버를 직접 작성할 수 있습니다. 레코드 종류에 합성 메서드의 시그니처와 일치하는 메서드가 있는 경우 해당 메서드는 컴파일러에서 합성되지 않습니다. 앞의 `Dog` 레코드 예제에는 수동 코딩된 <xref:System.String.ToString> 메서드가 예제로 포함되어 있습니다.

## <a name="init-only-setters"></a>Init 전용 setter

***Init 전용 setter***는 개체의 멤버를 초기화하는 일관성 있는 구문을 제공합니다. 속성 이니셜라이저를 사용하면 어떤 값이 어떤 속성을 설정하는지 명확하게 파악할 수 있습니다. 단점은 해당 속성이 설정 가능해야 한다는 것입니다. C# 9.0부터 속성 및 인덱서에 대해 `set` 접근자 대신 `init` 접근자를 만들 수 있습니다. 호출자는 속성 이니셜라이저 구문을 사용하여 생성 식에서 해당 값을 설정할 수 있지만, 생성이 완료되고 나면 readonly 속성이 됩니다. Init 전용 setter는 상태 변경 창을 제공합니다. 이 창은 생성 단계가 끝날 때 닫힙니다. 속성 이니셜라이저 및 with-expression을 비롯한 모든 초기화가 완료되면 생성 단계가 사실상 끝납니다.

위치 레코드에 대한 앞의 예제에서는 init 전용 setter를 사용하여 with expression으로 속성을 설정하는 방법을 보여 줍니다. 작성하는 모든 종류에서 init 전용 setter를 선언할 수 있습니다. 예를 들어 다음 구조체는 기상 관측 구조체를 정의합니다.

:::code language="csharp" source="snippets/whats-new-csharp9/WeatherObservation.cs" ID="DeclareWeatherObservation":::

호출자는 불변성을 유지하면서 속성 이니셜라이저 구문을 사용하여 값을 설정할 수 있습니다.

:::code language="csharp" source="snippets/whats-new-csharp9/WeatherObservation.cs" ID="UseWeatherObservation":::

하지만 초기화 후 관측을 변경할 경우 초기화 외부에서 init 전용 속성에 할당하여 오류가 발생합니다.

```csharp
// Error! CS8852.
now.TemperatureInCelsius = 18;
```

init 전용 setter는 파생 클래스에서 기본 클래스 속성을 설정하는 데 유용할 수 있습니다. 기본 클래스의 도우미를 통해 파생 속성을 설정할 수도 있습니다. 위치 레코드는 init 전용 setter를 사용하여 속성을 선언합니다. 해당 setter는 with-expression에 사용됩니다. 정의하는 모든 `class` 또는 `struct`에 대해 Init 전용 setter를 선언할 수 있습니다.

## <a name="top-level-statements"></a>최상위 문

***최상위 문***은 많은 애플리케이션에서 불필요한 공식 절차를 제거합니다. 정식 “Hello World!” 프로그램을 고려해 보세요.

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

작업을 수행하는 코드 줄은 1줄뿐입니다. 최상위 문을 사용하면 모든 상용구를 `using` 문과 작업을 수행하는 1줄로 바꿀 수 있습니다.

:::code language="csharp" source="snippets/whats-new-csharp9/Program.cs" ID="TopLevelStatements":::

1줄 프로그램을 원하는 경우 `using` 지시문을 제거하고 정규화된 형식 이름을 사용할 수 있습니다.

```csharp
System.Console.WriteLine("Hello World!");
```

애플리케이션의 한 파일에서만 최상위 문을 사용할 수 있습니다. 컴파일러가 여러 소스 파일에서 최상위 문을 발견할 경우 오류가 발생합니다. 일반적으로 `Main` 메서드인 선언된 프로그램 진입점 메서드와 최상위 문을 결합하는 경우에도 오류가 발생합니다. 따라서 일반적으로 `Program` 클래스의 `Main` 메서드에 있는 문이 한 파일에 포함되어 있다고 생각할 수 있습니다.  

이 기능의 가장 일반적인 용도 중 하나는 교육 자료를 만드는 경우입니다. 초급 C# 개발자가 1~2줄의 코드로 정식 “Hello World!”를 작성할 수 있습니다. 추가 공식 절차가 필요하지 않습니다. 그러나 숙련된 개발자도 이 기능의 다양한 용도를 발견하게 됩니다. 최상위 수준 문을 통해 Jupyter Notebook에서 제공하는 것과 비슷한 스크립트 유사 환경을 실험용으로 사용할 수 있습니다. 최상위 수준 문은 작은 콘솔 프로그램 및 유틸리티에 적합합니다. Azure 함수는 최상위 문의 이상적인 사용 사례입니다.

가장 중요한 점은 최상위 문이 애플리케이션의 범위나 복잡성을 제한하지 않는다는 것입니다. 해당 문은 모든 .NET 클래스에 액세스하거나 사용할 수 있습니다. 또한 명령줄 인수나 반환 값의 사용을 제한하지 않습니다. 최상위 문은 args라는 문자열 배열에 액세스할 수 있습니다. 최상위 문에서 정수 값을 반환하는 경우 해당 값은 합성된 `Main` 메서드의 정수 반환 코드가 됩니다. 최상위 문에 비동기 식을 포함할 수 있습니다. 이 경우 합성 진입점은 `Task` 또는 `Task<int>`를 반환합니다.

## <a name="pattern-matching-enhancements"></a>패턴 일치 개선 사항

C# 9에는 새로운 패턴 일치 개선 사항이 포함되어 있습니다.

- ***형식 패턴***은 변수를 형식과 일치시킵니다.
- ***괄호로 묶인 패턴***은 패턴 조합의 우선 순위를 적용하거나 강조합니다.
- ***결합 `and` 패턴***은 두 패턴이 모두 일치해야 합니다.
- ***분리 `or` 패턴***은 패턴 중 하나가 일치해야 합니다.
- ***부정 `not` 패턴***은 패턴이 일치하지 않아야 합니다.
- ***관계형 패턴***은 입력과 지정된 상수 간에 작음, 큼, 작거나 같음, 크거나 같음 또는 같음 관계가 있어야 합니다.

새로운 패턴은 패턴 구문을 보강합니다. 이 예제를 참조하십시오.

:::code language="csharp" source="snippets/whats-new-csharp9/PatternUtilities.cs" ID="IsLetterPattern":::

또는 선택적 괄호를 사용하여 `and`에 `or`보다 높은 우선 순위가 있음을 명확하게 지정합니다.

:::code language="csharp" source="snippets/whats-new-csharp9/PatternUtilities.cs" ID="IsLetterOrSeparatorPattern":::

가장 일반적인 용도 중 하나는 새로운 null 검사 구문입니다.

```csharp
if (e is not null)
{
    // ...
}
```

`is` 패턴 식, `switch` 식, 중첩 패턴, `switch` 문의 `case` 레이블 패턴 등 패턴이 허용되는 모든 컨텍스트에서 새로운 패턴을 사용할 수 있습니다.

## <a name="performance-and-interop"></a>성능 및 interop

원시 크기 정수, 함수 포인터, `localsinit` 플래그 생략의 세 가지 새로운 기능을 통해 고성능이 필요한 하위 수준 라이브러리 및 네이티브 interop 지원이 향상되었습니다.

원시 크기 정수인 `nint` 및 `nuint`는 정수 형식입니다. 기본 형식 <xref:System.IntPtr?displayProperty=nameWithType> 및 <xref:System.UIntPtr?displayProperty=nameWithType>으로 표현됩니다. 컴파일러는 해당 형식의 추가 변환과 연산을 네이티브 정수 형식으로 표시합니다. `MinValue`가 `0`인 `nuint.MinValue`를 제외하고, 원시 크기 정수에는 `MaxValue` 또는 `MinValue` 상수가 없습니다. 다른 값은 대상 머신의 정수 원시 크기에 따라 달라지므로 상수로 표현할 수 없습니다. 다음 범위에서 `nint`의 상수 값을 사용할 수 있습니다. [`int.MinValue` .. `int.MaxValue`]. 다음 범위에서 `nuint`의 상수 값을 사용할 수 있습니다. [`uint.MinValue` .. `uint.MaxValue`]. 컴파일러는 <xref:System.Int32?displayProperty=nameWithType> 및 <xref:System.UInt32?displayProperty=nameWithType> 형식을 사용하여 모든 단항 및 이진 연산자에 대해 상수 정리를 수행합니다. 결과가 32비트에 맞지 않으면 런타임에 연산이 실행되고 상수로 간주하지 않습니다. 정수 연산이 광범위하게 사용되고 가장 빠른 성능이 필요한 시나리오에서는 원시 크기 정수를 사용하여 성능을 향상할 수 있습니다.

함수 포인터는 IL opcode `ldftn` 및 `calli`에 액세스하는 편리한 구문을 제공합니다. 새로운 `delegate*` 구문을 사용하여 함수 포인터를 선언할 수 있습니다. `delegate*` 형식은 포인터 형식입니다. `delegate*` 형식을 호출하면 `Invoke()` 메서드에서 `callvirt`를 사용하는 대리자와는 달리 `calli`가 사용됩니다. 호출 구문은 동일합니다. 함수 포인터 호출은 `managed` 호출 규칙을 사용합니다. `delegate*` 구문 뒤에 `unmanaged` 키워드를 추가하여 `unmanaged` 호출 규칙을 사용하도록 선언합니다. `delegate*` 선언에서 특성을 사용하여 다른 호출 규칙을 지정할 수 있습니다.

마지막으로, <xref:System.Runtime.CompilerServices.SkipLocalsInitAttribute?displayProperty=nameWithType>을 추가하여 컴파일러에 `localsinit` 플래그를 내보내지 않도록 지시할 수 있습니다. 이 플래그는 모든 지역 변수를 0으로 초기화하도록 CLR에 지시합니다. `localsinit` 플래그는 1.0부터 C#의 기본 동작이었습니다. 그러나 0으로 초기화를 추가로 수행할 경우 일부 시나리오에서 성능에 상당한 영향을 미칠 수 있습니다. 특히, `stackalloc`를 사용하는 경우에 해당합니다. 이 경우에는 <xref:System.Runtime.CompilerServices.SkipLocalsInitAttribute>를 추가할 수 있습니다. 단일 메서드 또는 속성이나 `class`, `struct`, `interface` 또는 모듈에 추가할 수도 있습니다. 이 특성은 `abstract` 메서드에는 영향을 주지 않고, 구현과 관련해서 생성된 코드에 적용됩니다.

위의 기능은 일부 시나리오에서 성능을 향상할 수 있습니다. 채택 전과 후에 모두 신중하게 벤치마킹한 후에만 사용해야 합니다. 원시 크기 정수를 사용하는 코드는 여러 대상 플랫폼에서 여러 정수 크기로 테스트해야 합니다. 다른 기능에는 안전하지 않은 코드가 필요합니다.

## <a name="fit-and-finish-features"></a>기능 마무리

다른 많은 기능을 통해 코드를 보다 효율적으로 작성할 수 있습니다. C# 9.0에서는 생성된 개체의 형식이 이미 알려진 경우 새 식에서 형식을 생략할 수 있습니다. 가장 일반적인 용도는 필드 선언입니다.

:::code language="csharp" source="snippets/whats-new-csharp9/FitAndFinish.cs" ID="WeatherStationField":::

메서드에 매개 변수로 전달할 새 개체를 만들어야 하는 경우 대상 유형 new를 사용할 수도 있습니다. 다음 시그니처를 사용하는 `ForecastFor()` 메서드를 고려해 보세요.

:::code language="csharp" source="snippets/whats-new-csharp9/FitAndFinish.cs" ID="ForecastSignature":::

다음과 같이 메서드를 호출할 수 있습니다.

:::code language="csharp" source="snippets/whats-new-csharp9/FitAndFinish.cs" ID="TargetTypeNewArgument":::

이 기능의 다른 유용한 용도는 init 전용 속성과 결합하여 새 개체를 초기화하는 것입니다.

:::code language="csharp" source="snippets/whats-new-csharp9/FitAndFinish.cs" ID="InitWeatherStation":::

`return new();` 식을 사용하여 기본 생성자에서 만든 인스턴스를 반환할 수 있습니다.

유사한 기능은 [조건식](../language-reference/operators/conditional-operator.md)의 대상 유형 확인을 개선합니다. 이 변경 내용이 도입되면서 두 식 간에 암시적 변환을 포함할 수는 없지만 두 식에 모두 대상 유형으로의 암시적 변환을 사용할 수 있습니다. 이 변경 내용을 발견하지 못할 수도 있습니다. 이전에 캐스트가 필요했거나 컴파일되지 않던 일부 조건식이 이제 작동할 뿐입니다.

C# 9.0부터 [람다](../language-reference/operators/lambda-expressions.md) 식 또는 [무명 메서드](../language-reference/operators/delegate-operator.md)에 `static` 한정자를 추가할 수 있습니다. 정적 람다 식은 `static` 로컬 함수와 유사합니다. 정적 람다 또는 무명 메서드는 지역 변수나 인스턴스 상태를 캡처할 수 없습니다. `static` 한정자는 실수에 의한 다른 변수 캡처를 방지합니다.

공변 반환 형식은 재정의된 함수의 반환 형식에 대한 유연성을 제공합니다. 재정의된 가상 함수는 기본 클래스 메서드에 선언된 반환 형식에서 파생된 형식을 반환할 수 있습니다. 이 함수는 레코드나 가상 클론 또는 팩터리 메서드를 지원하는 기타 형식에 유용할 수 있습니다.

또한 [`foreach` 루프](../language-reference/keywords/foreach-in.md)는 `foreach` 패턴을 충족하는 확장 메서드 `GetEnumerator`를 인식하고 사용합니다. 이렇게 변경함으로써 `foreach`는 비동기 패턴과 같은 다른 패턴 기반 생성 및 패턴 기반 분해와 일치하게 됩니다. 실제로 이 변경은 모든 형식에 `foreach` 지원을 추가할 수 있음을 의미합니다. 설계상 개체를 열거하는 것이 적합한 경우로 사용을 제한해야 합니다.

다음으로, 무시 항목을 람다 식에 대한 매개 변수로 사용할 수 있습니다. 이 편리한 기능을 사용하면 인수 이름을 지정할 필요가 없으며, 컴파일러에서 인수를 사용하지 않을 수 있습니다. 모든 인수에 `_`을 사용합니다. 자세한 내용은 [람다 식](../language-reference/operators/lambda-expressions.md) 문서의 [람다 식 입력 매개 변수](../language-reference/operators/lambda-expressions.md#input-parameters-of-a-lambda-expression) 섹션을 참조하세요.

마지막으로, 이제 로컬 함수에 특성을 적용할 수 있습니다. 예를 들어 로컬 함수에 null 허용 특성 주석을 적용할 수 있습니다.

## <a name="support-for-code-generators"></a>코드 생성기 지원

두 가지 최종 기능은 C# 코드 생성기를 지원합니다. C# 코드 생성기는 Roslyn 분석기나 코드 수정 사항과 유사하게, 직접 작성할 수 있는 구성 요소입니다. 차이점은 코드 생성기의 경우 컴파일 프로세스의 일부로 코드를 분석하고 새 소스 코드 파일을 작성한다는 것입니다. 일반적인 코드 생성기는 코드에서 특성이나 다른 규칙을 검색합니다.

코드 생성기는 Roslyn 분석 API를 사용하여 특성이나 다른 코드 요소를 읽습니다. 해당 정보를 통해 컴파일에 새 코드를 추가합니다. 소스 생성기는 코드를 추가할 수만 있고 컴파일의 기존 코드를 수정할 수는 없습니다.

코드 생성기에 대해 추가된 두 가지 기능은 ***부분 메서드 구문*** 확장 및 ***모듈 이니셜라이저***입니다. 먼저 부분 메서드 변경 내용입니다. C# 9.0 이전에는 부분 메서드가 `private`이지만 액세스 한정자를 지정하거나 `void` 반환 또는 `out` 매개 변수를 사용할 수 없습니다. 이 제한 사항 때문에, 메서드 구현을 제공하지 않을 경우 컴파일러에서 부분 메서드 호출을 모두 제거합니다. C# 9.0에서는 해당 제한 사항이 제거되었지만 부분 메서드 선언에 구현이 필요합니다. 코드 생성기에서 이 구현을 제공할 수 있습니다. 호환성이 손상되는 변경을 방지하기 위해 컴파일러에서 액세스 한정자가 없는 부분 메서드는 이전 규칙을 따른다고 간주합니다. 부분 메서드에 `private` 액세스 한정자가 포함되어 있으면 새 규칙에 따라 부분 메서드가 제어됩니다.

코드 생성기의 두 번째 새로운 기능은 ***모듈 이니셜라이저***입니다. 모듈 이니셜라이저는 <xref:System.Runtime.CompilerServices.ModuleInitializerAttribute> 특성이 연결된 메서드입니다. 이 메서드는 어셈블리를 로드할 때 런타임에서 호출됩니다. 모듈 이니셜라이저 메서드는 다음과 같아야 합니다.

- 정적이어야 함
- 매개 변수가 없어야 함
- void를 반환해야 함
- 제네릭 메서드가 아니어야 함
- 제네릭 클래스에 포함되지 않아야 함
- 포함하는 모듈에서 액세스할 수 있어야 함

마지막 글머리 기호 사항은 사실상, 메서드와 메서드를 포함하는 클래스가 internal 또는 public이어야 함을 의미합니다. 메서드는 로컬 함수가 될 수 없습니다.
