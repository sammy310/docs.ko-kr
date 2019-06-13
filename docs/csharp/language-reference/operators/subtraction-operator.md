---
title: '- 및 -= 연산자 - C# 참조'
ms.custom: seodec18
ms.date: 05/27/2019
f1_keywords:
- -_CSharpKeyword
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction operator [C#]
- delegate removal [C#]
- '- operator [C#]'
- subtraction assignment operator [C#]
- event unsubscription [C#]
- -= operator [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: aae10f8b03a16e55f0b26981f17585c8790e00c1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816075"
---
# <a name="--and---operators-c-reference"></a>- 및 -= 연산자(C# 참조)

`-` 연산자는 기본 제공 숫자 형식 및 [대리자](../keywords/delegate.md) 형식에서 지원됩니다.

산술 `-` 연산자에 대한 자세한 내용은 [산술 연산자](arithmetic-operators.md) 문서의 [단항 더하기 및 빼기 연산자](arithmetic-operators.md#unary-plus-and-minus-operators) 및 [빼기 연산자 -](arithmetic-operators.md#subtraction-operator--) 섹션을 참조하세요.

## <a name="delegate-removal"></a>대리자 제거

동일한 [대리자](../keywords/delegate.md) 형식의 피연산자에 대해 `-` 연산자는 다음과 같이 계산되는 대리자 인스턴스를 반환합니다.

- 두 피연산자가 모두 null이 아니고 두 번째 피연산자의 호출 목록이 첫 번째 피연산자의 호출 목록에 적절한 연속 하위 목록인 경우, 이 작업의 결과는 첫 번째 피연산자의 호출 목록에서 두 번째 피연산자의 항목을 제거하여 얻은 새로운 호출 목록입니다. 두 번째 피연산자의 목록이 첫 번째 피연산자 목록의 여러 개의 연속 하위 목록과 일치하는 경우 가장 오른쪽에 일치하는 하위 목록만 제거됩니다. 제거로 인해 빈 목록이 생성되면 결과는 `null`입니다.

  [!code-csharp-interactive[delegate removal](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemoval)]

- 두 번째 피연산자의 호출 목록이 첫 번째 피연산자의 호출 목록의 적절한 연속 하위 목록이 아닌 경우, 해당 작업의 결과는 첫 번째 피연자입니다. 예를 들어, 멀티 캐스트 대리자의 일부가 아닌 대리자를 제거 합니다. 아무 작업도 수행 하지 및 변경 되지 않은 멀티 캐스트 대리자의 결과입니다.

  [!code-csharp-interactive[delegate removal with no effect](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalNoChange)]

  또한 앞의 예제는 대리자 중 제거 대리자 인스턴스 비교는 방법을 보여 줍니다. 예를 들어, 동일한 평가에서 생성 되는 대리자 [람다 식](../../programming-guide/statements-expressions-operators/lambda-expressions.md) 같지 않습니다. 대리자 같음에 대 한 자세한 내용은 참조 하세요.는 [같음 연산자를 대리자](~/_csharplang/spec/expressions.md#delegate-equality-operators) 섹션을 [ C# 언어 사양](../language-specification/index.md).

- 첫 번째 피연산자가 `null`이면, 작업의 결과는 `null`입니다. 두 번째 피연산자가 `null`이면, 작업 결과는 첫 번째 피연산자입니다.

  [!code-csharp-interactive[delegate removal and null](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalAndNull)]

대리자를 결합 하려면 사용 합니다 [ `+` 연산자](addition-operator.md#delegate-combination)합니다.

대리자 형식에 대한 자세한 내용은 [대리자](../../programming-guide/delegates/index.md)를 참조하세요.

## <a name="subtraction-assignment-operator--"></a>빼기 할당 연산자 -=

다음과 같은 `-=` 연산자를 사용하는 식의 경우

```csharp
x -= y
```

위의 식은 아래의 식과 동일합니다.

```csharp
x = x - y
```

단, `x`가 한 번만 계산됩니다.
  
다음 예제에서는 `-=` 연산자의 사용법을 보여 줍니다.

[!code-csharp-interactive[-= examples](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#SubtractAndAssign)]

또한 [이벤트](../keywords/event.md)에서 구독 취소할 때 `-=` 연산자를 사용하여 제거할 이벤트 처리기 메서드를 지정합니다. 자세한 내용은 [방법: 이벤트 구독 및 구독 취소](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)를 참조하세요.

## <a name="operator-overloadability"></a>연산자 오버로드 가능성

사용자 정의 형식은 `-` 연산자를 [오버로드](../keywords/operator.md)할 수 있습니다. 이진 `-` 연산자가 오버로드되면 `-=` 연산자도 암시적으로 오버로드됩니다. 사용자 정의 형식에는 `-=` 연산자를 명시적으로 오버로드할 수 없습니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [단항 빼기 연산자](~/_csharplang/spec/expressions.md#unary-minus-operator) 및 [빼기 연산자](~/_csharplang/spec/expressions.md#subtraction-operator) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 연산자](index.md)
- [대리자](../../programming-guide/delegates/index.md)
- [이벤트](../../programming-guide/events/index.md)
- [Checked 및 Unchecked](../keywords/checked-and-unchecked.md)
- [산술 연산자](arithmetic-operators.md)
- [+ 및 += 연산자](addition-operator.md)
