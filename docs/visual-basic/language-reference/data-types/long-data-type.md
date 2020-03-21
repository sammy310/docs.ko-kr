---
title: Long 데이터 형식
ms.date: 01/31/2018
f1_keywords:
- vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
ms.openlocfilehash: 16d7409c802e97b1f33474d810134db4d9f0ad6c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401402"
---
# <a name="long-data-type-visual-basic"></a><span data-ttu-id="8667b-102">긴 데이터 유형(비주얼 베이직)</span><span class="sxs-lookup"><span data-stu-id="8667b-102">Long data type (Visual Basic)</span></span>

<span data-ttu-id="8667b-103">보유 는 -9,223,372,036,854,775,808에서 9,223,372,032,854,775,807 (9.2...E+18)의 가치에 이르는 64비트(8바이트) 정수에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span></span>

## <a name="remarks"></a><span data-ttu-id="8667b-104">설명</span><span class="sxs-lookup"><span data-stu-id="8667b-104">Remarks</span></span>

<span data-ttu-id="8667b-105">데이터 `Long` 형식을 사용하여 데이터 형식에 맞지 않는 너무 큰 `Integer` 정수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span></span>

<span data-ttu-id="8667b-106">`Long`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-106">The default value of `Long` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="8667b-107">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="8667b-107">Literal assignments</span></span>

<span data-ttu-id="8667b-108">소수점 문자, 육각 형 리터럴, 옥탈 리터럴 또는 (Visual Basic 2017로 시작) 이진 리터럴을 할당하여 `Long` 변수를 선언하고 초기화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="8667b-109">정수 리터럴이 `Long` 범위를 벗어나는 경우(즉 <xref:System.Int64.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.Int64.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-109">If the integer literal is outside the range of `Long` (that is, if it is less than <xref:System.Int64.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="8667b-110">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 4,294,967,296과 같은 정수가 `Long` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-110">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `Long` values.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> <span data-ttu-id="8667b-111">접두사를 `&h` 사용하거나 `&H` 육각 문자 문자, `&b` 접두사 또는 이진 `&B` 리터럴을 나타내거나 접두사를 `&o` 나타내거나 `&O` 팔각형 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="8667b-112">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="8667b-113">Visual Basic 2017부터는 다음 예제와 같이 `_`밑줄 문자를 숫자 구분 기호로 사용하여 가독성을 향상시킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="8667b-114">Visual Basic 15.5부터는 접두사와 육각형, 이진 또는 옥탈 숫자 사이의 선행 구분 기호로 밑줄 문자()를`_`사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="8667b-115">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-115">For example:</span></span>

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="8667b-116">숫자 리터럴은 다음 예제와 `L` 같이 `Long` 데이터 형식을 나타내는 형식 [문자를](../../programming-guide/language-features/data-types/type-characters.md) 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-116">Numeric literals can also include the `L` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a><span data-ttu-id="8667b-117">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="8667b-117">Programming tips</span></span>

- <span data-ttu-id="8667b-118">**Interop 고려 사항.**</span><span class="sxs-lookup"><span data-stu-id="8667b-118">**Interop Considerations.**</span></span> <span data-ttu-id="8667b-119">.NET Framework(예: 자동화 또는 COM 개체)에 대해 작성되지 않은 `Long` 구성 요소와 인터페이싱하는 경우 다른 환경에서는 데이터 너비(32비트)가 다르다는 것을 기억하십시오.</span><span class="sxs-lookup"><span data-stu-id="8667b-119">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="8667b-120">이러한 구성 요소에 32비트 인수를 전달하는 경우 새 `Integer` Visual `Long` Basic 코드 대신선언합니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-120">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span></span>

- <span data-ttu-id="8667b-121">**확대.**</span><span class="sxs-lookup"><span data-stu-id="8667b-121">**Widening.**</span></span> <span data-ttu-id="8667b-122">데이터 `Long` 형식은 `Decimal`을 `Single`로 `Double`확장합니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-122">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="8667b-123">이는 `Long` 오류 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType>를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-123">This means you can convert `Long` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="8667b-124">**문자를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="8667b-124">**Type Characters.**</span></span> <span data-ttu-id="8667b-125">리터럴 형식 문자 `L`를 리터럴에 추가하면 `Long` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-125">Appending the literal type character `L` to a literal forces it to the `Long` data type.</span></span> <span data-ttu-id="8667b-126">식별자 형식 문자 `&`를 식별자에 추가하면 `Long`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-126">Appending the identifier type character `&` to any identifier forces it to `Long`.</span></span>

- <span data-ttu-id="8667b-127">**Framework 형식.**</span><span class="sxs-lookup"><span data-stu-id="8667b-127">**Framework Type.**</span></span> <span data-ttu-id="8667b-128">.NET Framework에서 해당하는 형식은 <xref:System.Int64?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="8667b-128">The corresponding type in the .NET Framework is the <xref:System.Int64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="8667b-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8667b-129">See also</span></span>

- <xref:System.Int64>
- [<span data-ttu-id="8667b-130">데이터 유형</span><span class="sxs-lookup"><span data-stu-id="8667b-130">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="8667b-131">정수 데이터 유형</span><span class="sxs-lookup"><span data-stu-id="8667b-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="8667b-132">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8667b-132">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="8667b-133">CString</span><span class="sxs-lookup"><span data-stu-id="8667b-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="8667b-134">변환 요약</span><span class="sxs-lookup"><span data-stu-id="8667b-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="8667b-135">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="8667b-135">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
