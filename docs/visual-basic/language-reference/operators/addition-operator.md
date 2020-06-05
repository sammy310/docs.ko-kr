---
title: + 연산자
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
ms.openlocfilehash: 6ae3feae6ecb63b82426f2aa69359625bbffcec8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372118"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="b579d-102">+ 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b579d-102">+ Operator (Visual Basic)</span></span>
<span data-ttu-id="b579d-103">숫자 식의 양수 값을 두 개 더 추가 하거나 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-103">Adds two numbers or returns the positive value of a numeric expression.</span></span> <span data-ttu-id="b579d-104">를 사용 하 여 두 문자열 식을 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-104">Can also be used to concatenate two string expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b579d-105">구문</span><span class="sxs-lookup"><span data-stu-id="b579d-105">Syntax</span></span>  
  
```vb
expression1 + expression2
```
  
<span data-ttu-id="b579d-106">또는</span><span class="sxs-lookup"><span data-stu-id="b579d-106">or</span></span>

```vb  
+expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="b579d-107">부분</span><span class="sxs-lookup"><span data-stu-id="b579d-107">Parts</span></span>  
  
|<span data-ttu-id="b579d-108">용어</span><span class="sxs-lookup"><span data-stu-id="b579d-108">Term</span></span>|<span data-ttu-id="b579d-109">정의</span><span class="sxs-lookup"><span data-stu-id="b579d-109">Definition</span></span>|  
|---|---|  
|`expression1`|<span data-ttu-id="b579d-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b579d-110">Required.</span></span> <span data-ttu-id="b579d-111">임의의 숫자 또는 문자열 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-111">Any numeric or string expression.</span></span>|  
|`expression2`|<span data-ttu-id="b579d-112">`+`연산자가 음수 값을 계산 하지 않는 경우 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-112">Required unless the `+` operator is calculating a negative value.</span></span> <span data-ttu-id="b579d-113">임의의 숫자 또는 문자열 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-113">Any numeric or string expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="b579d-114">결과</span><span class="sxs-lookup"><span data-stu-id="b579d-114">Result</span></span>  
 <span data-ttu-id="b579d-115">`expression1`과 `expression2` 가 모두 숫자인 경우 결과는 산술 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-115">If `expression1` and `expression2` are both numeric, the result is their arithmetic sum.</span></span>  
  
 <span data-ttu-id="b579d-116">`expression2`가 없으면 `+` 연산자는 변경 되지 않은 식 값의 *단항* id 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-116">If `expression2` is absent, the `+` operator is the *unary* identity operator for the unchanged value of an expression.</span></span> <span data-ttu-id="b579d-117">이 의미에서 작업은의 부호를 유지 하는 것으로 구성 `expression1` 되므로가 음수인 경우 결과가 음수입니다 `expression1` .</span><span class="sxs-lookup"><span data-stu-id="b579d-117">In this sense, the operation consists of retaining the sign of `expression1`, so the result is negative if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="b579d-118">`expression1`및 `expression2` 가 둘 다 문자열이 면 결과는 값을 연결 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-118">If `expression1` and `expression2` are both strings, the result is the concatenation of their values.</span></span>  
  
 <span data-ttu-id="b579d-119">`expression1`및 `expression2` 가 혼합 형식이 면 수행 되는 작업은 형식, 해당 내용 및 [Option Strict 문의](../statements/option-strict-statement.md)설정에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-119">If `expression1` and `expression2` are of mixed types, the action taken depends on their types, their contents, and the setting of the [Option Strict Statement](../statements/option-strict-statement.md).</span></span> <span data-ttu-id="b579d-120">자세한 내용은 "주의"의 표를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b579d-120">For more information, see the tables in "Remarks."</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="b579d-121">지원 형식</span><span class="sxs-lookup"><span data-stu-id="b579d-121">Supported Types</span></span>  
 <span data-ttu-id="b579d-122">부호 없는 형식 및 부동 소수점 형식 및 및를 포함 하는 모든 숫자 형식 `Decimal` `String` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-122">All numeric types, including the unsigned and floating-point types and `Decimal`, and `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b579d-123">설명</span><span class="sxs-lookup"><span data-stu-id="b579d-123">Remarks</span></span>  
 <span data-ttu-id="b579d-124">일반적으로는 `+` 가능한 경우 산술 덧셈을 수행 하 고 두 식이 모두 문자열인 경우에만 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-124">In general, `+` performs arithmetic addition when possible, and concatenates only when both expressions are strings.</span></span>  
  
 <span data-ttu-id="b579d-125">두 식이 모두 이면 `Object` Visual Basic는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-125">If neither expression is an `Object`, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="b579d-126">식의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b579d-126">Data types of expressions</span></span>|<span data-ttu-id="b579d-127">컴파일러 작업</span><span class="sxs-lookup"><span data-stu-id="b579d-127">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="b579d-128">두 식은 모두 숫자 데이터 형식 (,,,,,,,,, `SByte` `Byte` `Short` `UShort` `Integer` `UInteger` `Long` `ULong` `Decimal` `Single` 또는 `Double` )입니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-128">Both expressions are numeric data types (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`)</span></span>|<span data-ttu-id="b579d-129">추가</span><span class="sxs-lookup"><span data-stu-id="b579d-129">Add.</span></span> <span data-ttu-id="b579d-130">결과 데이터 형식은 및의 데이터 형식에 적합 한 숫자 형식입니다 `expression1` `expression2` .</span><span class="sxs-lookup"><span data-stu-id="b579d-130">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="b579d-131">[연산자 결과의 데이터 형식](data-types-of-operator-results.md)에서 "정수 산술 연산" 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b579d-131">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="b579d-132">두 식이 모두 형식입니다.`String`</span><span class="sxs-lookup"><span data-stu-id="b579d-132">Both expressions are of type `String`</span></span>|<span data-ttu-id="b579d-133">연결.</span><span class="sxs-lookup"><span data-stu-id="b579d-133">Concatenate.</span></span>|  
