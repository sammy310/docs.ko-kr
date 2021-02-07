---
description: '자세한 정보: Like 연산자 (Visual Basic)'
title: Like 연산자
ms.date: 07/20/2015
f1_keywords:
- Like
- vb.Like
helpviewer_keywords:
- similar to
- pattern matching
- Like operator [Visual Basic]
- '? symbol, wildcard character'
- string comparison [Visual Basic], Like operator
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- symbols, wildcard
- wildcards, Like operator
- strings [Visual Basic], matching
- string comparison [Visual Basic], sorting data
- data [Visual Basic], sorting
- text [Visual Basic], comparing
- operators [Visual Basic], pattern-matching
- data [Visual Basic], string comparisons
- string comparison [Visual Basic], Like operators
ms.assetid: 966283ec-80e2-4294-baa8-c75baff804f9
ms.openlocfilehash: f1be174010b7acae5bface4fc0a2d0e606a90fca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665590"
---
# <a name="like-operator-visual-basic"></a><span data-ttu-id="87914-103">Like 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87914-103">Like Operator (Visual Basic)</span></span>

<span data-ttu-id="87914-104">문자열과 패턴을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="87914-104">Compares a string against a pattern.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="87914-105">`Like`연산자는 현재 .Net Core 및 .NET Standard 프로젝트에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87914-105">The `Like` operator is currently not supported in .NET Core and .NET Standard projects.</span></span>

## <a name="syntax"></a><span data-ttu-id="87914-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="87914-106">Syntax</span></span>  
  
```vb  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="87914-107">부분</span><span class="sxs-lookup"><span data-stu-id="87914-107">Parts</span></span>  

 `result`  
 <span data-ttu-id="87914-108">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="87914-108">Required.</span></span> <span data-ttu-id="87914-109">모든 `Boolean` 변수.</span><span class="sxs-lookup"><span data-stu-id="87914-109">Any `Boolean` variable.</span></span> <span data-ttu-id="87914-110">결과는가를 `Boolean` 충족 하는지 여부를 나타내는 값입니다 `string` `pattern` .</span><span class="sxs-lookup"><span data-stu-id="87914-110">The result is a `Boolean` value indicating whether or not the `string` satisfies the `pattern`.</span></span>  
  
 `string`  
 <span data-ttu-id="87914-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="87914-111">Required.</span></span> <span data-ttu-id="87914-112">임의의 `String` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="87914-112">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="87914-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="87914-113">Required.</span></span> <span data-ttu-id="87914-114">`String`"주의"에 설명 된 패턴 일치 규칙을 준수 하는 모든 식입니다.</span><span class="sxs-lookup"><span data-stu-id="87914-114">Any `String` expression conforming to the pattern-matching conventions described in "Remarks."</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87914-115">설명</span><span class="sxs-lookup"><span data-stu-id="87914-115">Remarks</span></span>  

 <span data-ttu-id="87914-116">의 값 `string` 이에 포함 된 패턴을 충족 `pattern` 하는 경우 `result` 는 `True` 입니다.</span><span class="sxs-lookup"><span data-stu-id="87914-116">If the value in `string` satisfies the pattern contained in `pattern`, `result` is `True`.</span></span> <span data-ttu-id="87914-117">문자열이 패턴을 충족 하지 않는 경우 `result` 는 `False` 입니다.</span><span class="sxs-lookup"><span data-stu-id="87914-117">If the string does not satisfy the pattern, `result` is `False`.</span></span> <span data-ttu-id="87914-118">및가 `string` 모두 `pattern` 빈 문자열인 경우 결과는 `True` 입니다.</span><span class="sxs-lookup"><span data-stu-id="87914-118">If both `string` and `pattern` are empty strings, the result is `True`.</span></span>  
  
## <a name="comparison-method"></a><span data-ttu-id="87914-119">비교 방법</span><span class="sxs-lookup"><span data-stu-id="87914-119">Comparison Method</span></span>  

 <span data-ttu-id="87914-120">연산자의 동작은 `Like` [Option Compare 문에](../statements/option-compare-statement.md)따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="87914-120">The behavior of the `Like` operator depends on the [Option Compare Statement](../statements/option-compare-statement.md).</span></span> <span data-ttu-id="87914-121">각 소스 파일에 대 한 기본 문자열 비교 방법은 `Option Compare Binary` 입니다.</span><span class="sxs-lookup"><span data-stu-id="87914-121">The default string comparison method for each source file is `Option Compare Binary`.</span></span>  
  
## <a name="pattern-options"></a><span data-ttu-id="87914-122">패턴 옵션</span><span class="sxs-lookup"><span data-stu-id="87914-122">Pattern Options</span></span>  

 <span data-ttu-id="87914-123">기본 제공 패턴 일치는 문자열 비교를 위한 다양 한 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="87914-123">Built-in pattern matching provides a versatile tool for string comparisons.</span></span> <span data-ttu-id="87914-124">패턴 일치 기능을 사용 하면 `string` 특정 문자, 와일드 카드 문자, 문자 목록 또는 문자 범위에 대해의 각 문자를 일치 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87914-124">The pattern-matching features allow you to match each character in `string` against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="87914-125">다음 표에서는에서 허용 되는 문자와 일치 하는 문자를 보여 줍니다 `pattern` .</span><span class="sxs-lookup"><span data-stu-id="87914-125">The following table shows the characters allowed in `pattern` and what they match.</span></span>  
  
|<span data-ttu-id="87914-126">문자 `pattern`</span><span class="sxs-lookup"><span data-stu-id="87914-126">Characters in `pattern`</span></span>|<span data-ttu-id="87914-127">일치 항목 `string`</span><span class="sxs-lookup"><span data-stu-id="87914-127">Matches in `string`</span></span>|  
|-----------------------------|-------------------------|  
|`?`|<span data-ttu-id="87914-128">임의의 단일 문자</span><span class="sxs-lookup"><span data-stu-id="87914-128">Any single character</span></span>|  
|`*`|<span data-ttu-id="87914-129">0 개 이상의 문자</span><span class="sxs-lookup"><span data-stu-id="87914-129">Zero or more characters</span></span>|  
|`#`|<span data-ttu-id="87914-130">임의의 단일 숫자 (0-9)</span><span class="sxs-lookup"><span data-stu-id="87914-130">Any single digit (0–9)</span></span>|  
|`[charlist]`|<span data-ttu-id="87914-131">의 단일 문자 `charlist`</span><span class="sxs-lookup"><span data-stu-id="87914-131">Any single character in `charlist`</span></span>|  
|`[!charlist]`|<span data-ttu-id="87914-132">에 없는 모든 단일 문자 `charlist`</span><span class="sxs-lookup"><span data-stu-id="87914-132">Any single character not in `charlist`</span></span>|  
  
