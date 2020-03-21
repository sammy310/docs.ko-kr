---
title: Byte 데이터 형식
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 347d7e7d0f09e089886bc81bd0be659deaca9b46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401354"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="be33c-102">바이트 데이터 유형(비주얼 베이직)</span><span class="sxs-lookup"><span data-stu-id="be33c-102">Byte data type (Visual Basic)</span></span>

<span data-ttu-id="be33c-103">0에서 255까지의 값 범위의 서명되지 않은 8비트(1바이트) 정수를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="be33c-104">설명</span><span class="sxs-lookup"><span data-stu-id="be33c-104">Remarks</span></span>

<span data-ttu-id="be33c-105">`Byte` 데이터 형식을 사용하여 이진 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="be33c-106">`Byte`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="be33c-107">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="be33c-107">Literal assignments</span></span>

<span data-ttu-id="be33c-108">소수점 문자, 육각 형 리터럴, 옥탈 리터럴 또는 (Visual Basic 2017로 시작) 이진 리터럴을 할당하여 `Byte` 변수를 선언하고 초기화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="be33c-109">정수 리터럴이 a의 `Byte` 범위를 벗어나면(즉, 보다 <xref:System.Byte.MinValue?displayProperty=nameWithType> 크거나 <xref:System.Byte.MaxValue?displayProperty=nameWithType>큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="be33c-110">다음 예제에서는 소수점, 육각형 및 이진 리터럴로 표시되는 201과 같은 정수는 [정수에서](integer-data-type.md) 값으로 `byte` 암시적으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="be33c-111">접두사를 `&h` 사용하거나 `&H` 육각 문자 문자, `&b` 접두사 또는 이진 `&B` 리터럴을 나타내거나 접두사를 `&o` 나타내거나 `&O` 팔각형 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="be33c-112">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="be33c-113">Visual Basic 2017부터는 다음 예제와 같이 `_`밑줄 문자를 숫자 구분 기호로 사용하여 가독성을 향상시킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="be33c-114">Visual Basic 15.5부터는 접두사와 육각형, 이진 또는 옥탈 숫자 사이의 선행 구분 기호로 밑줄 문자()를`_`사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="be33c-115">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="be33c-116">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="be33c-116">Programming tips</span></span>

- <span data-ttu-id="be33c-117">**음수.**</span><span class="sxs-lookup"><span data-stu-id="be33c-117">**Negative Numbers.**</span></span> <span data-ttu-id="be33c-118">서명되지 않은 형식이기 때문에 `Byte` 음수를 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="be33c-119">입력을`-` `Byte`평가하는 식에서 unary 빼기 () 연산자를 사용하는 경우 `Short` Visual Basic은 식을 먼저 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
- <span data-ttu-id="be33c-120">**형식 변환.**</span><span class="sxs-lookup"><span data-stu-id="be33c-120">**Format Conversions.**</span></span> <span data-ttu-id="be33c-121">Visual Basic이 파일을 읽거나 쓰거나 DLL, 메서드 및 속성을 호출할 때 데이터 형식 간에 자동으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="be33c-122">변수 및 `Byte` 배열에 저장된 이진 데이터는 이러한 형식 변환 중에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="be33c-123">ANSI와 `String` 유니코드 형식을 변환하는 동안 내용이 손상될 수 있으므로 이진 데이터에 변수를 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

- <span data-ttu-id="be33c-124">**확대.**</span><span class="sxs-lookup"><span data-stu-id="be33c-124">**Widening.**</span></span> <span data-ttu-id="be33c-125">데이터 `Byte` 형식은 `Short` `UShort`" `Integer` `UInteger` `Long` `ULong` `Decimal`에 대해 , " `Single` `Double`</span><span class="sxs-lookup"><span data-stu-id="be33c-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="be33c-126">즉, <xref:System.OverflowException?displayProperty=nameWithType> 오류가 `Byte` 발생하지 않고 이러한 유형으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
- <span data-ttu-id="be33c-127">**문자를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="be33c-127">**Type Characters.**</span></span> <span data-ttu-id="be33c-128">`Byte`리터럴 형식 문자 또는 식별자 유형 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-128">`Byte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="be33c-129">**Framework 형식.**</span><span class="sxs-lookup"><span data-stu-id="be33c-129">**Framework Type.**</span></span> <span data-ttu-id="be33c-130">.NET Framework에서 해당하는 형식은 <xref:System.Byte?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="be33c-131">예제</span><span class="sxs-lookup"><span data-stu-id="be33c-131">Example</span></span>

 <span data-ttu-id="be33c-132">다음 예제에서는 `b` 변수입니다. `Byte`</span><span class="sxs-lookup"><span data-stu-id="be33c-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="be33c-133">문은 변수의 범위와 비트 시프트 연산자의 적용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be33c-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a><span data-ttu-id="be33c-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be33c-134">See also</span></span>

- <xref:System.Byte?displayProperty=nameWithType>
- [<span data-ttu-id="be33c-135">데이터 유형</span><span class="sxs-lookup"><span data-stu-id="be33c-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="be33c-136">CString</span><span class="sxs-lookup"><span data-stu-id="be33c-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="be33c-137">변환 요약</span><span class="sxs-lookup"><span data-stu-id="be33c-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="be33c-138">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="be33c-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
