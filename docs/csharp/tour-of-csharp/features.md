---
title: C#주요 언어 영역 둘러보기
description: C#을 처음 사용하시나요? 언어의 기본 사항에 대해 알아봅니다. 이 문서에는 주 언어 기능에 대한 설문 조사가 포함되어 있습니다.
ms.date: 08/06/2020
ms.openlocfilehash: 943701b544dd3495fa2286e804e2566da146cb45
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99216657"
---
# <a name="major-language-areas"></a>주 언어 영역

## <a name="arrays-collections-and-linq"></a>배열, 컬렉션 및 LINQ

C#과 .NET은 여러 컬렉션 형식을 제공합니다. 배열에는 언어에 의해 정의된 구문이 있습니다. 제네릭 컬렉션 형식은 <xref:System.Collections.Generic?displayProperty=fullName> 네임스페이스에 나열되어 있습니다. 특수 컬렉션에는 스택 프레임에서 연속 메모리에 액세스하기 위한 <xref:System.Span%601?displayProperty=nameWithType>와 관리되는 힙에서 연속 메모리에 액세스하기 위한 <xref:System.Memory%601?displayProperty=nameWithType>가 있습니다. 배열, <xref:System.Span%601>, <xref:System.Memory%601>를 포함하는 모든 컬렉션은 반복을 위한 통일된 원칙을 공유합니다. 사용자는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 인터페이스를 사용합니다. 이 통일된 원칙은 모든 컬렉션 형식을 LINQ 쿼리 또는 기타 알고리즘과 함께 사용할 수 있음을 의미합니다. 메서드는 <xref:System.Collections.Generic.IEnumerable%601>를 사용하여 작성하며, 이러한 알고리즘은 모든 컬렉션에서 작동합니다.

### <a name="arrays"></a>배열

[**배열**](../programming-guide/arrays/index.md)은 계산된 인덱스를 통해 액세스되는 여러 변수를 포함하는 데이터 구조입니다.* 배열에 포함된 변수, 즉 배열의 요소라고도 하는 배열은 모두 같은 형식이며, 이 형식을 배열의 요소 형식이라고 합니다.

배열 형식은 참조 형식이고 배열 변수의 선언은 배열 인스턴스에 대한 참조를 위한 공간을 설정합니다. 실제 배열 인스턴스는 `new` 연산자를 사용하여 런타임에 동적으로 만들어집니다. `new` 연산은 새 배열 인스턴스의 길이(인스턴스 수명 동안 고정됨)를 지정합니다. 배열 요소의 인덱스 범위는 `0`에서 `Length - 1` 사이입니다. `new` 연산자는 배열의 요소를 모든 숫자 형식에 대해 0이고, 모든 참조 형식에 대해 `null`인 기본값으로 자동으로 초기화합니다.

다음 예제에서는 `int` 요소의 배열을 만들고 배열을 초기화하고 배열의 콘텐츠를 출력합니다.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="ArraysSample":::

이 예제에서는 1차원 배열을 만들고 작업을 수행합니다. C#에서는 다차원 배열도 지원합니다. 배열 형식의 ‘순위’라고도 하는 배열 형식의 차원 수는 배열 형식의 대괄호 사이에 사용된 쉼표 수에 1을 더한 값입니다. 다음 예제에서는 1차원, 2차원 및 3차원 배열을 각각 할당합니다.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="DeclareArrays":::

`a1` 배열에는 10개의 요소가 들어 있고 `a2` 배열에는 50(10 × 5)개의 요소가 들어 있고 `a3` 배열에는 100(10 × 5 × 2)개 요소가 들어 있습니다.
배열의 요소 형식은 배열 형식을 비롯한 어떤 형식도 될 수 있습니다. 배열 형식의 요소가 있는 배열을 가변 배열이라고도 합니다. 요소 배열의 길이가 항상 동일할 필요는 없기 때문입니다. 다음 예제에서는 `int` 배열의 배열을 할당합니다.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="ArrayOfArrays":::

첫 번째 줄은 형식이 `int[]`이고 초기 값이 `null`인 3개 요소가 있는 배열을 만듭니다. 다음 줄은 가변 길이의 개별 배열 인스턴스에 대한 참조로 3개 요소를 초기화합니다.

