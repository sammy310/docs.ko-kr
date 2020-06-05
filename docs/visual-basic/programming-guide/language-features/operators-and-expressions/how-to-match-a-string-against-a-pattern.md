---
title: '방법: 패턴에 대해 문자열 비교'
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- pattern matching
- strings [Visual Basic], comparing
- string comparison [Visual Basic], operators
- Visual Basic code, operators
- pattern matching [Visual Basic], string comparison
- string comparison [Visual Basic]
- Like operator [Visual Basic], pattern matching
- pattern matching, empty strings
- operators [Visual Basic], comparison
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
ms.openlocfilehash: d8a3c363d1a443db4a0b7633e380562af1913aca
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403448"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="47ba1-102">방법: 패턴에 대해 문자열 비교(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47ba1-102">How to: Match a String against a Pattern (Visual Basic)</span></span>

<span data-ttu-id="47ba1-103">[문자열 데이터 형식의](../../../language-reference/data-types/string-data-type.md) 식이 패턴을 충족 하는지 확인 하려는 경우 [Like 연산자](../../../language-reference/operators/like-operator.md)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-103">If you want to find out if an expression of the [String Data Type](../../../language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../language-reference/operators/like-operator.md).</span></span>

<span data-ttu-id="47ba1-104">`Like`두 개의 피연산자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-104">`Like` takes two operands.</span></span> <span data-ttu-id="47ba1-105">왼쪽 피연산자는 문자열 식이고 오른쪽 피연산자는 일치에 사용할 패턴이 포함 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="47ba1-106">`Like``Boolean`문자열 식이 패턴을 충족 하는지 여부를 나타내는 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>

<span data-ttu-id="47ba1-107">문자열 식의 각 문자를 특정 문자, 와일드 카드 문자, 문자 목록 또는 문자 범위에 대해 일치 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="47ba1-108">패턴 문자열의 사양 위치는 문자열 식에서 일치 시킬 문자의 위치에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>

## <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="47ba1-109">문자열 식의 문자를 특정 문자와 일치 시키려면</span><span class="sxs-lookup"><span data-stu-id="47ba1-109">To match a character in the string expression against a specific character</span></span>

