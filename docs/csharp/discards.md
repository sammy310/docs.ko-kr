---
title: 무시 항목 - C# 가이드
description: 할당되지 않은 무시 가능한 변수인 무시 항목에 대한 C#의 지원과 무시 항목을 사용할 수 있는 방법에 관해 설명합니다.
ms.technology: csharp-fundamentals
ms.date: 09/22/2020
ms.openlocfilehash: eefa81d3bd8d56c9296e01533aaf93c4725323a3
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104954"
---
# <a name="discards---c-guide"></a>무시 항목 - C# 가이드

C# 7.0부터 C#에서는 애플리케이션 코드에서 의도적으로 사용되지 않는 자리 표시자 변수인 무시 항목을 지원합니다. 무시 항목은 할당되지 않은 변수에 해당하므로 값을 가지지 않습니다. 무시 항목은 컴파일러 및 코드를 읽는 다른 사용자에게 의도를 전달합니다. 식의 결과를 무시하라는 것입니다. 식의 결과, 하나 이상의 튜플 식 멤버, 메서드에 대한 `out` 매개 변수 또는 패턴 일치 식의 대상을 무시해야 할 수 있습니다.

단일 무시 변수만 있으므로 해당 변수를 스토리지에 할당하지 못할 수도 있습니다. 무시 항목은 메모리 할당을 줄일 수 있습니다. 무시 항목은 코드의 의도를 명확하게 합니다. 또한 코드의 가독성 및 유지 관리를 향상시킵니다.

변수가 무시 항목임을 지정하려면 변수에 밑줄(`_`)을 이름으로 할당합니다. 예를 들어 다음 메서드 호출은 첫 번째 및 두 번째 값이 무시 항목인 튜플을 반환합니다. `area`는 이전에 선언된 변수로, `GetCityInformation`에서 반환된 세 번째 구성 요소로 설정됩니다.

```csharp
(_, _, area) = city.GetCityInformation(cityName);
```

C# 9.0부터 무시 항목을 사용하여 람다 식의 사용하지 않는 입력 매개 변수를 지정할 수 있습니다. 자세한 내용은 [람다 식](language-reference/operators/lambda-expressions.md) 문서의 [람다 식 입력 매개 변수](language-reference/operators/lambda-expressions.md#input-parameters-of-a-lambda-expression) 섹션을 참조하세요.

`_`이 유효한 무시 항목인 경우, 해당 값을 검색하거나 할당 작업에서 사용하려고 하면 “이름 ‘\_’이 현재 컨텍스트에 없습니다.”라는 컴파일러 오류 CS0301이 생성됩니다. 이 오류는 `_`에 값이 할당되어 있지 않고 스토리지 위치도 할당되어 있지 않을 수 있기 때문입니다. 실제 변수인 경우에는 이전 예제에서처럼 2개 이상의 값을 무시할 수 없습니다.

## <a name="tuple-and-object-deconstruction"></a>튜플 및 개체 분해

무시 항목은 튜플을 작업할 때 애플리케이션 코드에 튜플 요소 중 일부만 사용하고 일부는 무시하는 경우에 유용합니다. 예를 들어, 다음 `QueryCityDataForYears` 메서드는 도시의 이름, 도시의 면적, 연도, 해당 연도의 도시 인구, 두 번째 연도, 해당 두 번째 연도의 도구 인구를 포함하는 튜플을 반환합니다. 이 예제는 이러한 두 연도 사이의 인구 변화를 보여 줍니다. 튜플에서 사용 가능한 데이터 중 도시 면적에는 관심이 없고 디자인 타임에 도시 이름과 두 날짜를 알고 있습니다. 따라서 튜플에 저장된 두 가지 인구 값에만 관심이 있고 나머지 값은 무시 항목으로 처리할 수 있습니다.  

:::code language="csharp" source="snippets/discards/discard-tuple.cs" ID="DiscardTupleMember" :::

