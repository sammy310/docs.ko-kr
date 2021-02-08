---
description: '자세히 알아보기: 비교 연산자 (Visual Basic)'
title: 비교 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basic
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: 28eded0cfae54ec83ad9546b801243e4de0e45fc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774111"
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="1eaf0-103">비교 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1eaf0-103">Comparison Operators (Visual Basic)</span></span>

<span data-ttu-id="1eaf0-104">다음은 Visual Basic에 정의 된 비교 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-104">The following are the comparison operators defined in Visual Basic.</span></span>

 <span data-ttu-id="1eaf0-105">`<` 연산자</span><span class="sxs-lookup"><span data-stu-id="1eaf0-105">`<` operator</span></span>

 <span data-ttu-id="1eaf0-106">`<=` 연산자</span><span class="sxs-lookup"><span data-stu-id="1eaf0-106">`<=` operator</span></span>

 <span data-ttu-id="1eaf0-107">`>` 연산자</span><span class="sxs-lookup"><span data-stu-id="1eaf0-107">`>` operator</span></span>

 <span data-ttu-id="1eaf0-108">`>=` 연산자</span><span class="sxs-lookup"><span data-stu-id="1eaf0-108">`>=` operator</span></span>

 <span data-ttu-id="1eaf0-109">`=` 연산자</span><span class="sxs-lookup"><span data-stu-id="1eaf0-109">`=` operator</span></span>

 <span data-ttu-id="1eaf0-110">`<>` 연산자</span><span class="sxs-lookup"><span data-stu-id="1eaf0-110">`<>` operator</span></span>

 [<span data-ttu-id="1eaf0-111">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="1eaf0-111">Is Operator</span></span>](is-operator.md)

 [<span data-ttu-id="1eaf0-112">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="1eaf0-112">IsNot Operator</span></span>](isnot-operator.md)

 [<span data-ttu-id="1eaf0-113">Like 연산자</span><span class="sxs-lookup"><span data-stu-id="1eaf0-113">Like Operator</span></span>](like-operator.md)

 <span data-ttu-id="1eaf0-114">이러한 연산자는 두 식을 비교 하 여 같은지 여부와 그렇지 않은 경우의 차이점을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-114">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="1eaf0-115">`Is`, `IsNot` 및 `Like` 은 별도의 도움말 페이지에 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-115">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="1eaf0-116">관계형 비교 연산자에 대해서는이 페이지에서 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-116">The relational comparison operators are discussed in detail on this page.</span></span>

## <a name="syntax"></a><span data-ttu-id="1eaf0-117">Syntax</span><span class="sxs-lookup"><span data-stu-id="1eaf0-117">Syntax</span></span>
  
