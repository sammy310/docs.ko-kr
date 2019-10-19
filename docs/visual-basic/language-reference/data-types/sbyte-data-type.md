---
title: SByte 데이터 형식(Visual Basic)
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
ms.openlocfilehash: a962200195002858257b92e92e0dd1383d4fb2d2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582507"
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="b82d1-102">SByte 데이터 형식 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b82d1-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="b82d1-103">-128부터 127 까지의 값 범위에 해당 하는 부호 있는 8 비트 (1 바이트) 정수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>

## <a name="remarks"></a><span data-ttu-id="b82d1-104">주의</span><span class="sxs-lookup"><span data-stu-id="b82d1-104">Remarks</span></span>

<span data-ttu-id="b82d1-105">@No__t_0 데이터 형식을 사용 하 여 전체 데이터 너비가 `Integer` 또는 `Short`의 절반 데이터 너비를 요구 하지 않는 정수 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="b82d1-106">경우에 따라 공용 언어 런타임에서 `SByte` 변수를 긴밀 하 게 압축 하 고 메모리 사용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="b82d1-107">`SByte`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="b82d1-108">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="b82d1-108">Literal assignments</span></span>

<span data-ttu-id="b82d1-109">10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴 또는 (2017 Visual Basic부터) 이진 리터럴을 할당 하 여 `SByte` 변수를 선언 하 고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="b82d1-110">다음 예제에서는 10 진수, 16 진수 및 이진 리터럴로 표시 되는-102와 동일한 정수가 `SByte` 값에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="b82d1-111">이 예제를 사용 하려면 `/removeintchecks` 컴파일러 스위치를 사용 하 여 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> <span data-ttu-id="b82d1-112">@No__t_0 또는 `&H` 접두사를 사용 하 여 16 진수 리터럴을 나타내고, 접두사 `&b` 또는 `&B`를 사용 하 여 이진 리터럴을 표시 하 고, 접두사 `&o` 또는 `&O`을 사용 하 여 8 진수 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="b82d1-113">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="b82d1-114">Visual Basic 2017부터 다음 예제에 나와 있는 것 처럼 밑줄 문자 `_`를 자릿수 구분 기호로 사용 하 여 가독성을 높일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

<span data-ttu-id="b82d1-115">Visual Basic 15.5부터 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 밑줄 문자 (`_`)를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="b82d1-116">예를 들면,</span><span class="sxs-lookup"><span data-stu-id="b82d1-116">For example:</span></span>

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="b82d1-117">정수 리터럴이 `SByte` 범위를 벗어나는 경우(즉 <xref:System.SByte.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.SByte.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-117">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="b82d1-118">정수 리터럴에 접미사가 없으면 [정수가](integer-data-type.md) 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-118">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="b82d1-119">정수 리터럴이 `Integer` 형식의 범위를 벗어나면 [Long](long-data-type.md) 이 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-119">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="b82d1-120">즉, 앞의 예제에서 숫자 리터럴 `0x9A` 및 `0b10011010` 값이 156 인 32 비트의 부호 있는 정수로 해석 됩니다 .이 값은 <xref:System.SByte.MaxValue?displayProperty=nameWithType>을 초과 합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-120">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b82d1-121">@No__t_0에 10 진수가 아닌 정수를 할당 하는 다음과 같은 코드를 성공적으로 컴파일하려면 다음 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-121">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="b82d1-122">@No__t_0 컴파일러 스위치를 사용 하 여 컴파일하여 정수 범위 검사를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-122">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="b82d1-123">[형식 문자](../../programming-guide/language-features/data-types/type-characters.md) 를 사용 하 여 `SByte`에 할당 하려는 리터럴 값을 명시적으로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-123">Use a [type character](../../programming-guide/language-features/data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="b82d1-124">다음 예에서는 `SByte`에 음수 리터럴 `Short` 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-124">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="b82d1-125">음수의 경우 숫자 리터럴의 상위 단어에 대 한 상위 비트를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-125">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="b82d1-126">이 예제의 경우 리터럴 `Short` 값의 비트 15입니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-126">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="b82d1-127">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="b82d1-127">Programming tips</span></span>

- <span data-ttu-id="b82d1-128">**CLS 규격.**</span><span class="sxs-lookup"><span data-stu-id="b82d1-128">**CLS Compliance.**</span></span> <span data-ttu-id="b82d1-129">@No__t_0 데이터 형식은 cls ( [공용 언어 사양](https://www.ecma-international.org/publications/standards/Ecma-335.htm) )의 일부가 아니므로 cls 규격 코드는이를 사용 하는 구성 요소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-129">The `SByte` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="b82d1-130">**넓혀.**</span><span class="sxs-lookup"><span data-stu-id="b82d1-130">**Widening.**</span></span> <span data-ttu-id="b82d1-131">@No__t_0 데이터 형식은 `Short`, `Integer`, `Long`, `Decimal`, `Single` 및 `Double`로 확대 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-131">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="b82d1-132">즉, <xref:System.OverflowException?displayProperty=nameWithType> 오류가 발생 하지 않고 `SByte`를 이러한 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-132">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="b82d1-133">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b82d1-133">**Type Characters.**</span></span> <span data-ttu-id="b82d1-134">`SByte`에는 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-134">`SByte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="b82d1-135">**프레임 워크 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="b82d1-135">**Framework Type.**</span></span> <span data-ttu-id="b82d1-136">.NET Framework에서 해당하는 형식은 <xref:System.SByte?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="b82d1-136">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="b82d1-137">참조</span><span class="sxs-lookup"><span data-stu-id="b82d1-137">See also</span></span>

- <xref:System.SByte?displayProperty=nameWithType>
- [<span data-ttu-id="b82d1-138">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b82d1-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="b82d1-139">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="b82d1-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="b82d1-140">변환 요약</span><span class="sxs-lookup"><span data-stu-id="b82d1-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="b82d1-141">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b82d1-141">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="b82d1-142">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b82d1-142">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="b82d1-143">Long 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b82d1-143">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="b82d1-144">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="b82d1-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
