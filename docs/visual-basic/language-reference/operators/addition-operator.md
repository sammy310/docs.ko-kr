---
title: + 연산자 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
ms.openlocfilehash: ab18a7137a31ed8e616f465e7d617305c96d7b10
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943018"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="ddecd-102">+ 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ddecd-102">+ Operator (Visual Basic)</span></span>
<span data-ttu-id="ddecd-103">숫자 식의 양수 값을 두 개 더 추가 하거나 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-103">Adds two numbers or returns the positive value of a numeric expression.</span></span> <span data-ttu-id="ddecd-104">를 사용 하 여 두 문자열 식을 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-104">Can also be used to concatenate two string expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddecd-105">구문</span><span class="sxs-lookup"><span data-stu-id="ddecd-105">Syntax</span></span>  
  
```vb
expression1 + expression2  
- or -  
+ expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="ddecd-106">요소</span><span class="sxs-lookup"><span data-stu-id="ddecd-106">Parts</span></span>  
  
|<span data-ttu-id="ddecd-107">용어</span><span class="sxs-lookup"><span data-stu-id="ddecd-107">Term</span></span>|<span data-ttu-id="ddecd-108">정의</span><span class="sxs-lookup"><span data-stu-id="ddecd-108">Definition</span></span>|  
|---|---|  
|`expression1`|<span data-ttu-id="ddecd-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="ddecd-109">Required.</span></span> <span data-ttu-id="ddecd-110">임의의 숫자 또는 문자열 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-110">Any numeric or string expression.</span></span>|  
|`expression2`|<span data-ttu-id="ddecd-111">`+` 연산자가 음수 값을 계산 하지 않는 경우 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-111">Required unless the `+` operator is calculating a negative value.</span></span> <span data-ttu-id="ddecd-112">임의의 숫자 또는 문자열 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-112">Any numeric or string expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="ddecd-113">결과</span><span class="sxs-lookup"><span data-stu-id="ddecd-113">Result</span></span>  
 <span data-ttu-id="ddecd-114">`expression1` 과`expression2` 가 모두 숫자인 경우 결과는 산술 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-114">If `expression1` and `expression2` are both numeric, the result is their arithmetic sum.</span></span>  
  
 <span data-ttu-id="ddecd-115">가 없으면 연산자는 변경 되지 않은 식 값의 단항 id 연산자입니다. `expression2` `+`</span><span class="sxs-lookup"><span data-stu-id="ddecd-115">If `expression2` is absent, the `+` operator is the *unary* identity operator for the unchanged value of an expression.</span></span> <span data-ttu-id="ddecd-116">이 의미에서 작업은의 `expression1`부호를 유지 하는 것으로 구성 되므로가 음수인 경우 `expression1` 결과가 음수입니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-116">In this sense, the operation consists of retaining the sign of `expression1`, so the result is negative if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="ddecd-117">`expression1` 및`expression2` 가 둘 다 문자열이 면 결과는 값을 연결 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-117">If `expression1` and `expression2` are both strings, the result is the concatenation of their values.</span></span>  
  
 <span data-ttu-id="ddecd-118">`expression1` 및`expression2` 가 혼합 형식이 면 수행 되는 작업은 형식, 해당 내용 및 [Option Strict 문의](../../../visual-basic/language-reference/statements/option-strict-statement.md)설정에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-118">If `expression1` and `expression2` are of mixed types, the action taken depends on their types, their contents, and the setting of the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span> <span data-ttu-id="ddecd-119">자세한 내용은 "주의"의 표를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ddecd-119">For more information, see the tables in "Remarks."</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="ddecd-120">지원 형식</span><span class="sxs-lookup"><span data-stu-id="ddecd-120">Supported Types</span></span>  
 <span data-ttu-id="ddecd-121">부호 없는 형식 및 부동 소수점 형식 및 `Decimal`및 `String`를 포함 하는 모든 숫자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-121">All numeric types, including the unsigned and floating-point types and `Decimal`, and `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddecd-122">설명</span><span class="sxs-lookup"><span data-stu-id="ddecd-122">Remarks</span></span>  
 <span data-ttu-id="ddecd-123">일반적으로는 `+` 가능한 경우 산술 덧셈을 수행 하 고 두 식이 모두 문자열인 경우에만 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-123">In general, `+` performs arithmetic addition when possible, and concatenates only when both expressions are strings.</span></span>  
  
 <span data-ttu-id="ddecd-124">두 식이 `Object`모두 이면 Visual Basic는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-124">If neither expression is an `Object`, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="ddecd-125">식의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ddecd-125">Data types of expressions</span></span>|<span data-ttu-id="ddecd-126">컴파일러 작업</span><span class="sxs-lookup"><span data-stu-id="ddecd-126">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="ddecd-127">두 식은 모두 숫자 데이터 형식 (`SByte` `Short`, `Byte`,, `UShort` `Integer` `UInteger` ,,`Double`,,,, 또는)입니다. `Long` `ULong` `Decimal` `Single`</span><span class="sxs-lookup"><span data-stu-id="ddecd-127">Both expressions are numeric data types (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`)</span></span>|<span data-ttu-id="ddecd-128">추가.</span><span class="sxs-lookup"><span data-stu-id="ddecd-128">Add.</span></span> <span data-ttu-id="ddecd-129">결과 데이터 형식은 및 `expression1` `expression2`의 데이터 형식에 적합 한 숫자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-129">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="ddecd-130">[연산자 결과의 데이터 형식](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)에서 "정수 산술 연산" 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ddecd-130">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="ddecd-131">두 식이 모두 형식입니다.`String`</span><span class="sxs-lookup"><span data-stu-id="ddecd-131">Both expressions are of type `String`</span></span>|<span data-ttu-id="ddecd-132">연결.</span><span class="sxs-lookup"><span data-stu-id="ddecd-132">Concatenate.</span></span>|  
|<span data-ttu-id="ddecd-133">한 식은 숫자 데이터 형식이 고 다른 하나는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-133">One expression is a numeric data type and the other is a string</span></span>|<span data-ttu-id="ddecd-134">`Option Strict` 가`On`이면 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-134">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="ddecd-135">가 이면는 `Double` 를로 암시적으로 변환 하 고를 추가 합니다. `String` `Off` `Option Strict`</span><span class="sxs-lookup"><span data-stu-id="ddecd-135">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="ddecd-136"><xref:System.InvalidCastException> 을로 `Double`변환할 수 없으면 예외를 throw 합니다. `String`</span><span class="sxs-lookup"><span data-stu-id="ddecd-136">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="ddecd-137">한 식은 숫자 데이터 형식이 고 다른 하나는 [Nothing](../../../visual-basic/language-reference/nothing.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-137">One expression is a numeric data type, and the other is [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|<span data-ttu-id="ddecd-138">값이 0 `Nothing` 인을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-138">Add, with `Nothing` valued as zero.</span></span>|  
|<span data-ttu-id="ddecd-139">한 식은 문자열이 고 다른 하나는입니다.`Nothing`</span><span class="sxs-lookup"><span data-stu-id="ddecd-139">One expression is a string, and the other is `Nothing`</span></span>|<span data-ttu-id="ddecd-140">`Nothing` 값을 ""로 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-140">Concatenate, with `Nothing` valued as "".</span></span>|  
  
 <span data-ttu-id="ddecd-141">한 식이 `Object` 식인 경우 Visual Basic는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-141">If one expression is an `Object` expression, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="ddecd-142">식의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ddecd-142">Data types of expressions</span></span>|<span data-ttu-id="ddecd-143">컴파일러 작업</span><span class="sxs-lookup"><span data-stu-id="ddecd-143">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="ddecd-144">`Object`식은 숫자 값을 포함 하 고 다른 값은 숫자 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-144">`Object` expression holds a numeric value and the other is a numeric data type</span></span>|<span data-ttu-id="ddecd-145">`Option Strict` 가`On`이면 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-145">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="ddecd-146">`Option Strict` 가`Off`이면를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-146">If `Option Strict` is `Off`, then add.</span></span>|  
|<span data-ttu-id="ddecd-147">`Object`식에는 숫자 값이 포함 되 고 다른 값은 형식입니다.`String`</span><span class="sxs-lookup"><span data-stu-id="ddecd-147">`Object` expression holds a numeric value and the other is of type `String`</span></span>|<span data-ttu-id="ddecd-148">`Option Strict` 가`On`이면 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-148">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="ddecd-149">가 이면는 `Double` 를로 암시적으로 변환 하 고를 추가 합니다. `String` `Off` `Option Strict`</span><span class="sxs-lookup"><span data-stu-id="ddecd-149">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="ddecd-150"><xref:System.InvalidCastException> 을로 `Double`변환할 수 없으면 예외를 throw 합니다. `String`</span><span class="sxs-lookup"><span data-stu-id="ddecd-150">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="ddecd-151">`Object`식은 문자열을 포함 하 고 다른 문자열은 숫자 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-151">`Object` expression holds a string and the other is a numeric data type</span></span>|<span data-ttu-id="ddecd-152">`Option Strict` 가`On`이면 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-152">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="ddecd-153">가 이면에서 암시적으로 문자열 `Object` 을로 변환 `Double` 하 고를 추가 합니다. `Off` `Option Strict`</span><span class="sxs-lookup"><span data-stu-id="ddecd-153">If `Option Strict` is `Off`, then implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="ddecd-154">문자열 `Object` 을로 `Double`변환할 수 없으면 <xref:System.InvalidCastException> 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-154">If the string `Object` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="ddecd-155">`Object`식은 문자열을 포함 하 고 나머지는 형식입니다.`String`</span><span class="sxs-lookup"><span data-stu-id="ddecd-155">`Object` expression holds a string and the other is of type `String`</span></span>|<span data-ttu-id="ddecd-156">`Option Strict` 가`On`이면 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-156">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="ddecd-157">가 이면 `Off`는 암시적으로로 `Object` `String` 변환 하 고 연결 합니다. `Option Strict`</span><span class="sxs-lookup"><span data-stu-id="ddecd-157">If `Option Strict` is `Off`, then implicitly convert `Object` to `String` and concatenate.</span></span>|  
  
 <span data-ttu-id="ddecd-158">두 식이 `Object` 모두 식인 경우 Visual Basic는 다음 작업을 수행 합니다`Option Strict Off` (만 해당).</span><span class="sxs-lookup"><span data-stu-id="ddecd-158">If both expressions are `Object` expressions, Visual Basic takes the following actions (`Option Strict Off` only).</span></span>  
  
|<span data-ttu-id="ddecd-159">식의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ddecd-159">Data types of expressions</span></span>|<span data-ttu-id="ddecd-160">컴파일러 작업</span><span class="sxs-lookup"><span data-stu-id="ddecd-160">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="ddecd-161">두 `Object` 식 모두 숫자 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-161">Both `Object` expressions hold numeric values</span></span>|<span data-ttu-id="ddecd-162">추가.</span><span class="sxs-lookup"><span data-stu-id="ddecd-162">Add.</span></span>|  
|<span data-ttu-id="ddecd-163">두 `Object` 식이 모두 형식입니다.`String`</span><span class="sxs-lookup"><span data-stu-id="ddecd-163">Both `Object` expressions are of type `String`</span></span>|<span data-ttu-id="ddecd-164">연결.</span><span class="sxs-lookup"><span data-stu-id="ddecd-164">Concatenate.</span></span>|  
|<span data-ttu-id="ddecd-165">한 `Object` 식에는 숫자 값이 포함 되 고 다른 식에는 문자열이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-165">One `Object` expression holds a numeric value and the other holds a string</span></span>|<span data-ttu-id="ddecd-166">암시적으로 문자열 `Object` 을로 `Double` 변환 하 고를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-166">Implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="ddecd-167">문자열 `Object` 을 숫자 값으로 변환할 수 없으면 <xref:System.InvalidCastException> 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-167">If the string `Object` cannot be converted to a numeric value, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
  
 <span data-ttu-id="ddecd-168">두 식이 `Object` 모두 [Nothing](../../../visual-basic/language-reference/nothing.md) 또는 <xref:System.DBNull>로 계산 되는 `+` 경우 연산자는 값을 `String` ""로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-168">If either `Object` expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md) or <xref:System.DBNull>, the `+` operator treats it as a `String` with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ddecd-169">연산자를 사용 하 `+` 는 경우 더하기 또는 문자열 연결의 발생 여부를 확인 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-169">When you use the `+` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="ddecd-170">모호성을 없애고 자체 문서화 코드를 제공 하려면 연산자를연결에사용합니다.`&`</span><span class="sxs-lookup"><span data-stu-id="ddecd-170">Use the `&` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="ddecd-171">오버로딩</span><span class="sxs-lookup"><span data-stu-id="ddecd-171">Overloading</span></span>  
 <span data-ttu-id="ddecd-172">연산자를 오버 로드할 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다. `+`</span><span class="sxs-lookup"><span data-stu-id="ddecd-172">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ddecd-173">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-173">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="ddecd-174">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ddecd-174">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddecd-175">예제</span><span class="sxs-lookup"><span data-stu-id="ddecd-175">Example</span></span>  
 <span data-ttu-id="ddecd-176">다음 예에서는 `+` 연산자를 사용 하 여 숫자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-176">The following example uses the `+` operator to add numbers.</span></span> <span data-ttu-id="ddecd-177">피연산자가 둘 다 숫자인 경우 Visual Basic 산술 결과를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-177">If the operands are both numeric, Visual Basic computes the arithmetic result.</span></span> <span data-ttu-id="ddecd-178">산술 결과는 두 피연산자의 합계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-178">The arithmetic result represents the sum of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 <span data-ttu-id="ddecd-179">연산자를 `+` 사용 하 여 문자열을 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-179">You can also use the `+` operator to concatenate strings.</span></span> <span data-ttu-id="ddecd-180">피연산자가 둘 다 문자열이 면 Visual Basic 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-180">If the operands are both strings, Visual Basic concatenates them.</span></span> <span data-ttu-id="ddecd-181">연결 결과는 두 피연산자의 콘텐츠로 구성 된 단일 문자열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-181">The concatenation result represents a single string consisting of the contents of the two operands one after the other.</span></span>  
  
 <span data-ttu-id="ddecd-182">피연산자가 혼합 형식인 경우 결과는 [Option Strict 문의](../../../visual-basic/language-reference/statements/option-strict-statement.md)설정에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-182">If the operands are of mixed types, the result depends on the setting of the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span> <span data-ttu-id="ddecd-183">다음 예에서는가 인 `Option Strict` `On`경우의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-183">The following example illustrates the result when `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 <span data-ttu-id="ddecd-184">다음 예에서는가 인 `Option Strict` `Off`경우의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-184">The following example illustrates the result when `Option Strict` is `Off`.</span></span>  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 <span data-ttu-id="ddecd-185">모호성을 없애려면를 연결 하는 `&` `+` 대신 연산자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddecd-185">To eliminate ambiguity, you should use the `&` operator instead of `+` for concatenation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddecd-186">참고자료</span><span class="sxs-lookup"><span data-stu-id="ddecd-186">See also</span></span>

- [<span data-ttu-id="ddecd-187">& 연산자</span><span class="sxs-lookup"><span data-stu-id="ddecd-187">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="ddecd-188">연결 연산자</span><span class="sxs-lookup"><span data-stu-id="ddecd-188">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="ddecd-189">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="ddecd-189">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="ddecd-190">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="ddecd-190">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="ddecd-191">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="ddecd-191">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="ddecd-192">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="ddecd-192">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="ddecd-193">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="ddecd-193">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
