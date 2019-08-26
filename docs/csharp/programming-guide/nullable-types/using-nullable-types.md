---
title: nullable 형식 사용 - C# 프로그래밍 가이드
ms.custom: seodec18
description: C# nullable 형식을 사용하는 방법 알아보기
ms.date: 08/02/2018
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: 75b8889f5f1f1b0dab4aa365daa34ef5ae226b02
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588826"
---
# <a name="using-nullable-types-c-programming-guide"></a>nullable 형식 사용(C# 프로그래밍 가이드)

nullable 형식은 기본 값 형식 `T`의 모든 값과 추가 [Null](../../language-reference/keywords/null.md) 값을 나타내는 형식입니다. 자세한 내용은 [Nullable 형식](index.md) 항목을 참조하세요.

다음 형식 `Nullable<T>` 또는 `T?` 중 하나에서 nullable 형식을 참조할 수 있습니다. 이러한 두 가지 형태는 동일하게 사용할 수 있습니다.  
  
## <a name="declaration-and-assignment"></a>선언 및 할당

값 형식은 해당 nullable 형식으로 암시적으로 변환될 수 있으므로 해당 기본 값 형식과 마찬가지로 값을 nullable 형식에 할당합니다. `null` 값을 할당할 수도 있습니다.  예:
  
[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a>nullable 형식 값의 검사

다음 읽기 전용 속성을 사용하여 Null에 대한 nullable 형식의 인스턴스를 검사하고 내부 형식의 값을 검색합니다.  
  
- <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType>은 nullable 형식의 인스턴스에 해당 기본 형식의 값이 있는지 여부를 나타냅니다.
  
- <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType>은 <xref:System.Nullable%601.HasValue%2A>가 `true`인 경우 기본 형식의 값을 가져옵니다. <xref:System.Nullable%601.HasValue%2A>가 `false`인 경우 <xref:System.Nullable%601.Value%2A> 속성은 <xref:System.InvalidOperationException>을 throw합니다.
  
다음 예제의 코드는 `HasValue` 속성을 사용하여 표시하기 전에 변수가 값을 포함하는지 여부를 테스트합니다.
  
[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]
  
다음 예제와 같이 `HasValue` 속성을 사용하는 대신 nullable 형식 변수를 `null`과 비교할 수도 있습니다.  
  
[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

C# 7.0부터는 [패턴 일치](../../pattern-matching.md)를 사용하여 nullable 형식의 값을 검사하고 가져올 수 있습니다.

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-type-to-an-underlying-type"></a>nullable 형식에서 기본 형식으로 변환

nullable이 아닌 형식에 nullable 형식 값을 할당해야 하는 경우 [Null 병합 연산자를 사용하여 `??`](../../language-reference/operators/null-coalescing-operator.md) nullable 형식 값이 Null인 경우 할당될 값을 지정합니다(<xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> 메서드를 사용하여 작업을 수행할 수도 있음).
  
[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

nullable 형식 값이 Null일 때 사용될 값이 기본 값 형식의 기본 값이어야 하는 경우 <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> 메서드를 사용합니다.
  
nullable 형식을 nullable이 아닌 형식으로 명시적으로 캐스팅할 수 있습니다. 예:  
  
[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

런타임 시 nullable 형식의 값이 Null인 경우 명시적 캐스트는 <xref:System.InvalidOperationException>을 throw합니다.

nullable이 아닌 값 형식이 해당 nullable 형식으로 암시적으로 변환됩니다.
  
## <a name="operators"></a>연산자

미리 정의된 단항 및 이항 연산자와 값 형식에 대해 존재하는 모든 사용자 정의 연산자는 nullable 형식에도 사용할 수 있습니다. 이러한 연산자는 하나 또는 두 개의 피연산자가 Null인 경우 Null 값을 생성하고, 그렇지 않으면 연산자는 포함된 값을 사용하여 결과를 계산합니다. 예:  
  
[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]

> [!NOTE]
> `|` 형식의 경우 미리 정의된 `bool?` 및 `&` 연산자는 이 섹션에서 설명된 규칙을 따르지 않습니다. 연산자 평가의 결과는 피연산자 중 하나가 Null인 경우에도 Null이 아닐 수 있습니다. 자세한 내용은 [부울 논리 연산자](../../language-reference/operators/boolean-logical-operators.md) 문서의 [Nullable 부울 논리 연산자](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) 섹션을 참조하세요.
  
관계 연산자(`<`, `>`, `<=`, `>=`)의 경우 하나 또는 두 개의 피연산자가 Null인 경우 결과는 `false`입니다. 특정 비교(예: `<=`)에서는 `false`를 반환하고 그 반대의 비교(`>`)에서는 `true`를 반환한다고 가정하지 마십시오. 다음 예제에서는 10이

- Null보다 크거나 같거나
- Null보다 작지 않음을 보여줍니다.
  
[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]
  
또한 위의 예제에서는 둘 다 Null인 두 nullable 형식의 같음 비교는 `true`로 계산되는 것을 보여줍니다.

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [리프트 연산자](~/_csharplang/spec/expressions.md#lifted-operators) 섹션을 참조하세요.

## <a name="boxing-and-unboxing"></a>boxing 및 unboxing

nullable 값 형식은 다음 규칙에 따라 [boxed](../types/boxing-and-unboxing.md)됩니다.

- <xref:System.Nullable%601.HasValue%2A>가 `false`를 반환하는 경우 Null 참조가 생성됩니다.  
- <xref:System.Nullable%601.HasValue%2A>가 `true`를 반환하는 경우 <xref:System.Nullable%601>의 인스턴스가 아닌 기본 값 형식의 값 `T`는 boxed됩니다.

다음 예제와 같이 boxed 값 형식을 해당 nullable 형식으로 unbox할 수 있습니다.

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="see-also"></a>참고 항목

- [Nullable 형식](index.md)
- [C# 프로그래밍 가이드](../index.md)
- ['리프트'란 정확히 어떤 의미입니까?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