<span data-ttu-id="47ba1-110">패턴 문자열에 특정 문자를 직접 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="47ba1-111">특정 특수 문자는 대괄호 ()로 묶어야 합니다 `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="47ba1-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="47ba1-112">자세한 내용은 [Like 연산자](../../../language-reference/operators/like-operator.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47ba1-112">For more information, see [Like Operator](../../../language-reference/operators/like-operator.md).</span></span>

<span data-ttu-id="47ba1-113">다음 예제에서는가 `myString` 단일 문자를 정확 하 게 구성 하는지 테스트 합니다 `H` .</span><span class="sxs-lookup"><span data-stu-id="47ba1-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>

[!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]

## <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="47ba1-114">와일드 카드 문자를 기준으로 문자열 식의 문자를 일치 시키려면</span><span class="sxs-lookup"><span data-stu-id="47ba1-114">To match a character in the string expression against a wildcard character</span></span>

<span data-ttu-id="47ba1-115">`?`패턴 문자열에 물음표 ()를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="47ba1-116">이 위치에 있는 모든 유효한 문자가 성공적으로 일치 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-116">Any valid character in this position makes a successful match.</span></span>

<span data-ttu-id="47ba1-117">다음 예제에서는 `myString` 가 단일 문자 `W` 다음에 정확히 두 개의 문자로 구성 되어 있는지 여부를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>

[!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]

## <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="47ba1-118">문자열 식의 문자를 문자 목록과 일치 시키려면</span><span class="sxs-lookup"><span data-stu-id="47ba1-118">To match a character in the string expression against a list of characters</span></span>

<span data-ttu-id="47ba1-119">패턴 문자열에 대괄호 ()를 배치 하 `[ ]` 고 대괄호 안에 문자 목록을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="47ba1-120">문자를 쉼표 또는 다른 구분 기호로 구분 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="47ba1-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="47ba1-121">목록의 모든 단일 문자가 성공적으로 일치 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-121">Any single character in the list makes a successful match.</span></span>

<span data-ttu-id="47ba1-122">다음 예제에서는가 `myString` 유효한 모든 문자로 구성 되어 있는지 여부를 테스트 합니다 `A` `C` `E` .</span><span class="sxs-lookup"><span data-stu-id="47ba1-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>

[!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]

<span data-ttu-id="47ba1-123">이 일치 항목은 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-123">Note that this match is case-sensitive.</span></span>

## <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="47ba1-124">문자열 식에서 문자 범위에 대해 문자를 일치 시키려면</span><span class="sxs-lookup"><span data-stu-id="47ba1-124">To match a character in the string expression against a range of characters</span></span>

<span data-ttu-id="47ba1-125">패턴 문자열에 대괄호 ()를 배치 하 `[ ]` 고, 대괄호 안에는 범위에서 가장 낮거나 가장 높은 문자를 하이픈 ()으로 구분 하 여 입력 `–` 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="47ba1-126">범위 내의 모든 단일 문자가 성공적으로 일치 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-126">Any single character within the range makes a successful match.</span></span>

<span data-ttu-id="47ba1-127">다음 예제에서는가 문자로 구성 되어 있는지 여부를 테스트 하 고,,,, `myString` `num` 또는 문자 중 하나만 입력 `i` `j` `k` `l` `m` `n` 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>

[!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]

<span data-ttu-id="47ba1-128">이 일치 항목은 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-128">Note that this match is case-sensitive.</span></span>

## <a name="matching-empty-strings"></a><span data-ttu-id="47ba1-129">빈 문자열 일치</span><span class="sxs-lookup"><span data-stu-id="47ba1-129">Matching Empty Strings</span></span>

<span data-ttu-id="47ba1-130">`Like`시퀀스를 `[]` 길이가 0 인 문자열 ()로 처리 합니다 `""` .</span><span class="sxs-lookup"><span data-stu-id="47ba1-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="47ba1-131">를 사용 하 여 `[]` 전체 문자열 식이 비어 있는지 여부를 테스트할 수 있지만 문자열 식의 특정 위치가 비어 있는지 테스트 하는 데 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="47ba1-132">빈 위치가 테스트 해야 하는 옵션 중 하나인 경우 두 번 이상 사용할 수 있습니다 `Like` .</span><span class="sxs-lookup"><span data-stu-id="47ba1-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>

### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="47ba1-133">문자열 식의 문자를 문자 목록에 대해 일치 하거나 문자를 검색 하지 않으려면</span><span class="sxs-lookup"><span data-stu-id="47ba1-133">To match a character in the string expression against a list of characters or no character</span></span>

1. <span data-ttu-id="47ba1-134">`Like`동일한 문자열 식에서 연산자를 두 번 호출 하 고, [or 연산자](../../../language-reference/operators/or-operator.md) 또는 [OrElse 연산자](../../../language-reference/operators/orelse-operator.md)중 하나를 사용 하 여 두 호출을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../language-reference/operators/or-operator.md) or the [OrElse Operator](../../../language-reference/operators/orelse-operator.md).</span></span>

2. <span data-ttu-id="47ba1-135">첫 번째 절에 대 한 패턴 문자열에서 `Like` 대괄호 ()로 묶인 문자 목록을 포함 `[ ]` 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>

3. <span data-ttu-id="47ba1-136">두 번째 절의 패턴 문자열에서 해당 `Like` 위치에 문자를 넣지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>

    <span data-ttu-id="47ba1-137">다음 예에서는 `phoneNum` 정확히 3 자리 숫자에 대해 7 자리 전화 번호를 테스트 한 후 공백, 하이픈 ( `–` ), 마침표 ( `.` ) 또는 문자 없이 문자를 정확히 4 자리 숫자로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ba1-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>

    [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]

## <a name="see-also"></a><span data-ttu-id="47ba1-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47ba1-138">See also</span></span>

- [<span data-ttu-id="47ba1-139">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="47ba1-139">Comparison Operators</span></span>](../../../language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="47ba1-140">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="47ba1-140">Operators and Expressions</span></span>](index.md)
- [<span data-ttu-id="47ba1-141">Like 연산자</span><span class="sxs-lookup"><span data-stu-id="47ba1-141">Like Operator</span></span>](../../../language-reference/operators/like-operator.md)
- [<span data-ttu-id="47ba1-142">문자열 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="47ba1-142">String Data Type</span></span>](../../../language-reference/data-types/string-data-type.md)
