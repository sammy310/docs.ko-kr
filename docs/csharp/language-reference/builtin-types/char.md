---
title: char 형식- C# 참조
ms.date: 11/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 3b2eec4f0e17aa329fe3865fb3ef453ee030c6a7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450843"
---
# <a name="char-c-reference"></a><span data-ttu-id="f9204-102">char(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f9204-102">char (C# reference)</span></span>

<span data-ttu-id="f9204-103">`char` 형식 키워드는 유니코드 UTF-16 문자를 나타내는 .NET <xref:System.Char?displayProperty=nameWithType> 구조체 형식의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="f9204-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character.</span></span>

|<span data-ttu-id="f9204-104">형식</span><span class="sxs-lookup"><span data-stu-id="f9204-104">Type</span></span>|<span data-ttu-id="f9204-105">범위</span><span class="sxs-lookup"><span data-stu-id="f9204-105">Range</span></span>|<span data-ttu-id="f9204-106">Size</span><span class="sxs-lookup"><span data-stu-id="f9204-106">Size</span></span>|<span data-ttu-id="f9204-107">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="f9204-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="f9204-108">U+0000~U+FFFF</span><span class="sxs-lookup"><span data-stu-id="f9204-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="f9204-109">16비트</span><span class="sxs-lookup"><span data-stu-id="f9204-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

<span data-ttu-id="f9204-110">[string](reference-types.md#the-string-type) 형식은 텍스트를 `char` 값의 시퀀스로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9204-110">The [string](reference-types.md#the-string-type) type represents text as a sequence of `char` values.</span></span>

## <a name="literals"></a><span data-ttu-id="f9204-111">리터럴</span><span class="sxs-lookup"><span data-stu-id="f9204-111">Literals</span></span>

<span data-ttu-id="f9204-112">`char` 값을 다음 형식으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9204-112">You can specify a `char` value with:</span></span>

- <span data-ttu-id="f9204-113">문자 리터럴.</span><span class="sxs-lookup"><span data-stu-id="f9204-113">a character literal.</span></span>
- <span data-ttu-id="f9204-114">유니코드 이스케이프 시퀀스입니다. 이는 문자 코드의 네 개 기호를 사용하는 16진수 표현이 뒤에 표시되는 `\u`입니다.</span><span class="sxs-lookup"><span data-stu-id="f9204-114">a Unicode escape sequence, which is `\u` followed by the four-symbol hexadecimal representation of a character code.</span></span>
- <span data-ttu-id="f9204-115">16진수 이스케이프 시퀀스입니다. 이는 문자 코드의 16진수 표현이 뒤에 표시되는 `\x`입니다.</span><span class="sxs-lookup"><span data-stu-id="f9204-115">a hexadecimal escape sequence, which is `\x` followed by the hexadecimal representation of a character code.</span></span>

[!code-csharp-interactive[char literals](~/samples/csharp/language-reference/builtin-types/CharType.cs#Literals)]

<span data-ttu-id="f9204-116">앞의 예제에서 볼 수 있듯이, 문자 코드의 값을 해당하는 `char` 값으로 캐스팅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9204-116">As the preceding example shows, you also can cast the value of a character code into the corresponding `char` value.</span></span>

> [!NOTE]
> <span data-ttu-id="f9204-117">유니코드 이스케이프 시퀀스의 경우, 네 개의 16진수를 모두 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9204-117">In the case of a Unicode escape sequence, you must specify all four hexadecimal digits.</span></span> <span data-ttu-id="f9204-118">즉, `\u006A`은(는) 유효한 이스케이프 시퀀스이지만, `\u06A` 및 `\u6A`은(는) 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9204-118">That is, `\u006A` is a valid escape sequence, while `\u06A` and `\u6A` are not valid.</span></span>
>
> <span data-ttu-id="f9204-119">16진수 이스케이프 시퀀스의 경우, 앞에 오는 0을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9204-119">In the case of a hexadecimal escape sequence, you can omit the leading zeros.</span></span> <span data-ttu-id="f9204-120">즉, `\x006A`, `\x06A` 및 `\x6A` 이스케이프 시퀀스가 유효하며 동일한 문자에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="f9204-120">That is, the `\x006A`, `\x06A`, and `\x6A` escape sequences are valid and correspond to the same character.</span></span>

## <a name="conversions"></a><span data-ttu-id="f9204-121">변환</span><span class="sxs-lookup"><span data-stu-id="f9204-121">Conversions</span></span>

<span data-ttu-id="f9204-122">`char` 형식은 `ushort`, `int`, `uint`, `long`, `ulong` 등의 [정수](integral-numeric-types.md) 형식으로 암시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9204-122">The `char` type is implicitly convertible to the following [integral](integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="f9204-123">`float`, `double`, `decimal` 등의 기본 제공 [부동 소수점](floating-point-numeric-types.md) 숫자 형식으로 암시적으로 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9204-123">It's also implicitly convertible to the built-in [floating-point](floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="f9204-124">`sbyte`, `byte` 및 `short` 정수 형식으로 명시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9204-124">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="f9204-125">다른 형식에서 `char` 형식으로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9204-125">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="f9204-126">그러나 [정수](integral-numeric-types.md) 또는 [부동 소수점](floating-point-numeric-types.md) 숫자 형식을 `char`로 명시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9204-126">However, any [integral](integral-numeric-types.md) or [floating-point](floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f9204-127">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="f9204-127">C# language specification</span></span>

<span data-ttu-id="f9204-128">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [정수 형식](~/_csharplang/spec/types.md#integral-types) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9204-128">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f9204-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9204-129">See also</span></span>

- [<span data-ttu-id="f9204-130">C# 참조</span><span class="sxs-lookup"><span data-stu-id="f9204-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f9204-131">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="f9204-131">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="f9204-132">문자열</span><span class="sxs-lookup"><span data-stu-id="f9204-132">Strings</span></span>](../../programming-guide/strings/index.md)
