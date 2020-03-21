---
title: Integer 데이터 형식
ms.date: 01/31/2018
f1_keywords:
- vb.Integer
- Integer
helpviewer_keywords:
- numbers [Visual Basic], whole
- enumerated values [Visual Basic]
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- literal type characters [Visual Basic], I
- integers [Visual Basic], types
- data types [Visual Basic], integral
- '% identifier type character'
- data types [Visual Basic], assigning
- identifier type characters [Visual Basic], %
- I literal type character [Visual Basic]
- Integer data type
ms.assetid: a8f233b4-4be3-455c-861b-05af2fbb6c60
ms.openlocfilehash: c5b1041b8ef0ca9898a846fea03888537bb4abbf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401348"
---
# <a name="integer-data-type-visual-basic"></a><span data-ttu-id="ff886-102">정수 데이터 유형(시각적 기본)</span><span class="sxs-lookup"><span data-stu-id="ff886-102">Integer data type (Visual Basic)</span></span>

<span data-ttu-id="ff886-103">-2,147,483,648에서 2,147,483,647까지의 값 범위에 속하는 부호 있는 32비트(4바이트) 정수를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-103">Holds signed 32-bit (4-byte) integers that range in value from -2,147,483,648 through 2,147,483,647.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff886-104">설명</span><span class="sxs-lookup"><span data-stu-id="ff886-104">Remarks</span></span>

 <span data-ttu-id="ff886-105">`Integer` 데이터 형식은 32비트 프로세서에서 최적의 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-105">The `Integer` data type provides optimal performance on a 32-bit processor.</span></span> <span data-ttu-id="ff886-106">다른 정수 계열 형식은 메모리에서 로드하고 저장하는 속도가 더 느려집니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-106">The other integral types are slower to load and store from and to memory.</span></span>  
  
 <span data-ttu-id="ff886-107">`Integer`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-107">The default value of `Integer` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="ff886-108">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="ff886-108">Literal assignments</span></span>

<span data-ttu-id="ff886-109">소수점 문자, 육각 형 리터럴, 옥탈 리터럴 또는 (Visual Basic 2017로 시작) 이진 리터럴을 할당하여 `Integer` 변수를 선언하고 초기화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-109">You can declare and initialize an `Integer` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="ff886-110">정수 리터럴이 `Integer` 범위를 벗어나는 경우(즉 <xref:System.Int32.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.Int32.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-110">If the integer literal is outside the range of `Integer` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="ff886-111">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 90,946와 같은 정수가 `Integer` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-111">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `Integer` values.</span></span>

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Int)]  

> [!NOTE]
> <span data-ttu-id="ff886-112">접두사를 `&h` 사용하거나 `&H` 육각 문자 문자, `&b` 접두사 또는 이진 `&B` 리터럴을 나타내거나 접두사를 `&o` 나타내거나 `&O` 팔각형 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="ff886-113">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="ff886-114">Visual Basic 2017부터는 다음 예제와 같이 `_`밑줄 문자를 숫자 구분 기호로 사용하여 가독성을 향상시킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#IntS)]  

<span data-ttu-id="ff886-115">Visual Basic 15.5부터는 접두사와 육각형, 이진 또는 옥탈 숫자 사이의 선행 구분 기호로 밑줄 문자()를`_`사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="ff886-116">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-116">For example:</span></span>

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="ff886-117">숫자 리터럴은 다음 예제와 `I` 같이 `Integer` 데이터 형식을 나타내는 형식 [문자를](../../programming-guide/language-features/data-types/type-characters.md) 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-117">Numeric literals can also include the `I` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Integer` data type, as the following example shows.</span></span>

```vb
Dim number = &H_035826I
```

## <a name="programming-tips"></a><span data-ttu-id="ff886-118">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="ff886-118">Programming tips</span></span>

