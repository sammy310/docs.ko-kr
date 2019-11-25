---
title: 문자열 데이터 형식
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
ms.openlocfilehash: c2c6f9632646c432abb7b6da8887253e526cc994
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343905"
---
# <a name="string-data-type-visual-basic"></a><span data-ttu-id="c1a80-102">String 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1a80-102">String Data Type (Visual Basic)</span></span>

<span data-ttu-id="c1a80-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span><span class="sxs-lookup"><span data-stu-id="c1a80-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span></span> <span data-ttu-id="c1a80-104">Each *code point*, or character code, represents a single Unicode character.</span><span class="sxs-lookup"><span data-stu-id="c1a80-104">Each *code point*, or character code, represents a single Unicode character.</span></span> <span data-ttu-id="c1a80-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span><span class="sxs-lookup"><span data-stu-id="c1a80-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1a80-106">주의</span><span class="sxs-lookup"><span data-stu-id="c1a80-106">Remarks</span></span>  

 <span data-ttu-id="c1a80-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span><span class="sxs-lookup"><span data-stu-id="c1a80-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span></span>  
  
 <span data-ttu-id="c1a80-108">The default value of `String` is `Nothing` (a null reference).</span><span class="sxs-lookup"><span data-stu-id="c1a80-108">The default value of `String` is `Nothing` (a null reference).</span></span> <span data-ttu-id="c1a80-109">Note that this is not the same as the empty string (value `""`).</span><span class="sxs-lookup"><span data-stu-id="c1a80-109">Note that this is not the same as the empty string (value `""`).</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="c1a80-110">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="c1a80-110">Unicode Characters</span></span>  

 <span data-ttu-id="c1a80-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span><span class="sxs-lookup"><span data-stu-id="c1a80-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="c1a80-112">These first 128 code points are the same as those the ASCII character set defines.</span><span class="sxs-lookup"><span data-stu-id="c1a80-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="c1a80-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span><span class="sxs-lookup"><span data-stu-id="c1a80-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="c1a80-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span><span class="sxs-lookup"><span data-stu-id="c1a80-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span></span> <span data-ttu-id="c1a80-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span><span class="sxs-lookup"><span data-stu-id="c1a80-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="c1a80-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span><span class="sxs-lookup"><span data-stu-id="c1a80-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="c1a80-117">형식 요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1a80-117">Format Requirements</span></span>  

 <span data-ttu-id="c1a80-118">You must enclose a `String` literal within quotation marks (`" "`).</span><span class="sxs-lookup"><span data-stu-id="c1a80-118">You must enclose a `String` literal within quotation marks (`" "`).</span></span> <span data-ttu-id="c1a80-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span><span class="sxs-lookup"><span data-stu-id="c1a80-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span></span> <span data-ttu-id="c1a80-120">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a80-120">The following example illustrates this.</span></span>  
  
```vb  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 <span data-ttu-id="c1a80-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span><span class="sxs-lookup"><span data-stu-id="c1a80-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span></span>  
  
## <a name="string-manipulations"></a><span data-ttu-id="c1a80-122">String Manipulations</span><span class="sxs-lookup"><span data-stu-id="c1a80-122">String Manipulations</span></span>  

 <span data-ttu-id="c1a80-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span><span class="sxs-lookup"><span data-stu-id="c1a80-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span></span> <span data-ttu-id="c1a80-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span><span class="sxs-lookup"><span data-stu-id="c1a80-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span></span> <span data-ttu-id="c1a80-125">The `String` variable then points to the new string.</span><span class="sxs-lookup"><span data-stu-id="c1a80-125">The `String` variable then points to the new string.</span></span>  
  
 <span data-ttu-id="c1a80-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span><span class="sxs-lookup"><span data-stu-id="c1a80-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span></span> <span data-ttu-id="c1a80-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span><span class="sxs-lookup"><span data-stu-id="c1a80-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span></span>  
  
```vb  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 <span data-ttu-id="c1a80-128">A string created by another component might be padded with leading or trailing spaces.</span><span class="sxs-lookup"><span data-stu-id="c1a80-128">A string created by another component might be padded with leading or trailing spaces.</span></span> <span data-ttu-id="c1a80-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span><span class="sxs-lookup"><span data-stu-id="c1a80-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span></span>  
  
 <span data-ttu-id="c1a80-130">For more information about string manipulations, see [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).</span><span class="sxs-lookup"><span data-stu-id="c1a80-130">For more information about string manipulations, see [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="c1a80-131">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="c1a80-131">Programming Tips</span></span>  
  
- <span data-ttu-id="c1a80-132">**Negative Numbers.**</span><span class="sxs-lookup"><span data-stu-id="c1a80-132">**Negative Numbers.**</span></span> <span data-ttu-id="c1a80-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span><span class="sxs-lookup"><span data-stu-id="c1a80-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span></span> <span data-ttu-id="c1a80-134">In any case, you should not use `String` to hold numeric values.</span><span class="sxs-lookup"><span data-stu-id="c1a80-134">In any case, you should not use `String` to hold numeric values.</span></span>  
  
- <span data-ttu-id="c1a80-135">**Interop Considerations.**</span><span class="sxs-lookup"><span data-stu-id="c1a80-135">**Interop Considerations.**</span></span> <span data-ttu-id="c1a80-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span><span class="sxs-lookup"><span data-stu-id="c1a80-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="c1a80-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span><span class="sxs-lookup"><span data-stu-id="c1a80-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span></span>  
  
- <span data-ttu-id="c1a80-138">**Type Characters.**</span><span class="sxs-lookup"><span data-stu-id="c1a80-138">**Type Characters.**</span></span> <span data-ttu-id="c1a80-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span><span class="sxs-lookup"><span data-stu-id="c1a80-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span></span> <span data-ttu-id="c1a80-140">`String` has no literal type character.</span><span class="sxs-lookup"><span data-stu-id="c1a80-140">`String` has no literal type character.</span></span> <span data-ttu-id="c1a80-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span><span class="sxs-lookup"><span data-stu-id="c1a80-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span></span>  
  
- <span data-ttu-id="c1a80-142">**Framework Type.**</span><span class="sxs-lookup"><span data-stu-id="c1a80-142">**Framework Type.**</span></span> <span data-ttu-id="c1a80-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=nameWithType> class.</span><span class="sxs-lookup"><span data-stu-id="c1a80-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=nameWithType> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1a80-144">참조</span><span class="sxs-lookup"><span data-stu-id="c1a80-144">See also</span></span>

- <xref:System.String?displayProperty=nameWithType>
- [<span data-ttu-id="c1a80-145">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c1a80-145">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="c1a80-146">Char 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c1a80-146">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="c1a80-147">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="c1a80-147">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="c1a80-148">변환 요약</span><span class="sxs-lookup"><span data-stu-id="c1a80-148">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="c1a80-149">방법: 부호 없는 형식을 사용하는 Windows 함수 호출</span><span class="sxs-lookup"><span data-stu-id="c1a80-149">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="c1a80-150">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="c1a80-150">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
