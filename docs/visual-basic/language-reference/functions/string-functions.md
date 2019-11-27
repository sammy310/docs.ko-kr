---
title: 문자열 함수
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: 2608159e28ee63a0fdb10c82054fd65efe79ac62
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349976"
---
# <a name="string-functions-visual-basic"></a><span data-ttu-id="f812b-102">문자열 함수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f812b-102">String Functions (Visual Basic)</span></span>

<span data-ttu-id="f812b-103">다음 표에서는 문자열을 검색 하 고 조작 하는 Visual Basic <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType> 클래스에서 제공 하는 함수를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-103">The following table lists the functions that Visual Basic provides in the <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType> class to search and manipulate strings.</span></span> <span data-ttu-id="f812b-104">Visual Basic 내장 함수로 간주할 수 있습니다. 즉, 예제에서 보여 주는 것 처럼 클래스의 명시적 멤버로 호출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-104">They can be regarded as Visual Basic intrinsic functions; that is, you do not have to call them as explicit members of a class, as the examples show.</span></span> <span data-ttu-id="f812b-105"><xref:System.String?displayProperty=nameWithType> 클래스에서 추가 메서드 및 경우에 따라 보충 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-105">Additional methods, and in some cases complementary methods, are available in the <xref:System.String?displayProperty=nameWithType> class.</span></span>

|<span data-ttu-id="f812b-106">.NET Framework 메서드</span><span class="sxs-lookup"><span data-stu-id="f812b-106">.NET Framework method</span></span>|<span data-ttu-id="f812b-107">설명</span><span class="sxs-lookup"><span data-stu-id="f812b-107">Description</span></span>|
|---------------------------|-----------------|
|<span data-ttu-id="f812b-108"><xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A></span><span class="sxs-lookup"><span data-stu-id="f812b-108"><xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A></span></span>|<span data-ttu-id="f812b-109">문자에 해당 하는 문자 코드를 나타내는 `Integer` 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-109">Returns an `Integer` value representing the character code corresponding to a character.</span></span>|
|<span data-ttu-id="f812b-110"><xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A></span><span class="sxs-lookup"><span data-stu-id="f812b-110"><xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A></span></span>|<span data-ttu-id="f812b-111">지정 된 문자 코드와 연관 된 문자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-111">Returns the character associated with the specified character code.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|<span data-ttu-id="f812b-112">지정 된 필터 조건에 따라 `String` 배열의 하위 집합을 포함 하는 0부터 시작 하는 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-112">Returns a zero-based array containing a subset of a `String` array based on specified filter criteria.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|<span data-ttu-id="f812b-113">형식 `String` 식에 포함 된 명령에 따라 형식이 지정 된 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-113">Returns a string formatted according to instructions contained in a format `String` expression.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|<span data-ttu-id="f812b-114">시스템 제어판에 정의 된 통화 기호를 사용 하 여 통화 값으로 형식이 지정 된 식을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-114">Returns an expression formatted as a currency value using the currency symbol defined in the system control panel.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|<span data-ttu-id="f812b-115">날짜/시간 값을 나타내는 문자열 식을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-115">Returns a string expression representing a date/time value.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|<span data-ttu-id="f812b-116">숫자로 서식이 지정 된 식을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-116">Returns an expression formatted as a number.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|<span data-ttu-id="f812b-117">백분율로 서식이 지정된 식(100을 곱함)을 % 문자를 붙여 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-117">Returns an expression formatted as a percentage (that is, multiplied by 100) with a trailing % character.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|<span data-ttu-id="f812b-118">한 문자열 안에 다른 문자열이 처음 나타나는 시작 위치를 지정 하는 정수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-118">Returns an integer specifying the start position of the first occurrence of one string within another.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|<span data-ttu-id="f812b-119">다른 문자열의 오른쪽에서 시작에서 한 문자열의 첫 번째 발생 위치를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-119">Returns the position of the first occurrence of one string within another, starting from the right side of the string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|<span data-ttu-id="f812b-120">여러 배열에 포함 된 문자열을 조인 하 여 만든 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-120">Returns a string created by joining a number of substrings contained in an array.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|<span data-ttu-id="f812b-121">소문자로 변환 된 문자열 또는 문자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-121">Returns a string or character converted to lowercase.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|<span data-ttu-id="f812b-122">지정 된 개수의 문자열의 왼쪽에서 문자를 포함 하는 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-122">Returns a string containing a specified number of characters from the left side of a string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|<span data-ttu-id="f812b-123">문자열의 문자 수를 포함 하는 정수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-123">Returns an integer that contains the number of characters in a string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|<span data-ttu-id="f812b-124">지정 된 길이에 맞게 조정 하는 지정된 된 문자열을 포함 하는 왼쪽 맞춤 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-124">Returns a left-aligned string containing the specified string adjusted to the specified length.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|<span data-ttu-id="f812b-125">선행 공백 없이 지정 된 문자열의 복사본을 포함 하는 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-125">Returns a string containing a copy of a specified string with no leading spaces.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|<span data-ttu-id="f812b-126">문자열에서 지정 된 수의 문자를 포함 하는 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-126">Returns a string containing a specified number of characters from a string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|<span data-ttu-id="f812b-127">문자열의 지정된 된 부분 문자열에 바뀌는 다른 반환 된 지정 된 횟수 만큼 부분 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-127">Returns a string in which a specified substring has been replaced with another substring a specified number of times.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|<span data-ttu-id="f812b-128">지정 된 문자열의 오른쪽에 있는 문자 수를 포함 하는 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-128">Returns a string containing a specified number of characters from the right side of a string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|<span data-ttu-id="f812b-129">지정 된 길이에 맞게 조정 하는 지정된 된 문자열을 포함 하는 오른쪽 맞춤 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-129">Returns a right-aligned string containing the specified string adjusted to the specified length.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|<span data-ttu-id="f812b-130">후행 공백 없이 지정 된 문자열의 복사본을 포함 하는 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-130">Returns a string containing a copy of a specified string with no trailing spaces.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|<span data-ttu-id="f812b-131">지정 된 수 만큼의 공백으로 구성 된 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-131">Returns a string consisting of the specified number of spaces.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|<span data-ttu-id="f812b-132">부분 문자열의 지정된 된 수를 포함 하는 0부터 시작 하는 1 차원 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-132">Returns a zero-based, one-dimensional array containing a specified number of substrings.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|<span data-ttu-id="f812b-133">-1, 0 또는 1, 문자열 비교의 결과 기반으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-133">Returns -1, 0, or 1, based on the result of a string comparison.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|<span data-ttu-id="f812b-134">지정 된 대로 변환 된 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-134">Returns a string converted as specified.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|<span data-ttu-id="f812b-135">문자열 또는 지정된 된 문자도 이루어진 개체를 반복 횟수가 지정 된 횟수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-135">Returns a string or object consisting of the specified character repeated the specified number of times.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|<span data-ttu-id="f812b-136">지정된 된 문자열의 문자 순서를 역순 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-136">Returns a string in which the character order of a specified string is reversed.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|<span data-ttu-id="f812b-137">선행 또는 후행 공백이 없는 지정 된 문자열의 복사본을 포함 하는 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-137">Returns a string containing a copy of a specified string with no leading or trailing spaces.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|<span data-ttu-id="f812b-138">문자열 또는 문자를 대문자로 변환 된 지정 된 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-138">Returns a string or character containing the specified string converted to uppercase.</span></span>|

