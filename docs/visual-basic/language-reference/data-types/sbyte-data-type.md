---
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
ms.openlocfilehash: 01a0a4a261213d7e6e2016bf49128092e5b22308
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401384"
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="d2d8f-102">SByte 데이터 유형(비주얼 베이직)</span><span class="sxs-lookup"><span data-stu-id="d2d8f-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="d2d8f-103">-128에서 127까지의 값 범위의 서명된 8비트(1바이트) 정수를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>

## <a name="remarks"></a><span data-ttu-id="d2d8f-104">설명</span><span class="sxs-lookup"><span data-stu-id="d2d8f-104">Remarks</span></span>

<span data-ttu-id="d2d8f-105">`SByte` 데이터 형식을 사용하여 `Short`의 전체 데이터 너비 `Integer` 또는 의 절반 데이터 너비가 필요하지 않은 정수 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="d2d8f-106">경우에 따라 공통 언어 런타임으로 `SByte` 변수를 밀접하게 압축하고 메모리 소비를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="d2d8f-107">`SByte`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="d2d8f-108">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="d2d8f-108">Literal assignments</span></span>

<span data-ttu-id="d2d8f-109">소수점 문자, 육각 형 리터럴, 옥탈 리터럴 또는 (Visual Basic 2017로 시작) 이진 리터럴을 할당하여 `SByte` 변수를 선언하고 초기화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="d2d8f-110">다음 예제에서는 소수점, 육각형 및 이진 리터럴로 표시되는 -102와 같은 정수는 값에 `SByte` 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="d2d8f-111">이 예제에서는 컴파일러 `/removeintchecks` 스위치를 사용 하 고 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> <span data-ttu-id="d2d8f-112">접두사를 `&h` 사용하거나 `&H` 육각 문자 문자, `&b` 접두사 또는 이진 `&B` 리터럴을 나타내거나 접두사를 `&o` 나타내거나 `&O` 팔각형 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="d2d8f-113">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="d2d8f-114">Visual Basic 2017부터는 다음 예제와 같이 `_`밑줄 문자를 숫자 구분 기호로 사용하여 가독성을 향상시킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

<span data-ttu-id="d2d8f-115">Visual Basic 15.5부터는 접두사와 육각형, 이진 또는 옥탈 숫자 사이의 선행 구분 기호로 밑줄 문자()를`_`사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="d2d8f-116">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-116">For example:</span></span>

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="d2d8f-117">정수 리터럴이 `SByte` 범위를 벗어나는 경우(즉 <xref:System.SByte.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.SByte.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-117">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="d2d8f-118">정수 리터럴에 접미사가 없는 경우 [정수는](integer-data-type.md) 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-118">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="d2d8f-119">정수 리터럴이 `Integer` 형식의 범위를 벗어나면 [Long이](long-data-type.md) 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-119">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="d2d8f-120">즉, 이전 예제에서는 숫자 `0x9A` 리터럴이 156값을 `0b10011010` 초과하는 32비트 서명된 정수로 해석됩니다. <xref:System.SByte.MaxValue?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d2d8f-120">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d2d8f-121">소수점 정수를 `SByte`할당하는 이와 같은 코드를 성공적으로 컴파일하려면 다음 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-121">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="d2d8f-122">`/removeintchecks` 컴파일러 스위치로 컴파일하여 정수 경계 검사를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-122">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="d2d8f-123">형식 [문자를](../../programming-guide/language-features/data-types/type-characters.md) 사용하여 `SByte`에 할당할 리터럴 값을 명시적으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-123">Use a [type character](../../programming-guide/language-features/data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="d2d8f-124">다음 예제에서 에 음수 `Short` 리터럴 `SByte`값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-124">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="d2d8f-125">음수의 경우 숫자 리터럴의 높은 차수 단어의 높은 순서 비트를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-125">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="d2d8f-126">이 예제의 경우 리터럴 `Short` 값의 비트 15입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-126">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="d2d8f-127">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="d2d8f-127">Programming tips</span></span>

- <span data-ttu-id="d2d8f-128">**CLS 규정 준수.**</span><span class="sxs-lookup"><span data-stu-id="d2d8f-128">**CLS Compliance.**</span></span> <span data-ttu-id="d2d8f-129">`SByte` 데이터 형식은 공통 언어 [사양(CLS)의](https://www.ecma-international.org/publications/standards/Ecma-335.htm) 일부가 아니므로 CLS 호환 코드는 이를 사용하는 구성 요소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-129">The `SByte` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="d2d8f-130">**확대.**</span><span class="sxs-lookup"><span data-stu-id="d2d8f-130">**Widening.**</span></span> <span data-ttu-id="d2d8f-131">데이터 `SByte` `Short`형식은 " `Integer` `Long` `Decimal` `Single`을 로 확대합니다. `Double`</span><span class="sxs-lookup"><span data-stu-id="d2d8f-131">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="d2d8f-132">즉, <xref:System.OverflowException?displayProperty=nameWithType> 오류가 `SByte` 발생하지 않고 이러한 유형으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-132">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="d2d8f-133">**문자를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2d8f-133">**Type Characters.**</span></span> <span data-ttu-id="d2d8f-134">`SByte`리터럴 형식 문자 또는 식별자 유형 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-134">`SByte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="d2d8f-135">**Framework 형식.**</span><span class="sxs-lookup"><span data-stu-id="d2d8f-135">**Framework Type.**</span></span> <span data-ttu-id="d2d8f-136">.NET Framework에서 해당하는 형식은 <xref:System.SByte?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d8f-136">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2d8f-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2d8f-137">See also</span></span>

- <xref:System.SByte?displayProperty=nameWithType>
- [<span data-ttu-id="d2d8f-138">데이터 유형</span><span class="sxs-lookup"><span data-stu-id="d2d8f-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="d2d8f-139">CString</span><span class="sxs-lookup"><span data-stu-id="d2d8f-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="d2d8f-140">변환 요약</span><span class="sxs-lookup"><span data-stu-id="d2d8f-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="d2d8f-141">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d2d8f-141">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="d2d8f-142">정수 데이터 유형</span><span class="sxs-lookup"><span data-stu-id="d2d8f-142">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="d2d8f-143">Long 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d2d8f-143">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="d2d8f-144">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="d2d8f-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
