---
description: '자세한 정보: 문자열 함수 (Visual Basic)'
title: 문자열 함수
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: 1c121bc3de66caf748426b5cd04d049b30bf78bb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731142"
---
# <a name="string-functions-visual-basic"></a><span data-ttu-id="79500-103">문자열 함수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79500-103">String Functions (Visual Basic)</span></span>

<span data-ttu-id="79500-104">다음 표에서는 <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType> 문자열을 검색 하 고 조작 하기 위해 클래스에서 제공 Visual Basic는 함수를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-104">The following table lists the functions that Visual Basic provides in the <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType> class to search and manipulate strings.</span></span> <span data-ttu-id="79500-105">Visual Basic 내장 함수로 간주할 수 있습니다. 즉, 예제에서 보여 주는 것 처럼 클래스의 명시적 멤버로 호출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79500-105">They can be regarded as Visual Basic intrinsic functions; that is, you do not have to call them as explicit members of a class, as the examples show.</span></span> <span data-ttu-id="79500-106">클래스에서 추가 메서드 및 경우에 따라 보충 메서드를 사용할 수 있습니다 <xref:System.String?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="79500-106">Additional methods, and in some cases complementary methods, are available in the <xref:System.String?displayProperty=nameWithType> class.</span></span>

|<span data-ttu-id="79500-107">.NET Framework 메서드</span><span class="sxs-lookup"><span data-stu-id="79500-107">.NET Framework method</span></span>|<span data-ttu-id="79500-108">Description</span><span class="sxs-lookup"><span data-stu-id="79500-108">Description</span></span>|
|---------------------------|-----------------|
|<span data-ttu-id="79500-109"><xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A></span><span class="sxs-lookup"><span data-stu-id="79500-109"><xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A></span></span>|<span data-ttu-id="79500-110">`Integer`문자에 해당 하는 문자 코드를 나타내는 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-110">Returns an `Integer` value representing the character code corresponding to a character.</span></span>|
|<span data-ttu-id="79500-111"><xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A></span><span class="sxs-lookup"><span data-stu-id="79500-111"><xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A></span></span>|<span data-ttu-id="79500-112">지정한 문자 코드와 연관된 문자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-112">Returns the character associated with the specified character code.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|<span data-ttu-id="79500-113">지정된 필터링 기준에 따라 `String` 배열의 하위 집합을 포함하는 0부터 시작하는 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-113">Returns a zero-based array containing a subset of a `String` array based on specified filter criteria.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|<span data-ttu-id="79500-114">형식 `String` 식에 포함된 명령에 따라 형식 지정된 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-114">Returns a string formatted according to instructions contained in a format `String` expression.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|<span data-ttu-id="79500-115">시스템 제어판에 정의된 통화 기호를 사용하여 통화 값으로 서식이 지정된 식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-115">Returns an expression formatted as a currency value using the currency symbol defined in the system control panel.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|<span data-ttu-id="79500-116">날짜/시간 값을 나타내는 문자열 식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-116">Returns a string expression representing a date/time value.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|<span data-ttu-id="79500-117">숫자로 서식이 지정된 식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-117">Returns an expression formatted as a number.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|<span data-ttu-id="79500-118">백분율로 서식이 지정된 식(100을 곱함)을 % 문자를 붙여 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-118">Returns an expression formatted as a percentage (that is, multiplied by 100) with a trailing % character.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|<span data-ttu-id="79500-119">한 문자열에서 다른 문자열이 처음으로 나타나는 위치를 지정하는 정수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-119">Returns an integer specifying the start position of the first occurrence of one string within another.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|<span data-ttu-id="79500-120">문자열의 오른쪽에서 시작하여 한 문자열 내에서 다른 문자열이 처음 나오는 위치를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-120">Returns the position of the first occurrence of one string within another, starting from the right side of the string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|<span data-ttu-id="79500-121">배열에 포함된 여러 부분 문자열을 조인하여 작성되는 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-121">Returns a string created by joining a number of substrings contained in an array.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|<span data-ttu-id="79500-122">소문자로 변환된 문자열 또는 문자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-122">Returns a string or character converted to lowercase.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|<span data-ttu-id="79500-123">문자열의 왼쪽에서 지정한 수의 문자를 포함하는 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-123">Returns a string containing a specified number of characters from the left side of a string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|<span data-ttu-id="79500-124">문자열의 문자 수를 포함 하는 정수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-124">Returns an integer that contains the number of characters in a string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|<span data-ttu-id="79500-125">지정된 문자열을 지정한 길이에 맞게 조정하고 왼쪽에 맞춘 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-125">Returns a left-aligned string containing the specified string adjusted to the specified length.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|<span data-ttu-id="79500-126">선행 공백 없이 지정 된 문자열의 복사본을 포함 하는 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-126">Returns a string containing a copy of a specified string with no leading spaces.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|<span data-ttu-id="79500-127">문자열에서 지정 된 수의 문자를 포함 하는 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-127">Returns a string containing a specified number of characters from a string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|<span data-ttu-id="79500-128">지정된 부분 문자열이 지정된 횟수만큼 다른 부분 문자열로 대체된 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-128">Returns a string in which a specified substring has been replaced with another substring a specified number of times.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|<span data-ttu-id="79500-129">문자열의 오른쪽에서 지정한 개수의 문자를 포함하는 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-129">Returns a string containing a specified number of characters from the right side of a string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|<span data-ttu-id="79500-130">지정된 길이에 맞게 조정된 특정 문자열이 포함된 문자열(오른쪽에 맞춰진 문자열)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-130">Returns a right-aligned string containing the specified string adjusted to the specified length.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|<span data-ttu-id="79500-131">후행 공백 없이 지정 된 문자열의 복사본을 포함 하는 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-131">Returns a string containing a copy of a specified string with no trailing spaces.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|<span data-ttu-id="79500-132">지정한 수 만큼의 공백으로 구성되는 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-132">Returns a string consisting of the specified number of spaces.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|<span data-ttu-id="79500-133">지정된 수의 부분 문자열을 포함하는 0부터 시작하는 1차원 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-133">Returns a zero-based, one-dimensional array containing a specified number of substrings.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|<span data-ttu-id="79500-134">문자열 비교의 결과에 따라 -1, 0 또는 1을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-134">Returns -1, 0, or 1, based on the result of a string comparison.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|<span data-ttu-id="79500-135">지정된 대로 변환된 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-135">Returns a string converted as specified.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|<span data-ttu-id="79500-136">지정된 횟수만큼 반복되는 특정 문자로 구성된 문자열 또는 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-136">Returns a string or object consisting of the specified character repeated the specified number of times.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|<span data-ttu-id="79500-137">지정된 문자열의 문자 순서를 역순으로 한 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-137">Returns a string in which the character order of a specified string is reversed.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|<span data-ttu-id="79500-138">선행 또는 후행 공백이 없는 지정 된 문자열의 복사본을 포함 하는 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-138">Returns a string containing a copy of a specified string with no leading or trailing spaces.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|<span data-ttu-id="79500-139">대문자로 변환된 특정 문자열이 있는 문자열 또는 문자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-139">Returns a string or character containing the specified string converted to uppercase.</span></span>|

