---
title: switch 식 - C# 참조
description: 패턴 일치 및 기타 데이터 검사에 C# switch 식을 사용하는 방법을 알아봅니다.
ms.date: 03/19/2020
ms.openlocfilehash: 2249afc1ff1cc81e9ad423d910ebb95df8c787d4
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916659"
---
# <a name="switch-expression-c-reference"></a>switch 식(C# 참조)

이 문서에서는 C# 8.0에 도입된 `switch` 식에 대해 설명합니다. `switch` 문에 대한 자세한 내용은 [문](../keywords/index.md) 섹션의 [`switch` 문](../keywords/switch.md) 문서를 참조하세요.

## <a name="basic-example"></a>기본 예제

`switch` 식은 식 컨텍스트에서 `switch`와 유사한 의미 체계를 제공합니다. 스위치 암(arm)에서 값을 생성할 때 간결한 구문을 제공합니다. 다음 예제에서는 switch 식의 구조를 보여 줍니다. 온라인 맵의 시각적 방향을 나타내는 `enum`의 값을 해당하는 기본 방향으로 변환합니다.

:::code language="csharp" source="snippets/shared/SwitchExpressions.cs" id="SnippetBasicStructure":::

위의 샘플에서는 switch 식의 기본 요소를 보여 줍니다.

- *range 식*: 위의 예제에서는 `direction` 변수를 range 식으로 사용합니다.
- *switch 식 암(arm)* : 각 switch 식 암(arm)에는 *패턴*, 선택적인 *케이스 가드*, `=>` 토큰 및 *식*이 포함되어 있습니다.

*switch 식*의 결과는 *패턴*이 *range 식*과 일치하고 *케이스 가드*(있는 경우)가 `true`로 평가되는 첫 번째 *switch 식 암(arm)* 의 값입니다. `=>` 토큰 오른쪽에 있는 *식*은 식 문이 될 수 없습니다.

*switch 식 암(arm)* 은 텍스트 순서대로 평가됩니다. 상위 *switch 식 암(arm)* 이 모든 값과 일치하기 때문에 하위 *switch 식 암(arm)* 을 선택할 수 없는 경우 컴파일러에서 오류를 발생시킵니다.

## <a name="patterns-and-case-guards"></a>패턴 및 케이스 가드

switch 식 암(arm)에서는 많은 패턴이 지원됩니다. 앞의 예제에서는 ‘상수 패턴’을 사용합니다. ‘상수 패턴’은 range 식을 값과 비교합니다. 이 값은 컴파일 시간 상수여야 합니다. *형식 패턴*은 range 식을 알려진 형식과 비교합니다. 다음 예제에서는 시퀀스에서 세 번째 요소를 검색합니다. 시퀀스의 형식에 따라 다른 메서드를 사용합니다.

:::code language="csharp" source="snippets/shared/SwitchExpressions.cs" id="SnippetTypePattern":::

패턴은 재귀적으로 지정할 수 있습니다. 그러면 패턴이 형식을 테스트하고 해당 형식이 일치하는 경우 패턴이 range 식의 하나 이상의 속성 값과 일치합니다. 재귀 패턴을 사용하여 앞의 예제를 확장할 수 있습니다. 요소가 3개 미만인 배열에 대해 switch 식 암(arm)을 추가합니다. 다음 예제에서는 재귀 패턴을 보여 줍니다.

:::code language="csharp" source="snippets/shared/SwitchExpressions.cs" id="SnippetRecursivePattern":::

재귀 패턴은 range 식의 속성을 검사할 수 있지만 임의의 코드를 실행할 수는 없습니다. `when` 절에 지정된 *케이스 가드*를 사용하여 다른 시퀀스 형식에 비슷한 검사를 제공할 수 있습니다.

:::code language="csharp" source="snippets/shared/SwitchExpressions.cs" id="SnippetGuardCase":::

마지막으로 `_` 패턴과 `null` 패턴을 추가하여 다른 switch 식 암(arm)에서 처리되지 않은 인수를 catch할 수 있습니다. 이렇게 하면 switch 식이 range 식의 가능한 값을 모두 처리합니다(*exhaustive*). 다음 예제에서는 이러한 식 암(arm)을 추가합니다.

:::code language="csharp" source="snippets/shared/SwitchExpressions.cs" id="SnippetExhaustive":::

앞의 예제는 `null` 패턴을 추가하고 `IEnumerable<T>` 형식 패턴을 `_` 패턴으로 변경합니다. `null` 패턴은 switch 식 암(arm)으로 null 검사를 제공합니다. 해당 암(arm)에 대한 식에서 <xref:System.ArgumentNullException>을 throw합니다. `_` 패턴은 이전 암(arm)과 일치하지 않은 모든 입력을 일치시킵니다. `null` 검사 후에 오거나 `null` 입력과 일치해야 합니다.

[재귀 패턴](~/_csharplang/proposals/csharp-8.0/patterns.md#switch-expression)에 대한 C# 언어 사양 제안에서 자세한 내용을 알아볼 수 있습니다.

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [C# 연산자 및 식](index.md)
- [패턴 일치](../../pattern-matching.md)
