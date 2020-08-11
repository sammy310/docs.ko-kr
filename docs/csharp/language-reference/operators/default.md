---
title: 기본값 식 - C# 참조
description: 기본값 식을 사용하여 형식의 기본값을 가져옵니다.
ms.date: 03/13/2020
f1_keywords:
- default_CSharpKeyword
- default
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: f03971efa87bf03967c79512e44d22134dd80c17
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916874"
---
# <a name="default-value-expressions-c-reference"></a>기본값 식(C# 참조)

기본값 식은 형식의 [기본값](../builtin-types/default-values.md)을 생성합니다. 기본값 식에는 두 가지가 있습니다. [기본 연산자](#default-operator) 호출 및 [기본 리터럴](#default-literal).

또한 `default` 키워드를 [`switch` 문](../keywords/switch.md) 내의 기본 사례 레이블로 사용할 수 있습니다.

## <a name="default-operator"></a>default 연산자

`default` 연산자의 인수는 다음 예제와 같이 형식 또는 형식 매개 변수의 이름이어야 합니다.

[!code-csharp-interactive[default of T](snippets/shared/DefaultOperator.cs#WithOperand)]

## <a name="default-literal"></a>기본 리터럴

C# 7.1부터 `default` 리터럴을 사용하여 컴파일러가 식 형식을 유추할 수 있는 경우 형식의 기본값을 생성할 수 있습니다. `default` 리터럴 식은 `T`가 추론된 형식은 `default(T)` 식과 동일한 값을 생성합니다. 다음과 같은 경우에 `default` 리터럴 사용할 수 있습니다.

- 변수의 할당 또는 초기화에서
- [선택적 메서드 매개 변수](../../methods.md#optional-parameters-and-arguments)에 대한 기본값 선언에서
- 인수 값을 제공하기 위한 메서드 호출에서
- [`return` 문](../keywords/return.md)에서 또는 [식 본문 멤버](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)의 식으로

다음 예제에서는 `default` 리터의 사용법을 보여 줍니다.

[!code-csharp-interactive[default literal](snippets/shared/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [기본값 식](~/_csharplang/spec/expressions.md#default-value-expressions) 섹션을 참조하세요.

`default` 리터럴에 대한 자세한 내용은 [기능 제안 노트](~/_csharplang/proposals/csharp-7.1/target-typed-default.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 연산자 및 식](index.md)
- [C# 형식의 기본값](../builtin-types/default-values.md)
- [.NET의 제네릭](../../../standard/generics/index.md)
