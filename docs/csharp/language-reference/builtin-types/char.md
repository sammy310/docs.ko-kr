---
title: char 형식- C# 참조
ms.date: 11/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 8727e47e13082e8550fb174c92139dfd5c17ec36
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134335"
---
# <a name="char-c-reference"></a>char(C# 참조)

`char` 형식 키워드는 유니코드 UTF-16 문자를 나타내는 .NET <xref:System.Char?displayProperty=nameWithType> 구조체 형식의 별칭입니다.

|Type|범위|크기|.NET 형식|
|----------|-----------|----------|-------------------------|
|`char`|U+0000~U+FFFF|16비트|<xref:System.Char?displayProperty=nameWithType>|

`char` 형식의 기본값은 `\0`(U + 0000)입니다.

[string](reference-types.md#the-string-type) 형식은 텍스트를 `char` 값의 시퀀스로 나타냅니다.

## <a name="literals"></a>리터럴

`char` 값을 다음 형식으로 지정할 수 있습니다.

- 문자 리터럴.
- 유니코드 이스케이프 시퀀스입니다. 이는 문자 코드의 네 개 기호를 사용하는 16진수 표현이 뒤에 표시되는 `\u`입니다.
- 16진수 이스케이프 시퀀스입니다. 이는 문자 코드의 16진수 표현이 뒤에 표시되는 `\x`입니다.

[!code-csharp-interactive[char literals](snippets/CharType.cs#Literals)]

앞의 예제에서 볼 수 있듯이, 문자 코드의 값을 해당하는 `char` 값으로 캐스팅할 수도 있습니다.

> [!NOTE]
> 유니코드 이스케이프 시퀀스의 경우, 네 개의 16진수를 모두 지정해야 합니다. 즉, `\u006A`은(는) 유효한 이스케이프 시퀀스이지만, `\u06A` 및 `\u6A`은(는) 유효하지 않습니다.
>
> 16진수 이스케이프 시퀀스의 경우, 앞에 오는 0을 생략할 수 있습니다. 즉, `\x006A`, `\x06A` 및 `\x6A` 이스케이프 시퀀스가 유효하며 동일한 문자에 해당합니다.

## <a name="conversions"></a>변환

`char` 형식은 `ushort`, `int`, `uint`, `long`, `ulong` 등의 [정수](integral-numeric-types.md) 형식으로 암시적으로 변환할 수 있습니다. `float`, `double`, `decimal` 등의 기본 제공 [부동 소수점](floating-point-numeric-types.md) 숫자 형식으로 암시적으로 변환할 수도 있습니다. `sbyte`, `byte` 및 `short` 정수 형식으로 명시적으로 변환할 수 있습니다.

다른 형식에서 `char` 형식으로의 암시적 변환은 없습니다. 그러나 [정수](integral-numeric-types.md) 또는 [부동 소수점](floating-point-numeric-types.md) 숫자 형식을 `char`로 명시적으로 변환할 수 있습니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [정수 형식](~/_csharplang/spec/types.md#integral-types) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [값 형식](value-types.md)
- [문자열](../../programming-guide/strings/index.md)
- <xref:System.Text.Rune?displayProperty=nameWithType>
- [.NET의 문자 인코딩](../../../standard/base-types/character-encoding-introduction.md)