```vb
result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="1eaf0-118">부분</span><span class="sxs-lookup"><span data-stu-id="1eaf0-118">Parts</span></span>

 `result`  
 <span data-ttu-id="1eaf0-119">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-119">Required.</span></span> <span data-ttu-id="1eaf0-120">`Boolean`비교 결과를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-120">A `Boolean` value representing the result of the comparison.</span></span>

 <span data-ttu-id="1eaf0-121">`expression1`, `expression2`</span><span class="sxs-lookup"><span data-stu-id="1eaf0-121">`expression1`, `expression2`</span></span>  
 <span data-ttu-id="1eaf0-122">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-122">Required.</span></span> <span data-ttu-id="1eaf0-123">임의의 식입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-123">Any expression.</span></span>

 `comparisonoperator`  
 <span data-ttu-id="1eaf0-124">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-124">Required.</span></span> <span data-ttu-id="1eaf0-125">모든 관계형 비교 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-125">Any relational comparison operator.</span></span>

 <span data-ttu-id="1eaf0-126">`object1`, `object2`</span><span class="sxs-lookup"><span data-stu-id="1eaf0-126">`object1`, `object2`</span></span>  
 <span data-ttu-id="1eaf0-127">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-127">Required.</span></span> <span data-ttu-id="1eaf0-128">참조 개체 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-128">Any reference object names.</span></span>

 `string`  
 <span data-ttu-id="1eaf0-129">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-129">Required.</span></span> <span data-ttu-id="1eaf0-130">임의의 `String` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-130">Any `String` expression.</span></span>

 `pattern`  
 <span data-ttu-id="1eaf0-131">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-131">Required.</span></span> <span data-ttu-id="1eaf0-132">모든 `String` 식 또는 문자 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-132">Any `String` expression or range of characters.</span></span>

## <a name="remarks"></a><span data-ttu-id="1eaf0-133">설명</span><span class="sxs-lookup"><span data-stu-id="1eaf0-133">Remarks</span></span>

 <span data-ttu-id="1eaf0-134">다음 표에는 관계 비교 연산자 목록 및가 인지 여부를 결정 하는 조건이 포함 되어 있습니다 `result` `True` `False` .</span><span class="sxs-lookup"><span data-stu-id="1eaf0-134">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>

|<span data-ttu-id="1eaf0-135">연산자</span><span class="sxs-lookup"><span data-stu-id="1eaf0-135">Operator</span></span>|<span data-ttu-id="1eaf0-136">`True`</span><span class="sxs-lookup"><span data-stu-id="1eaf0-136">`True` if</span></span>|<span data-ttu-id="1eaf0-137">`False`</span><span class="sxs-lookup"><span data-stu-id="1eaf0-137">`False` if</span></span>|
|--------------|---------------|----------------|
|<span data-ttu-id="1eaf0-138">`<` (보다 작음)</span><span class="sxs-lookup"><span data-stu-id="1eaf0-138">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|
|<span data-ttu-id="1eaf0-139">`<=` (작거나 같음)</span><span class="sxs-lookup"><span data-stu-id="1eaf0-139">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|
|<span data-ttu-id="1eaf0-140">`>` (보다 큼)</span><span class="sxs-lookup"><span data-stu-id="1eaf0-140">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|
|<span data-ttu-id="1eaf0-141">`>=` (크거나 같음)</span><span class="sxs-lookup"><span data-stu-id="1eaf0-141">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|
|<span data-ttu-id="1eaf0-142">`=` (같음)</span><span class="sxs-lookup"><span data-stu-id="1eaf0-142">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|
|<span data-ttu-id="1eaf0-143">`<>` (같지 않음)</span><span class="sxs-lookup"><span data-stu-id="1eaf0-143">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|

> [!NOTE]
> <span data-ttu-id="1eaf0-144">[= 연산자](assignment-operator.md) 는 할당 연산자로도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-144">The [= Operator](assignment-operator.md) is also used as an assignment operator.</span></span>

 <span data-ttu-id="1eaf0-145">연산자 `Is` , `IsNot` 연산자 및 연산자에는 `Like` 위의 표에 있는 연산자와 다른 특정 비교 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-145">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>

## <a name="comparing-numbers"></a><span data-ttu-id="1eaf0-146">숫자 비교</span><span class="sxs-lookup"><span data-stu-id="1eaf0-146">Comparing Numbers</span></span>

 <span data-ttu-id="1eaf0-147">형식의 식을 형식 중 하 나와 비교 하는 경우 `Single` `Double` `Single` 식이로 변환 됩니다 `Double` .</span><span class="sxs-lookup"><span data-stu-id="1eaf0-147">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="1eaf0-148">이 동작은 Visual Basic 6에서 발견 된 동작과 반대입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-148">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>

 <span data-ttu-id="1eaf0-149">마찬가지로 형식의 식을 or 형식의 식과 비교할 때 `Decimal` `Single` `Double` `Decimal` 식이 또는로 변환 됩니다 `Single` `Double` .</span><span class="sxs-lookup"><span data-stu-id="1eaf0-149">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="1eaf0-150">식의 경우 `Decimal` 1e-28 보다 작은 모든 소수 자릿수가 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-150">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="1eaf0-151">이러한 소수 자릿수 값이 손실 되 면 두 값이 일치 하지 않는 것으로 간주 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-151">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="1eaf0-152">이러한 이유로 같음 ()을 사용 하 여 `=` 두 개의 부동 소수점 변수를 비교할 때 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-152">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="1eaf0-153">두 숫자 간의 차이에 대 한 절대값은 허용 가능한 작은 허용 오차 보다 작음을 테스트 하는 것이 더 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-153">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>

### <a name="floating-point-imprecision"></a><span data-ttu-id="1eaf0-154">부동 소수점 부정확</span><span class="sxs-lookup"><span data-stu-id="1eaf0-154">Floating-point Imprecision</span></span>

 <span data-ttu-id="1eaf0-155">부동 소수점 숫자를 사용 하는 경우 항상 메모리에 정확한 표현이 없다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-155">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="1eaf0-156">이로 인해 값 비교 및 [Mod 연산자](mod-operator.md)와 같은 특정 작업에서 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-156">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](mod-operator.md).</span></span> <span data-ttu-id="1eaf0-157">자세한 내용은 [데이터 형식 문제 해결](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-157">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

## <a name="comparing-strings"></a><span data-ttu-id="1eaf0-158">문자열 비교</span><span class="sxs-lookup"><span data-stu-id="1eaf0-158">Comparing Strings</span></span>

 <span data-ttu-id="1eaf0-159">문자열을 비교 하는 경우 문자열 식은 설정에 따라 사전순 정렬 순서에 따라 평가 됩니다 `Option Compare` .</span><span class="sxs-lookup"><span data-stu-id="1eaf0-159">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>

 <span data-ttu-id="1eaf0-160">`Option Compare Binary` 문자에 대 한 내부 이진 표현에서 파생 된 정렬 순서에 대 한 문자열 비교를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-160">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="1eaf0-161">정렬 순서는 코드 페이지에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-161">The sort order is determined by the code page.</span></span> <span data-ttu-id="1eaf0-162">다음 예제에서는 일반적인 이진 정렬 순서를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-162">The following example shows a typical binary sort order.</span></span>

 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

 <span data-ttu-id="1eaf0-163">`Option Compare Text` 응용 프로그램 로캘로 결정 되는 대/소문자를 구분 하지 않는 텍스트 정렬 순서에 대 한 문자열 비교를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-163">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="1eaf0-164">`Option Compare Text`앞의 예제에서 문자를 설정 하 고 정렬 하는 경우 다음 텍스트 정렬 순서가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-164">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>

 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`

