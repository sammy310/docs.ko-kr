---
title: char 키워드 - C# 참조
ms.custom: seodec18
ms.date: 10/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 1b9f8d1bb205a6cbfe521830a11bd8878ccde991
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771794"
---
# <a name="char-c-reference"></a>char(C# 참조)

`char` 형식 키워드는 유니코드 UTF-16 문자를 나타내는 .NET <xref:System.Char?displayProperty=nameWithType> 구조체 형식의 별칭입니다.

|형식|범위|Size|.NET 형식|
|----------|-----------|----------|-------------------------|
|`char`|U+0000~U+FFFF|16비트|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a>리터럴

`char` 형식의 상수는 문자 리터럴, 16진수 이스케이프 시퀀스 또는 유니코드 표현으로 기록될 수 있습니다. 정수 문자 코드를 해당하는 `char` 값으로 캐스팅할 수도 있습니다. 다음 예제에서는 `char` 배열의 네 요소가 같은 문자 `X`로 초기화됩니다.

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a>변환

`char` 형식은 `ushort`, `int`, `uint`, `long`, `ulong` 등의 [정수](../builtin-types/integral-numeric-types.md) 형식으로 암시적으로 변환할 수 있습니다. `float`, `double`, `decimal` 등의 기본 제공 [부동 소수점](../builtin-types/floating-point-numeric-types.md) 숫자 형식으로 암시적으로 변환할 수도 있습니다. `sbyte`, `byte` 및 `short` 정수 형식으로 명시적으로 변환할 수 있습니다.

다른 형식에서 `char` 형식으로의 암시적 변환은 없습니다. 그러나 [정수](../builtin-types/integral-numeric-types.md) 또는 [부동 소수점](../builtin-types/floating-point-numeric-types.md) 숫자 형식을 `char`로 명시적으로 변환할 수 있습니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [정수 형식](~/_csharplang/spec/types.md#integral-types) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 키워드](./index.md)
- [기본 제공 형식 표](./built-in-types-table.md)
- [문자열](../../programming-guide/strings/index.md)
- <xref:System.Char?displayProperty=nameWithType>
