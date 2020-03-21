---
title: UShort 데이터 형식
ms.date: 01/31/2018
f1_keywords:
- vb.ushort
helpviewer_keywords:
- numbers [Visual Basic], whole
- literal type characters [Visual Basic], US
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- UShort data type
- US literal type characters [Visual Basic]
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
ms.openlocfilehash: 7cdbd5fb192fd5cc1be6260dcdcdb1f30cf3f865
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401312"
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="5efd2-102">UShort 데이터 유형(시각적 기본)</span><span class="sxs-lookup"><span data-stu-id="5efd2-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="5efd2-103">0에서 65,535사이의 부호없는 16비트(2바이트) 정수를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5efd2-104">설명</span><span class="sxs-lookup"><span data-stu-id="5efd2-104">Remarks</span></span>

 <span data-ttu-id="5efd2-105">`UShort` 데이터 형식을 사용하여 에 대한 `Byte`이진 데이터가 너무 큽에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="5efd2-106">`UShort`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-106">The default value of `UShort` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="5efd2-107">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="5efd2-107">Literal assignments</span></span>

<span data-ttu-id="5efd2-108">소수점 문자, 육각 형 리터럴, 옥탈 리터럴 또는 (Visual Basic 2017로 시작) 이진 리터럴을 할당하여 `UShort` 변수를 선언하고 초기화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="5efd2-109">정수 리터럴이 `UShort` 범위를 벗어나는 경우(즉 <xref:System.UInt16.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt16.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="5efd2-110">다음 예제에서는 소수점, 육각형 및 이진 리터럴로 표시되는 정수는 65,034와 같으며 값에 `UShort` 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="5efd2-111">접두사를 `&h` 사용하거나 `&H` 육각 문자 문자, `&b` 접두사 또는 이진 `&B` 리터럴을 나타내거나 접두사를 `&o` 나타내거나 `&O` 팔각형 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="5efd2-112">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="5efd2-113">Visual Basic 2017부터는 다음 예제와 같이 `_`밑줄 문자를 숫자 구분 기호로 사용하여 가독성을 향상시킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="5efd2-114">Visual Basic 15.5부터는 접두사와 육각형, 이진 또는 옥탈 숫자 사이의 선행 구분 기호로 밑줄 문자()를`_`사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="5efd2-115">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-115">For example:</span></span>

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="5efd2-116">숫자 리터럴은 다음 `US` 예제와 `us` 같이 `UShort` 데이터 형식을 나타내는 문자 또는 [형식을](../../programming-guide/language-features/data-types/type-characters.md) 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-116">Numeric literals can also include the `US` or `us` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a><span data-ttu-id="5efd2-117">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="5efd2-117">Programming tips</span></span>
  
- <span data-ttu-id="5efd2-118">**음수.**</span><span class="sxs-lookup"><span data-stu-id="5efd2-118">**Negative Numbers.**</span></span> <span data-ttu-id="5efd2-119">서명되지 않은 형식이기 때문에 `UShort` 음수를 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-119">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="5efd2-120">입력을`-` `UShort`평가하는 식에서 unary 빼기 () 연산자를 사용하는 경우 `Integer` Visual Basic은 식을 먼저 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
- <span data-ttu-id="5efd2-121">**CLS 규정 준수.**</span><span class="sxs-lookup"><span data-stu-id="5efd2-121">**CLS Compliance.**</span></span> <span data-ttu-id="5efd2-122">`UShort` 데이터 형식은 공통 언어 [사양(CLS)의](https://www.ecma-international.org/publications/standards/Ecma-335.htm) 일부가 아니므로 CLS 호환 코드는 이를 사용하는 구성 요소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-122">The `UShort` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
- <span data-ttu-id="5efd2-123">**확대.**</span><span class="sxs-lookup"><span data-stu-id="5efd2-123">**Widening.**</span></span> <span data-ttu-id="5efd2-124">데이터 `UShort` 형식은 `Integer`" `UInteger` `Long` `ULong` `Decimal` `Single`에 대해 , `Double`</span><span class="sxs-lookup"><span data-stu-id="5efd2-124">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="5efd2-125">즉, <xref:System.OverflowException?displayProperty=nameWithType> 오류가 `UShort` 발생하지 않고 이러한 유형으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-125">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="5efd2-126">**문자를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="5efd2-126">**Type Characters.**</span></span> <span data-ttu-id="5efd2-127">리터럴 형식 문자를 `US` 리터럴 문자에 적용하면 `UShort` 데이터 형식에 강제로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-127">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="5efd2-128">`UShort`식별자 유형 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-128">`UShort` has no identifier type character.</span></span>  
  
- <span data-ttu-id="5efd2-129">**Framework 형식.**</span><span class="sxs-lookup"><span data-stu-id="5efd2-129">**Framework Type.**</span></span> <span data-ttu-id="5efd2-130">.NET Framework에서 해당하는 형식은 <xref:System.UInt16?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="5efd2-130">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5efd2-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5efd2-131">See also</span></span>

- <xref:System.UInt16>
- [<span data-ttu-id="5efd2-132">데이터 유형</span><span class="sxs-lookup"><span data-stu-id="5efd2-132">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="5efd2-133">CString</span><span class="sxs-lookup"><span data-stu-id="5efd2-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="5efd2-134">변환 요약</span><span class="sxs-lookup"><span data-stu-id="5efd2-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="5efd2-135">방법: 부호 없는 형식을 사용하는 Windows 함수 호출</span><span class="sxs-lookup"><span data-stu-id="5efd2-135">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="5efd2-136">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="5efd2-136">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
