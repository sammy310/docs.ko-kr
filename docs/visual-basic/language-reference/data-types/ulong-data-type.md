---
title: ULong 데이터 형식(Visual Basic)
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
ms.openlocfilehash: 19a75f056436b858a22588d7ac5f37df5dd326f2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583120"
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="9bd47-102">ULong 데이터 형식 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bd47-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="9bd47-103">0에서 18446744073709551615 까지의 값에 해당 하는 부호 없는 64 비트 (8 바이트) 정수를 보유 합니다 (1.84 시간 10 ^ 19 초과).</span><span class="sxs-lookup"><span data-stu-id="9bd47-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>

## <a name="remarks"></a><span data-ttu-id="9bd47-104">주의</span><span class="sxs-lookup"><span data-stu-id="9bd47-104">Remarks</span></span>

<span data-ttu-id="9bd47-105">@No__t_0 데이터 형식을 사용 하 여 `UInteger`에 비해 너무 큰 이진 데이터 또는 가능한 가장 큰 부호 없는 정수 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>

<span data-ttu-id="9bd47-106">`ULong`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="9bd47-107">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="9bd47-107">Literal assignments</span></span>

<span data-ttu-id="9bd47-108">10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴 또는 (2017 Visual Basic부터) 이진 리터럴을 할당 하 여 `ULong` 변수를 선언 하 고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="9bd47-109">정수 리터럴이 `ULong` 범위를 벗어나는 경우(즉 <xref:System.UInt64.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="9bd47-110">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 7,934,076,125와 같은 정수가 `ULong` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> <span data-ttu-id="9bd47-111">@No__t_0 또는 `&H` 접두사를 사용 하 여 16 진수 리터럴을 나타내고, 접두사 `&b` 또는 `&B`를 사용 하 여 이진 리터럴을 표시 하 고, 접두사 `&o` 또는 `&O`을 사용 하 여 8 진수 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="9bd47-112">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="9bd47-113">Visual Basic 2017부터 다음 예제에 나와 있는 것 처럼 밑줄 문자 `_`를 자릿수 구분 기호로 사용 하 여 가독성을 높일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="9bd47-114">Visual Basic 15.5부터 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 밑줄 문자 (`_`)를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="9bd47-115">예를 들면,</span><span class="sxs-lookup"><span data-stu-id="9bd47-115">For example:</span></span>

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="9bd47-116">숫자 리터럴은 `UL` 또는 `ul` [형식 문자](../../programming-guide/language-features/data-types/type-characters.md) 를 포함 하 여 다음 예제와 같이 `ULong` 데이터 형식을 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-116">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="9bd47-117">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="9bd47-117">Programming tips</span></span>

- <span data-ttu-id="9bd47-118">**음수.**</span><span class="sxs-lookup"><span data-stu-id="9bd47-118">**Negative Numbers.**</span></span> <span data-ttu-id="9bd47-119">@No__t_0는 부호 없는 형식이 기 때문에 음수를 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-119">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="9bd47-120">@No__t_1 형식을 반환 하는 식에 단항 빼기 (`-`) 연산자를 사용 하는 경우 Visual Basic 식을 먼저 `Decimal` 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>

- <span data-ttu-id="9bd47-121">**CLS 규격.**</span><span class="sxs-lookup"><span data-stu-id="9bd47-121">**CLS Compliance.**</span></span> <span data-ttu-id="9bd47-122">@No__t_0 데이터 형식은 cls ( [공용 언어 사양](https://www.ecma-international.org/publications/standards/Ecma-335.htm) )의 일부가 아니므로 cls 규격 코드는이를 사용 하는 구성 요소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-122">The `ULong` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="9bd47-123">**Interop 고려 사항**</span><span class="sxs-lookup"><span data-stu-id="9bd47-123">**Interop Considerations.**</span></span> <span data-ttu-id="9bd47-124">.NET Framework 용으로 작성 되지 않은 구성 요소 (예: Automation 또는 COM 개체)와 상호 작용 하는 경우 `ulong` 같은 형식에 다른 환경에서 다른 데이터 너비 (32 비트)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-124">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="9bd47-125">이러한 구성 요소에 32 비트 인수를 전달 하는 경우 관리 되는 Visual Basic 코드에서 `ULong` 대신 `UInteger`으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-125">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>

  <span data-ttu-id="9bd47-126">또한 자동화는 Windows 95, Windows 98, Windows ME 또는 Windows 2000에서 64 비트 정수를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-126">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="9bd47-127">이러한 플랫폼의 자동화 구성 요소에 Visual Basic `ULong` 인수를 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-127">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>

- <span data-ttu-id="9bd47-128">**넓혀.**</span><span class="sxs-lookup"><span data-stu-id="9bd47-128">**Widening.**</span></span> <span data-ttu-id="9bd47-129">@No__t_0 데이터 형식은 `Decimal`, `Single` 및 `Double`로 확대 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-129">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="9bd47-130">즉, <xref:System.OverflowException?displayProperty=nameWithType> 오류가 발생 하지 않고 `ULong`를 이러한 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-130">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="9bd47-131">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9bd47-131">**Type Characters.**</span></span> <span data-ttu-id="9bd47-132">리터럴 형식 문자 `UL`을 리터럴에 추가 하면 `ULong` 데이터 형식으로 강제 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-132">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="9bd47-133">`ULong`에 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-133">`ULong` has no identifier type character.</span></span>

- <span data-ttu-id="9bd47-134">**프레임 워크 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="9bd47-134">**Framework Type.**</span></span> <span data-ttu-id="9bd47-135">.NET Framework에서 해당하는 형식은 <xref:System.UInt64?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="9bd47-135">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="9bd47-136">참조</span><span class="sxs-lookup"><span data-stu-id="9bd47-136">See also</span></span>

- <xref:System.UInt64>
- [<span data-ttu-id="9bd47-137">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9bd47-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="9bd47-138">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="9bd47-138">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="9bd47-139">변환 요약</span><span class="sxs-lookup"><span data-stu-id="9bd47-139">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="9bd47-140">방법: 부호 없는 형식을 사용하는 Windows 함수 호출</span><span class="sxs-lookup"><span data-stu-id="9bd47-140">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="9bd47-141">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="9bd47-141">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
