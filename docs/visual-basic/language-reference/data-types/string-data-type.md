---
title: String 데이터 형식(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.String
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings [Visual Basic], string data type
- literals [Visual Basic], string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals [Visual Basic]
- data types [Visual Basic], assigning
- String literals [Visual Basic]
- identifier type characters [Visual Basic], $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
ms.openlocfilehash: 6d2fd226735622de5cd7197060c05b8ac12b69f1
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696840"
---
# <a name="string-data-type-visual-basic"></a><span data-ttu-id="4704e-102">String 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4704e-102">String Data Type (Visual Basic)</span></span>
<span data-ttu-id="4704e-103">0에서 65535 사이의 값 범위에 해당 하는 부호 없는 16 비트 (2 바이트) 코드 요소의 시퀀스를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span></span> <span data-ttu-id="4704e-104">각 *코드 포인트*또는 문자 코드는 단일 유니코드 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-104">Each *code point*, or character code, represents a single Unicode character.</span></span> <span data-ttu-id="4704e-105">문자열은 0에서 약 20억 (2 ^ 31) 자의 유니코드 문자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4704e-106">설명</span><span class="sxs-lookup"><span data-stu-id="4704e-106">Remarks</span></span>  
 <span data-ttu-id="4704e-107">@No__t-0 데이터 형식을 사용 하 여 `Char` 요소의 배열인 `Char()`의 배열 관리 오버 헤드 없이 여러 문자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span></span>  
  
 <span data-ttu-id="4704e-108">@No__t-0의 기본값은-1 (null 참조) @no__t입니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-108">The default value of `String` is `Nothing` (a null reference).</span></span> <span data-ttu-id="4704e-109">이 값은 빈 문자열 (값 `""`)과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-109">Note that this is not the same as the empty string (value `""`).</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="4704e-110">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="4704e-110">Unicode Characters</span></span>  
 <span data-ttu-id="4704e-111">유니코드의 처음 128 코드 요소 (0 – 127)는 표준 미국 키보드의 문자 및 기호에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="4704e-112">이러한 첫 번째 128 코드 포인트가 ASCII 문자 집합에서 정의 하는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="4704e-113">두 번째 128 코드 요소 (128-255)는 특수 문자 (예: 라틴어 기반 영문자, 악센트, 통화 기호 및 분수)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="4704e-114">유니코드는 다양 한 기호에 대해 나머지 코드 요소 (256-65535)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span></span> <span data-ttu-id="4704e-115">여기에는 전 세계 텍스트 문자, 분음 부호, 수학 및 기술 기호가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="4704e-116">@No__t-2 변수의 개별 문자에 <xref:System.Char.IsDigit%2A> 및 <xref:System.Char.IsPunctuation%2A>과 같은 메서드를 사용 하 여 해당 유니코드 분류를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="4704e-117">형식 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4704e-117">Format Requirements</span></span>  
 <span data-ttu-id="4704e-118">@No__t-0 리터럴을 따옴표 (`" "`)로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-118">You must enclose a `String` literal within quotation marks (`" "`).</span></span> <span data-ttu-id="4704e-119">문자열의 문자 중 하나로 따옴표를 포함 해야 하는 경우에는 두 개의 연속 된 따옴표 (`""`)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span></span> <span data-ttu-id="4704e-120">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-120">The following example illustrates this.</span></span>  
  
```vb  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 <span data-ttu-id="4704e-121">문자열의 따옴표를 나타내는 연속 된 따옴표는 `String` 리터럴을 시작 하 고 종료 하는 따옴표와는 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span></span>  
  
## <a name="string-manipulations"></a><span data-ttu-id="4704e-122">문자열 조작</span><span class="sxs-lookup"><span data-stu-id="4704e-122">String Manipulations</span></span>  
 <span data-ttu-id="4704e-123">@No__t-0 변수에 문자열을 할당 하면 해당 문자열은 변경할 수 없습니다. 즉, 해당 문자열의 길이 또는 *내용을 변경할 수*없습니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span></span> <span data-ttu-id="4704e-124">어떤 방식으로든 문자열을 변경 하는 경우 Visual Basic는 새 문자열을 만들어 이전 문자열을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span></span> <span data-ttu-id="4704e-125">그러면 `String` 변수가 새 문자열을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-125">The `String` variable then points to the new string.</span></span>  
  
 <span data-ttu-id="4704e-126">다양 한 문자열 함수를 사용 하 여 `String` 변수의 내용을 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span></span> <span data-ttu-id="4704e-127">다음 예에서는 <xref:Microsoft.VisualBasic.Strings.Left%2A> 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span></span>  
  
```vb  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 <span data-ttu-id="4704e-128">다른 구성 요소에 의해 생성 된 문자열은 선행 또는 후행 공백으로 채워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-128">A string created by another component might be padded with leading or trailing spaces.</span></span> <span data-ttu-id="4704e-129">이러한 문자열을 수신 하는 경우 <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A> 및 <xref:Microsoft.VisualBasic.Strings.RTrim%2A> 함수를 사용 하 여 이러한 공백을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span></span>  
  
 <span data-ttu-id="4704e-130">문자열 조작에 대 한 자세한 내용은 [문자열](../../../visual-basic/programming-guide/language-features/strings/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4704e-130">For more information about string manipulations, see [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="4704e-131">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="4704e-131">Programming Tips</span></span>  
  
- <span data-ttu-id="4704e-132">**음수.**</span><span class="sxs-lookup"><span data-stu-id="4704e-132">**Negative Numbers.**</span></span> <span data-ttu-id="4704e-133">@No__t-0에 의해 유지 되는 문자는 부호가 없으며 음수 값을 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span></span> <span data-ttu-id="4704e-134">어떤 경우 든 `String`을 사용 하 여 숫자 값을 저장 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-134">In any case, you should not use `String` to hold numeric values.</span></span>  
  
- <span data-ttu-id="4704e-135">**Interop 고려 사항**</span><span class="sxs-lookup"><span data-stu-id="4704e-135">**Interop Considerations.**</span></span> <span data-ttu-id="4704e-136">.NET Framework 용으로 작성 되지 않은 구성 요소 (예: Automation 또는 COM 개체)와 상호 작용 하는 경우 다른 환경에서는 문자열 문자에 다른 데이터 너비 (8 비트)가 있다는 점에 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="4704e-137">8 비트 문자에 대 한 문자열 인수를 이러한 구성 요소에 전달 하는 경우 새 Visual Basic 코드의 `String` 대신 `Byte` 요소의 배열인 `Byte()`으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span></span>  
  
- <span data-ttu-id="4704e-138">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4704e-138">**Type Characters.**</span></span> <span data-ttu-id="4704e-139">식별자 형식 문자 `$`을 식별자에 추가 하면 `String` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span></span> <span data-ttu-id="4704e-140">`String`에는 리터럴 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-140">`String` has no literal type character.</span></span> <span data-ttu-id="4704e-141">그러나 컴파일러는 따옴표 (`" "`)로 묶인 리터럴을 `String`로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span></span>  
  
- <span data-ttu-id="4704e-142">**프레임 워크 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="4704e-142">**Framework Type.**</span></span> <span data-ttu-id="4704e-143">.NET Framework에서 해당 하는 형식은 <xref:System.String?displayProperty=nameWithType> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4704e-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=nameWithType> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4704e-144">참조</span><span class="sxs-lookup"><span data-stu-id="4704e-144">See also</span></span>

- <xref:System.String?displayProperty=nameWithType>
- [<span data-ttu-id="4704e-145">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4704e-145">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="4704e-146">Char 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4704e-146">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="4704e-147">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="4704e-147">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="4704e-148">변환 요약</span><span class="sxs-lookup"><span data-stu-id="4704e-148">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="4704e-149">방법: 부호 없는 형식을 사용하는 Windows 함수 호출</span><span class="sxs-lookup"><span data-stu-id="4704e-149">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="4704e-150">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="4704e-150">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
