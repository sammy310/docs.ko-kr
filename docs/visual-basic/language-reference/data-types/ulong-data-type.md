---
title: ULong 데이터 형식
ms.date: 01/31/2018
f1_keywords:
- vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
ms.openlocfilehash: 3c6cd4086e08b808c158948756b4806f098196b9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343878"
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="d1b29-102">ULong data type (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1b29-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="d1b29-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span><span class="sxs-lookup"><span data-stu-id="d1b29-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>

## <a name="remarks"></a><span data-ttu-id="d1b29-104">주의</span><span class="sxs-lookup"><span data-stu-id="d1b29-104">Remarks</span></span>

<span data-ttu-id="d1b29-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span><span class="sxs-lookup"><span data-stu-id="d1b29-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>

<span data-ttu-id="d1b29-106">`ULong`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="d1b29-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="d1b29-107">Literal assignments</span><span class="sxs-lookup"><span data-stu-id="d1b29-107">Literal assignments</span></span>

<span data-ttu-id="d1b29-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span><span class="sxs-lookup"><span data-stu-id="d1b29-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="d1b29-109">정수 리터럴이 `ULong` 범위를 벗어나는 경우(즉 <xref:System.UInt64.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d1b29-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="d1b29-110">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 7,934,076,125와 같은 정수가 `ULong` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1b29-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> <span data-ttu-id="d1b29-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span><span class="sxs-lookup"><span data-stu-id="d1b29-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="d1b29-112">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1b29-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="d1b29-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span><span class="sxs-lookup"><span data-stu-id="d1b29-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="d1b29-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span><span class="sxs-lookup"><span data-stu-id="d1b29-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="d1b29-115">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1b29-115">For example:</span></span>

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="d1b29-116">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span><span class="sxs-lookup"><span data-stu-id="d1b29-116">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="d1b29-117">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="d1b29-117">Programming tips</span></span>

- <span data-ttu-id="d1b29-118">**Negative Numbers.**</span><span class="sxs-lookup"><span data-stu-id="d1b29-118">**Negative Numbers.**</span></span> <span data-ttu-id="d1b29-119">Because `ULong` is an unsigned type, it cannot represent a negative number.</span><span class="sxs-lookup"><span data-stu-id="d1b29-119">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="d1b29-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span><span class="sxs-lookup"><span data-stu-id="d1b29-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>

- <span data-ttu-id="d1b29-121">**CLS Compliance.**</span><span class="sxs-lookup"><span data-stu-id="d1b29-121">**CLS Compliance.**</span></span> <span data-ttu-id="d1b29-122">The `ULong` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span><span class="sxs-lookup"><span data-stu-id="d1b29-122">The `ULong` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="d1b29-123">**Interop Considerations.**</span><span class="sxs-lookup"><span data-stu-id="d1b29-123">**Interop Considerations.**</span></span> <span data-ttu-id="d1b29-124">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span><span class="sxs-lookup"><span data-stu-id="d1b29-124">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="d1b29-125">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span><span class="sxs-lookup"><span data-stu-id="d1b29-125">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>

  <span data-ttu-id="d1b29-126">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="d1b29-126">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="d1b29-127">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span><span class="sxs-lookup"><span data-stu-id="d1b29-127">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>

- <span data-ttu-id="d1b29-128">**Widening.**</span><span class="sxs-lookup"><span data-stu-id="d1b29-128">**Widening.**</span></span> <span data-ttu-id="d1b29-129">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span><span class="sxs-lookup"><span data-stu-id="d1b29-129">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="d1b29-130">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="d1b29-130">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="d1b29-131">**Type Characters.**</span><span class="sxs-lookup"><span data-stu-id="d1b29-131">**Type Characters.**</span></span> <span data-ttu-id="d1b29-132">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span><span class="sxs-lookup"><span data-stu-id="d1b29-132">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="d1b29-133">`ULong` has no identifier type character.</span><span class="sxs-lookup"><span data-stu-id="d1b29-133">`ULong` has no identifier type character.</span></span>

- <span data-ttu-id="d1b29-134">**Framework Type.**</span><span class="sxs-lookup"><span data-stu-id="d1b29-134">**Framework Type.**</span></span> <span data-ttu-id="d1b29-135">.NET Framework에서 해당하는 형식은 <xref:System.UInt64?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="d1b29-135">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1b29-136">참조</span><span class="sxs-lookup"><span data-stu-id="d1b29-136">See also</span></span>

- <xref:System.UInt64>
- [<span data-ttu-id="d1b29-137">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d1b29-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="d1b29-138">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="d1b29-138">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="d1b29-139">변환 요약</span><span class="sxs-lookup"><span data-stu-id="d1b29-139">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="d1b29-140">방법: 부호 없는 형식을 사용하는 Windows 함수 호출</span><span class="sxs-lookup"><span data-stu-id="d1b29-140">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="d1b29-141">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="d1b29-141">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