- <span data-ttu-id="ff886-119">**Interop 고려 사항.**</span><span class="sxs-lookup"><span data-stu-id="ff886-119">**Interop Considerations.**</span></span> <span data-ttu-id="ff886-120">자동화 또는 COM 개체와 같은 .NET Framework에 대해 작성되지 않은 `Integer` 구성 요소와 인터페이싱하는 경우 다른 환경에서는 데이터 너비(16비트)가 다르다는 것을 기억하십시오.</span><span class="sxs-lookup"><span data-stu-id="ff886-120">If you are interfacing with components not written for the .NET Framework, such as Automation or COM objects, remember that `Integer` has a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="ff886-121">이러한 구성 요소에 16비트 인수를 전달하는 경우 새 Visual Basic 코드에서 이 인수를 `Short` 대신 `Integer`로 선언하십시오.</span><span class="sxs-lookup"><span data-stu-id="ff886-121">If you are passing a 16-bit argument to such a component, declare it as `Short` instead of `Integer` in your new Visual Basic code.</span></span>  
  
- <span data-ttu-id="ff886-122">**확대.**</span><span class="sxs-lookup"><span data-stu-id="ff886-122">**Widening.**</span></span> <span data-ttu-id="ff886-123">`Integer` 데이터 형식은 `Long`, `Decimal`, `Single` 또는 `Double`로 확대 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-123">The `Integer` data type widens to `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="ff886-124">이는 `Integer` 오류 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType>를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-124">This means you can convert `Integer` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="ff886-125">**문자를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="ff886-125">**Type Characters.**</span></span> <span data-ttu-id="ff886-126">리터럴 형식 문자 `I`를 리터럴에 추가하면 `Integer` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-126">Appending the literal type character `I` to a literal forces it to the `Integer` data type.</span></span> <span data-ttu-id="ff886-127">식별자 형식 문자 `%`를 식별자에 추가하면 `Integer`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-127">Appending the identifier type character `%` to any identifier forces it to `Integer`.</span></span>  
  
- <span data-ttu-id="ff886-128">**Framework 형식.**</span><span class="sxs-lookup"><span data-stu-id="ff886-128">**Framework Type.**</span></span> <span data-ttu-id="ff886-129">.NET Framework에서 해당하는 형식은 <xref:System.Int32?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-129">The corresponding type in the .NET Framework is the <xref:System.Int32?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="range"></a><span data-ttu-id="ff886-130">범위</span><span class="sxs-lookup"><span data-stu-id="ff886-130">Range</span></span>

<span data-ttu-id="ff886-131">정수 계열 형식의 변수를 이 형식의 범위에서 벗어난 숫자로 설정하려고 하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-131">If you try to set a variable of an integral type to a number outside the range for that type, an error occurs.</span></span> <span data-ttu-id="ff886-132">분수로 설정하려고 하면 숫자는 가장 근사한 정수값으로 반올림되거나 반내림됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-132">If you try to set it to a fraction, the number is rounded up or down to the nearest integer value.</span></span> <span data-ttu-id="ff886-133">숫자가 두 정수 값에 가까우면 값은 가장 근사한 짝수 정수로 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-133">If the number is equally close to two integer values, the value is rounded to the nearest even integer.</span></span> <span data-ttu-id="ff886-134">이 동작은 중간값을 한 방향으로 계속해서 반올림할 때 발생하는 반올림 오류가 최소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-134">This behavior minimizes rounding errors that result from consistently rounding a midpoint value in a single direction.</span></span> <span data-ttu-id="ff886-135">다음 코드는 반올림의 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff886-135">The following code shows examples of rounding.</span></span>  

```vb  
' The valid range of an Integer variable is -2147483648 through +2147483647.  
Dim k As Integer  
' The following statement causes an error because the value is too large.  
k = 2147483648  
' The following statement sets k to 6.  
k = 5.9  
' The following statement sets k to 4  
k = 4.5  
' The following statement sets k to 6  
' Note, Visual Basic uses banker’s rounding (toward nearest even number)  
k = 5.5  
```

## <a name="see-also"></a><span data-ttu-id="ff886-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff886-136">See also</span></span>

- <xref:System.Int32?displayProperty=nameWithType>
- [<span data-ttu-id="ff886-137">데이터 유형</span><span class="sxs-lookup"><span data-stu-id="ff886-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="ff886-138">Long 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ff886-138">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="ff886-139">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ff886-139">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="ff886-140">CString</span><span class="sxs-lookup"><span data-stu-id="ff886-140">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="ff886-141">변환 요약</span><span class="sxs-lookup"><span data-stu-id="ff886-141">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="ff886-142">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="ff886-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
