---
description: nameof 식 - C# 참조
title: nameof 식 - C# 참조
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 568127a64efc02717b34fbd9d1e508e2e40596fd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100464393"
---
# <a name="nameof-expression-c-reference"></a>nameof 식(C# 참조)

`nameof` 식은 변수, 형식 또는 멤버의 이름을 문자열 상수로 가져옵니다.

[!code-csharp-interactive[nameof expression](snippets/shared/NameOfOperator.cs#Examples)]

이전 예제와 같이 형식 및 네임스페이스의 경우 생성되는 이름은 [정규화된](~/_csharplang/spec/basic-concepts.md#fully-qualified-names) 이름이 아닙니다.

[verbatim 식별자](../tokens/verbatim.md)의 경우 다음 예제와 같이 `@` 문자는 이름의 일부가 아닙니다.

[!code-csharp-interactive[nameof verbatim](snippets/shared/NameOfOperator.cs#Verbatim)]

`nameof` 식은 컴파일 시간에 계산되며 런타임에는 영향을 주지 않습니다.

`nameof` 식을 사용하여 인수 검사 코드를 더 쉽게 유지 관리할 수 있습니다.

[!code-csharp[nameof and argument check](snippets/shared/NameOfOperator.cs#ExceptionMessage)]

`nameof` 식은 C# 6 이상에서 사용할 수 있습니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [Nameof 식](~/_csharplang/spec/expressions.md#nameof-expressions) 섹션을 참조하세요.

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [C# 연산자 및 식](index.md)
