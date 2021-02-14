---
description: '자세한 정보: 데이터 형식 문제 해결 (Visual Basic)'
title: 데이터 형식 문제 해결
ms.date: 07/20/2015
helpviewer_keywords:
- Char data type [Visual Basic], converting
- Decimal data type [Visual Basic], conversions
- data types [Visual Basic], troubleshooting
- literals [Visual Basic], default types
- type characters [Visual Basic], literal
- Mod operator [Visual Basic], in floating-point operations
- troubleshooting Visual Basic, data types
- troubleshooting data types [Visual Basic]
- floating-point numbers [Visual Basic], precision
- Boolean data type [Visual Basic], converting
- literal types [Visual Basic]
- literal type characters [Visual Basic]
- floating-point numbers [Visual Basic], imprecision
- String data type [Visual Basic], converting
- floating-point numbers [Visual Basic], comparison
- floating-point numbers
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
ms.openlocfilehash: 417a71e88dcd0bfb0c6582ee6304a64871640255
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100463847"
---
# <a name="troubleshooting-data-types-visual-basic"></a><span data-ttu-id="8bbe0-103">데이터 형식 문제 해결(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8bbe0-103">Troubleshooting Data Types (Visual Basic)</span></span>

<span data-ttu-id="8bbe0-104">이 페이지에는 내장 데이터 형식에 대 한 작업을 수행할 때 발생할 수 있는 몇 가지 일반적인 문제가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-104">This page lists some common problems that can occur when you perform operations on intrinsic data types.</span></span>

## <a name="floating-point-expressions-do-not-compare-as-equal"></a><span data-ttu-id="8bbe0-105">Floating-Point 식이 동일 하 게 비교 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-105">Floating-Point Expressions Do Not Compare as Equal</span></span>

<span data-ttu-id="8bbe0-106">부동 소수점 숫자 ([단일 데이터 형식](../../../language-reference/data-types/single-data-type.md) 및 [Double 데이터 형식](../../../language-reference/data-types/double-data-type.md))를 사용 하는 경우 이진 분수로 저장 된다는 점에 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-106">When you work with floating-point numbers ([Single Data Type](../../../language-reference/data-types/single-data-type.md) and [Double Data Type](../../../language-reference/data-types/double-data-type.md)), remember that they are stored as binary fractions.</span></span> <span data-ttu-id="8bbe0-107">즉, 이진 분수가 아닌 수량을 정확 하 게 표현할 수 없습니다 (k 및 n은 정수). 여기서 k 및 n은 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-107">This means they cannot hold an exact representation of any quantity that is not a binary fraction (of the form k / (2 ^ n) where k and n are integers).</span></span> <span data-ttu-id="8bbe0-108">예를 들어 0.5 (= 1/2) 및 0.3125 (= 5/16)는 정확한 값으로 보유할 수 있지만 0.2 (= 1/5) 및 0.3 (= 3/10)만 근사치 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-108">For example, 0.5 (= 1/2) and 0.3125 (= 5/16) can be held as precise values, whereas 0.2 (= 1/5) and 0.3 (= 3/10) can be only approximations.</span></span>

<span data-ttu-id="8bbe0-109">이 부정확 인해 부동 소수점 값에 대해 작업을 수행 하는 경우 정확한 결과를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-109">Because of this imprecision, you cannot rely on exact results when you operate on floating-point values.</span></span> <span data-ttu-id="8bbe0-110">특히 이론적으로 동일한 두 값의 표현은 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-110">In particular, two values that are theoretically equal might have slightly different representations.</span></span>

| <span data-ttu-id="8bbe0-111">부동 소수점 수량을 비교 하려면</span><span class="sxs-lookup"><span data-stu-id="8bbe0-111">To compare floating-point quantities</span></span> |
|---|
|<span data-ttu-id="8bbe0-112">1. <xref:System.Math.Abs%2A> <xref:System.Math> 네임 스페이스에 있는 클래스의 메서드를 사용 하 여 해당 차이의 절대값을 계산 합니다. <xref:System></span><span class="sxs-lookup"><span data-stu-id="8bbe0-112">1.  Calculate the absolute value of their difference by using the <xref:System.Math.Abs%2A> method of the <xref:System.Math> class in the <xref:System> namespace.</span></span><br /><span data-ttu-id="8bbe0-113">2. 허용 되는 최대 차이를 결정 합니다. 즉, 차이가 더 크지 않은 경우 두 수량이 동일한 것으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-113">2.  Determine an acceptable maximum difference, such that you can consider the two quantities to be equal for practical purposes if their difference is no larger.</span></span><br /><span data-ttu-id="8bbe0-114">3. 차이의 절대값을 허용 가능한 차이와 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-114">3.  Compare the absolute value of the difference to the acceptable difference.</span></span>|

