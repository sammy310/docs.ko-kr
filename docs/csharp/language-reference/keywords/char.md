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
# <a name="char-c-reference"></a><span data-ttu-id="1a978-102">char(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="1a978-102">char (C# reference)</span></span>

<span data-ttu-id="1a978-103">`char` 형식 키워드는 유니코드 UTF-16 문자를 나타내는 .NET <xref:System.Char?displayProperty=nameWithType> 구조체 형식의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="1a978-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character:</span></span>

|<span data-ttu-id="1a978-104">형식</span><span class="sxs-lookup"><span data-stu-id="1a978-104">Type</span></span>|<span data-ttu-id="1a978-105">범위</span><span class="sxs-lookup"><span data-stu-id="1a978-105">Range</span></span>|<span data-ttu-id="1a978-106">Size</span><span class="sxs-lookup"><span data-stu-id="1a978-106">Size</span></span>|<span data-ttu-id="1a978-107">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="1a978-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="1a978-108">U+0000~U+FFFF</span><span class="sxs-lookup"><span data-stu-id="1a978-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="1a978-109">16비트</span><span class="sxs-lookup"><span data-stu-id="1a978-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="1a978-110">리터럴</span><span class="sxs-lookup"><span data-stu-id="1a978-110">Literals</span></span>

<span data-ttu-id="1a978-111">`char` 형식의 상수는 문자 리터럴, 16진수 이스케이프 시퀀스 또는 유니코드 표현으로 기록될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a978-111">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="1a978-112">정수 문자 코드를 해당하는 `char` 값으로 캐스팅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a978-112">You can also cast an integral character code into the corresponding `char` value.</span></span> <span data-ttu-id="1a978-113">다음 예제에서는 `char` 배열의 네 요소가 같은 문자 `X`로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a978-113">In the following example, the four elements of an array of `char` are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="1a978-114">변환</span><span class="sxs-lookup"><span data-stu-id="1a978-114">Conversions</span></span>

<span data-ttu-id="1a978-115">`char` 형식은 `ushort`, `int`, `uint`, `long`, `ulong` 등의 [정수](../builtin-types/integral-numeric-types.md) 형식으로 암시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a978-115">The `char` type is implicitly convertible to the following [integral](../builtin-types/integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="1a978-116">`float`, `double`, `decimal` 등의 기본 제공 [부동 소수점](../builtin-types/floating-point-numeric-types.md) 숫자 형식으로 암시적으로 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a978-116">It's also implicitly convertible to the built-in [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="1a978-117">`sbyte`, `byte` 및 `short` 정수 형식으로 명시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a978-117">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="1a978-118">다른 형식에서 `char` 형식으로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a978-118">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="1a978-119">그러나 [정수](../builtin-types/integral-numeric-types.md) 또는 [부동 소수점](../builtin-types/floating-point-numeric-types.md) 숫자 형식을 `char`로 명시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a978-119">However, any [integral](../builtin-types/integral-numeric-types.md) or [floating-point](../builtin-types/floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1a978-120">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="1a978-120">C# language specification</span></span>

<span data-ttu-id="1a978-121">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [정수 형식](~/_csharplang/spec/types.md#integral-types) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a978-121">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1a978-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a978-122">See also</span></span>

- [<span data-ttu-id="1a978-123">C# 참조</span><span class="sxs-lookup"><span data-stu-id="1a978-123">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1a978-124">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="1a978-124">C# keywords</span></span>](./index.md)
- [<span data-ttu-id="1a978-125">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="1a978-125">Built-in types table</span></span>](./built-in-types-table.md)
- [<span data-ttu-id="1a978-126">문자열</span><span class="sxs-lookup"><span data-stu-id="1a978-126">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Char?displayProperty=nameWithType>
