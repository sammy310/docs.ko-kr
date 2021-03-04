---
description: '자세한 정보: SByte 데이터 형식 (Visual Basic)'
title: SByte 데이터 형식
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
ms.openlocfilehash: a6a63ec742cf4a93080c9cc2f9906c5c6c21f0a8
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102102895"
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="2c508-103">SByte 데이터 형식 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c508-103">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="2c508-104">-128부터 127 까지의 값 범위에 해당 하는 부호 있는 8 비트 (1 바이트) 정수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-104">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>

## <a name="remarks"></a><span data-ttu-id="2c508-105">설명</span><span class="sxs-lookup"><span data-stu-id="2c508-105">Remarks</span></span>

<span data-ttu-id="2c508-106">`SByte`데이터 형식을 사용 하 여 전체 데이터 너비를 요구 하지 않는 정수 값을 포함 `Integer` 하거나의 데이터 너비의 절반에 해당 하는 정수 값을 포함 합니다 `Short` .</span><span class="sxs-lookup"><span data-stu-id="2c508-106">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="2c508-107">경우에 따라 공용 언어 런타임은 변수를 긴밀 하 게 압축 하 고 메모리 사용을 줄일 수 있습니다 `SByte` .</span><span class="sxs-lookup"><span data-stu-id="2c508-107">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="2c508-108">`SByte`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-108">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="2c508-109">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="2c508-109">Literal assignments</span></span>

<span data-ttu-id="2c508-110">`SByte`10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴 또는 (Visual Basic 2017부터) 이진 리터럴을 할당 하 여 변수를 선언 하 고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-110">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="2c508-111">다음 예제에서는 10 진수, 16 진수 및 이진 리터럴로 표시 되는-102와 동일한 정수가 값에 할당 됩니다 `SByte` .</span><span class="sxs-lookup"><span data-stu-id="2c508-111">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="2c508-112">이 예제를 사용 하려면 컴파일러 스위치를 사용 하 여 컴파일해야 `/removeintchecks` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-112">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> <span data-ttu-id="2c508-113">접두사 또는를 사용 하 여 `&h` `&H` 16 진수 리터럴을 표시 하거나, 접두사 또는을 사용 하 여 이진 리터럴을 표시 하 고, 접두사 또는를 사용 하 여 `&b` `&B` `&o` `&O` 8 진수 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-113">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="2c508-114">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-114">Decimal literals have no prefix.</span></span>

<span data-ttu-id="2c508-115">Visual Basic 2017부터 `_` 다음 예제와 같이 밑줄 문자를 자릿수 구분 기호로 사용 하 여 가독성을 높일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-115">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

<span data-ttu-id="2c508-116">Visual Basic 15.5부터 `_` 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 밑줄 문자 ()를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-116">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="2c508-117">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="2c508-117">For example:</span></span>

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="2c508-118">정수 리터럴이 `SByte` 범위를 벗어나는 경우(즉 <xref:System.SByte.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.SByte.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-118">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="2c508-119">정수 리터럴에 접미사가 없으면 [정수가](integer-data-type.md) 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-119">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="2c508-120">정수 리터럴이 형식의 범위를 벗어나면 `Integer` [Long](long-data-type.md) 이 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-120">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="2c508-121">즉, 앞의 예제에서 숫자 리터럴 및은 값이 `0x9A` `0b10011010` 156 인 32 비트 부호 있는 정수로 해석 됩니다 <xref:System.SByte.MaxValue?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="2c508-121">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2c508-122">Decimal이 아닌 정수를에 할당 하는 것과 같은 코드를 성공적으로 컴파일하려면 `SByte` 다음 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-122">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="2c508-123">컴파일러 스위치를 사용 하 여 컴파일하여 정수 범위 검사를 사용 하지 않도록 설정 `/removeintchecks` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-123">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="2c508-124">[형식 문자](../../programming-guide/language-features/data-types/type-characters.md) 를 사용 하 여에 할당 하려는 리터럴 값을 명시적으로 정의 `SByte` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-124">Use a [type character](../../programming-guide/language-features/data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="2c508-125">다음 예에서는에 음수 리터럴 값을 할당 합니다 `Short` `SByte` .</span><span class="sxs-lookup"><span data-stu-id="2c508-125">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="2c508-126">음수의 경우 숫자 리터럴의 상위 단어에 대 한 상위 비트를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-126">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="2c508-127">이 예제의 경우 리터럴 값의 비트는 15입니다 `Short` .</span><span class="sxs-lookup"><span data-stu-id="2c508-127">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="2c508-128">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="2c508-128">Programming tips</span></span>

- <span data-ttu-id="2c508-129">**CLS 규격.**</span><span class="sxs-lookup"><span data-stu-id="2c508-129">**CLS Compliance.**</span></span> <span data-ttu-id="2c508-130">`SByte`데이터 형식이 cls ( [공용 언어 사양](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/) )의 일부가 아니므로 cls 규격 코드는이를 사용 하는 구성 요소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-130">The `SByte` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="2c508-131">**넓혀.**</span><span class="sxs-lookup"><span data-stu-id="2c508-131">**Widening.**</span></span> <span data-ttu-id="2c508-132">`SByte`데이터 형식은,,,, 및로 확대 변환 `Short` `Integer` `Long` `Decimal` `Single` `Double` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-132">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="2c508-133">즉, `SByte` 오류가 발생 하지 않고 이러한 형식으로 변환할 수 있습니다 <xref:System.OverflowException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="2c508-133">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="2c508-134">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="2c508-134">**Type Characters.**</span></span> <span data-ttu-id="2c508-135">`SByte` 에는 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-135">`SByte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="2c508-136">**Framework 형식.**</span><span class="sxs-lookup"><span data-stu-id="2c508-136">**Framework Type.**</span></span> <span data-ttu-id="2c508-137">.NET Framework에서 해당하는 형식은 <xref:System.SByte?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="2c508-137">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c508-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c508-138">See also</span></span>

- <xref:System.SByte?displayProperty=nameWithType>
- [<span data-ttu-id="2c508-139">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2c508-139">Data Types</span></span>](index.md)
- [<span data-ttu-id="2c508-140">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="2c508-140">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="2c508-141">변환 요약</span><span class="sxs-lookup"><span data-stu-id="2c508-141">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="2c508-142">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2c508-142">Short Data Type</span></span>](short-data-type.md)
- [<span data-ttu-id="2c508-143">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2c508-143">Integer Data Type</span></span>](integer-data-type.md)
- [<span data-ttu-id="2c508-144">Long 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2c508-144">Long Data Type</span></span>](long-data-type.md)
- [<span data-ttu-id="2c508-145">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="2c508-145">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
