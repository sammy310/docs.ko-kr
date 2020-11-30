---
description: '! (null-forgiving) 연산자- C# 참조'
title: '! (null-forgiving) 연산자- C# 참조'
ms.date: 11/13/2020
f1_keywords:
- nullForgiving_CSharpKeyword
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 5489c77fa7290bdd1c03e04d8cc777ab772fdce7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699632"
---
# <a name="-null-forgiving-operator-c-reference"></a>! (null-forgiving) 연산자(C# 참조)

C# 8.0 이상에서 사용할 수 있는 단항 후위 `!` 연산자는 null-forgiving 연산자입니다. [null 허용 주석 컨텍스트](../../nullable-references.md#nullable-annotation-context)가 활성화된 경우에는 참조 형식의 `x` 식이 `null`: `x!`가 아님을 선언하는 데 null-forgiving 연산자를 사용할 수 있습니다. 단항 접두사 `!` 연산자는 [논리 부정 연산자](boolean-logical-operators.md#logical-negation-operator-)입니다.

null-forgiving 연산자는 런타임에 영향을 주지 않습니다. 식의 null 상태를 변경하여 컴파일러의 정적 흐름 분석에만 영향을 줍니다. 런타임에서 `x!` 식은 기본 식 `x`의 결과로 계산됩니다.

nullable 참조 형식 기능에 대한 자세한 내용은 [nullable 참조 형식](../builtin-types/nullable-reference-types.md)을 참조하세요.

## <a name="examples"></a>예

null-forgiving 연산자의 사용 사례 중 하나는 인수 유효성 검사 논리를 테스트하는 것입니다. 예를 들어 다음 클래스를 예로 들어 볼 수 있습니다.

[!code-csharp[Person class](snippets/shared/NullForgivingOperator.cs#PersonClass)]

[MSTest 테스트 프레임워크](../../../core/testing/unit-testing-with-mstest.md)를 사용하여 생성자에서 유효성 검사 논리에 대해 다음 테스트를 만들 수 있습니다.

[!code-csharp[Person test](snippets/shared/NullForgivingOperator.cs#TestPerson)]

null-forgiving 연산자가 없으면 컴파일러가 이전 코드에 대해 다음 경고를 생성합니다. `Warning CS8625: Cannot convert null literal to non-nullable reference type`. null-forgiving 연산자를 사용하여 `null`이 전달될 것이고 경고를 표시하지 않아야 함을 컴파일러에 알립니다.

식이 `null`이 될 수 없지만 컴파일러가 이를 인식할 수 없음이 확실할 경우에는 null-forgiving 연산자를 사용할 수도 있습니다. 다음 예에서는 `IsValid` 메서드가 `true`를 반환하는 경우 해당 인수는 `null`이 아니므로 안전하게 역참조할 수 있습니다.

[!code-csharp[Use null-forgiving operator](snippets/shared/NullForgivingOperator.cs#UseNullForgiving)]

null-forgiving 연산자가 없으면 컴파일러가 `p.Name` 코드에 대해 다음 경고를 생성합니다. `Warning CS8602: Dereference of a possibly null reference`.

`IsValid` 메서드를 수정할 수 있는 경우 [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) 특성을 사용하여 메서드가 `true`를 반환할 때 `IsValid` 메서드의 인수는 `null`일 수 없다는 것을 컴파일러에 알릴 수 있습니다.

[!code-csharp[Use an attribute](snippets/shared/NullForgivingOperator.cs#UseAttribute)]

앞의 예제에서는 컴파일러가 `if` 문 내에서 `p`가 `null`일 수 없다는 것을 확인할 수 있는 충분한 정보를 제공하기 때문에 null-forgiving 연산자를 사용할 필요가 없습니다. 변수의 null 상태에 대한 추가 정보를 제공하는 데 사용할 수 있는 특성에 대한 자세한 내용은 [null 예상을 정의하는 특성을 포함한 API 업그레이드](../attributes/nullable-analysis.md)를 참조하세요.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [Nullable 참조 형식 사양 초안](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md#the-null-forgiving-operator)의 [null-forgiving 연산자](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md) 섹션을 참조하세요.

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [C# 연산자 및 식](index.md)
- [자습서: nullable 참조 형식을 사용하여 디자인](../../tutorials/nullable-reference-types.md)
