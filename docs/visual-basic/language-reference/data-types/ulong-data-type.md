---
description: '자세한 정보: ULong 데이터 형식 (Visual Basic)'
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
ms.openlocfilehash: 9082fc9444f0754c60a6aa3f9b58db1d833349b8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792091"
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="ee176-103">ULong 데이터 형식 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee176-103">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="ee176-104">0에서 18446744073709551615 까지의 값에 해당 하는 부호 없는 64 비트 (8 바이트) 정수를 보유 합니다 (1.84 시간 10 ^ 19 초과).</span><span class="sxs-lookup"><span data-stu-id="ee176-104">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>

## <a name="remarks"></a><span data-ttu-id="ee176-105">설명</span><span class="sxs-lookup"><span data-stu-id="ee176-105">Remarks</span></span>

<span data-ttu-id="ee176-106">`ULong`에 대해 너무 큰 이진 데이터가 포함 되도록 데이터 형식을 사용 `UInteger` 하거나 부호 없는 최대 정수 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-106">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>

<span data-ttu-id="ee176-107">`ULong`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-107">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="ee176-108">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="ee176-108">Literal assignments</span></span>

<span data-ttu-id="ee176-109">`ULong`10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴 또는 (Visual Basic 2017부터) 이진 리터럴을 할당 하 여 변수를 선언 하 고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-109">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="ee176-110">정수 리터럴이 `ULong` 범위를 벗어나는 경우(즉 <xref:System.UInt64.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-110">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="ee176-111">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 7,934,076,125와 같은 정수가 `ULong` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-111">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> <span data-ttu-id="ee176-112">접두사 또는를 사용 하 여 `&h` `&H` 16 진수 리터럴을 표시 하거나, 접두사 또는을 사용 하 여 이진 리터럴을 표시 하 고, 접두사 또는를 사용 하 여 `&b` `&B` `&o` `&O` 8 진수 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="ee176-113">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="ee176-114">Visual Basic 2017부터 `_` 다음 예제와 같이 밑줄 문자를 자릿수 구분 기호로 사용 하 여 가독성을 높일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="ee176-115">Visual Basic 15.5부터 `_` 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 밑줄 문자 ()를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="ee176-116">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="ee176-116">For example:</span></span>

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="ee176-117">`UL`다음 예제와 같이 숫자 리터럴은 또는 `ul` [형식 문자](../../programming-guide/language-features/data-types/type-characters.md) 를 포함 하 여 데이터 형식을 나타낼 수도 있습니다 `ULong` .</span><span class="sxs-lookup"><span data-stu-id="ee176-117">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="ee176-118">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="ee176-118">Programming tips</span></span>

- <span data-ttu-id="ee176-119">**음수.**</span><span class="sxs-lookup"><span data-stu-id="ee176-119">**Negative Numbers.**</span></span> <span data-ttu-id="ee176-120">`ULong`는 부호 없는 형식이 기 때문에 음수를 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-120">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="ee176-121">`-`형식을 반환 하는 식에 단항 빼기 () 연산자를 사용 하는 경우 `ULong` Visual Basic는 식을 `Decimal` 먼저 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-121">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>

- <span data-ttu-id="ee176-122">**CLS 규격.**</span><span class="sxs-lookup"><span data-stu-id="ee176-122">**CLS Compliance.**</span></span> <span data-ttu-id="ee176-123">`ULong`데이터 형식이 cls ( [공용 언어 사양](https://www.ecma-international.org/publications/standards/Ecma-335.htm) )의 일부가 아니므로 cls 규격 코드는이를 사용 하는 구성 요소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-123">The `ULong` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="ee176-124">**Interop 고려 사항.**</span><span class="sxs-lookup"><span data-stu-id="ee176-124">**Interop Considerations.**</span></span> <span data-ttu-id="ee176-125">.NET Framework 용으로 작성 되지 않은 구성 요소 (예: Automation 또는 COM 개체)와 상호 작용 하는 경우와 같은 형식은 `ulong` 다른 환경에서 서로 다른 데이터 너비 (32 비트)를 가질 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="ee176-125">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="ee176-126">이러한 구성 요소에 32 비트 인수를 전달 하는 경우 `UInteger` `ULong` 관리 되는 Visual Basic 코드에서 대신로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-126">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>

  <span data-ttu-id="ee176-127">또한 자동화는 Windows 95, Windows 98, Windows ME 또는 Windows 2000에서 64 비트 정수를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-127">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="ee176-128">`ULong`이러한 플랫폼에서는 자동화 구성 요소에 Visual Basic 인수를 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-128">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>

- <span data-ttu-id="ee176-129">**넓혀.**</span><span class="sxs-lookup"><span data-stu-id="ee176-129">**Widening.**</span></span> <span data-ttu-id="ee176-130">`ULong`데이터 형식은, 및로 확대 변환 `Decimal` `Single` `Double` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-130">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="ee176-131">즉, `ULong` 오류가 발생 하지 않고 이러한 형식으로 변환할 수 있습니다 <xref:System.OverflowException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ee176-131">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="ee176-132">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ee176-132">**Type Characters.**</span></span> <span data-ttu-id="ee176-133">리터럴 형식 문자를 리터럴에 추가 하면 `UL` `ULong` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-133">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="ee176-134">`ULong` 에는 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-134">`ULong` has no identifier type character.</span></span>

- <span data-ttu-id="ee176-135">**Framework 형식.**</span><span class="sxs-lookup"><span data-stu-id="ee176-135">**Framework Type.**</span></span> <span data-ttu-id="ee176-136">.NET Framework에서 해당하는 형식은 <xref:System.UInt64?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="ee176-136">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee176-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee176-137">See also</span></span>

- <xref:System.UInt64>
- [<span data-ttu-id="ee176-138">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ee176-138">Data Types</span></span>](index.md)
- [<span data-ttu-id="ee176-139">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="ee176-139">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="ee176-140">변환 요약</span><span class="sxs-lookup"><span data-stu-id="ee176-140">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="ee176-141">방법: 부호 없는 형식을 사용하는 Windows 함수 호출</span><span class="sxs-lookup"><span data-stu-id="ee176-141">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="ee176-142">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="ee176-142">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
