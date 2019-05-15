---
title: 오버로드할 수 있는 연산자 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 08/27/2018
helpviewer_keywords:
- C# language, operator overloading
- operator overloading [C#]
ms.assetid: 390d9d01-79fc-40ab-9ed3-0bf448da1b6a
ms.openlocfilehash: 850b10958446193026506418c57d7f565c98b714
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452775"
---
# <a name="overloadable-operators-c-programming-guide"></a>오버로드할 수 있는 연산자(C# 프로그래밍 가이드)

C#에서는 [operator](../../language-reference/keywords/operator.md) 키워드로 정적 멤버 함수를 정의하여 사용자 정의 형식에서 연산자를 오버로드할 수 있습니다. 그러나 일부 연산자는 오버로드할 수 없으며 일부는 다음 표에 나열된 제한 사항이 적용됩니다.

| 연산자 | 오버로드 가능성 |
| --------- | --------------- |
|[+](../../language-reference/operators/addition-operator.md), [-](../../language-reference/operators/subtraction-operator.md), [!](../../language-reference/operators/boolean-logical-operators.md#logical-negation-operator-), [~](../../language-reference/operators/bitwise-and-shift-operators.md#bitwise-complement-operator-), [++](../../language-reference/operators/arithmetic-operators.md#increment-operator-), [--](../../language-reference/operators/arithmetic-operators.md#decrement-operator---), [true](../../language-reference/keywords/true-false-operators.md), [false](../../language-reference/keywords/true-false-operators.md)|이러한 단항 연산자는 오버로드할 수 있습니다.|
|[+](../../language-reference/operators/addition-operator.md), [-](../../language-reference/operators/subtraction-operator.md), [\*](../../language-reference/operators/arithmetic-operators.md#multiplication-operator-), [/](../../language-reference/operators/arithmetic-operators.md#division-operator-), [%](../../language-reference/operators/arithmetic-operators.md#remainder-operator-), [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-), [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-), [^](../../language-reference/operators/boolean-logical-operators.md#logical-exclusive-or-operator-), [\<\<](../../language-reference/operators/bitwise-and-shift-operators.md#left-shift-operator-), [>>](../../language-reference/operators/bitwise-and-shift-operators.md#right-shift-operator-)|이러한 이항 연산자는 오버로드할 수 있습니다.|
|[==](../../language-reference/operators/equality-operators.md#equality-operator-), [!=](../../language-reference/operators/equality-operators.md#inequality-operator-), [\<](../../language-reference/operators/comparison-operators.md#less-than-operator-), [>](../../language-reference/operators/comparison-operators.md#greater-than-operator-), [\<=](../../language-reference/operators/comparison-operators.md#less-than-or-equal-operator-), [>=](../../language-reference/operators/comparison-operators.md#greater-than-or-equal-operator-)|비교 연산자는 오버로드할 수 있지만 이 표 다음에 오는 참고 사항을 참조하세요.|
|[&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-)|조건부 논리 연산자는 오버로드할 수 없지만 오버로드할 수 있는 `&` 및 <code>&#124;</code>를 사용하여 계산됩니다.|
|[&#91;&#93;](../../language-reference/operators/member-access-operators.md#indexer-operator-)|배열 인덱싱 연산자는 오버로드할 수 없지만 [인덱서](../indexers/index.md)를 정의할 수 있습니다.|
|[(T)x](../../language-reference/operators/invocation-operator.md)|캐스트 연산자는 오버로드할 수 없지만 새 변환 연산자를 정의할 수 있습니다([explicit](../../language-reference/keywords/explicit.md) 및 [implicit](../../language-reference/keywords/implicit.md) 참조).|
|[+=](../../language-reference/operators/addition-assignment-operator.md), [-=](../../language-reference/operators/subtraction-assignment-operator.md), [\*=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [/=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [%=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [&=](../../language-reference/operators/boolean-logical-operators.md#compound-assignment), [&#124;=](../../language-reference/operators/boolean-logical-operators.md#compound-assignment), [^=](../../language-reference/operators/boolean-logical-operators.md#compound-assignment), [\<\<=](../../language-reference/operators/bitwise-and-shift-operators.md#compound-assignment), [>>=](../../language-reference/operators/bitwise-and-shift-operators.md#compound-assignment)|할당 연산자를 명시적으로 오버로드할 수 없습니다. 그러나 이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다. 예를 들어 `+=`는 오버로드될 수 있는 `+`를 사용하여 계산됩니다.|
|[=](../../language-reference/operators/assignment-operator.md), [.](../../language-reference/operators/member-access-operators.md#member-access-operator-), [?:](../../language-reference/operators/conditional-operator.md), [??](../../language-reference/operators/null-coalescing-operator.md), [->](../../language-reference/operators/dereference-operator.md), [=>](../../language-reference/operators/lambda-operator.md), [f(x)](../../language-reference/operators/member-access-operators.md#invocation-operator-), [as](../../language-reference/keywords/as.md), [checked](../../language-reference/keywords/checked.md), [unchecked](../../language-reference/keywords/unchecked.md), [default](../../programming-guide/statements-expressions-operators/default-value-expressions.md), [delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md), [is](../../language-reference/keywords/is.md), [new](../../language-reference/keywords/new.md), [sizeof](../../language-reference/keywords/sizeof.md), [typeof](../../language-reference/keywords/typeof.md)|이러한 연산자는 오버로드할 수 없습니다.|

> [!NOTE]
> 비교 연산자는 오버로드될 경우 쌍으로 오버로드되어야 합니다. 즉, `==`가 오버로드되면 `!=`도 오버로드되어야 합니다. 그 반대의 경우도 마찬가지여서, `!=`를 오버로드하면 `==`도 오버로드해야 합니다. 비교 연산자 `<`와 `>`, `<=`와 `>=`도 마찬가지입니다.

연산자를 오버로드하는 방법에 대한 자세한 내용은 [연산자](../../language-reference/keywords/operator.md) 키워드 문서를 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../index.md)
- [문, 식, 연산자](index.md)
- [연산자](operators.md)
- [C# 연산자](../../language-reference/operators/index.md)
- [Why are overloaded operators always static in C#?](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/)(오버로드된 연산자가 C#에서 항상 정적인 이유)
