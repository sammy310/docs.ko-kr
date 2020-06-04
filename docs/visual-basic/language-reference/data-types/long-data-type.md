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
ms.openlocfilehash: 7c076cd2198c85560f7c63c69e051697966c9524
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415598"
---
# <a name="long-data-type-visual-basic"></a><span data-ttu-id="560c5-102">Long 데이터 형식 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="560c5-102">Long data type (Visual Basic)</span></span>

<span data-ttu-id="560c5-103">-9223372036854775808에서 9223372036854775807 (9.2 ... E + 18) 까지의 값 범위에 해당 하는 부호 있는 64 비트 (8 바이트) 정수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span></span>

## <a name="remarks"></a><span data-ttu-id="560c5-104">설명</span><span class="sxs-lookup"><span data-stu-id="560c5-104">Remarks</span></span>

<span data-ttu-id="560c5-105">데이터 형식을 사용 하 여 `Long` 너무 커서 데이터 형식에 맞지 않는 정수를 포함할 수 `Integer` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span></span>

<span data-ttu-id="560c5-106">`Long`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-106">The default value of `Long` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="560c5-107">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="560c5-107">Literal assignments</span></span>

<span data-ttu-id="560c5-108">`Long`10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴 또는 (Visual Basic 2017부터) 이진 리터럴을 할당 하 여 변수를 선언 하 고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="560c5-109">정수 리터럴이 `Long` 범위를 벗어나는 경우(즉 <xref:System.Int64.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.Int64.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-109">If the integer literal is outside the range of `Long` (that is, if it is less than <xref:System.Int64.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="560c5-110">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 4,294,967,296과 같은 정수가 `Long` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-110">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `Long` values.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> <span data-ttu-id="560c5-111">접두사 또는를 사용 하 여 `&h` `&H` 16 진수 리터럴을 표시 하거나, 접두사 또는을 사용 하 여 이진 리터럴을 표시 하 고, 접두사 또는를 사용 하 여 `&b` `&B` `&o` `&O` 8 진수 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="560c5-112">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="560c5-113">Visual Basic 2017부터 `_` 다음 예제와 같이 밑줄 문자를 자릿수 구분 기호로 사용 하 여 가독성을 높일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="560c5-114">Visual Basic 15.5부터 `_` 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 밑줄 문자 ()를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="560c5-115">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-115">For example:</span></span>

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="560c5-116">`L`다음 예제와 같이 숫자 리터럴은 [형식 문자](../../programming-guide/language-features/data-types/type-characters.md) 를 포함 하 여 데이터 형식을 나타낼 수도 있습니다 `Long` .</span><span class="sxs-lookup"><span data-stu-id="560c5-116">Numeric literals can also include the `L` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a><span data-ttu-id="560c5-117">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="560c5-117">Programming tips</span></span>

- <span data-ttu-id="560c5-118">**Interop 고려 사항.**</span><span class="sxs-lookup"><span data-stu-id="560c5-118">**Interop Considerations.**</span></span> <span data-ttu-id="560c5-119">.NET Framework 용으로 작성 되지 않은 구성 요소 (예: Automation 또는 COM 개체)와 상호 작용 하는 경우 `Long` 다른 환경에서는의 데이터 너비 (32 비트)가 다르다는 점에 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-119">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="560c5-120">이러한 구성 요소에 32 비트 인수를 전달 하는 경우 `Integer` `Long` 새 Visual Basic 코드에서 대신로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-120">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span></span>

- <span data-ttu-id="560c5-121">**넓혀.**</span><span class="sxs-lookup"><span data-stu-id="560c5-121">**Widening.**</span></span> <span data-ttu-id="560c5-122">`Long`데이터 형식은, 또는로 확대 변환 `Decimal` `Single` `Double` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-122">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="560c5-123">이는 `Long` 오류 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType>를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-123">This means you can convert `Long` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="560c5-124">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="560c5-124">**Type Characters.**</span></span> <span data-ttu-id="560c5-125">리터럴 형식 문자 `L`를 리터럴에 추가하면 `Long` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-125">Appending the literal type character `L` to a literal forces it to the `Long` data type.</span></span> <span data-ttu-id="560c5-126">식별자 형식 문자 `&`를 식별자에 추가하면 `Long`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-126">Appending the identifier type character `&` to any identifier forces it to `Long`.</span></span>

- <span data-ttu-id="560c5-127">**Framework 형식.**</span><span class="sxs-lookup"><span data-stu-id="560c5-127">**Framework Type.**</span></span> <span data-ttu-id="560c5-128">.NET Framework에서 해당하는 형식은 <xref:System.Int64?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="560c5-128">The corresponding type in the .NET Framework is the <xref:System.Int64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="560c5-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="560c5-129">See also</span></span>

- <xref:System.Int64>
- [<span data-ttu-id="560c5-130">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="560c5-130">Data Types</span></span>](index.md)
- [<span data-ttu-id="560c5-131">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="560c5-131">Integer Data Type</span></span>](integer-data-type.md)
- [<span data-ttu-id="560c5-132">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="560c5-132">Short Data Type</span></span>](short-data-type.md)
- [<span data-ttu-id="560c5-133">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="560c5-133">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="560c5-134">변환 요약</span><span class="sxs-lookup"><span data-stu-id="560c5-134">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="560c5-135">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="560c5-135">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
