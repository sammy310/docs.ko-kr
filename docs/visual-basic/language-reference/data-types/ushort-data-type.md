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
ms.openlocfilehash: ee31156e00059699125fd72a7f091afbb21beab0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415481"
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="f8209-102">UShort 데이터 형식 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8209-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="f8209-103">0에서 65535 사이의 값에 해당 하는 부호 없는 16 비트 (2 바이트) 정수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8209-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8209-104">설명</span><span class="sxs-lookup"><span data-stu-id="f8209-104">Remarks</span></span>

 <span data-ttu-id="f8209-105">`UShort`에 대해 너무 크지 않은 이진 데이터를 포함 하려면 데이터 형식을 사용 `Byte` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8209-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="f8209-106">`UShort`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="f8209-106">The default value of `UShort` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="f8209-107">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="f8209-107">Literal assignments</span></span>

<span data-ttu-id="f8209-108">`UShort`10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴 또는 (Visual Basic 2017부터) 이진 리터럴을 할당 하 여 변수를 선언 하 고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8209-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="f8209-109">정수 리터럴이 `UShort` 범위를 벗어나는 경우(즉 <xref:System.UInt16.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt16.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f8209-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="f8209-110">다음 예제에서는 10 진수, 16 진수 및 이진 리터럴로 표현 된 65034와 동일한 정수가 값에 할당 됩니다 `UShort` .</span><span class="sxs-lookup"><span data-stu-id="f8209-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="f8209-111">접두사 또는를 사용 하 여 `&h` `&H` 16 진수 리터럴을 표시 하거나, 접두사 또는을 사용 하 여 이진 리터럴을 표시 하 고, 접두사 또는를 사용 하 여 `&b` `&B` `&o` `&O` 8 진수 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f8209-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="f8209-112">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8209-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="f8209-113">Visual Basic 2017부터 `_` 다음 예제와 같이 밑줄 문자를 자릿수 구분 기호로 사용 하 여 가독성을 높일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8209-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="f8209-114">Visual Basic 15.5부터 `_` 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 밑줄 문자 ()를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8209-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="f8209-115">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f8209-115">For example:</span></span>

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="f8209-116">`US`다음 예제와 같이 숫자 리터럴은 또는 `us` [형식 문자](../../programming-guide/language-features/data-types/type-characters.md) 를 포함 하 여 데이터 형식을 나타낼 수도 있습니다 `UShort` .</span><span class="sxs-lookup"><span data-stu-id="f8209-116">Numeric literals can also include the `US` or `us` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a><span data-ttu-id="f8209-117">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="f8209-117">Programming tips</span></span>
  
- <span data-ttu-id="f8209-118">**음수.**</span><span class="sxs-lookup"><span data-stu-id="f8209-118">**Negative Numbers.**</span></span> <span data-ttu-id="f8209-119">`UShort`는 부호 없는 형식이 기 때문에 음수를 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8209-119">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="f8209-120">`-`형식을 반환 하는 식에 단항 빼기 () 연산자를 사용 하는 경우 `UShort` Visual Basic는 식을 `Integer` 먼저 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8209-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
- <span data-ttu-id="f8209-121">**CLS 규격.**</span><span class="sxs-lookup"><span data-stu-id="f8209-121">**CLS Compliance.**</span></span> <span data-ttu-id="f8209-122">`UShort`데이터 형식이 cls ( [공용 언어 사양](https://www.ecma-international.org/publications/standards/Ecma-335.htm) )의 일부가 아니므로 cls 규격 코드는이를 사용 하는 구성 요소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8209-122">The `UShort` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
- <span data-ttu-id="f8209-123">**넓혀.**</span><span class="sxs-lookup"><span data-stu-id="f8209-123">**Widening.**</span></span> <span data-ttu-id="f8209-124">`UShort`데이터 형식은,,,,, 및로 확대 변환 `Integer` `UInteger` `Long` `ULong` `Decimal` `Single` `Double` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8209-124">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="f8209-125">즉, `UShort` 오류가 발생 하지 않고 이러한 형식으로 변환할 수 있습니다 <xref:System.OverflowException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f8209-125">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="f8209-126">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f8209-126">**Type Characters.**</span></span> <span data-ttu-id="f8209-127">리터럴 형식 문자를 리터럴에 추가 하면 `US` `UShort` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8209-127">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="f8209-128">`UShort`에는 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8209-128">`UShort` has no identifier type character.</span></span>  
  
- <span data-ttu-id="f8209-129">**Framework 형식.**</span><span class="sxs-lookup"><span data-stu-id="f8209-129">**Framework Type.**</span></span> <span data-ttu-id="f8209-130">.NET Framework에서 해당하는 형식은 <xref:System.UInt16?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="f8209-130">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8209-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8209-131">See also</span></span>

- <xref:System.UInt16>
- [<span data-ttu-id="f8209-132">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f8209-132">Data Types</span></span>](index.md)
- [<span data-ttu-id="f8209-133">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="f8209-133">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="f8209-134">변환 요약</span><span class="sxs-lookup"><span data-stu-id="f8209-134">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="f8209-135">방법: 부호 없는 형식을 사용하는 Windows 함수 호출</span><span class="sxs-lookup"><span data-stu-id="f8209-135">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="f8209-136">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="f8209-136">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
