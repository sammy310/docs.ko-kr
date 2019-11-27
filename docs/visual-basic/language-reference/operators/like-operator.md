---
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
ms.openlocfilehash: 5db9488bbec716156a3ab464042c0853241a82b1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350940"
---
# <a name="like-operator-visual-basic"></a><span data-ttu-id="8063e-102">Like 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8063e-102">Like Operator (Visual Basic)</span></span>
<span data-ttu-id="8063e-103">문자열과 패턴을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-103">Compares a string against a pattern.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="8063e-104">`Like` 연산자는 현재 .NET Core 및 .NET Standard 프로젝트에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-104">The `Like` operator is currently not supported in .NET Core and .NET Standard projects.</span></span>

## <a name="syntax"></a><span data-ttu-id="8063e-105">구문</span><span class="sxs-lookup"><span data-stu-id="8063e-105">Syntax</span></span>  
  
```vb  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="8063e-106">요소</span><span class="sxs-lookup"><span data-stu-id="8063e-106">Parts</span></span>  
 `result`  
 <span data-ttu-id="8063e-107">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-107">Required.</span></span> <span data-ttu-id="8063e-108">모든 `Boolean` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-108">Any `Boolean` variable.</span></span> <span data-ttu-id="8063e-109">결과는 `string` `pattern`충족 하는지 여부를 나타내는 `Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-109">The result is a `Boolean` value indicating whether or not the `string` satisfies the `pattern`.</span></span>  
  
 `string`  
 <span data-ttu-id="8063e-110">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-110">Required.</span></span> <span data-ttu-id="8063e-111">임의의 `String` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-111">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="8063e-112">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-112">Required.</span></span> <span data-ttu-id="8063e-113">"주의"에 설명 된 패턴 일치 규칙을 따르는 `String` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-113">Any `String` expression conforming to the pattern-matching conventions described in "Remarks."</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8063e-114">주의</span><span class="sxs-lookup"><span data-stu-id="8063e-114">Remarks</span></span>  
 <span data-ttu-id="8063e-115">`string`의 값이 `pattern`에 포함 된 패턴을 충족 하는 경우 `result` `True`됩니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-115">If the value in `string` satisfies the pattern contained in `pattern`, `result` is `True`.</span></span> <span data-ttu-id="8063e-116">문자열이 패턴을 충족 하지 않으면 `result` `False`됩니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-116">If the string does not satisfy the pattern, `result` is `False`.</span></span> <span data-ttu-id="8063e-117">`string`와 `pattern` 모두 빈 문자열이 면 결과는 `True`됩니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-117">If both `string` and `pattern` are empty strings, the result is `True`.</span></span>  
  
## <a name="comparison-method"></a><span data-ttu-id="8063e-118">비교 방법</span><span class="sxs-lookup"><span data-stu-id="8063e-118">Comparison Method</span></span>  
 <span data-ttu-id="8063e-119">`Like` 연산자의 동작은 [Option Compare 문에](../../../visual-basic/language-reference/statements/option-compare-statement.md)따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-119">The behavior of the `Like` operator depends on the [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span> <span data-ttu-id="8063e-120">각 소스 파일에 대 한 기본 문자열 비교 메서드는 `Option Compare Binary`됩니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-120">The default string comparison method for each source file is `Option Compare Binary`.</span></span>  
  
## <a name="pattern-options"></a><span data-ttu-id="8063e-121">패턴 옵션</span><span class="sxs-lookup"><span data-stu-id="8063e-121">Pattern Options</span></span>  
 <span data-ttu-id="8063e-122">기본 제공 패턴 일치는 문자열 비교를 위한 다양 한 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-122">Built-in pattern matching provides a versatile tool for string comparisons.</span></span> <span data-ttu-id="8063e-123">패턴 일치 기능을 사용 하면 `string`의 각 문자를 특정 문자, 와일드 카드 문자, 문자 목록 또는 문자 범위에 대해 일치 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-123">The pattern-matching features allow you to match each character in `string` against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="8063e-124">다음 표에서는 `pattern`에서 허용 되는 문자와 일치 하는 문자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-124">The following table shows the characters allowed in `pattern` and what they match.</span></span>  
  
