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
ms.openlocfilehash: f4e95aacc8e7063cbac8f9ed8e117137836f08bd
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647026"
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="bcfeb-102">SByte 데이터 형식 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bcfeb-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="bcfeb-103">부호 있는 8 비트 (1 바이트) 정수 값 범위에 있는-128에서 127를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcfeb-104">설명</span><span class="sxs-lookup"><span data-stu-id="bcfeb-104">Remarks</span></span>

<span data-ttu-id="bcfeb-105">사용 된 `SByte` 의 전체 데이터 너비를 필요 하지 않은 정수 값을 포함 하는 데이터 형식 `Integer` 절반 데이터 너비 또는 `Short`.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="bcfeb-106">일부 경우에 공용 언어 런타임 팩 할 수 있습니다 프로그램 `SByte` 변수 밀접 하 게 함께 및 메모리 사용량을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="bcfeb-107">`SByte`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="bcfeb-108">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="bcfeb-108">Literal assignments</span></span>
  
<span data-ttu-id="bcfeb-109">선언 하 고 초기화할 수 있습니다는 `SByte` 변수 (Visual Basic 2017부터) 이진 리터럴을 또는 10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="bcfeb-110">다음 예제에서는 10 진수, 16 진수 표현 된-102와 같은 및 이진 리터럴로에 할당 된 `SByte` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="bcfeb-111">이 예제에서는 사용 하 여 컴파일하는 `/removeintchecks` 컴파일러 스위치입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> <span data-ttu-id="bcfeb-112">접두사를 사용할 `&h` 또는 `&H` 16 진수 리터럴, 접두사를 나타내는 `&b` 또는 `&B` 이진 리터럴 및 접두사를 나타내는 `&o` 또는 `&O` 8 진수 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="bcfeb-113">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="bcfeb-114">Visual Basic 2017부터 사용할 수도 있습니다 밑줄 문자 `_`, 가독성 향상을 위해 숫자 구분 기호를 다음 예제와 같이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

<span data-ttu-id="bcfeb-115">Visual Basic 15.5부터 사용할 수도 있습니다는 밑줄 문자 (`_`) 접두사 및 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="bcfeb-116">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="bcfeb-116">For example:</span></span>

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="bcfeb-117">정수 리터럴이 `SByte` 범위를 벗어나는 경우(즉 <xref:System.SByte.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.SByte.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-117">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="bcfeb-118">정수 리터럴에 접미사가 없는 경우는 [정수](integer-data-type.md) 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-118">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="bcfeb-119">정수 리터럴이의 범위를 벗어난 경우는 `Integer` 형식에는 [긴](long-data-type.md) 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-119">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="bcfeb-120">즉, 이전 예제에서는 숫자 리터럴 `0x9A` 하 고 `0b10011010` 초과 하는 156 인 값을 사용 하 여 32 비트 부호 있는 정수로 해석 됩니다 <xref:System.SByte.MaxValue?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-120">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bcfeb-121">성공적으로 10 진수가 아닌 정수를 할당 하는 다음과 같은 코드를 컴파일하는 데는 `SByte`, 다음 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-121">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="bcfeb-122">사용 하 여 컴파일하면 정수 범위 검사를 사용 하지 않도록 설정 된 `/removeintchecks` 컴파일러 스위치입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-122">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="bcfeb-123">사용 하 여는 [형식 문자](../../programming-guide/language-features/data-types/type-characters.md) 명시적으로 할당 하려는 리터럴 값을 정의 하는 `SByte`합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-123">Use a [type character](../../programming-guide/language-features/data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="bcfeb-124">다음 예제에서는 할당 음수 리터럴이 `Short` 값을 `SByte`입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-124">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="bcfeb-125">음수를 참고 하십시오 숫자 리터럴의 상위 단어의 상위 비트를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-125">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="bcfeb-126">이 예의 경우이 비트는 리터럴 15 `Short` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-126">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="bcfeb-127">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="bcfeb-127">Programming tips</span></span>
  
- <span data-ttu-id="bcfeb-128">**CLS 규격입니다.**</span><span class="sxs-lookup"><span data-stu-id="bcfeb-128">**CLS Compliance.**</span></span> <span data-ttu-id="bcfeb-129">합니다 `SByte` 데이터 형식이 아닙니다 부분 합니다 [공용 언어 사양](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), CLS 규격 코드를 사용 하는 구성 요소를 사용할 수 없습니다 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-129">The `SByte` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="bcfeb-130">**확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="bcfeb-130">**Widening.**</span></span> <span data-ttu-id="bcfeb-131">`SByte` 데이터 형식으로 확장 되는지를 `Short`, `Integer`, `Long`를 `Decimal`를 `Single`, 및 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-131">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="bcfeb-132">즉, 변환할 수 있습니다 `SByte` 발생 없이 이러한 형식 중 하나에 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-132">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
- <span data-ttu-id="bcfeb-133">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="bcfeb-133">**Type Characters.**</span></span> <span data-ttu-id="bcfeb-134">`SByte` 에 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-134">`SByte` has no literal type character or identifier type character.</span></span>  
  
- <span data-ttu-id="bcfeb-135">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="bcfeb-135">**Framework Type.**</span></span> <span data-ttu-id="bcfeb-136">.NET Framework에서 해당하는 형식은 <xref:System.SByte?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfeb-136">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bcfeb-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="bcfeb-137">See also</span></span>

- <xref:System.SByte?displayProperty=nameWithType>
- [<span data-ttu-id="bcfeb-138">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bcfeb-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="bcfeb-139">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="bcfeb-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="bcfeb-140">변환 요약</span><span class="sxs-lookup"><span data-stu-id="bcfeb-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="bcfeb-141">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bcfeb-141">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="bcfeb-142">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bcfeb-142">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="bcfeb-143">Long 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bcfeb-143">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="bcfeb-144">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="bcfeb-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