<span data-ttu-id="79500-140">[Option Compare](../statements/option-compare-statement.md) 문을 사용 하 여 문자열을 대/소문자를 구분 하지 않는 텍스트 정렬 순서를 사용 하 여 비교할 수 있습니다 (). 시스템의 로캘 ( `Text` ) 또는 문자 ()의 내부 이진 표현에 따라 결정 됩니다 `Binary` .</span><span class="sxs-lookup"><span data-stu-id="79500-140">You can use the [Option Compare](../statements/option-compare-statement.md) statement to set whether strings are compared using a case-insensitive text sort order determined by your system's locale (`Text`) or by the internal binary representations of the characters (`Binary`).</span></span> <span data-ttu-id="79500-141">기본 텍스트 비교 방법은 `Binary`입니다.</span><span class="sxs-lookup"><span data-stu-id="79500-141">The default text comparison method is `Binary`.</span></span>

## <a name="example-ucase"></a><span data-ttu-id="79500-142">예: UCase</span><span class="sxs-lookup"><span data-stu-id="79500-142">Example: UCase</span></span>

<span data-ttu-id="79500-143">다음 예제에서는 `UCase` 함수를 사용하여 대문자 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-143">This example uses the `UCase` function to return an uppercase version of a string.</span></span>
[!code-vb[VbVbalrStrings#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#31)]

## <a name="example-ltrim"></a><span data-ttu-id="79500-144">예: LTrim</span><span class="sxs-lookup"><span data-stu-id="79500-144">Example: LTrim</span></span>

<span data-ttu-id="79500-145">이 예제에서는 문자열 변수에서 `LTrim` 함수를 사용하여 선행 공백을 제거하고 `RTrim` 함수를 사용하여 후행 공백을 제거하며</span><span class="sxs-lookup"><span data-stu-id="79500-145">This example uses the `LTrim` function to strip leading spaces and the `RTrim` function to strip trailing spaces from a string variable.</span></span> <span data-ttu-id="79500-146">`Trim` 함수를 사용하여 양쪽 공백을 모두 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-146">It uses the `Trim` function to strip both types of spaces.</span></span>

[!code-vb[VbVbalrStrings#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#25)]

## <a name="example-mid"></a><span data-ttu-id="79500-147">예: Mid</span><span class="sxs-lookup"><span data-stu-id="79500-147">Example: Mid</span></span>

<span data-ttu-id="79500-148">이 예에서는 함수를 사용 하 여 `Mid` 문자열에서 지정 된 수의 문자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-148">This example uses the `Mid` function to return a specified number of characters from a string.</span></span>

[!code-vb[VbVbalrStrings#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#17)]

## <a name="example-len"></a><span data-ttu-id="79500-149">예: Len</span><span class="sxs-lookup"><span data-stu-id="79500-149">Example: Len</span></span>

<span data-ttu-id="79500-150">다음 예제에서는 `Len` 함수를 사용하여 문자열의 문자 개수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-150">This example uses `Len` to return the number of characters in a string.</span></span>

[!code-vb[VbVbalrStrings#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#33)]

## <a name="example-instr"></a><span data-ttu-id="79500-151">예: InStr</span><span class="sxs-lookup"><span data-stu-id="79500-151">Example: InStr</span></span>

<span data-ttu-id="79500-152">다음 예제에서는 `InStr` 함수를 사용하여 한 문자열 안에 다른 문자열이 처음으로 나타나는 위치를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79500-152">This example uses the `InStr` function to return the position of the first occurrence of one string within another.</span></span>

[!code-vb[VbVbalrStrings#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#8)]

## <a name="example-format"></a><span data-ttu-id="79500-153">예: Format</span><span class="sxs-lookup"><span data-stu-id="79500-153">Example: Format</span></span>

<span data-ttu-id="79500-154">다음 예제에서는 `Format` 형식과 사용자 정의 형식을 모두 사용하여 값의 형식을 지정하는 `String` 함수의 다양한 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="79500-154">This example shows various uses of the `Format` function to format values using both `String` formats and user-defined formats.</span></span> <span data-ttu-id="79500-155">날짜 구분 기호(`/`), 시간 구분 기호(`:`), AM/PM 표시기(`t` 및 `tt`)의 경우 시스템에 실제로 표시되는 출력 형식은 코드에서 사용하는 로캘 설정에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="79500-155">For the date separator (`/`), time separator (`:`), and the AM/PM indicators (`t` and `tt`), the actual formatted output displayed by your system depends on the locale settings the code is using.</span></span> <span data-ttu-id="79500-156">개발 환경에 시간과 날짜가 표시되는 경우 코드 로캘의 간단한 시간 형식과 날짜 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79500-156">When times and dates are displayed in the development environment, the short time format and short date format of the code locale are used.</span></span>

> [!NOTE]
> <span data-ttu-id="79500-157">24시간 형식을 사용하는 로캘의 경우에는 AM/PM 표시기(`t`와 `tt`)에 아무것도 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79500-157">For locales that use a 24-hour clock, the AM/PM indicators (`t` and `tt`) display nothing.</span></span>

[!code-vb[VbVbalrStrings#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#27)]

## <a name="see-also"></a><span data-ttu-id="79500-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79500-158">See also</span></span>

- [<span data-ttu-id="79500-159">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="79500-159">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="79500-160">Visual Basic 런타임 라이브러리 멤버</span><span class="sxs-lookup"><span data-stu-id="79500-160">Visual Basic Runtime Library Members</span></span>](../runtime-library-members.md)
- [<span data-ttu-id="79500-161">문자열 조작 요약</span><span class="sxs-lookup"><span data-stu-id="79500-161">String Manipulation Summary</span></span>](../keywords/string-manipulation-summary.md)
- [<span data-ttu-id="79500-162">System.string 클래스 메서드</span><span class="sxs-lookup"><span data-stu-id="79500-162">System.String class methods</span></span>](xref:System.String#methods)