### <a name="locale-dependence"></a><span data-ttu-id="1eaf0-165">로캘 종속성</span><span class="sxs-lookup"><span data-stu-id="1eaf0-165">Locale Dependence</span></span>

 <span data-ttu-id="1eaf0-166">를 설정 하는 경우 `Option Compare Text` 문자열 비교의 결과는 응용 프로그램이 실행 되 고 있는 로캘에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-166">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="1eaf0-167">두 문자는 한 로캘에서 동일 하 게 비교 될 수 있지만 다른 로캘에서는 동일 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-167">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="1eaf0-168">문자열 비교를 사용 하 여 로그온 시도를 수락할지 여부와 같은 중요 한 결정을 내리는 경우 로캘 민감도에 대 한 경고를 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-168">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="1eaf0-169">로캘을 고려 하 여를 설정 하거나 호출 하는 것이 좋습니다 `Option Compare Binary` <xref:Microsoft.VisualBasic.Strings.StrComp%2A> .</span><span class="sxs-lookup"><span data-stu-id="1eaf0-169">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>

## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="1eaf0-170">관계형 비교 연산자를 사용한 관대 한 형식의 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="1eaf0-170">Typeless Programming with Relational Comparison Operators</span></span>

 <span data-ttu-id="1eaf0-171">에서 식에 관계 비교 연산자를 사용할 `Object` 수 없습니다 `Option Strict On` .</span><span class="sxs-lookup"><span data-stu-id="1eaf0-171">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="1eaf0-172">`Option Strict`가이 `Off` 고 `expression1` 또는 `expression2` 가 `Object` 식인 경우 런타임 형식에 따라 비교 방법이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-172">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="1eaf0-173">다음 표에서는 피연산자의 런타임 형식에 따라 식을 비교 하 고 비교 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-173">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>