## <a name="character-lists"></a><span data-ttu-id="87914-133">문자 목록</span><span class="sxs-lookup"><span data-stu-id="87914-133">Character Lists</span></span>  

 <span data-ttu-id="87914-134">대괄호 ()로 묶인 하나 이상의 문자 () 그룹을 `charlist` `[ ]` 사용 하 여의 단일 문자를 일치 `string` 시키고, 숫자를 비롯 한 거의 모든 문자 코드를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87914-134">A group of one or more characters (`charlist`) enclosed in brackets (`[ ]`) can be used to match any single character in `string` and can include almost any character code, including digits.</span></span>  
  
 <span data-ttu-id="87914-135">의 시작 부분에서 느낌표 ( `!` )는의 `charlist` 문자를 제외한 모든 문자를에서 찾을 수 있으면 일치가 수행 됨을 의미 `charlist` `string` 합니다.</span><span class="sxs-lookup"><span data-stu-id="87914-135">An exclamation point (`!`) at the beginning of `charlist` means that a match is made if any character except the characters in `charlist` is found in `string`.</span></span> <span data-ttu-id="87914-136">대괄호 외부에서 사용 하는 경우 느낌표는 자체와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="87914-136">When used outside brackets, the exclamation point matches itself.</span></span>  
  
## <a name="special-characters"></a><span data-ttu-id="87914-137">특수 문자</span><span class="sxs-lookup"><span data-stu-id="87914-137">Special Characters</span></span>  

 <span data-ttu-id="87914-138">특수 문자 왼쪽 대괄호 ( `[` ), 물음표 ( `?` ), 숫자 기호 () `#` 및 별표 ()를 일치 시키려면 `*` 대괄호로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="87914-138">To match the special characters left bracket (`[`), question mark (`?`), number sign (`#`), and asterisk (`*`), enclose them in brackets.</span></span> <span data-ttu-id="87914-139">`]`그룹 내에서 오른쪽 대괄호 ()를 사용 하 여 자신을 일치 시킬 수는 없지만 그룹 외부에서 개별 문자로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87914-139">The right bracket (`]`) cannot be used within a group to match itself, but it can be used outside a group as an individual character.</span></span>  
  
 <span data-ttu-id="87914-140">문자 시퀀스는 `[]` 길이가 0 인 문자열 ()로 간주 됩니다 `""` .</span><span class="sxs-lookup"><span data-stu-id="87914-140">The character sequence `[]` is considered a zero-length string (`""`).</span></span> <span data-ttu-id="87914-141">그러나 대괄호로 묶은 문자 목록의 일부일 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87914-141">However, it cannot be part of a character list enclosed in brackets.</span></span> <span data-ttu-id="87914-142">의 위치에 `string` 문자 그룹 중 하나가 포함 되어 있는지 또는 문자가 없는지를 확인 하려는 경우 두 번 사용할 수 있습니다 `Like` .</span><span class="sxs-lookup"><span data-stu-id="87914-142">If you want to check whether a position in `string` contains one of a group of characters or no character at all, you can use `Like` twice.</span></span> <span data-ttu-id="87914-143">예제는 [방법: 패턴에 대해 문자열 일치](../../programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87914-143">For an example, see [How to: Match a String against a Pattern](../../programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span></span>  
  
## <a name="character-ranges"></a><span data-ttu-id="87914-144">문자 범위</span><span class="sxs-lookup"><span data-stu-id="87914-144">Character Ranges</span></span>  

 <span data-ttu-id="87914-145">하이픈 ()을 사용 하 여 `–` 범위의 하 한 및 상한을 구분 하면에서 `charlist` 문자 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87914-145">By using a hyphen (`–`) to separate the lower and upper bounds of the range, `charlist` can specify a range of characters.</span></span> <span data-ttu-id="87914-146">예를 `[A–Z]` 들어,의 해당 문자 위치에 –의 모든 문자가 포함 된 경우 일치 항목이 반환 되 `string` `A` `Z` 고 `[!H–L]` 해당 문자 위치에-범위를 벗어난 문자가 포함 된 경우 일치 항목이 반환 `H` `L` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87914-146">For example, `[A–Z]` results in a match if the corresponding character position in `string` contains any character within the range `A`–`Z`, and `[!H–L]` results in a match if the corresponding character position contains any character outside the range `H`–`L`.</span></span>  
  
 <span data-ttu-id="87914-147">문자 범위를 지정 하는 경우 오름차순 정렬 순서로 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87914-147">When you specify a range of characters, they must appear in ascending sort order, that is, from lowest to highest.</span></span> <span data-ttu-id="87914-148">따라서 `[A–Z]` 는 유효한 패턴 이지만 `[Z–A]` 는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87914-148">Thus, `[A–Z]` is a valid pattern, but `[Z–A]` is not.</span></span>  
  
### <a name="multiple-character-ranges"></a><span data-ttu-id="87914-149">여러 문자 범위</span><span class="sxs-lookup"><span data-stu-id="87914-149">Multiple Character Ranges</span></span>  

 <span data-ttu-id="87914-150">동일한 문자 위치에 여러 범위를 지정 하려면 구분 기호 없이 동일한 대괄호 안에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="87914-150">To specify multiple ranges for the same character position, put them within the same brackets without delimiters.</span></span> <span data-ttu-id="87914-151">예를 `[A–CX–Z]` 들어의 해당 문자 위치에 `string` 범위 또는 범위 내에 있는 문자가 포함 된 경우는 일치 하는 항목을 반환 합니다 `A` `C` `X` `Z` .</span><span class="sxs-lookup"><span data-stu-id="87914-151">For example, `[A–CX–Z]` results in a match if the corresponding character position in `string` contains any character within either the range `A`–`C` or the range `X`–`Z`.</span></span>  
  
### <a name="usage-of-the-hyphen"></a><span data-ttu-id="87914-152">하이픈 사용</span><span class="sxs-lookup"><span data-stu-id="87914-152">Usage of the Hyphen</span></span>  

 <span data-ttu-id="87914-153">하이픈 ( `–` )은 시작 부분 (느낌표 이후) 또는 끝 부분 (의 끝)에 표시 될 수 있습니다 `charlist` .</span><span class="sxs-lookup"><span data-stu-id="87914-153">A hyphen (`–`) can appear either at the beginning (after an exclamation point, if any) or at the end of `charlist` to match itself.</span></span> <span data-ttu-id="87914-154">다른 위치에서 하이픈은 하이픈 양쪽의 문자로 구분 되는 문자 범위를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="87914-154">In any other location, the hyphen identifies a range of characters delimited by the characters on either side of the hyphen.</span></span>  
  
## <a name="collating-sequence"></a><span data-ttu-id="87914-155">데이터 정렬 순서</span><span class="sxs-lookup"><span data-stu-id="87914-155">Collating Sequence</span></span>  

 <span data-ttu-id="87914-156">지정 된 범위의 의미는 런타임에의 문자 순서 `Option Compare` 와 코드를 실행 하는 시스템의 로캘 설정에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="87914-156">The meaning of a specified range depends on the character ordering at run time, as determined by `Option Compare` and the locale setting of the system the code is running on.</span></span> <span data-ttu-id="87914-157">에서 `Option Compare Binary` 범위는,,, `[A–E]` 및와 일치 `A` `B` `C` `D` `E` 합니다.</span><span class="sxs-lookup"><span data-stu-id="87914-157">With `Option Compare Binary`, the range `[A–E]` matches `A`, `B`, `C`, `D`, and `E`.</span></span> <span data-ttu-id="87914-158">에서,,,,,,,,,, `Option Compare Text` `[A–E]` 및를 일치 시킵니다 `A` `a` `À` `à` `B` `b` `C` `c` `D` `d` `E` `e` .</span><span class="sxs-lookup"><span data-stu-id="87914-158">With `Option Compare Text`, `[A–E]` matches `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, and `e`.</span></span> <span data-ttu-id="87914-159">범위가 일치 하지 않거나 `Ê` , `ê` 악센트 부호가 있는 문자가 정렬 순서에서 악센트가 없는 문자 다음에 정렬 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="87914-159">The range does not match `Ê` or `ê` because accented characters collate after unaccented characters in the sort order.</span></span>  
  
## <a name="digraph-characters"></a><span data-ttu-id="87914-160">D i g 문자</span><span class="sxs-lookup"><span data-stu-id="87914-160">Digraph Characters</span></span>  

 <span data-ttu-id="87914-161">일부 언어에는 두 개의 개별 문자를 나타내는 영문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87914-161">In some languages, there are alphabetic characters that represent two separate characters.</span></span> <span data-ttu-id="87914-162">예를 들어 여러 언어는 문자를 사용 `æ` 하 여 문자를 나타내고 `a` `e` 함께 표시 될 때 문자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="87914-162">For example, several languages use the character `æ` to represent the characters `a` and `e` when they appear together.</span></span> <span data-ttu-id="87914-163">`Like`연산자는 단일 d i g 문자 및 두 개의 개별 문자가 동일 하다는 것을 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="87914-163">The `Like` operator recognizes that the single digraph character and the two individual characters are equivalent.</span></span>  
  
 <span data-ttu-id="87914-164">D i g 문자를 사용 하는 언어가 시스템 로캘 설정에 지정 된 경우 또는의 단일 d i g 문자가 `pattern` `string` 다른 문자열의 두 문자 시퀀스와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="87914-164">When a language that uses a digraph character is specified in the system locale settings, an occurrence of the single digraph character in either `pattern` or `string` matches the equivalent two-character sequence in the other string.</span></span> <span data-ttu-id="87914-165">마찬가지로 `pattern` 대괄호 안에 포함 된 d i g 문자 (목록 또는 범위)는의 두 문자 시퀀스와 일치 합니다 `string` .</span><span class="sxs-lookup"><span data-stu-id="87914-165">Similarly, a digraph character in `pattern` enclosed in brackets (by itself, in a list, or in a range) matches the equivalent two-character sequence in `string`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="87914-166">오버로딩</span><span class="sxs-lookup"><span data-stu-id="87914-166">Overloading</span></span>  

 <span data-ttu-id="87914-167">`Like`연산자를 *오버 로드할* 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87914-167">The `Like` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="87914-168">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87914-168">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="87914-169">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87914-169">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="87914-170">예제</span><span class="sxs-lookup"><span data-stu-id="87914-170">Example</span></span>  

 <span data-ttu-id="87914-171">이 예제에서는 연산자를 사용 하 여 `Like` 문자열을 다양 한 패턴과 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="87914-171">This example uses the `Like` operator to compare strings to various patterns.</span></span> <span data-ttu-id="87914-172">결과는 `Boolean` 각 문자열이 패턴을 충족 하는지 여부를 나타내는 변수로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="87914-172">The results go into a `Boolean` variable indicating whether each string satisfies the pattern.</span></span>  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="87914-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87914-173">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [<span data-ttu-id="87914-174">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="87914-174">Comparison Operators</span></span>](comparison-operators.md)
- [<span data-ttu-id="87914-175">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="87914-175">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="87914-176">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="87914-176">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="87914-177">Option Compare 문</span><span class="sxs-lookup"><span data-stu-id="87914-177">Option Compare Statement</span></span>](../statements/option-compare-statement.md)
- [<span data-ttu-id="87914-178">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="87914-178">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="87914-179">방법: 패턴에 대해 문자열 비교</span><span class="sxs-lookup"><span data-stu-id="87914-179">How to: Match a String against a Pattern</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
