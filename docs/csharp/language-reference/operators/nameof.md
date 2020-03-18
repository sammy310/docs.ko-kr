---
title: nameof 연산자 - C# 참조
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof operator [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: ffbc801acf61bf72db1c88912dc2142a478fa280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846274"
---
# <a name="nameof-operator-c-reference"></a>nameof 연산자(C# 참조)

`nameof` 연산자는 변수, 형식 또는 멤버의 이름을 문자열 상수로 가져옵니다.

[!code-csharp-interactive[nameof operator](snippets/NameOfOperator.cs#Examples)]

이전 예제와 같이 형식 및 네임스페이스의 경우 생성되는 이름은 일반적으로 [정규화된](~/_csharplang/spec/basic-concepts.md#fully-qualified-names) 이름이 아닙니다.

`nameof` 연산자는 컴파일 시간에 평가되며 런타임에는 영향을 주지 않습니다.

`nameof` 연산자를 사용하여 인수 검사 코드를 더 쉽게 유지 관리할 수 있습니다.

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

`nameof` 연산자는 C# 6 이상에서 사용할 수 있습니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/expressions.md#nameof-expressions)의 [Nameof 식](~/_csharplang/spec/introduction.md) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 연산자](index.md)