<span data-ttu-id="f812b-139">[Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) 문을 사용 하 여 시스템의 로캘 (`Text`)에서 결정 한 대/소문자를 구분 하지 않는 텍스트 정렬 순서나 문자 (`Binary`)의 내부 이진 표시를 사용 하 여 문자열을 비교할지 여부를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-139">You can use the [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) statement to set whether strings are compared using a case-insensitive text sort order determined by your system's locale (`Text`) or by the internal binary representations of the characters (`Binary`).</span></span> <span data-ttu-id="f812b-140">기본 텍스트 비교 방법은 `Binary`입니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-140">The default text comparison method is `Binary`.</span></span>

## <a name="example-ucase"></a><span data-ttu-id="f812b-141">예: UCase</span><span class="sxs-lookup"><span data-stu-id="f812b-141">Example: UCase</span></span>

<span data-ttu-id="f812b-142">이 예에서는 `UCase` 함수를 사용 하 여 문자열의 대문자 버전을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-142">This example uses the `UCase` function to return an uppercase version of a string.</span></span>
[!code-vb[VbVbalrStrings#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#31)]

## <a name="example-ltrim"></a><span data-ttu-id="f812b-143">예: LTrim</span><span class="sxs-lookup"><span data-stu-id="f812b-143">Example: LTrim</span></span>

<span data-ttu-id="f812b-144">이 예에서는 `LTrim` 함수를 사용 하 여 선행 공백을 제거 하 고 `RTrim` 함수를 사용 하 여 문자열 변수에서 후행 공백을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-144">This example uses the `LTrim` function to strip leading spaces and the `RTrim` function to strip trailing spaces from a string variable.</span></span> <span data-ttu-id="f812b-145">`Trim` 함수를 사용 하 여 두 가지 유형의 공백을 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-145">It uses the `Trim` function to strip both types of spaces.</span></span>

[!code-vb[VbVbalrStrings#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#25)]

## <a name="example-mid"></a><span data-ttu-id="f812b-146">예: Mid</span><span class="sxs-lookup"><span data-stu-id="f812b-146">Example: Mid</span></span>

<span data-ttu-id="f812b-147">이 예에서는 `Mid` 함수를 사용 하 여 문자열에서 지정 된 수의 문자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-147">This example uses the `Mid` function to return a specified number of characters from a string.</span></span>

[!code-vb[VbVbalrStrings#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#17)]

## <a name="example-len"></a><span data-ttu-id="f812b-148">예: Len</span><span class="sxs-lookup"><span data-stu-id="f812b-148">Example: Len</span></span>

<span data-ttu-id="f812b-149">이 예제에서는 `Len`를 사용 하 여 문자열의 문자 수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-149">This example uses `Len` to return the number of characters in a string.</span></span>

[!code-vb[VbVbalrStrings#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#33)]

## <a name="example-instr"></a><span data-ttu-id="f812b-150">예: InStr</span><span class="sxs-lookup"><span data-stu-id="f812b-150">Example: InStr</span></span>

<span data-ttu-id="f812b-151">이 예제에서는 `InStr` 함수를 사용 하 여 다른 문자열 내에서 한 문자열의 첫 번째 발생 위치를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-151">This example uses the `InStr` function to return the position of the first occurrence of one string within another.</span></span>

[!code-vb[VbVbalrStrings#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#8)]

## <a name="example-format"></a><span data-ttu-id="f812b-152">예: Format</span><span class="sxs-lookup"><span data-stu-id="f812b-152">Example: Format</span></span>

<span data-ttu-id="f812b-153">이 예에서는 `String` 형식 및 사용자 정의 형식을 사용 하 여 값의 서식을 지정 하는 `Format` 함수의 다양 한 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-153">This example shows various uses of the `Format` function to format values using both `String` formats and user-defined formats.</span></span> <span data-ttu-id="f812b-154">날짜 구분 기호 (`/`), 시간 구분 기호 (`:`) 및 AM/PM 표시기 (`t` 및 `tt`)의 경우 시스템에 표시 되는 실제 형식이 지정 된 출력은 코드에서 사용 하는 로캘 설정에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-154">For the date separator (`/`), time separator (`:`), and the AM/PM indicators (`t` and `tt`), the actual formatted output displayed by your system depends on the locale settings the code is using.</span></span> <span data-ttu-id="f812b-155">경우 시간 및 개발 환경에서 표시 되는 날짜, 간단한 시간 형식 및 코드 로캘의 간단한 날짜 서식을 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-155">When times and dates are displayed in the development environment, the short time format and short date format of the code locale are used.</span></span>

> [!NOTE]
> <span data-ttu-id="f812b-156">24 시간제를 사용 하는 로캘의 경우 AM/PM 표시기 (`t` 및 `tt`)는 아무 것도 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f812b-156">For locales that use a 24-hour clock, the AM/PM indicators (`t` and `tt`) display nothing.</span></span>

[!code-vb[VbVbalrStrings#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#27)]

## <a name="see-also"></a><span data-ttu-id="f812b-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f812b-157">See also</span></span>

- [<span data-ttu-id="f812b-158">키워드</span><span class="sxs-lookup"><span data-stu-id="f812b-158">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="f812b-159">Visual Basic 런타임 라이브러리 멤버</span><span class="sxs-lookup"><span data-stu-id="f812b-159">Visual Basic Runtime Library Members</span></span>](../../../visual-basic/language-reference/runtime-library-members.md)
- [<span data-ttu-id="f812b-160">문자열 조작 요약</span><span class="sxs-lookup"><span data-stu-id="f812b-160">String Manipulation Summary</span></span>](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)
- [<span data-ttu-id="f812b-161">System.string 클래스 메서드</span><span class="sxs-lookup"><span data-stu-id="f812b-161">System.String class methods</span></span>](xref:System.String#methods)
