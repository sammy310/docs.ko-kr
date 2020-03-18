---
title: char 형식 - C# 참조
ms.date: 11/26/2019
f1_keywords:
- bool
- bool_CSharpKeyword
helpviewer_keywords:
- bool data type [C#]
- Boolean [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 2ba2e54a6b0f24402fc3728dfe19b548a2368830
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846447"
---
# <a name="bool-c-reference"></a>bool(C# 참조)

`bool` 형식 키워드는 부울 값(<xref:System.Boolean?displayProperty=nameWithType> 또는 `true`)을 나타내는 .NET `false` 구조체 형식의 별칭입니다.

`bool` 형식의 값을 사용하여 논리 연산을 수행하려면 [부울 논리](../operators/boolean-logical-operators.md) 연산자를 사용합니다. `bool` 형식은 [비교](../operators/comparison-operators.md) 및 [같음](../operators/equality-operators.md) 연산자의 결과 형식입니다. `bool` 식은 [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md) 및 [for](../keywords/for.md) 문과 [조건부 연산자`?:`](../operators/conditional-operator.md)에서 제어하는 조건식입니다.

`bool` 형식의 기본값은 `false`입니다.

## <a name="literals"></a>리터럴

`true` 및 `false` 리터럴을 사용하여 `bool` 변수를 초기화하거나 `bool` 값을 전달할 수 있습니다.

[!code-csharp-interactive[bool literals](snippets/BoolType.cs#Literals)]

## <a name="three-valued-boolean-logic"></a>값이 세 개인 부울 논리

예를 들어 값이 세 개인 논리를 지원해야 하는 경우(예: 값이 세 개인 부울 형식을 지원하는 데이터베이스에서 작업하는 경우) nullable `bool?` 형식을 사용합니다. `bool?` 피연산자의 경우 미리 정의된 `&` 및 `|` 연산자는 값이 세 개인 논리를 지원합니다. 자세한 내용은 [부울 논리 연산자](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) 문서의 [Nullable 부울 논리 연산자](../operators/boolean-logical-operators.md) 섹션을 참조하세요.

nullable 값 형식에 대한 자세한 내용은 [Nullable 값 형식](nullable-value-types.md)을 참조하세요.

## <a name="conversions"></a>변환

C#는 `bool` 형식을 포함하는 두 개의 변환만 제공합니다. 여기에는 해당하는 nullable `bool?` 형식으로의 암시적 변환과 `bool?` 형식에서의 명시적 변환이 있습니다. 그러나 .NET에서는 `bool` 형식으로 변환하거나 해당 형식에서 변환하는 데 사용할 수 있는 추가 메서드를 제공합니다. 자세한 내용은 [ API 참조 페이지의 ](/dotnet/api/system.boolean#converting-to-and-from-boolean-values)부울 값 사이의 변환<xref:System.Boolean?displayProperty=nameWithType> 섹션을 참조하세요.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/types.md#the-bool-type)의 [bool 형식](~/_csharplang/spec/introduction.md) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [값 형식](value-types.md)
- [true 및 false 연산자](../operators/true-false-operators.md)