`new` 연산자는 구분 기호 `{`와 `}` 사이에 쓰인 식 목록인 배열 이니셜라이저를 사용하여 배열 요소의 초기 값이 지정되도록 허용합니다. 다음 예제에서는 3개 요소로 `int[]`를 할당하고 초기화합니다.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="InitializeArray":::

배열의 길이는 `{`와 `}` 사이에 있는 식의 개수에서 유추됩니다. 배열 형식을 다시 시작할 필요가 없도록 배열 초기화를 더 줄일 수 있습니다.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="InitializeShortened":::

앞의 두 예제는 다음 코드와 동일합니다.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="InitializeGenerated":::

`foreach` 문은 컬렉션의 요소를 열거하는 데 사용할 수 있습니다. 다음 코드는 앞에 나온 예제의 배열을 열거합니다.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="EnumerateArray":::

`foreach` 문은 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 사용하므로 모든 컬렉션에서 사용할 수 있습니다.

## <a name="string-interpolation"></a>문자열 보간

C# [문자열 보간](../language-reference/tokens/interpolated.md)을 사용하면 결과가 서식 문자열에 배치되는 식을 정의하여 문자열에 서식을 지정할 수 있습니다. 예를 들어 다음 예제에서는 날씨 데이터 세트에서 지정된 날짜의 온도를 출력합니다.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="StringInterpolation":::

보간된 문자열은 `$` 토큰을 사용하여 선언됩니다. 문자열 보간은 `{`와 `}` 사이의 식을 계산한 다음 결과를 `string`으로 변환하고 대괄호 사이에 있는 텍스트를 식의 문자열 결과로 바꿉니다. 첫 번째 식 `{weatherData.Date:MM-DD-YYYY}`의 `:`은 서식 문자열을 지정합니다. 앞의 예제에서는 “MM-DD_YYYY” 형식으로 출력해야 할 날짜를 지정합니다.

## <a name="pattern-matching"></a>패턴 일치

C# 언어는 개체 상태를 쿼리하고 이 상태에 따라 코드를 실행하는 [**패턴 일치**](../pattern-matching.md) 식을 제공합니다.* 형식과 속성 및 필드의 값을 검사하여 수행할 동작을 결정할 수 있습니다. `switch` 식은 패턴 일치를 위한 기본 식입니다.

## <a name="delegates-and-lambda-expressions"></a>대리자와 람다 식

[대리자 형식](../delegates-overview.md)은 특정 매개 변수 목록 및 반환 형식이 있는 메서드에 대한 참조를 나타냅니다. 대리자는 메서드를 변수에 할당되고 매개 변수로 전달될 수 있는 엔터티로 취급할 수 있도록 합니다. 대리자는 다른 언어의 함수 포인터와 개념이 비슷하지만 함수 포인터와 달리 대리자는 개체 지향적이며 형식이 안전한 방식입니다.

다음 예제에서는 `Function`라는 대리자 형식을 선언하고 사용합니다.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="DelegateExample":::

`Function` 대리자 형식의 인스턴스는 `double` 인수를 사용하고 `double` 값을 반환하는 메서드를 참조할 수 있습니다. `Apply` 메서드는 `double[]`의 요소에 지정된 `Function`을 적용하여 결과가 있는 `double[]`을 반환합니다. `Main` 메서드에서 `Apply`는 세 가지 다른 함수를 `double[]`에 적용하는 데 사용됩니다.

대리자는 정적 메서드(예: 이전 예제의 `Square` 또는 `Math.Sin`) 또는 인스턴스 메서드(예: 이전 예제의 `m.Multiply`)를 참조할 수 있습니다. 인스턴스 메서드를 참조하는 대리자는 특정 개체도 참조하며, 인스턴스 메서드가 대리자를 통해 호출되는 경우 해당 개체도 이 호출에서 `this`가 됩니다.

선언 즉시 만들어지는 “인라인 메서드”인 익명 함수를 사용하여 대리자를 만들 수도 있습니다. 익명 함수는 주변 메서드의 지역 변수를 볼 수 있습니다. 다음 예제에서는 클래스를 만들지 않습니다.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="UseDelegate":::

대리자는 해당 대리자가 참조하는 메서드의 클래스를 알지 못하고 클래스가 무엇인지와 관계없이 작동합니다. 중요한 것은 참조되는 메서드가 대리자와 동일한 매개 변수와 반환 형식을 갖는다는 사실입니다.