|<span data-ttu-id="8063e-125">`pattern`의 문자</span><span class="sxs-lookup"><span data-stu-id="8063e-125">Characters in `pattern`</span></span>|<span data-ttu-id="8063e-126">`string` 일치</span><span class="sxs-lookup"><span data-stu-id="8063e-126">Matches in `string`</span></span>|  
|-----------------------------|-------------------------|  
|`?`|<span data-ttu-id="8063e-127">단일 문자</span><span class="sxs-lookup"><span data-stu-id="8063e-127">Any single character</span></span>|  
|`*`|<span data-ttu-id="8063e-128">0 개 이상의 문자</span><span class="sxs-lookup"><span data-stu-id="8063e-128">Zero or more characters</span></span>|  
|`#`|<span data-ttu-id="8063e-129">임의의 단일 숫자 (0-9)</span><span class="sxs-lookup"><span data-stu-id="8063e-129">Any single digit (0–9)</span></span>|  
|`[charlist]`|<span data-ttu-id="8063e-130">`charlist`의 단일 문자</span><span class="sxs-lookup"><span data-stu-id="8063e-130">Any single character in `charlist`</span></span>|  
|`[!charlist]`|<span data-ttu-id="8063e-131">`charlist`에 없는 모든 단일 문자</span><span class="sxs-lookup"><span data-stu-id="8063e-131">Any single character not in `charlist`</span></span>|  
  
## <a name="character-lists"></a><span data-ttu-id="8063e-132">문자 목록</span><span class="sxs-lookup"><span data-stu-id="8063e-132">Character Lists</span></span>  
 <span data-ttu-id="8063e-133">대괄호 (`[ ]`)로 묶인 하나 이상의 문자 (`charlist`) 그룹을 사용 하 여 `string`의 단일 문자를 일치 시키고, 숫자를 포함 하 여 거의 모든 문자 코드를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-133">A group of one or more characters (`charlist`) enclosed in brackets (`[ ]`) can be used to match any single character in `string` and can include almost any character code, including digits.</span></span>  
  
 <span data-ttu-id="8063e-134">`charlist` 시작 부분에서 느낌표 (`!`)는 `charlist`의 문자를 제외한 문자를 `string`에서 찾을 수 있으면 일치가 수행 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-134">An exclamation point (`!`) at the beginning of `charlist` means that a match is made if any character except the characters in `charlist` is found in `string`.</span></span> <span data-ttu-id="8063e-135">대괄호 외부에서 사용 하는 경우 느낌표는 자체와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-135">When used outside brackets, the exclamation point matches itself.</span></span>  
  
