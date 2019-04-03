---
title: UShort 데이터 형식(Visual Basic)
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
ms.openlocfilehash: 8845a6bde4e1a701b5420029788259724cd0f8d9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829956"
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="5e7e1-102">UShort 데이터 형식 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e7e1-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="5e7e1-103">0에서 65,535 범위의 부호 없는 16 비트 (2 바이트) 정수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e7e1-104">설명</span><span class="sxs-lookup"><span data-stu-id="5e7e1-104">Remarks</span></span>

 <span data-ttu-id="5e7e1-105">사용 된 `UShort` 데이터 형식에 비해 너무 큰 이진 데이터를 포함 하도록 `Byte`합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="5e7e1-106">`UShort`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-106">The default value of `UShort` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="5e7e1-107">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="5e7e1-107">Literal assignments</span></span>

<span data-ttu-id="5e7e1-108">선언 하 고 초기화할 수 있습니다는 `UShort` 변수 (Visual Basic 2017부터) 이진 리터럴을 또는 10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="5e7e1-109">정수 리터럴이 `UShort` 범위를 벗어나는 경우(즉 <xref:System.UInt16.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt16.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="5e7e1-110">다음 예제에서는 10 진수, 16 진수 표현 된 65,034와 같은 정수가 및 이진 리터럴로에 할당 된 `UShort` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="5e7e1-111">접두사를 사용할 `&h` 또는 `&H` 16 진수 리터럴, 접두사를 나타내는 `&b` 또는 `&B` 이진 리터럴 및 접두사를 나타내는 `&o` 또는 `&O` 8 진수 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="5e7e1-112">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="5e7e1-113">Visual Basic 2017부터 사용할 수도 있습니다 밑줄 문자 `_`, 가독성 향상을 위해 숫자 구분 기호를 다음 예제와 같이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="5e7e1-114">Visual Basic 15.5부터 사용할 수도 있습니다는 밑줄 문자 (`_`) 접두사 및 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="5e7e1-115">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="5e7e1-115">For example:</span></span>

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="5e7e1-116">숫자 리터럴을 포함할 수도 있습니다는 `US` 또는 `us` [문자를 입력](../../programming-guide/language-features/data-types/type-characters.md) 나타내기 위해는 `UShort` 다음 예제와 같이 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-116">Numeric literals can also include the `US` or `us` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a><span data-ttu-id="5e7e1-117">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="5e7e1-117">Programming tips</span></span>
  
-   <span data-ttu-id="5e7e1-118">**음수를 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="5e7e1-118">**Negative Numbers.**</span></span> <span data-ttu-id="5e7e1-119">때문에 `UShort` 부호 없는 형식에는 음수를 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-119">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="5e7e1-120">단항 빼기를 사용 하는 경우 (`-`) 형식으로 계산 되는 식에 연산자 `UShort`, Visual Basic 변환 식이 `Integer` 첫 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
-   <span data-ttu-id="5e7e1-121">**CLS 규격입니다.**</span><span class="sxs-lookup"><span data-stu-id="5e7e1-121">**CLS Compliance.**</span></span> <span data-ttu-id="5e7e1-122">합니다 `UShort` 데이터 형식이 아닙니다 부분 합니다 [공용 언어 사양](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), CLS 규격 코드를 사용 하는 구성 요소를 사용할 수 없습니다 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-122">The `UShort` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="5e7e1-123">**확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5e7e1-123">**Widening.**</span></span> <span data-ttu-id="5e7e1-124">`UShort` 데이터 형식으로 확장 되는지를 `Integer`, `UInteger`, `Long`, `ULong`를 `Decimal`, `Single`, 및 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-124">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="5e7e1-125">즉, 변환할 수 있습니다 `UShort` 발생 없이 이러한 형식 중 하나에 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-125">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="5e7e1-126">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="5e7e1-126">**Type Characters.**</span></span> <span data-ttu-id="5e7e1-127">리터럴 형식 문자를 추가 `US` 리터럴에 리터럴에 `UShort` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-127">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="5e7e1-128">`UShort` 에 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-128">`UShort` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="5e7e1-129">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="5e7e1-129">**Framework Type.**</span></span> <span data-ttu-id="5e7e1-130">.NET Framework에서 해당하는 형식은 <xref:System.UInt16?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7e1-130">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e7e1-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="5e7e1-131">See also</span></span>

- <xref:System.UInt16>
- [<span data-ttu-id="5e7e1-132">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5e7e1-132">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="5e7e1-133">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="5e7e1-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="5e7e1-134">변환 요약</span><span class="sxs-lookup"><span data-stu-id="5e7e1-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="5e7e1-135">방법: 부호 없는 형식을 사용하는 Windows 함수 호출</span><span class="sxs-lookup"><span data-stu-id="5e7e1-135">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="5e7e1-136">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="5e7e1-136">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