## <a name="async--await"></a>async / await

C#은 두 개의 키워드 `async`와 `await`로 비동기 프로그램을 지원합니다. 메서드를 비동기로 선언하려면 메서드 선언에 `async` 한정자를 추가합니다. `await` 연산자는 컴파일러에 결과가 완료될 때까지 비동기적으로 대기하도록 지시합니다. 제어는 호출자에게 반환되고, 메서드는 비동기 작업의 상태를 관리하는 구조체를 반환합니다. 구조체는 일반적으로 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>이지만, awaiter 패턴을 지원하는 어떤 형식도 될 수 있습니다. 이러한 기능을 사용하면 동기식으로 읽히지만 비동기적으로 실행되는 코드를 작성할 수 있습니다. 예를 들어 다음 코드는 [Microsoft docs](/)의 홈페이지를 다운로드합니다.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="AsyncExample":::

이 작은 샘플은 비동기 프로그래밍의 주요 특징을 보여 줍니다.

- 메서드 선언에는 `async` 한정자가 포함됩니다.
- 메서드의 본문은 `GetByteArrayAsync` 메서드의 반환을 `await`합니다.
- `return` 문에 지정된 형식은 메서드의 `Task<T>` 선언에 있는 형식 인수와 일치합니다. (`Task`를 반환하는 메서드는 `return` 문을 인수 없이 사용합니다.)

## <a name="attributes"></a>특성

C# 프로그램의 형식, 멤버 및 기타 엔터티는 동작의 특정 측면을 제어하는 한정자를 지원합니다. 예를 들어 메서드의 액세스 가능성은 `public`, `protected`, `internal` 및 `private` 한정자를 사용하여 제어됩니다. C#은 선언적 정보의 사용자 정의 형식을 프로그램 엔터티에 연결하고 런타임에 검색할 수 있도록 이러한 기능을 일반화합니다. 프로그램은 [특성*](../programming-guide/concepts/attributes/index.md)을 정의하고 사용하여 이러한 추가적인 선언적 정보를 지정합니다.

다음 예제에서는 관련 설명서에 대한 링크를 제공하기 위해 프로그램 엔터티에 배치될 수 있는 `HelpAttribute` 특성을 선언합니다.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="DefineAttribute":::

모든 특성 클래스는 .NET 라이브러리에서 제공하는 <xref:System.Attribute> 기본 클래스에서 파생됩니다. 연결된 선언 바로 앞에 대괄호로 묶은 특성 이름을 인수와 함께 적용할 수 있습니다. 특성 이름이 `Attribute`로 끝나는 경우 특성이 참조될 때 이름의 해당 부분을 생략해도 됩니다. 예를 들어 `HelpAttribute`는 다음과 같이 사용할 수 있습니다.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="UseAttributes":::

이 예제에서는 `HelpAttribute`를 `Widget` 클래스에 연결합니다. 그런 후 다른 `HelpAttribute`를 클래스의 `Display` 메서드에 추가합니다. 특성 클래스의 공용 생성자는 프로그램 엔터티에 특성을 추가할 때 제공해야 하는 정보를 제어합니다. 특성 클래스의 공용 읽기/쓰기 속성을 참조하여 추가 정보를 제공할 수 있습니다(예: 앞에 나온 `Topic` 속성 참조).

특성에 의해 정의된 메타데이터는 리플렉션을 사용하여 런타임 시 읽고 조작할 수 있습니다. 이 기술을 사용하여 특정 특성이 요청되면 특성 클래스에 대한 생성자가 프로그램 소스에 제공된 정보와 함께 호출됩니다. 결과 특성 인스턴스가 반환됩니다. 속성을 통해 추가 정보를 제공한 경우 해당 속성은 특성 인스턴스가 반환되기 전에 지정된 값으로 설정됩니다.

다음 코드 샘플에서는 `Widget` 클래스와 해당 `Display` 메서드에 연결된 `HelpAttribute` 인스턴스를 가져오는 방법을 보여줍니다.

:::code language="csharp" source="./snippets/shared/Features.cs" ID="ReadAttributes":::

## <a name="learn-more"></a>자세한 정보

여러 [자습서](../tutorials/index.md)를 통해 C#에 대해 자세히 알아볼 수 있습니다.

>[!div class="step-by-step"]
>[이전](program-building-blocks.md)
