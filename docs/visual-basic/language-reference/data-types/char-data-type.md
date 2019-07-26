---
title: Char 데이터 형식(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
ms.openlocfilehash: ca40e6c8dcba3da29bdb68b29c91c852e477f8f7
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512784"
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="d08a0-102">Char 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d08a0-102">Char Data Type (Visual Basic)</span></span>

<span data-ttu-id="d08a0-103">0에서 65535 사이의 값에 해당 하는 부호 없는 16 비트 (2 바이트) 코드 요소를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="d08a0-104">각 *코드 포인트*또는 문자 코드는 단일 유니코드 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-104">Each *code point*, or character code, represents a single Unicode character.</span></span>

## <a name="remarks"></a><span data-ttu-id="d08a0-105">설명</span><span class="sxs-lookup"><span data-stu-id="d08a0-105">Remarks</span></span>

<span data-ttu-id="d08a0-106">단일 문자만 포함 해야 하며의 `String`오버 헤드가 필요 하지 않은 경우 데이터형식을사용합니다.`Char`</span><span class="sxs-lookup"><span data-stu-id="d08a0-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="d08a0-107">일부 경우에는 `Char()` `Char` 요소의 배열을 사용 하 여 여러 문자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>

<span data-ttu-id="d08a0-108">의 `Char` 기본값은 코드 포인트가 0 인 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-108">The default value of `Char` is the character with a code point of 0.</span></span>

## <a name="unicode-characters"></a><span data-ttu-id="d08a0-109">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="d08a0-109">Unicode Characters</span></span>

<span data-ttu-id="d08a0-110">유니코드의 처음 128 코드 요소 (0 – 127)는 표준 미국 키보드의 문자 및 기호에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="d08a0-111">이러한 첫 번째 128 코드 포인트가 ASCII 문자 집합에서 정의 하는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="d08a0-112">두 번째 128 코드 요소 (128-255)는 특수 문자 (예: 라틴어 기반 영문자, 악센트, 통화 기호 및 분수)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="d08a0-113">유니코드는 전 세계 텍스트 문자, 분음 부호, 수학 및 기술 기호를 비롯 한 다양 한 기호에 대해 나머지 코드 요소 (256-65535)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>

<span data-ttu-id="d08a0-114">변수에서 <xref:System.Char.IsPunctuation%2A> <xref:System.Char.IsDigit%2A> 및와같은메서드를사용하여유니코드분류를확인할수있습니다`Char` .</span><span class="sxs-lookup"><span data-stu-id="d08a0-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>

## <a name="type-conversions"></a><span data-ttu-id="d08a0-115">형식 변환</span><span class="sxs-lookup"><span data-stu-id="d08a0-115">Type Conversions</span></span>

<span data-ttu-id="d08a0-116">Visual Basic는와 숫자 형식 사이 `Char` 에서 직접 변환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="d08a0-117"><xref:Microsoft.VisualBasic.Strings.Asc%2A> 또는 `Char` `Integer` 함수를 사용 하 여 값을 해당 코드 포인트를 나타내는로 변환할 수 있습니다. <xref:Microsoft.VisualBasic.Strings.AscW%2A></span><span class="sxs-lookup"><span data-stu-id="d08a0-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="d08a0-118"><xref:Microsoft.VisualBasic.Strings.Chr%2A> 또는 `Integer` `Char` 함수를 사용 하 여 값을 해당 코드 포인트가 있는로 변환할 수 있습니다. <xref:Microsoft.VisualBasic.Strings.ChrW%2A></span><span class="sxs-lookup"><span data-stu-id="d08a0-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>

<span data-ttu-id="d08a0-119">형식 검사 스위치 ([Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md))가 on 인 경우 리터럴 형식 문자를 `Char` 데이터 형식으로 식별 하는 단일 문자 문자열 리터럴에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-119">If the type checking switch ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="d08a0-120">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-120">The following example illustrates this.</span></span>

```vb
Option Strict On
Dim charVar As Char
' The following statement attempts to convert a String literal to Char.
' Because Option Strict is On, it generates a compiler error.
charVar = "Z"
' The following statement succeeds because it specifies a Char literal.
charVar = "Z"C
```

## <a name="programming-tips"></a><span data-ttu-id="d08a0-121">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="d08a0-121">Programming Tips</span></span>

- <span data-ttu-id="d08a0-122">**음수.**</span><span class="sxs-lookup"><span data-stu-id="d08a0-122">**Negative Numbers.**</span></span> <span data-ttu-id="d08a0-123">`Char`는 부호 없는 형식이 며 음수 값을 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-123">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="d08a0-124">어떤 경우에는를 사용 `Char` 하 여 숫자 값을 포함 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-124">In any case, you should not use `Char` to hold numeric values.</span></span>

- <span data-ttu-id="d08a0-125">**Interop 고려 사항**</span><span class="sxs-lookup"><span data-stu-id="d08a0-125">**Interop Considerations.**</span></span> <span data-ttu-id="d08a0-126">.NET Framework 용으로 작성 되지 않은 구성 요소 (예: Automation 또는 COM 개체)와 상호 작용 하는 경우에는 다른 환경에서 문자 형식의 데이터 너비 (8 비트)가 서로 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-126">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="d08a0-127">이러한 구성 요소에 8 비트 인수를 전달 하는 경우 새 Visual Basic 코드 `Byte` `Char` 에서 대신로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-127">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>

- <span data-ttu-id="d08a0-128">**넓혀.**</span><span class="sxs-lookup"><span data-stu-id="d08a0-128">**Widening.**</span></span> <span data-ttu-id="d08a0-129">데이터 형식이로 `String`확대 됩니다. `Char`</span><span class="sxs-lookup"><span data-stu-id="d08a0-129">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="d08a0-130">즉 `Char` `String`,로 변환할 수 있으며 오류가발생하지않습니다.<xref:System.OverflowException?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d08a0-130">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="d08a0-131">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d08a0-131">**Type Characters.**</span></span> <span data-ttu-id="d08a0-132">리터럴 형식 문자 `C` 를 단일 문자 문자열 리터럴에 `Char` 추가 하면 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-132">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="d08a0-133">`Char`에는 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-133">`Char` has no identifier type character.</span></span>

- <span data-ttu-id="d08a0-134">**프레임 워크 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="d08a0-134">**Framework Type.**</span></span> <span data-ttu-id="d08a0-135">.NET Framework에서 해당하는 형식은 <xref:System.Char?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="d08a0-135">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="d08a0-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="d08a0-136">See also</span></span>

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="d08a0-137">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d08a0-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="d08a0-138">String 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d08a0-138">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="d08a0-139">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="d08a0-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="d08a0-140">변환 요약</span><span class="sxs-lookup"><span data-stu-id="d08a0-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="d08a0-141">방법: 부호 없는 형식을 사용하는 Windows 함수 호출</span><span class="sxs-lookup"><span data-stu-id="d08a0-141">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="d08a0-142">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="d08a0-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
