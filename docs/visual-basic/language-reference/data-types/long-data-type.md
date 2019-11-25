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
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343970"
---
# <a name="long-data-type-visual-basic"></a><span data-ttu-id="bb6ca-102">Long data type (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb6ca-102">Long data type (Visual Basic)</span></span>

<span data-ttu-id="bb6ca-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span><span class="sxs-lookup"><span data-stu-id="bb6ca-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span></span>

## <a name="remarks"></a><span data-ttu-id="bb6ca-104">주의</span><span class="sxs-lookup"><span data-stu-id="bb6ca-104">Remarks</span></span>

<span data-ttu-id="bb6ca-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span></span>

<span data-ttu-id="bb6ca-106">`Long`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-106">The default value of `Long` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="bb6ca-107">Literal assignments</span><span class="sxs-lookup"><span data-stu-id="bb6ca-107">Literal assignments</span></span>

<span data-ttu-id="bb6ca-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="bb6ca-109">정수 리터럴이 `Long` 범위를 벗어나는 경우(즉 <xref:System.Int64.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.Int64.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-109">If the integer literal is outside the range of `Long` (that is, if it is less than <xref:System.Int64.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="bb6ca-110">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 4,294,967,296과 같은 정수가 `Long` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-110">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `Long` values.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> <span data-ttu-id="bb6ca-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="bb6ca-112">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="bb6ca-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="bb6ca-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="bb6ca-115">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-115">For example:</span></span>

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="bb6ca-116">Numeric literals can also include the `L` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-116">Numeric literals can also include the `L` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a><span data-ttu-id="bb6ca-117">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="bb6ca-117">Programming tips</span></span>

- <span data-ttu-id="bb6ca-118">**Interop Considerations.**</span><span class="sxs-lookup"><span data-stu-id="bb6ca-118">**Interop Considerations.**</span></span> <span data-ttu-id="bb6ca-119">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-119">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="bb6ca-120">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-120">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span></span>

- <span data-ttu-id="bb6ca-121">**Widening.**</span><span class="sxs-lookup"><span data-stu-id="bb6ca-121">**Widening.**</span></span> <span data-ttu-id="bb6ca-122">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-122">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="bb6ca-123">이는 `Long` 오류 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType>를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-123">This means you can convert `Long` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="bb6ca-124">**Type Characters.**</span><span class="sxs-lookup"><span data-stu-id="bb6ca-124">**Type Characters.**</span></span> <span data-ttu-id="bb6ca-125">리터럴 형식 문자 `L`를 리터럴에 추가하면 `Long` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-125">Appending the literal type character `L` to a literal forces it to the `Long` data type.</span></span> <span data-ttu-id="bb6ca-126">식별자 형식 문자 `&`를 식별자에 추가하면 `Long`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-126">Appending the identifier type character `&` to any identifier forces it to `Long`.</span></span>

- <span data-ttu-id="bb6ca-127">**Framework Type.**</span><span class="sxs-lookup"><span data-stu-id="bb6ca-127">**Framework Type.**</span></span> <span data-ttu-id="bb6ca-128">.NET Framework에서 해당하는 형식은 <xref:System.Int64?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="bb6ca-128">The corresponding type in the .NET Framework is the <xref:System.Int64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb6ca-129">참조</span><span class="sxs-lookup"><span data-stu-id="bb6ca-129">See also</span></span>

- <xref:System.Int64>
- [<span data-ttu-id="bb6ca-130">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bb6ca-130">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="bb6ca-131">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bb6ca-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="bb6ca-132">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bb6ca-132">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="bb6ca-133">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="bb6ca-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="bb6ca-134">변환 요약</span><span class="sxs-lookup"><span data-stu-id="bb6ca-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="bb6ca-135">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="bb6ca-135">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