<span data-ttu-id="8bbe0-115">다음 예에서는 두 값의 잘못 된 비교와 정확한 비교를 모두 보여 줍니다 `Double` .</span><span class="sxs-lookup"><span data-stu-id="8bbe0-115">The following example demonstrates both incorrect and correct comparison of two `Double` values.</span></span>

[!code-vb[VbVbalrDataTypes#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#10)]

<span data-ttu-id="8bbe0-116">이전 예제에서는 <xref:System.Double.ToString%2A> <xref:System.Double> 키워드에서 사용 하는 것 보다 더 높은 정밀도를 지정할 수 있도록 구조체의 메서드를 사용 합니다 `CStr` .</span><span class="sxs-lookup"><span data-stu-id="8bbe0-116">The previous example uses the <xref:System.Double.ToString%2A> method of the <xref:System.Double> structure so that it can specify better  precision than the `CStr` keyword uses.</span></span> <span data-ttu-id="8bbe0-117">기본값은 15 자리 이지만 "G17" 형식은 17 자리로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-117">The default is 15 digits, but the "G17" format extends it to 17 digits.</span></span>

## <a name="mod-operator-does-not-return-accurate-result"></a><span data-ttu-id="8bbe0-118">Mod 연산자가 정확한 결과를 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-118">Mod Operator Does Not Return Accurate Result</span></span>

<span data-ttu-id="8bbe0-119">부동 소수점 저장소의 부정확 때문에 피연산자 중 하나 이상이 부동 소수점 이면 [Mod 연산자](../../../language-reference/operators/mod-operator.md) 는 예기치 않은 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-119">Because of the imprecision of floating-point storage, the [Mod Operator](../../../language-reference/operators/mod-operator.md) can return an unexpected result when at least one of the operands is floating-point.</span></span>

<span data-ttu-id="8bbe0-120">[Decimal 데이터 형식은](../../../language-reference/data-types/decimal-data-type.md) 부동 소수점 표현을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-120">The [Decimal Data Type](../../../language-reference/data-types/decimal-data-type.md) does not use floating-point representation.</span></span> <span data-ttu-id="8bbe0-121">및에서 부정확 한 되는 많은 `Single` 숫자 `Double` `Decimal` (예: 0.2 및 0.3)가 정확 하 게 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-121">Many numbers that are inexact in `Single` and `Double` are exact in `Decimal` (for example 0.2 and 0.3).</span></span> <span data-ttu-id="8bbe0-122">산술은 부동 소수점 보다 속도가 느리므로 `Decimal` 더 나은 정밀도를 얻기 위해 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-122">Although arithmetic is slower in `Decimal` than in floating-point, it might be worth the performance decrease to achieve better precision.</span></span>

|<span data-ttu-id="8bbe0-123">부동 소수점 수량의 정수 나머지를 찾으려면</span><span class="sxs-lookup"><span data-stu-id="8bbe0-123">To find the integer remainder of floating-point quantities</span></span>|
|---|
|<span data-ttu-id="8bbe0-124">1. 변수 `Decimal` 를로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-124">1.  Declare variables as `Decimal`.</span></span><br /><span data-ttu-id="8bbe0-125">2. 리터럴 형식 문자를 사용 `D` 하 여 `Decimal` 데이터 형식에 대 한 값이 너무 크면 리터럴을 강제로 적용 합니다. `Long`</span><span class="sxs-lookup"><span data-stu-id="8bbe0-125">2.  Use the literal type character `D` to force literals to `Decimal`, in case their values are too large for the `Long` data type.</span></span>|

<span data-ttu-id="8bbe0-126">다음 예제에서는 부동 소수점 피연산자의 잠재적 부정확을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-126">The following example demonstrates the potential imprecision of floating-point operands.</span></span>

[!code-vb[VbVbalrDataTypes#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#11)]

<span data-ttu-id="8bbe0-127">이전 예제에서는 <xref:System.Double.ToString%2A> <xref:System.Double> 키워드에서 사용 하는 것 보다 더 높은 정밀도를 지정할 수 있도록 구조체의 메서드를 사용 합니다 `CStr` .</span><span class="sxs-lookup"><span data-stu-id="8bbe0-127">The previous example uses the <xref:System.Double.ToString%2A> method of the <xref:System.Double> structure so that it can specify better precision than the `CStr` keyword uses.</span></span> <span data-ttu-id="8bbe0-128">기본값은 15 자리 이지만 "G17" 형식은 17 자리로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-128">The default is 15 digits, but the "G17" format extends it to 17 digits.</span></span>

<span data-ttu-id="8bbe0-129">가 이기 때문에 `zeroPointTwo` `Double` 0.2의 값은 저장 된 값이 0.20000000000000001 인 무한 반복 이진 분수입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-129">Because `zeroPointTwo` is `Double`, its value for 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="8bbe0-130">이 수량으로 2.0을 나누면 0.19999999999999991의 나머지가 9.9999999999999995 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-130">Dividing 2.0 by this quantity yields 9.9999999999999995 with a remainder of 0.19999999999999991.</span></span>

<span data-ttu-id="8bbe0-131">에 대 한 식에서 `decimalRemainder` 리터럴 형식 문자는 `D` 두 피연산자를 모두로 강제 적용 `Decimal` 하며, 0.2에는 정확한 표현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-131">In the expression for `decimalRemainder`, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span> <span data-ttu-id="8bbe0-132">따라서 `Mod` 연산자는 예상 되는 나머지가 0.0을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-132">Therefore the `Mod` operator yields the expected remainder of 0.0.</span></span>

<span data-ttu-id="8bbe0-133">을로 선언 하는 것 만으로는 충분 하지 않습니다 `decimalRemainder` `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="8bbe0-133">Note that it is not sufficient to declare `decimalRemainder` as `Decimal`.</span></span> <span data-ttu-id="8bbe0-134">또한 리터럴을에 강제로 적용 `Decimal` 하거나, 기본적으로를 사용 `Double` 하며와 `decimalRemainder` 동일한 부정확 한 값을 받습니다 `doubleRemainder` .</span><span class="sxs-lookup"><span data-stu-id="8bbe0-134">You must also force the literals to `Decimal`, or they use `Double` by default and `decimalRemainder` receives the same inaccurate value as `doubleRemainder`.</span></span>

## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a><span data-ttu-id="8bbe0-135">부울 형식이 숫자 형식으로 정확 하 게 변환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-135">Boolean Type Does Not Convert to Numeric Type Accurately</span></span>

<span data-ttu-id="8bbe0-136">[부울 데이터 형식](../../../language-reference/data-types/boolean-data-type.md) 값은 숫자로 저장 되지 않으며 저장 된 값은 숫자와 동일 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-136">[Boolean Data Type](../../../language-reference/data-types/boolean-data-type.md) values are not stored as numbers, and the stored values are not intended to be equivalent to numbers.</span></span> <span data-ttu-id="8bbe0-137">이전 버전과의 호환성을 위해 Visual Basic는[](../../../language-reference/functions/ctype-function.md) `CBool` `CInt` `Boolean` 및 숫자 형식 간에 변환 하는 변환 키워드 (CType 함수,, 등)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-137">For compatibility with earlier versions, Visual Basic provides conversion keywords ([CType Function](../../../language-reference/functions/ctype-function.md), `CBool`, `CInt`, and so on) to convert between `Boolean` and numeric types.</span></span> <span data-ttu-id="8bbe0-138">그러나 다른 언어에서는 .NET Framework 메서드와 같이 이러한 변환을 다르게 수행 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-138">However, other languages sometimes perform these conversions differently, as do the .NET Framework methods.</span></span>

<span data-ttu-id="8bbe0-139">및에 대해 동일한 숫자 값을 사용 하는 코드를 작성 하면 안 됩니다 `True` `False` .</span><span class="sxs-lookup"><span data-stu-id="8bbe0-139">You should never write code that relies on equivalent numeric values for `True` and `False`.</span></span> <span data-ttu-id="8bbe0-140">가능 하면 `Boolean` 변수의 사용을 디자인 된 논리 값으로 제한 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-140">Whenever possible, you should restrict usage of `Boolean` variables to the logical values for which they are designed.</span></span> <span data-ttu-id="8bbe0-141">및 숫자 값을 혼합 해야 하는 경우에는 `Boolean` 선택한 변환 방법을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-141">If you must mix `Boolean` and numeric values, make sure that you understand the conversion method that you select.</span></span>

### <a name="conversion-in-visual-basic"></a><span data-ttu-id="8bbe0-142">Visual Basic 변환</span><span class="sxs-lookup"><span data-stu-id="8bbe0-142">Conversion in Visual Basic</span></span>

<span data-ttu-id="8bbe0-143">또는 변환 키워드를 사용 하 여 `CType` `CBool` 숫자 데이터 형식을로 변환 하는 경우 `Boolean` 0은이 되 `False` 고 다른 모든 값은가 됩니다 `True` .</span><span class="sxs-lookup"><span data-stu-id="8bbe0-143">When you use the `CType` or `CBool` conversion keywords to convert numeric data types to `Boolean`, 0 becomes `False` and all other values become `True`.</span></span> <span data-ttu-id="8bbe0-144">`Boolean`변환 키워드를 사용 하 여 값을 숫자 형식으로 변환 하는 경우는 `False` 0이 되 고 `True` 가-1이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-144">When you convert `Boolean` values to numeric types by using the conversion keywords, `False` becomes 0 and `True` becomes -1.</span></span>

### <a name="conversion-in-the-framework"></a><span data-ttu-id="8bbe0-145">프레임 워크의 변환</span><span class="sxs-lookup"><span data-stu-id="8bbe0-145">Conversion in the Framework</span></span>

<span data-ttu-id="8bbe0-146"><xref:System.Convert.ToInt32%2A> <xref:System.Convert> 네임 스페이스에 있는 클래스의 메서드는 <xref:System> `True` 를 + 1로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-146">The <xref:System.Convert.ToInt32%2A> method of the <xref:System.Convert> class in the <xref:System> namespace converts `True` to +1.</span></span>

<span data-ttu-id="8bbe0-147">값을 숫자 데이터 형식으로 변환 해야 하는 경우 `Boolean` 사용 하는 변환 방법에 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-147">If you must convert a `Boolean` value to a numeric data type, be careful about which conversion method you use.</span></span>

## <a name="character-literal-generates-compiler-error"></a><span data-ttu-id="8bbe0-148">문자 리터럴이 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-148">Character Literal Generates Compiler Error</span></span>

<span data-ttu-id="8bbe0-149">형식 문자가 없으면 Visual Basic는 리터럴에 대 한 기본 데이터 형식을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-149">In the absence of any type characters, Visual Basic assumes default data types for literals.</span></span> <span data-ttu-id="8bbe0-150">문자 리터럴의 기본 형식은 따옴표 ()로 묶여 `" "` `String` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-150">The default type for a character literal — enclosed in quotation marks (`" "`) — is `String`.</span></span>

<span data-ttu-id="8bbe0-151">`String`데이터 형식이 [Char 데이터 형식](../../../language-reference/data-types/char-data-type.md)으로 확장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-151">The `String` data type does not widen to the [Char Data Type](../../../language-reference/data-types/char-data-type.md).</span></span> <span data-ttu-id="8bbe0-152">즉, 변수에 리터럴을 할당 하려는 경우 `Char` 축소 변환을 수행 하거나 리터럴을 형식으로 강제 적용 해야 합니다 `Char` .</span><span class="sxs-lookup"><span data-stu-id="8bbe0-152">This means that if you want to assign a literal to a `Char` variable, you must either make a narrowing conversion or force the literal to the `Char` type.</span></span>

|<span data-ttu-id="8bbe0-153">변수 또는 상수에 할당할 Char 리터럴을 만들려면</span><span class="sxs-lookup"><span data-stu-id="8bbe0-153">To create a Char literal to assign to a variable or constant</span></span>|
|---|
|<span data-ttu-id="8bbe0-154">1. 변수 또는 상수 `Char` 를로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-154">1.  Declare the variable or constant as `Char`.</span></span><br /><span data-ttu-id="8bbe0-155">2. 문자 값을 따옴표 ()로 묶습니다. `" "`</span><span class="sxs-lookup"><span data-stu-id="8bbe0-155">2.  Enclose the character value in quotation marks (`" "`).</span></span><br /><span data-ttu-id="8bbe0-156">3. 리터럴 형식 문자를 사용 하 여 닫는 큰따옴표를 따라 `C` 리터럴을 강제로 적용 `Char` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-156">3.  Follow the closing double quotation mark with the literal type character `C` to force the literal to `Char`.</span></span> <span data-ttu-id="8bbe0-157">이는 형식 검사 스위치 ([Option Strict 문](../../../language-reference/statements/option-strict-statement.md))가이 `On` 고 어떤 경우에도 적합 한 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-157">This is necessary if the type checking switch ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) is `On`, and it is desirable in any case.</span></span>|

<span data-ttu-id="8bbe0-158">다음 예에서는 변수에 대 한 실패 및 성공한 리터럴의 할당을 모두 보여 줍니다 `Char` .</span><span class="sxs-lookup"><span data-stu-id="8bbe0-158">The following example demonstrates both unsuccessful and successful assignments of a literal to a `Char` variable.</span></span>

[!code-vb[VbVbalrDataTypes#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#12)]

<span data-ttu-id="8bbe0-159">런타임에 실패할 수 있으므로 축소 변환을 사용할 경우 항상 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-159">There is always a risk in using narrowing conversions, because they can fail at run time.</span></span> <span data-ttu-id="8bbe0-160">예를 들어 값에 둘 `String` `Char` `String` 이상의 문자가 포함 되어 있으면에서로의 변환이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-160">For example, a conversion from `String` to `Char` can fail if the `String` value contains more than one character.</span></span> <span data-ttu-id="8bbe0-161">따라서 형식 문자를 사용 하는 것이 더 효율적입니다 `C` .</span><span class="sxs-lookup"><span data-stu-id="8bbe0-161">Therefore, it is better programming to use the `C` type character.</span></span>

## <a name="string-conversion-fails-at-run-time"></a><span data-ttu-id="8bbe0-162">런타임에 문자열 변환이 실패 함</span><span class="sxs-lookup"><span data-stu-id="8bbe0-162">String Conversion Fails at Run Time</span></span>

<span data-ttu-id="8bbe0-163">[문자열 데이터 형식은](../../../language-reference/data-types/string-data-type.md) 매우 적은 확대 변환에 참여 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-163">The [String Data Type](../../../language-reference/data-types/string-data-type.md) participates in very few widening conversions.</span></span> <span data-ttu-id="8bbe0-164">`String` 및만 확대 하 고 `Object` , 및 `Char` `Char()` ( `Char` 배열)만 확대 `String` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-164">`String` widens only to itself and `Object`, and only `Char` and `Char()` (a `Char` array) widen to `String`.</span></span> <span data-ttu-id="8bbe0-165">이는 `String` 변수와 상수에 다른 데이터 형식에 포함 될 수 없는 값이 포함 될 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-165">This is because `String` variables and constants can contain values that other data types cannot contain.</span></span>

<span data-ttu-id="8bbe0-166">형식 검사 스위치 ([Option Strict 문](../../../language-reference/statements/option-strict-statement.md))가 인 경우 `On` 컴파일러는 모든 암시적 축소 변환을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-166">When the type checking switch ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) is `On`, the compiler disallows all implicit narrowing conversions.</span></span> <span data-ttu-id="8bbe0-167">여기에는와 관련 된 내용이 포함 됩니다 `String` .</span><span class="sxs-lookup"><span data-stu-id="8bbe0-167">This includes those involving `String`.</span></span> <span data-ttu-id="8bbe0-168">코드에서 및 CType 함수와 같은 변환 키워드를 계속 사용할 수 있습니다 `CStr` .이 [함수](../../../language-reference/functions/ctype-function.md)는 .NET Framework를 전달 하 여 변환을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-168">Your code can still use conversion keywords such as `CStr` and [CType Function](../../../language-reference/functions/ctype-function.md), which direct the .NET Framework to attempt the conversion.</span></span>

> [!NOTE]
> <span data-ttu-id="8bbe0-169">컬렉션의 요소에서 루프 제어 변수로의 변환에 대 한 축소 변환 오류는 무시 됩니다 `For Each…Next` .</span><span class="sxs-lookup"><span data-stu-id="8bbe0-169">The narrowing-conversion error is suppressed for conversions from the elements in a `For Each…Next` collection to the loop control variable.</span></span> <span data-ttu-id="8bbe0-170">자세한 내용 및 예제는 각 항목에 대 한 "축소 변환" 섹션을 참조 하세요. [ 다음 문](../../../language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8bbe0-170">For more information and examples, see the "Narrowing Conversions" section in [For Each...Next Statement](../../../language-reference/statements/for-each-next-statement.md).</span></span>

### <a name="narrowing-conversion-protection"></a><span data-ttu-id="8bbe0-171">축소 변환 보호</span><span class="sxs-lookup"><span data-stu-id="8bbe0-171">Narrowing Conversion Protection</span></span>

<span data-ttu-id="8bbe0-172">축소 변환의 단점은 런타임에 실패할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-172">The disadvantage of narrowing conversions is that they can fail at run time.</span></span> <span data-ttu-id="8bbe0-173">예를 `String` 들어 변수가 "True" 또는 "False" 이외의 값을 포함 하는 경우로 변환할 수 없습니다 `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="8bbe0-173">For example, if a `String` variable contains anything other than "True" or "False," it cannot be converted to `Boolean`.</span></span> <span data-ttu-id="8bbe0-174">문장 부호 문자를 포함 하는 경우 숫자 형식으로 변환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-174">If it contains punctuation characters, conversion to any numeric type fails.</span></span> <span data-ttu-id="8bbe0-175">`String`변수에 항상 대상 형식이 수락할 수 있는 값이 포함 되어 있다는 것을 알고 있지 않으면 변환을 시도 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-175">Unless you know that your `String` variable always holds values that the destination type can accept, you should not try a conversion.</span></span>

<span data-ttu-id="8bbe0-176">에서 다른 데이터 형식으로 변환 해야 하는 경우 `String` 가장 안전한 절차는 [Try ... Catch ... Finally 문](../../../language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8bbe0-176">If you must convert from `String` to another data type, the safest procedure is to enclose the attempted conversion in the [Try...Catch...Finally Statement](../../../language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="8bbe0-177">이렇게 하면 런타임 오류를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-177">This lets you deal with a run-time failure.</span></span>

### <a name="character-arrays"></a><span data-ttu-id="8bbe0-178">문자 배열</span><span class="sxs-lookup"><span data-stu-id="8bbe0-178">Character Arrays</span></span>

<span data-ttu-id="8bbe0-179">단일 `Char` 및 `Char` 요소 배열이 모두로 확대 `String` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-179">A single `Char` and an array of `Char` elements both widen to `String`.</span></span> <span data-ttu-id="8bbe0-180">그러나 `String` 는로 확장 되지 않습니다 `Char()` .</span><span class="sxs-lookup"><span data-stu-id="8bbe0-180">However, `String` does not widen to `Char()`.</span></span> <span data-ttu-id="8bbe0-181">값을 배열로 변환 하려면 `String` `Char` <xref:System.String.ToCharArray%2A> 클래스의 메서드를 사용할 수 있습니다 <xref:System.String?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="8bbe0-181">To convert a `String` value to a `Char` array, you can use the <xref:System.String.ToCharArray%2A> method of the <xref:System.String?displayProperty=nameWithType> class.</span></span>

### <a name="meaningless-values"></a><span data-ttu-id="8bbe0-182">의미 없는 값</span><span class="sxs-lookup"><span data-stu-id="8bbe0-182">Meaningless Values</span></span>

<span data-ttu-id="8bbe0-183">일반적으로 `String` 값은 다른 데이터 형식에서 의미가 없으며 변환은 매우 인공이 고 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-183">In general, `String` values are not meaningful in other data types, and conversion is highly artificial and dangerous.</span></span> <span data-ttu-id="8bbe0-184">가능 하면 `String` 변수의 사용을 디자인 된 문자 시퀀스로 제한 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-184">Whenever possible, you should restrict usage of `String` variables to the character sequences for which they are designed.</span></span> <span data-ttu-id="8bbe0-185">다른 형식의 동일한 값에 의존 하는 코드를 작성 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbe0-185">You should never write code that relies on equivalent values in other types.</span></span>

## <a name="see-also"></a><span data-ttu-id="8bbe0-186">추가 정보</span><span class="sxs-lookup"><span data-stu-id="8bbe0-186">See also</span></span>

- [<span data-ttu-id="8bbe0-187">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8bbe0-187">Data Types</span></span>](index.md)
- [<span data-ttu-id="8bbe0-188">형식 문자</span><span class="sxs-lookup"><span data-stu-id="8bbe0-188">Type Characters</span></span>](type-characters.md)
- [<span data-ttu-id="8bbe0-189">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="8bbe0-189">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="8bbe0-190">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="8bbe0-190">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="8bbe0-191">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8bbe0-191">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="8bbe0-192">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="8bbe0-192">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="8bbe0-193">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="8bbe0-193">Efficient Use of Data Types</span></span>](efficient-use-of-data-types.md)