## <a name="special-characters"></a><span data-ttu-id="8063e-136">특수 문자</span><span class="sxs-lookup"><span data-stu-id="8063e-136">Special Characters</span></span>  
 <span data-ttu-id="8063e-137">특수 문자 왼쪽 대괄호 (`[`), 물음표 (`?`), 숫자 기호 (`#`) 및 별표 (`*`)를 일치 시키려면 대괄호로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-137">To match the special characters left bracket (`[`), question mark (`?`), number sign (`#`), and asterisk (`*`), enclose them in brackets.</span></span> <span data-ttu-id="8063e-138">그룹 내에서 오른쪽 대괄호 (`]`)를 사용 하 여 자신을 일치 시킬 수는 없지만 그룹 외부에서 개별 문자로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-138">The right bracket (`]`) cannot be used within a group to match itself, but it can be used outside a group as an individual character.</span></span>  
  
 <span data-ttu-id="8063e-139">문자 시퀀스 `[]`은 길이가 0 인 문자열 (`""`)로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-139">The character sequence `[]` is considered a zero-length string (`""`).</span></span> <span data-ttu-id="8063e-140">그러나 대괄호로 묶은 문자 목록의 일부일 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-140">However, it cannot be part of a character list enclosed in brackets.</span></span> <span data-ttu-id="8063e-141">`string`의 위치에 문자 그룹 중 하나가 포함 되어 있는지 또는 문자가 없는지를 확인 하려는 경우 `Like`를 두 번 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-141">If you want to check whether a position in `string` contains one of a group of characters or no character at all, you can use `Like` twice.</span></span> <span data-ttu-id="8063e-142">예제는 [방법: 패턴에 대해 문자열 일치](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8063e-142">For an example, see [How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span></span>  
  
## <a name="character-ranges"></a><span data-ttu-id="8063e-143">문자 범위</span><span class="sxs-lookup"><span data-stu-id="8063e-143">Character Ranges</span></span>  
 <span data-ttu-id="8063e-144">하이픈 (`–`)을 사용 하 여 범위의 하 한 및 상한을 구분 하면 `charlist` 문자 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-144">By using a hyphen (`–`) to separate the lower and upper bounds of the range, `charlist` can specify a range of characters.</span></span> <span data-ttu-id="8063e-145">예를 들어 `[A–Z]`은 `string`의 해당 문자 위치가 `A`–`Z`범위 내에 있는 모든 문자를 포함 하는 경우 일치 하는 항목을 반환 하 고 `[!H–L]`-`H`범위를 벗어나는 문자가 해당 문자 위치에 포함 되어 있으면`L`일치 항목을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-145">For example, `[A–Z]` results in a match if the corresponding character position in `string` contains any character within the range `A`–`Z`, and `[!H–L]` results in a match if the corresponding character position contains any character outside the range `H`–`L`.</span></span>  
  
 <span data-ttu-id="8063e-146">문자 범위를 지정 하는 경우 오름차순 정렬 순서로 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-146">When you specify a range of characters, they must appear in ascending sort order, that is, from lowest to highest.</span></span> <span data-ttu-id="8063e-147">따라서 `[A–Z]`는 유효한 패턴 이지만 `[Z–A]`는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-147">Thus, `[A–Z]` is a valid pattern, but `[Z–A]` is not.</span></span>  
  
### <a name="multiple-character-ranges"></a><span data-ttu-id="8063e-148">여러 문자 범위</span><span class="sxs-lookup"><span data-stu-id="8063e-148">Multiple Character Ranges</span></span>  
 <span data-ttu-id="8063e-149">동일한 문자 위치에 여러 범위를 지정 하려면 구분 기호 없이 동일한 대괄호 안에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-149">To specify multiple ranges for the same character position, put them within the same brackets without delimiters.</span></span> <span data-ttu-id="8063e-150">예를 들어 `[A–CX–Z]`은 `string`의 해당 문자 위치에 `A`–`C` 범위 또는 `X`–`Z`범위 내에 있는 문자가 포함 된 경우 일치 항목을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-150">For example, `[A–CX–Z]` results in a match if the corresponding character position in `string` contains any character within either the range `A`–`C` or the range `X`–`Z`.</span></span>  
  
### <a name="usage-of-the-hyphen"></a><span data-ttu-id="8063e-151">하이픈 사용</span><span class="sxs-lookup"><span data-stu-id="8063e-151">Usage of the Hyphen</span></span>  
 <span data-ttu-id="8063e-152">하이픈 (`–`)은 시작 부분 (느낌표 이후) 또는 `charlist` 끝에 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-152">A hyphen (`–`) can appear either at the beginning (after an exclamation point, if any) or at the end of `charlist` to match itself.</span></span> <span data-ttu-id="8063e-153">다른 위치에서 하이픈은 하이픈 양쪽의 문자로 구분 되는 문자 범위를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-153">In any other location, the hyphen identifies a range of characters delimited by the characters on either side of the hyphen.</span></span>  
  
## <a name="collating-sequence"></a><span data-ttu-id="8063e-154">데이터 정렬 순서</span><span class="sxs-lookup"><span data-stu-id="8063e-154">Collating Sequence</span></span>  
 <span data-ttu-id="8063e-155">지정 된 범위의 의미는 `Option Compare`에 의해 결정 된 대로 런타임에 문자 순서에 따라 달라 지 며, 코드를 실행 하는 시스템의 로캘 설정에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-155">The meaning of a specified range depends on the character ordering at run time, as determined by `Option Compare` and the locale setting of the system the code is running on.</span></span> <span data-ttu-id="8063e-156">`Option Compare Binary`에서 범위 `[A–E]` `A`, `B`, `C`, `D`및 `E`일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-156">With `Option Compare Binary`, the range `[A–E]` matches `A`, `B`, `C`, `D`, and `E`.</span></span> <span data-ttu-id="8063e-157">`Option Compare Text`에서 `[A–E]` `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, `e`일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-157">With `Option Compare Text`, `[A–E]` matches `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, and `e`.</span></span> <span data-ttu-id="8063e-158">악센트가 있는 문자가 정렬 순서에서 악센트가 없는 문자 다음에 정렬 되기 때문에 `Ê` 또는 `ê`와 일치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-158">The range does not match `Ê` or `ê` because accented characters collate after unaccented characters in the sort order.</span></span>  
  
## <a name="digraph-characters"></a><span data-ttu-id="8063e-159">D i g 문자</span><span class="sxs-lookup"><span data-stu-id="8063e-159">Digraph Characters</span></span>  
 <span data-ttu-id="8063e-160">일부 언어에는 두 개의 개별 문자를 나타내는 영문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-160">In some languages, there are alphabetic characters that represent two separate characters.</span></span> <span data-ttu-id="8063e-161">예를 들어 여러 언어는 문자 `æ`를 사용 하 여 `a` 문자를 나타내고 함께 표시 될 때 `e` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-161">For example, several languages use the character `æ` to represent the characters `a` and `e` when they appear together.</span></span> <span data-ttu-id="8063e-162">`Like` 연산자는 단일 d i g 문자 및 두 개의 개별 문자가 동일 하다는 것을 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-162">The `Like` operator recognizes that the single digraph character and the two individual characters are equivalent.</span></span>  
  
 <span data-ttu-id="8063e-163">D i g 문자를 사용 하는 언어가 시스템 로캘 설정에 지정 된 경우 `pattern` 또는 `string`의 단일 d i g 문자가 다른 문자열의 두 문자 시퀀스와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-163">When a language that uses a digraph character is specified in the system locale settings, an occurrence of the single digraph character in either `pattern` or `string` matches the equivalent two-character sequence in the other string.</span></span> <span data-ttu-id="8063e-164">마찬가지로 대괄호 안에 포함 된 `pattern`의 d i g 문자 (목록 또는 범위)는 `string`에서 해당 하는 두 문자 시퀀스와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-164">Similarly, a digraph character in `pattern` enclosed in brackets (by itself, in a list, or in a range) matches the equivalent two-character sequence in `string`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="8063e-165">오버로드</span><span class="sxs-lookup"><span data-stu-id="8063e-165">Overloading</span></span>  
 <span data-ttu-id="8063e-166">`Like` 연산자를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-166">The `Like` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="8063e-167">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-167">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="8063e-168">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8063e-168">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8063e-169">예제</span><span class="sxs-lookup"><span data-stu-id="8063e-169">Example</span></span>  
 <span data-ttu-id="8063e-170">이 예제에서는 `Like` 연산자를 사용 하 여 문자열을 다양 한 패턴과 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-170">This example uses the `Like` operator to compare strings to various patterns.</span></span> <span data-ttu-id="8063e-171">결과는 각 문자열이 패턴을 충족 하는지 여부를 나타내는 `Boolean` 변수로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8063e-171">The results go into a `Boolean` variable indicating whether each string satisfies the pattern.</span></span>  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="8063e-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8063e-172">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [<span data-ttu-id="8063e-173">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="8063e-173">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="8063e-174">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="8063e-174">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="8063e-175">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="8063e-175">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="8063e-176">Option Compare 문</span><span class="sxs-lookup"><span data-stu-id="8063e-176">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="8063e-177">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="8063e-177">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="8063e-178">방법: 패턴에 대해 문자열 비교</span><span class="sxs-lookup"><span data-stu-id="8063e-178">How to: Match a String against a Pattern</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
