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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401318"
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="500c6-102">ULong 데이터 유형(비주얼 베이직)</span><span class="sxs-lookup"><span data-stu-id="500c6-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="500c6-103">0에서 18,446,744,073,709,551,615(1.84배 10 ^ 19)의 값에 이르는 서명되지 않은 64비트(8바이트) 정수를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>

## <a name="remarks"></a><span data-ttu-id="500c6-104">설명</span><span class="sxs-lookup"><span data-stu-id="500c6-104">Remarks</span></span>

<span data-ttu-id="500c6-105">`ULong` 데이터 형식을 사용하여 이진 데이터가 `UInteger`너무 크거나 서명되지 않은 가장 큰 정수 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>

<span data-ttu-id="500c6-106">`ULong`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="500c6-107">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="500c6-107">Literal assignments</span></span>

<span data-ttu-id="500c6-108">소수점 문자, 육각 형 리터럴, 옥탈 리터럴 또는 (Visual Basic 2017로 시작) 이진 리터럴을 할당하여 `ULong` 변수를 선언하고 초기화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="500c6-109">정수 리터럴이 `ULong` 범위를 벗어나는 경우(즉 <xref:System.UInt64.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="500c6-110">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 7,934,076,125와 같은 정수가 `ULong` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> <span data-ttu-id="500c6-111">접두사를 `&h` 사용하거나 `&H` 육각 문자 문자, `&b` 접두사 또는 이진 `&B` 리터럴을 나타내거나 접두사를 `&o` 나타내거나 `&O` 팔각형 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="500c6-112">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="500c6-113">Visual Basic 2017부터는 다음 예제와 같이 `_`밑줄 문자를 숫자 구분 기호로 사용하여 가독성을 향상시킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="500c6-114">Visual Basic 15.5부터는 접두사와 육각형, 이진 또는 옥탈 숫자 사이의 선행 구분 기호로 밑줄 문자()를`_`사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="500c6-115">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-115">For example:</span></span>

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="500c6-116">숫자 리터럴은 다음 `UL` 예제와 `ul` 같이 `ULong` 데이터 형식을 나타내는 문자 또는 [형식을](../../programming-guide/language-features/data-types/type-characters.md) 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-116">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="500c6-117">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="500c6-117">Programming tips</span></span>

- <span data-ttu-id="500c6-118">**음수.**</span><span class="sxs-lookup"><span data-stu-id="500c6-118">**Negative Numbers.**</span></span> <span data-ttu-id="500c6-119">서명되지 않은 형식이기 때문에 `ULong` 음수를 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-119">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="500c6-120">입력을`-` `ULong`평가하는 식에서 unary 빼기 () 연산자를 사용하는 경우 `Decimal` Visual Basic은 식을 먼저 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>

- <span data-ttu-id="500c6-121">**CLS 규정 준수.**</span><span class="sxs-lookup"><span data-stu-id="500c6-121">**CLS Compliance.**</span></span> <span data-ttu-id="500c6-122">`ULong` 데이터 형식은 공통 언어 [사양(CLS)의](https://www.ecma-international.org/publications/standards/Ecma-335.htm) 일부가 아니므로 CLS 호환 코드는 이를 사용하는 구성 요소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-122">The `ULong` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="500c6-123">**Interop 고려 사항.**</span><span class="sxs-lookup"><span data-stu-id="500c6-123">**Interop Considerations.**</span></span> <span data-ttu-id="500c6-124">.NET Framework에 대해 작성되지 않은 구성 요소(예: 자동화 또는 COM 개체)와 `ulong` 인터페이싱하는 경우 다른 환경에서 다른 데이터 너비(32비트)를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-124">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="500c6-125">이러한 구성 요소에 32비트 인수를 전달하는 경우 관리되는 `UInteger` Visual `ULong` Basic 코드가 아닌 것처럼 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-125">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>

  <span data-ttu-id="500c6-126">또한 자동화는 Windows 95, Windows 98, Windows ME 또는 Windows 2000에서 64비트 정수를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-126">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="500c6-127">이러한 플랫폼의 자동화 `ULong` 구성 요소에 Visual Basic 인수를 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-127">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>

- <span data-ttu-id="500c6-128">**확대.**</span><span class="sxs-lookup"><span data-stu-id="500c6-128">**Widening.**</span></span> <span data-ttu-id="500c6-129">데이터 `ULong` 형식은 에 `Decimal` `Single`대해 `Double`넓혀지고 .</span><span class="sxs-lookup"><span data-stu-id="500c6-129">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="500c6-130">즉, <xref:System.OverflowException?displayProperty=nameWithType> 오류가 `ULong` 발생하지 않고 이러한 유형으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-130">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="500c6-131">**문자를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="500c6-131">**Type Characters.**</span></span> <span data-ttu-id="500c6-132">리터럴 형식 문자를 `UL` 리터럴 문자에 적용하면 `ULong` 데이터 형식에 강제로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-132">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="500c6-133">`ULong`식별자 유형 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-133">`ULong` has no identifier type character.</span></span>

- <span data-ttu-id="500c6-134">**Framework 형식.**</span><span class="sxs-lookup"><span data-stu-id="500c6-134">**Framework Type.**</span></span> <span data-ttu-id="500c6-135">.NET Framework에서 해당하는 형식은 <xref:System.UInt64?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="500c6-135">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="500c6-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="500c6-136">See also</span></span>

- <xref:System.UInt64>
- [<span data-ttu-id="500c6-137">데이터 유형</span><span class="sxs-lookup"><span data-stu-id="500c6-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="500c6-138">CString</span><span class="sxs-lookup"><span data-stu-id="500c6-138">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="500c6-139">변환 요약</span><span class="sxs-lookup"><span data-stu-id="500c6-139">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="500c6-140">방법: 부호 없는 형식을 사용하는 Windows 함수 호출</span><span class="sxs-lookup"><span data-stu-id="500c6-140">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="500c6-141">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="500c6-141">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
