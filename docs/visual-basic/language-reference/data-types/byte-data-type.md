---
title: Byte 데이터 형식
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 347d7e7d0f09e089886bc81bd0be659deaca9b46
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344073"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="72eac-102">Byte data type (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72eac-102">Byte data type (Visual Basic)</span></span>

<span data-ttu-id="72eac-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span><span class="sxs-lookup"><span data-stu-id="72eac-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="72eac-104">주의</span><span class="sxs-lookup"><span data-stu-id="72eac-104">Remarks</span></span>

<span data-ttu-id="72eac-105">Use the `Byte` data type to contain binary data.</span><span class="sxs-lookup"><span data-stu-id="72eac-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="72eac-106">`Byte`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="72eac-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="72eac-107">Literal assignments</span><span class="sxs-lookup"><span data-stu-id="72eac-107">Literal assignments</span></span>

<span data-ttu-id="72eac-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span><span class="sxs-lookup"><span data-stu-id="72eac-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="72eac-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span><span class="sxs-lookup"><span data-stu-id="72eac-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="72eac-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span><span class="sxs-lookup"><span data-stu-id="72eac-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="72eac-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span><span class="sxs-lookup"><span data-stu-id="72eac-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="72eac-112">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72eac-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="72eac-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span><span class="sxs-lookup"><span data-stu-id="72eac-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="72eac-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span><span class="sxs-lookup"><span data-stu-id="72eac-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="72eac-115">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72eac-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="72eac-116">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="72eac-116">Programming tips</span></span>

- <span data-ttu-id="72eac-117">**Negative Numbers.**</span><span class="sxs-lookup"><span data-stu-id="72eac-117">**Negative Numbers.**</span></span> <span data-ttu-id="72eac-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span><span class="sxs-lookup"><span data-stu-id="72eac-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="72eac-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span><span class="sxs-lookup"><span data-stu-id="72eac-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
- <span data-ttu-id="72eac-120">**Format Conversions.**</span><span class="sxs-lookup"><span data-stu-id="72eac-120">**Format Conversions.**</span></span> <span data-ttu-id="72eac-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span><span class="sxs-lookup"><span data-stu-id="72eac-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="72eac-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span><span class="sxs-lookup"><span data-stu-id="72eac-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="72eac-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span><span class="sxs-lookup"><span data-stu-id="72eac-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

- <span data-ttu-id="72eac-124">**Widening.**</span><span class="sxs-lookup"><span data-stu-id="72eac-124">**Widening.**</span></span> <span data-ttu-id="72eac-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span><span class="sxs-lookup"><span data-stu-id="72eac-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="72eac-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="72eac-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
- <span data-ttu-id="72eac-127">**Type Characters.**</span><span class="sxs-lookup"><span data-stu-id="72eac-127">**Type Characters.**</span></span> <span data-ttu-id="72eac-128">`Byte` has no literal type character or identifier type character.</span><span class="sxs-lookup"><span data-stu-id="72eac-128">`Byte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="72eac-129">**Framework Type.**</span><span class="sxs-lookup"><span data-stu-id="72eac-129">**Framework Type.**</span></span> <span data-ttu-id="72eac-130">.NET Framework에서 해당하는 형식은 <xref:System.Byte?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="72eac-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="72eac-131">예제</span><span class="sxs-lookup"><span data-stu-id="72eac-131">Example</span></span>

 <span data-ttu-id="72eac-132">In the following example, `b` is a `Byte` variable.</span><span class="sxs-lookup"><span data-stu-id="72eac-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="72eac-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span><span class="sxs-lookup"><span data-stu-id="72eac-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a><span data-ttu-id="72eac-134">참조</span><span class="sxs-lookup"><span data-stu-id="72eac-134">See also</span></span>

- <xref:System.Byte?displayProperty=nameWithType>
- [<span data-ttu-id="72eac-135">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="72eac-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="72eac-136">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="72eac-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="72eac-137">변환 요약</span><span class="sxs-lookup"><span data-stu-id="72eac-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="72eac-138">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="72eac-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