무시 항목을 사용한 튜플 분해에 대한 자세한 내용은 [튜플 및 기타 형식 분해](deconstruct.md#deconstructing-tuple-elements-with-discards)를 참조하세요.

클래스, 구조체 또는 인터페이스의 `Deconstruct` 메서드로도 개체에서 특정 데이터 집합을 검색 및 분해할 수 있습니다. 분해된 값의 하위 집합만으로 작업하려는 경우 무시 항목을 사용할 수 있습니다. 다음 예제에서는 `Person` 개체를 4개의 문자열(이름, 성, 도시 및 주)로 분해하지만 성과 주는 무시합니다.

:::code language="csharp" source="snippets/discards/discard-class.cs" :::

무시 항목을 사용한 사용자 정의 형식 분해에 대한 자세한 내용은 [튜플 및 기타 형식 분해](deconstruct.md#deconstructing-a-user-defined-type-with-discards)를 참조하세요.

## <a name="pattern-matching-with-switch"></a>`switch`를 사용한 패턴 일치

‘무시 패턴’은 [switch 식](language-reference/operators/switch-expression.md)을 사용한 패턴 일치에서 사용할 수 있습니다. `null`을 포함한 모든 식은 무시 패턴과 항상 일치합니다.

다음 예제에서는 `switch` 식을 사용하여 개체가 <xref:System.IFormatProvider> 구현을 제공하고 개체가 `null`인지 테스트하는지를 결정하는 `ProvidesFormatInfo` 메서드를 정의합니다. 또한 무시 패턴을 사용하여 다른 형식의 null이 아닌 개체도 처리합니다.

:::code language="csharp" source="snippets/discards/discard-pattern2.cs" ID="DiscardSwitchExample" :::

## <a name="calls-to-methods-with-out-parameters"></a>`out` 매개 변수를 사용한 메서드 호출

`Deconstruct` 메서드를 호출하여 사용자 정의 형식(클래스, 구조체 또는 인터페이스의 인스턴스)를 분해할 때 개별 `out` 인수의 값을 무시할 수 있습니다. 하지만 어느 메서드든 `out` 매개 변수를 사용하여 호출할 때 `out` 인수의 값을 무시할 수도 있습니다.

다음 예제에서는 [DateTime.TryParse(String, out DateTime)](<xref:System.DateTime.TryParse(System.String,System.DateTime@)>) 메서드를 호출하여 날짜의 문자열 표현이 현재 문화권에 유효한지 확인합니다. 이 예제에서는 날짜 문자열의 유효성 검사에만 관심이 있고 이 문자열의 구문 검사를 통한 날짜 추출에는 관심이 없으므로 메서드의 `out` 인수는 무시 항목입니다.

:::code language="csharp" source="snippets/discards/discard-out1.cs" ID="DiscardOutParameter" :::

## <a name="a-standalone-discard"></a>독립 실행형 무시 항목

독립 실행형 무시 항목을 사용하여 무시할 변수를 지정할 수 있습니다. 한 가지 일반적인 용도는 인수가 null이 아니도록 할당을 사용하는 것입니다. 다음 코드에서는 무시 항목을 사용하여 할당을 적용합니다. 할당의 오른쪽은 [null 병합 연산자](language-reference/operators/null-coalescing-operator.md)를 사용하여 인수가 `null`일 때 <xref:System.ArgumentNullException?displayProperty=nameWithType>을 throw합니다. 코드에 할당 결과가 필요하지 않으므로 할당이 무시됩니다. 식에서 null 검사를 강제로 수행합니다. 무시 항목은 할당 결과가 필요하지 않거나 사용되지 않는다는 의도를 명확하게 합니다.

:::code language="csharp" source="snippets/discards/standalone-discard1.cs" ID="ArgNullCheck" :::

다음 예제에서는 독립 실행형 무시 항목을 사용하여 비동기 작업에서 반환되는 <xref:System.Threading.Tasks.Task>개체를 무시합니다. 작업을 할당하면 작업이 완료되려고 할 때 throw되는 예외가 표시되지 않습니다. 그러므로 `Task`를 무시하고 해당 비동기 작업에서 생성되는 모든 오류를 무시하려고 하는 의도를 명확하게 합니다.

:::code language="csharp" source="snippets/discards/standalone-discard1.cs" ID="SnippetDiscardTask" :::

작업을 무시 항목에 할당하지 않으면 다음 코드는 컴파일러 경고를 생성합니다.

:::code language="csharp" source="snippets/discards/standalone-discard1.cs" ID="SnippetNoDiscardTask" :::

> [!NOTE]
> 디버거를 사용하여 위의 두 샘플 중 하나를 실행하면 예외가 throw될 때 디버거가 프로그램을 중지합니다. 연결된 디버거가 없으면 두 경우 모두 예외가 자동으로 무시됩니다.

`_`은 유효한 식별자이기도 합니다. 지원되는 컨텍스트 외부에서 사용하면 `_`은 무시 항목이 아니라 유효한 변수로 처리됩니다. `_`이라는 식별자가 이미 범위 내에 있는 경우 `_`을 독립 실행형 무시 항목으로 사용하면 다음과 같은 결과가 발생할 수 있습니다.

- 범위 내 `_` 변수 값을 실수로 수정하여 의도한 무시 항목의 값 할당. 예들 들어 다음과 같습니다.
   :::code language="csharp" source="snippets/discards/standalone-discard2.cs" ID="VariableIdentifier" :::
- 형식 안전성 위반으로 인한 컴파일러 오류. 예들 들어 다음과 같습니다.
   :::code language="csharp" source="snippets/discards/standalone-discard2.cs" ID="VariableTypeInference" :::
- 컴파일러 오류 CS0136, “이름이 ‘\_’인 지역 또는 매개 변수는 이 범위에서 선언될 수 없습니다. 해당 이름이 지역 또는 매개 변수를 정의하기 위해 바깥쪽 지역 범위에서 사용되었습니다.” 예를 들면 다음과 같습니다.
   :::code language="csharp" source="snippets/discards/standalone-discard2.cs" ID="CannotRedeclare" :::

## <a name="see-also"></a>참고 항목

- [튜플 및 기타 형식 분해](deconstruct.md)
- [`is` 키워드](language-reference/keywords/is.md)
- [`switch` 키워드](language-reference/keywords/switch.md)