|<span data-ttu-id="b579d-134">한 식은 숫자 데이터 형식이 고 다른 하나는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-134">One expression is a numeric data type and the other is a string</span></span>|<span data-ttu-id="b579d-135">`Option Strict`가 이면 `On` 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-135">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="b579d-136">`Option Strict`가 이면 `Off` 는를로 암시적으로 변환 하 `String` `Double` 고를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-136">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="b579d-137">을 `String` 로 변환할 수 없으면 `Double` 예외를 throw <xref:System.InvalidCastException> 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-137">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="b579d-138">한 식은 숫자 데이터 형식이 고 다른 하나는 [Nothing](../nothing.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-138">One expression is a numeric data type, and the other is [Nothing](../nothing.md)</span></span>|<span data-ttu-id="b579d-139">`Nothing`값이 0 인을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-139">Add, with `Nothing` valued as zero.</span></span>|  
|<span data-ttu-id="b579d-140">한 식은 문자열이 고 다른 하나는입니다.`Nothing`</span><span class="sxs-lookup"><span data-stu-id="b579d-140">One expression is a string, and the other is `Nothing`</span></span>|<span data-ttu-id="b579d-141">`Nothing`값을 ""로 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-141">Concatenate, with `Nothing` valued as "".</span></span>|  
  
 <span data-ttu-id="b579d-142">한 식이 `Object` 식인 경우 Visual Basic는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-142">If one expression is an `Object` expression, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="b579d-143">식의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b579d-143">Data types of expressions</span></span>|<span data-ttu-id="b579d-144">컴파일러 작업</span><span class="sxs-lookup"><span data-stu-id="b579d-144">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="b579d-145">`Object`식은 숫자 값을 포함 하 고 다른 값은 숫자 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-145">`Object` expression holds a numeric value and the other is a numeric data type</span></span>|<span data-ttu-id="b579d-146">`Option Strict`가 이면 `On` 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-146">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="b579d-147">`Option Strict`가 이면 `Off` 를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-147">If `Option Strict` is `Off`, then add.</span></span>|  
|<span data-ttu-id="b579d-148">`Object`식에는 숫자 값이 포함 되 고 다른 값은 형식입니다.`String`</span><span class="sxs-lookup"><span data-stu-id="b579d-148">`Object` expression holds a numeric value and the other is of type `String`</span></span>|<span data-ttu-id="b579d-149">`Option Strict`가 이면 `On` 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-149">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="b579d-150">`Option Strict`가 이면 `Off` 는를로 암시적으로 변환 하 `String` `Double` 고를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-150">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="b579d-151">을 `String` 로 변환할 수 없으면 `Double` 예외를 throw <xref:System.InvalidCastException> 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-151">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="b579d-152">`Object`식은 문자열을 포함 하 고 다른 문자열은 숫자 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-152">`Object` expression holds a string and the other is a numeric data type</span></span>|<span data-ttu-id="b579d-153">`Option Strict`가 이면 `On` 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-153">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="b579d-154">`Option Strict`가 이면 `Off` 에서 암시적으로 문자열을로 변환 하 `Object` `Double` 고를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-154">If `Option Strict` is `Off`, then implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="b579d-155">문자열을 `Object` 로 변환할 수 없으면 `Double` 예외를 throw <xref:System.InvalidCastException> 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-155">If the string `Object` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="b579d-156">`Object`식은 문자열을 포함 하 고 나머지는 형식입니다.`String`</span><span class="sxs-lookup"><span data-stu-id="b579d-156">`Object` expression holds a string and the other is of type `String`</span></span>|<span data-ttu-id="b579d-157">`Option Strict`가 이면 `On` 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-157">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="b579d-158">`Option Strict`가 이면는 `Off` 암시적으로로 변환 하 `Object` `String` 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-158">If `Option Strict` is `Off`, then implicitly convert `Object` to `String` and concatenate.</span></span>|  
  
 <span data-ttu-id="b579d-159">두 식이 모두 `Object` 식인 경우 Visual Basic는 다음 작업을 수행 합니다 ( `Option Strict Off` 만 해당).</span><span class="sxs-lookup"><span data-stu-id="b579d-159">If both expressions are `Object` expressions, Visual Basic takes the following actions (`Option Strict Off` only).</span></span>  
  
|<span data-ttu-id="b579d-160">식의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b579d-160">Data types of expressions</span></span>|<span data-ttu-id="b579d-161">컴파일러 작업</span><span class="sxs-lookup"><span data-stu-id="b579d-161">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="b579d-162">두 `Object` 식 모두 숫자 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-162">Both `Object` expressions hold numeric values</span></span>|<span data-ttu-id="b579d-163">추가</span><span class="sxs-lookup"><span data-stu-id="b579d-163">Add.</span></span>|  
|<span data-ttu-id="b579d-164">두 `Object` 식이 모두 형식입니다.`String`</span><span class="sxs-lookup"><span data-stu-id="b579d-164">Both `Object` expressions are of type `String`</span></span>|<span data-ttu-id="b579d-165">연결.</span><span class="sxs-lookup"><span data-stu-id="b579d-165">Concatenate.</span></span>|  
|<span data-ttu-id="b579d-166">한 `Object` 식에는 숫자 값이 포함 되 고 다른 식에는 문자열이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-166">One `Object` expression holds a numeric value and the other holds a string</span></span>|<span data-ttu-id="b579d-167">암시적으로 문자열을 `Object` 로 변환 하 `Double` 고를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-167">Implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="b579d-168">문자열을 `Object` 숫자 값으로 변환할 수 없으면 예외를 throw <xref:System.InvalidCastException> 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-168">If the string `Object` cannot be converted to a numeric value, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
  
 <span data-ttu-id="b579d-169">두 `Object` 식이 모두 [Nothing](../nothing.md) 또는로 계산 되 <xref:System.DBNull> 는 경우 연산자는 값을 `+` `String` ""로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-169">If either `Object` expression evaluates to [Nothing](../nothing.md) or <xref:System.DBNull>, the `+` operator treats it as a `String` with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b579d-170">연산자를 사용 하는 경우 `+` 더하기 또는 문자열 연결의 발생 여부를 확인 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-170">When you use the `+` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="b579d-171">모호성을 `&` 없애고 자체 문서화 코드를 제공 하려면 연산자를 연결에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-171">Use the `&` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="b579d-172">오버로딩</span><span class="sxs-lookup"><span data-stu-id="b579d-172">Overloading</span></span>  
 <span data-ttu-id="b579d-173">`+`연산자를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-173">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b579d-174">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-174">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b579d-175">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b579d-175">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b579d-176">예제</span><span class="sxs-lookup"><span data-stu-id="b579d-176">Example</span></span>  
 <span data-ttu-id="b579d-177">다음 예에서는 연산자를 사용 하 여 `+` 숫자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-177">The following example uses the `+` operator to add numbers.</span></span> <span data-ttu-id="b579d-178">피연산자가 둘 다 숫자인 경우 Visual Basic 산술 결과를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-178">If the operands are both numeric, Visual Basic computes the arithmetic result.</span></span> <span data-ttu-id="b579d-179">산술 결과는 두 피연산자의 합계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-179">The arithmetic result represents the sum of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 <span data-ttu-id="b579d-180">연산자를 사용 하 여 `+` 문자열을 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-180">You can also use the `+` operator to concatenate strings.</span></span> <span data-ttu-id="b579d-181">피연산자가 둘 다 문자열이 면 Visual Basic 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-181">If the operands are both strings, Visual Basic concatenates them.</span></span> <span data-ttu-id="b579d-182">연결 결과는 두 피연산자의 콘텐츠로 구성 된 단일 문자열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-182">The concatenation result represents a single string consisting of the contents of the two operands one after the other.</span></span>  
  
 <span data-ttu-id="b579d-183">피연산자가 혼합 형식인 경우 결과는 [Option Strict 문의](../statements/option-strict-statement.md)설정에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="b579d-183">If the operands are of mixed types, the result depends on the setting of the [Option Strict Statement](../statements/option-strict-statement.md).</span></span> <span data-ttu-id="b579d-184">다음 예에서는가 인 경우의 결과를 보여 줍니다 `Option Strict` `On` .</span><span class="sxs-lookup"><span data-stu-id="b579d-184">The following example illustrates the result when `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 <span data-ttu-id="b579d-185">다음 예에서는가 인 경우의 결과를 보여 줍니다 `Option Strict` `Off` .</span><span class="sxs-lookup"><span data-stu-id="b579d-185">The following example illustrates the result when `Option Strict` is `Off`.</span></span>  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 <span data-ttu-id="b579d-186">모호성을 없애려면를 연결 하는 대신 연산자를 사용 해야 합니다 `&` `+` .</span><span class="sxs-lookup"><span data-stu-id="b579d-186">To eliminate ambiguity, you should use the `&` operator instead of `+` for concatenation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b579d-187">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b579d-187">See also</span></span>

- [<span data-ttu-id="b579d-188">& 연산자</span><span class="sxs-lookup"><span data-stu-id="b579d-188">& Operator</span></span>](concatenation-operator.md)
- [<span data-ttu-id="b579d-189">연결 연산자</span><span class="sxs-lookup"><span data-stu-id="b579d-189">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="b579d-190">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="b579d-190">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="b579d-191">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="b579d-191">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="b579d-192">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="b579d-192">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="b579d-193">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="b579d-193">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="b579d-194">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="b579d-194">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
