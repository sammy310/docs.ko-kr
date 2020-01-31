---
title: 값 형식 - C# 참조
ms.date: 01/22/2020
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 6b96d65f657f2af1af5c9a245e956640ee06260e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76748490"
---
# <a name="value-types-c-reference"></a>값 형식(C# 참조)

*값 형식* 및 [참조 형식](../keywords/reference-types.md)은 C# 형식의 두 가지 주요 범주입니다. 값 형식의 변수에는 형식의 인스턴스가 포함되어 있습니다. 이는 형식 인스턴스에 대한 참조를 포함하는 참조 형식의 변수와 다릅니다. 기본적으로 [할당](../operators/assignment-operator.md)에서 메서드에 인수를 전달하거나, 메서드 결과를 반환하면 변수 값이 복사됩니다. 값 형식 변수의 경우 해당 형식 인스턴스가 복사됩니다. 다음 예제에서는 해당 동작을 보여줍니다.

[!code-csharp[copy of values](~/samples/csharp/language-reference/builtin-types/ValueTypes.cs#ValueTypeCopied)]

앞의 예제와 같이 값 형식 변수에 대한 작업은 변수에 저장된 값 형식의 인스턴스에만 영향을 줍니다.

값 형식이 참조 형식의 데이터 구성원을 포함하는 경우에는 값 형식 인스턴스가 복사될 때 참조 형식의 인스턴스에 대한 참조만 복사됩니다. 복사 및 원래 값 형식 인스턴스는 모두 동일한 참조 형식 인스턴스에 액세스할 수 있습니다. 다음 예제에서는 해당 동작을 보여줍니다.

[!code-csharp[shallow copy](~/samples/csharp/language-reference/builtin-types/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> 코드를 오류가 덜 발생하고 더 강력하게 만들려면 변경할 수 없는 값 형식을 정의 및 사용합니다. 이 문서에서는 데모용으로만 변경 가능한 값 형식을 사용합니다.

## <a name="kinds-of-value-types"></a>값 형식의 종류

값 형식은 다음 두 가지 중 하나일 수 있습니다.

- 데이터 및 관련 기능을 캡슐화하는[구조 형식](../keywords/struct.md)
- 명명된 상수 집합으로 정의되고 선택 사항 또는 선택 사항의 조합을 나타내는 [열거 형식](enum.md)

기본 값 형식 `T`의 모든 값과 추가 [Null](../keywords/null.md) 값을 나타내는 [ 값 형식](nullable-value-types.md) `T?` Null 허용 값 형식인 경우를 제외하고는 값 형식의 변수에 `null`을 할당할 수 없습니다.

## <a name="built-in-value-types"></a>기본 제공 값 형식

C#은 *단순 형식*이라고도 하는 다음과 같은 기본 제공 값 형식을 제공합니다.

- [정수 숫자 형식](integral-numeric-types.md)
- [부동 소수점 숫자 형식](floating-point-numeric-types.md)
- 부울 값을 나타내는 [bool](bool.md)
- 유니코드 UTF-16 문자를 나타내는 [문자](char.md)

모든 단순 형식은 구조체 형식이며, 특정 추가 작업을 허용한다는 점에서 다른 구조체 형식과 다릅니다.

- 리터럴을 사용하여 단순 형식의 값을 제공할 수 있습니다. 예를 들어 `'A'`는 `char` 형식의 리터럴이고, `2001`은 `int` 형식의 리터럴입니다.

- [const](../keywords/const.md) 키워드를 사용하여 단순 형식의 상수를 선언할 수 있습니다. 다른 구조체 형식의 상수는 포함할 수 없습니다.

- 해당 피연산자가 모두 단순 형식의 상수인 상수 식은 컴파일 시간에 계산됩니다.

C# 7.0부터는 C#에서 [값 튜플](../../tuples.md)을 지원합니다. 값 튜플은 단순 형식이 아닌 값 형식입니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.

- [값 형식](~/_csharplang/spec/types.md#value-types)
- [단순 형식](~/_csharplang/spec/types.md#simple-types)
- [변수](~/_csharplang/spec/variables.md)

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [참조 형식](../keywords/reference-types.md)