|<span data-ttu-id="1eaf0-174">피연산자가</span><span class="sxs-lookup"><span data-stu-id="1eaf0-174">If operands are</span></span>|<span data-ttu-id="1eaf0-175">비교</span><span class="sxs-lookup"><span data-stu-id="1eaf0-175">Comparison is</span></span>|
|---------------------|-------------------|
|<span data-ttu-id="1eaf0-176">양방향 `String`</span><span class="sxs-lookup"><span data-stu-id="1eaf0-176">Both `String`</span></span>|<span data-ttu-id="1eaf0-177">문자열 정렬 특성을 기반으로 하는 정렬 비교</span><span class="sxs-lookup"><span data-stu-id="1eaf0-177">Sort comparison based on string sorting characteristics.</span></span>|
|<span data-ttu-id="1eaf0-178">두 숫자</span><span class="sxs-lookup"><span data-stu-id="1eaf0-178">Both numeric</span></span>|<span data-ttu-id="1eaf0-179">숫자 비교로 변환 된 개체 `Double` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-179">Objects converted to `Double`, numeric comparison.</span></span>|
|<span data-ttu-id="1eaf0-180">숫자 1 개 `String`</span><span class="sxs-lookup"><span data-stu-id="1eaf0-180">One numeric and one `String`</span></span>|<span data-ttu-id="1eaf0-181">는 `String` 로 변환 되 `Double` 고 숫자 비교가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-181">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="1eaf0-182">을 `String` 로 변환할 수 없으면 `Double` <xref:System.InvalidCastException> 이 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-182">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|
|<span data-ttu-id="1eaf0-183">둘 중 하나 또는 둘 다가 아닌 참조 형식입니다. `String`</span><span class="sxs-lookup"><span data-stu-id="1eaf0-183">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="1eaf0-184"><xref:System.InvalidCastException>이 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-184">An <xref:System.InvalidCastException> is thrown.</span></span>|

 <span data-ttu-id="1eaf0-185">숫자 비교 `Nothing` 는 0으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-185">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="1eaf0-186">문자열 비교는 `Nothing` `""` (빈 문자열)로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-186">String comparisons treat `Nothing` as `""` (an empty string).</span></span>

## <a name="overloading"></a><span data-ttu-id="1eaf0-187">오버로딩</span><span class="sxs-lookup"><span data-stu-id="1eaf0-187">Overloading</span></span>

 <span data-ttu-id="1eaf0-188">관계형 비교 연산자 ( `<` .</span><span class="sxs-lookup"><span data-stu-id="1eaf0-188">The relational comparison operators (`<`.</span></span> <span data-ttu-id="1eaf0-189">`<=`,,, `>` `>=` `=` , `<>` )를 *오버 로드할* 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-189">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="1eaf0-190">코드가 이러한 클래스 또는 구조체에서 이러한 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-190">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="1eaf0-191">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-191">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>

 <span data-ttu-id="1eaf0-192">[= 연산자](assignment-operator.md) 는 할당 연산자가 아닌 관계형 비교 연산자로만 오버 로드 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-192">Notice that the [= Operator](assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>

## <a name="example"></a><span data-ttu-id="1eaf0-193">예제</span><span class="sxs-lookup"><span data-stu-id="1eaf0-193">Example</span></span>

 <span data-ttu-id="1eaf0-194">다음 예에서는 식을 비교 하는 데 사용 하는 다양 한 관계형 비교 연산자 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-194">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="1eaf0-195">관계형 비교 연산자 `Boolean` 는 명시 된 식이로 계산 되는지 여부를 나타내는 결과를 반환 `True` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-195">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="1eaf0-196">문자열에 및 연산자를 적용 하는 경우 `>` `<` 문자열의 일반적인 사전순 정렬 순서를 사용 하 여 비교가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-196">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="1eaf0-197">이 순서는 로캘 설정에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-197">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="1eaf0-198">정렬에서 대/소문자를 구분 하는지 여부는 [옵션 비교](../statements/option-compare-statement.md) 설정에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="1eaf0-198">Whether the sort is case-sensitive or not depends on the [Option Compare](../statements/option-compare-statement.md) setting.</span></span>

 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]

 <span data-ttu-id="1eaf0-199">앞의 예제에서 첫 번째 비교는을 반환 하 `False` 고 나머지 비교는를 반환 합니다 `True` .</span><span class="sxs-lookup"><span data-stu-id="1eaf0-199">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1eaf0-200">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1eaf0-200">See also</span></span>

- <xref:System.InvalidCastException>
- [<span data-ttu-id="1eaf0-201">= 연산자</span><span class="sxs-lookup"><span data-stu-id="1eaf0-201">= Operator</span></span>](assignment-operator.md)
- [<span data-ttu-id="1eaf0-202">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="1eaf0-202">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="1eaf0-203">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="1eaf0-203">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="1eaf0-204">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1eaf0-204">Troubleshooting Data Types</span></span>](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="1eaf0-205">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1eaf0-205">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
