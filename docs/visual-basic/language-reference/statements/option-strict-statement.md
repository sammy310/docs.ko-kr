---
title: Option Strict 문
ms.date: 07/20/2015
f1_keywords:
- vb.Strict
- vb.OptionStrict
helpviewer_keywords:
- Strict keyword [Visual Basic]
- Option Strict statement [Visual Basic]
- conversions [Visual Basic], implicit
- late binding [Visual Basic]
- implicit conversions [Visual Basic]
ms.assetid: 5883e0c1-a920-4274-8e46-b0ff047eaee5
ms.openlocfilehash: ab1094961e2bc3aed0e975e40369a5f5c1ba93eb
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873135"
---
# <a name="option-strict-statement"></a><span data-ttu-id="fdcc3-102">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="fdcc3-102">Option Strict Statement</span></span>

<span data-ttu-id="fdcc3-103">암시적 데이터 형식 변환을 확대 변환 으로만 제한 하 고 런타임에 바인딩을 허용 하지 않으며 형식을 생성 하는 암시적 형식화를 허용 하지 `Object` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-103">Restricts implicit data type conversions to only widening conversions, disallows late binding, and disallows implicit typing that results in an `Object` type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdcc3-104">구문</span><span class="sxs-lookup"><span data-stu-id="fdcc3-104">Syntax</span></span>  
  
```vb  
Option Strict { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="fdcc3-105">부분</span><span class="sxs-lookup"><span data-stu-id="fdcc3-105">Parts</span></span>  
  
|<span data-ttu-id="fdcc3-106">용어</span><span class="sxs-lookup"><span data-stu-id="fdcc3-106">Term</span></span>|<span data-ttu-id="fdcc3-107">정의</span><span class="sxs-lookup"><span data-stu-id="fdcc3-107">Definition</span></span>|  
|---|---|  
|`On`|<span data-ttu-id="fdcc3-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-108">Optional.</span></span> <span data-ttu-id="fdcc3-109">검사를 사용 하도록 설정 `Option Strict` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-109">Enables `Option Strict` checking.</span></span>|  
|`Off`|<span data-ttu-id="fdcc3-110">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-110">Optional.</span></span> <span data-ttu-id="fdcc3-111">검사를 사용 하지 않습니다 `Option Strict` .</span><span class="sxs-lookup"><span data-stu-id="fdcc3-111">Disables `Option Strict` checking.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdcc3-112">설명</span><span class="sxs-lookup"><span data-stu-id="fdcc3-112">Remarks</span></span>  

 <span data-ttu-id="fdcc3-113">`Option Strict On` `Option Strict` 파일이 파일에 표시 되 면 다음 조건으로 인해 컴파일 시간 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-113">When `Option Strict On` or `Option Strict` appears in a file, the following conditions cause a compile-time error:</span></span>  
  
- <span data-ttu-id="fdcc3-114">암시적 축소 변환</span><span class="sxs-lookup"><span data-stu-id="fdcc3-114">Implicit narrowing conversions</span></span>  
  
- <span data-ttu-id="fdcc3-115">런타임에 바인딩</span><span class="sxs-lookup"><span data-stu-id="fdcc3-115">Late binding</span></span>  
  
- <span data-ttu-id="fdcc3-116">`Object` 유형으로 이어지는 암시적 형식 지정</span><span class="sxs-lookup"><span data-stu-id="fdcc3-116">Implicit typing that results in an `Object` type</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fdcc3-117">[컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)에서 설정할 수 있는 경고 구성에는 컴파일 시간 오류를 발생 시키는 세 가지 조건에 해당 하는 세 가지 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-117">In the warning configurations that you can set on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), there are three settings that correspond to the three conditions that cause a compile-time error.</span></span> <span data-ttu-id="fdcc3-118">이러한 설정을 사용 하는 방법에 대 한 자세한 내용은이 항목의 뒷부분에 나오는 [IDE에서 경고 구성을 설정 하려면을](option-strict-statement.md#conditions) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-118">For information about how to use these settings, see [To set warning configurations in the IDE](option-strict-statement.md#conditions) later in this topic.</span></span>  
  
 <span data-ttu-id="fdcc3-119">`Option Strict Off`이 문은 연결 된 IDE 설정이 이러한 오류 또는 경고를 설정 하도록 지정 하더라도 세 가지 조건 모두에 대해 오류 및 경고 검사를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-119">The `Option Strict Off` statement turns off error and warning checking for all three conditions, even if the associated IDE settings specify to turn on these errors or warnings.</span></span> <span data-ttu-id="fdcc3-120">`Option Strict On`문은 연결 된 IDE 설정이 이러한 오류 또는 경고를 해제 하도록 지정 하더라도 세 가지 조건 모두에 대해 오류 및 경고 검사를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-120">The `Option Strict On` statement turns on error and warning checking for all three conditions, even if the associated IDE settings specify to turn off these errors or warnings.</span></span>  
  
 <span data-ttu-id="fdcc3-121">사용 되는 경우 `Option Strict` 문은 파일의 다른 코드 문 앞에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-121">If used, the `Option Strict` statement must appear before any other code statements in a file.</span></span>  
  
 <span data-ttu-id="fdcc3-122">`Option Strict`를로 설정 하면 `On` Visual Basic 모든 프로그래밍 요소에 대해 데이터 형식이 지정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-122">When you set `Option Strict` to `On`, Visual Basic checks that data types are specified for all programming elements.</span></span> <span data-ttu-id="fdcc3-123">데이터 형식은 명시적으로 지정 하거나 로컬 형식 유추를 사용 하 여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-123">Data types can be specified explicitly, or specified by using local type inference.</span></span> <span data-ttu-id="fdcc3-124">다음과 같은 이유로 모든 프로그래밍 요소에 대 한 데이터 형식을 지정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-124">Specifying data types for all your programming elements is recommended, for the following reasons:</span></span>  
  
- <span data-ttu-id="fdcc3-125">변수 및 매개 변수에 대해 IntelliSense를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-125">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="fdcc3-126">이렇게 하면 코드를 입력할 때 해당 속성 및 기타 멤버를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-126">This enables you to see their properties and other members as you type code.</span></span>  
  
- <span data-ttu-id="fdcc3-127">컴파일러에서 형식 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-127">It enables the compiler to perform type checking.</span></span> <span data-ttu-id="fdcc3-128">형식 검사를 사용 하면 형식 변환 오류로 인해 런타임에 실패할 수 있는 문을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-128">Type checking helps you find statements that can fail at run time because of type conversion errors.</span></span> <span data-ttu-id="fdcc3-129">또한 이러한 메서드를 지원 하지 않는 개체에 대 한 메서드 호출을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-129">It also identifies calls to methods on objects that do not support those methods.</span></span>  
  
- <span data-ttu-id="fdcc3-130">코드의 실행 속도를 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-130">It speeds up the execution of code.</span></span> <span data-ttu-id="fdcc3-131">한 가지 이유는 프로그래밍 요소에 대 한 데이터 형식을 지정 하지 않는 경우 Visual Basic 컴파일러에서 해당 형식을 할당 하는 것입니다 `Object` .</span><span class="sxs-lookup"><span data-stu-id="fdcc3-131">One reason for this is that if you do not specify a data type for a programming element, the Visual Basic compiler assigns it the `Object` type.</span></span> <span data-ttu-id="fdcc3-132">컴파일된 코드는 `Object` 와 다른 데이터 형식 간에 앞뒤로 변환 해야 하므로 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-132">Compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="implicit-narrowing-conversion-errors"></a><span data-ttu-id="fdcc3-133">암시적 축소 변환 오류</span><span class="sxs-lookup"><span data-stu-id="fdcc3-133">Implicit Narrowing Conversion Errors</span></span>  

 <span data-ttu-id="fdcc3-134">암시적 축소 변환 오류는 축소 변환인 암시적 데이터 형식 변환이 있을 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-134">Implicit narrowing conversion errors occur when there is an implicit data type conversion that is a narrowing conversion.</span></span>  
  
 <span data-ttu-id="fdcc3-135">Visual Basic는 여러 데이터 형식을 다른 데이터 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-135">Visual Basic can convert many data types to other data types.</span></span> <span data-ttu-id="fdcc3-136">한 데이터 형식의 값을 정밀도 나 용량이 더 적은 데이터 형식으로 변환 하는 경우 데이터 손실이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-136">Data loss can occur when the value of one data type is converted to a data type that has less precision or a smaller capacity.</span></span> <span data-ttu-id="fdcc3-137">이러한 축소 변환이 실패 하면 런타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-137">A run-time error occurs if such a narrowing conversion fails.</span></span> <span data-ttu-id="fdcc3-138">`Option Strict` 는 이러한 축소 변환을 방지할 수 있도록 컴파일 시간 알림을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-138">`Option Strict` ensures compile-time notification of these narrowing conversions so that you can avoid them.</span></span> <span data-ttu-id="fdcc3-139">자세한 내용은 [암시적 변환과 명시적 변환](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) 및 [확대/축소 변환](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-139">For more information, see [Implicit and Explicit Conversions](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) and [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
 <span data-ttu-id="fdcc3-140">오류를 일으킬 수 있는 변환에는 식에서 발생 하는 암시적 변환이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-140">Conversions that can cause errors include implicit conversions that occur in expressions.</span></span> <span data-ttu-id="fdcc3-141">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-141">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="fdcc3-142">+ 연산자</span><span class="sxs-lookup"><span data-stu-id="fdcc3-142">+ Operator</span></span>](../operators/addition-operator.md)  
  
- [<span data-ttu-id="fdcc3-143">+ = 연산자</span><span class="sxs-lookup"><span data-stu-id="fdcc3-143">+= Operator</span></span>](../operators/addition-assignment-operator.md)  
  
- [<span data-ttu-id="fdcc3-144">\ 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fdcc3-144">\ Operator (Visual Basic)</span></span>](../operators/integer-division-operator.md)  
  
- [<span data-ttu-id="fdcc3-145">/= 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fdcc3-145">/= Operator (Visual Basic)</span></span>](../operators/floating-point-division-assignment-operator.md)  
  
- [<span data-ttu-id="fdcc3-146">Char 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="fdcc3-146">Char Data Type</span></span>](../data-types/char-data-type.md)  
  
 <span data-ttu-id="fdcc3-147">[& 연산자](../operators/concatenation-operator.md)를 사용 하 여 문자열을 연결 하는 경우 문자열에 대 한 모든 변환이 확대 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-147">When you concatenate strings by using the [& Operator](../operators/concatenation-operator.md), all conversions to the strings are considered to be widening.</span></span> <span data-ttu-id="fdcc3-148">따라서 이러한 변환은가 on 이더라도 암시적 축소 변환 오류를 생성 하지 않습니다 `Option Strict` .</span><span class="sxs-lookup"><span data-stu-id="fdcc3-148">So these conversions do not generate an implicit narrowing conversion error, even if `Option Strict` is on.</span></span>  
  
 <span data-ttu-id="fdcc3-149">해당 매개 변수와 다른 데이터 형식의 인수를 포함 하는 메서드를 호출 하면가 on 인 경우 축소 변환을 수행 하면 컴파일 시간 오류가 발생 `Option Strict` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-149">When you call a method that has an argument that has a data type different from the corresponding parameter, a narrowing conversion causes a compile-time error if `Option Strict` is on.</span></span> <span data-ttu-id="fdcc3-150">확대 변환 또는 명시적 변환을 사용 하 여 컴파일 시간 오류를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-150">You can avoid the compile-time error by using a widening conversion or an explicit conversion.</span></span>  
  
 <span data-ttu-id="fdcc3-151">암시적 축소 변환 오류는 컬렉션의 요소에서 루프 제어 변수로의 변환을 위해 컴파일 타임에 표시 되지 않습니다 `For Each…Next` .</span><span class="sxs-lookup"><span data-stu-id="fdcc3-151">Implicit narrowing conversion errors are suppressed at compile-time for conversions from the elements in a `For Each…Next` collection to the loop control variable.</span></span> <span data-ttu-id="fdcc3-152">가 설정 된 경우에도이 오류가 발생 `Option Strict` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-152">This occurs even if `Option Strict` is on.</span></span> <span data-ttu-id="fdcc3-153">자세한 내용은 [각 항목에 대 한 "축소 변환" 섹션을 참조 하세요. 다음 문](for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fdcc3-153">For more information, see the "Narrowing Conversions" section in [For Each...Next Statement](for-each-next-statement.md).</span></span>  
  
## <a name="late-binding-errors"></a><span data-ttu-id="fdcc3-154">런타임에 바인딩 오류</span><span class="sxs-lookup"><span data-stu-id="fdcc3-154">Late Binding Errors</span></span>  

 <span data-ttu-id="fdcc3-155">개체에 `Object` 형식으로 선언된 변수의 속성 또는 메서드에 할당되면 런타임에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-155">An object is late bound when it is assigned to a property or method of a variable that is declared to be of type `Object`.</span></span> <span data-ttu-id="fdcc3-156">자세한 내용은 [초기 바인딩 및 런타임에 바인딩](../../programming-guide/language-features/early-late-binding/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-156">For more information, see [Early and Late Binding](../../programming-guide/language-features/early-late-binding/index.md).</span></span>  
  
## <a name="implicit-object-type-errors"></a><span data-ttu-id="fdcc3-157">암시적 개체 유형 오류</span><span class="sxs-lookup"><span data-stu-id="fdcc3-157">Implicit Object Type Errors</span></span>  

 <span data-ttu-id="fdcc3-158">암시적 개체 형식 오류는 선언된 변수에 대해 적절한 형식이 유추될 수 없어 `Object`의 형식이 유추될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-158">Implicit object type errors occur when an appropriate type cannot be inferred for a declared variable, so a type of `Object` is inferred.</span></span> <span data-ttu-id="fdcc3-159">주로 `As` 절을 사용하지 않고 `Dim` 문을 사용하여 변수를 선언하고, `Option Infer`가 꺼져 있는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-159">This primarily occurs when you use a `Dim` statement to declare a variable without using an `As` clause, and `Option Infer` is off.</span></span> <span data-ttu-id="fdcc3-160">자세한 내용은 [Option 유추 문](option-infer-statement.md) 및 [Visual Basic 언어 사양](../../reference/language-specification/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-160">For more information, see [Option Infer Statement](option-infer-statement.md) and the [Visual Basic Language Specification](../../reference/language-specification/index.md).</span></span>  
  
 <span data-ttu-id="fdcc3-161">메서드 매개 변수의 `As` 경우가 off 인 경우 절은 선택 사항입니다 `Option Strict` .</span><span class="sxs-lookup"><span data-stu-id="fdcc3-161">For method parameters, the `As` clause is optional if `Option Strict` is off.</span></span> <span data-ttu-id="fdcc3-162">그러나 한 매개 변수에서 절을 사용 하는 경우 `As` 모두 해당 매개 변수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-162">However, if any one parameter uses an `As` clause, they all must use it.</span></span> <span data-ttu-id="fdcc3-163">`Option Strict`가 on 이면 `As` 모든 매개 변수 정의에 절이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-163">If `Option Strict` is on, the `As` clause is required for every parameter definition.</span></span>  
  
 <span data-ttu-id="fdcc3-164">절을 사용 하지 않고 변수를 선언 하 `As` 고로 설정 하는 경우 `Nothing` 변수의 형식은 `Object` 입니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-164">If you declare a variable without using an `As` clause and set it to `Nothing`, the variable has a type of `Object`.</span></span> <span data-ttu-id="fdcc3-165">이 경우 `Option Strict` 가 on이 고가 on 이면 컴파일 시간 오류가 발생 하지 않습니다 `Option Infer` .</span><span class="sxs-lookup"><span data-stu-id="fdcc3-165">No compile-time error occurs in this case when `Option Strict` is on and `Option Infer` is on.</span></span> <span data-ttu-id="fdcc3-166">예를 들면 `Dim something = Nothing` 입니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-166">An example of this is `Dim something = Nothing`.</span></span>  
  
### <a name="default-data-types-and-values"></a><span data-ttu-id="fdcc3-167">기본 데이터 형식 및 값</span><span class="sxs-lookup"><span data-stu-id="fdcc3-167">Default Data Types and Values</span></span>  

 <span data-ttu-id="fdcc3-168">다음 표에서는 [Dim 문에](dim-statement.md)데이터 형식 및 이니셜라이저를 지정 하는 다양 한 조합의 결과에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-168">The following table describes the results of various combinations of specifying the data type and initializer in a [Dim Statement](dim-statement.md).</span></span>  
  
|<span data-ttu-id="fdcc3-169">데이터 형식 지정 여부</span><span class="sxs-lookup"><span data-stu-id="fdcc3-169">Data type specified?</span></span>|<span data-ttu-id="fdcc3-170">이니셜라이저 지정 여부</span><span class="sxs-lookup"><span data-stu-id="fdcc3-170">Initializer specified?</span></span>|<span data-ttu-id="fdcc3-171">예제</span><span class="sxs-lookup"><span data-stu-id="fdcc3-171">Example</span></span>|<span data-ttu-id="fdcc3-172">결과</span><span class="sxs-lookup"><span data-stu-id="fdcc3-172">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="fdcc3-173">아니요</span><span class="sxs-lookup"><span data-stu-id="fdcc3-173">No</span></span>|<span data-ttu-id="fdcc3-174">아니요</span><span class="sxs-lookup"><span data-stu-id="fdcc3-174">No</span></span>|`Dim qty`|<span data-ttu-id="fdcc3-175">`Option Strict`가 off(기본값)이면 변수는 `Nothing`으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-175">If `Option Strict` is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="fdcc3-176">`Option Strict`가 on이면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-176">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="fdcc3-177">아니요</span><span class="sxs-lookup"><span data-stu-id="fdcc3-177">No</span></span>|<span data-ttu-id="fdcc3-178">예</span><span class="sxs-lookup"><span data-stu-id="fdcc3-178">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="fdcc3-179">`Option Infer`가 on(기본값)이면 변수가 이니셜라이저의 데이터 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-179">If `Option Infer` is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="fdcc3-180">[지역 형식 유추](../../programming-guide/language-features/variables/local-type-inference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-180">See [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="fdcc3-181">`Option Infer`가 off이고 `Option Strict`고 off이면 변수가 `Object`의 데이터 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-181">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="fdcc3-182">`Option Infer`가 off이고 `Option Strict`는 on이면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-182">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="fdcc3-183">예</span><span class="sxs-lookup"><span data-stu-id="fdcc3-183">Yes</span></span>|<span data-ttu-id="fdcc3-184">예</span><span class="sxs-lookup"><span data-stu-id="fdcc3-184">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="fdcc3-185">변수는 데이터 형식의 기본값으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-185">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="fdcc3-186">자세한 내용은 [Dim 문](dim-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-186">For more information, see [Dim Statement](dim-statement.md).</span></span>|  
|<span data-ttu-id="fdcc3-187">예</span><span class="sxs-lookup"><span data-stu-id="fdcc3-187">Yes</span></span>|<span data-ttu-id="fdcc3-188">예</span><span class="sxs-lookup"><span data-stu-id="fdcc3-188">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="fdcc3-189">이니셜라이저의 데이터 형식을 지정한 데이터 형식으로 변환할 수 없으면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-189">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a><span data-ttu-id="fdcc3-190">Option Strict 문이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="fdcc3-190">When an Option Strict Statement Is Not Present</span></span>  

 <span data-ttu-id="fdcc3-191">소스 코드에 문이 포함 되어 있지 않으면 `Option Strict` [프로젝트 디자이너 (Visual Basic)의 컴파일 페이지](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) 에서 **Option strict** 설정이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-191">If the source code does not contain an `Option Strict` statement, the **Option strict** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="fdcc3-192">**컴파일 페이지** 에는 오류를 생성 하는 조건에 대 한 추가 제어를 제공 하는 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-192">The **Compile Page** has settings that provide additional control over the conditions that generate an error.</span></span>  
  
 <span data-ttu-id="fdcc3-193">명령줄 컴파일러를 사용 하는 경우 [-옵션 strict](../../reference/command-line-compiler/optionstrict.md) 컴파일러 옵션을 사용 하 여에 대 한 설정을 지정할 수 있습니다 `Option Strict` .</span><span class="sxs-lookup"><span data-stu-id="fdcc3-193">If you are using the command-line compiler, you can use the [-optionstrict](../../reference/command-line-compiler/optionstrict.md) compiler option to specify a setting for `Option Strict`.</span></span>  
  
### <a name="to-set-option-strict-in-the-ide"></a><span data-ttu-id="fdcc3-194">IDE에서 Option Strict를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="fdcc3-194">To set Option Strict in the IDE</span></span>  

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
1. <span data-ttu-id="fdcc3-195">**솔루션 탐색기**에서 프로젝트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-195">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="fdcc3-196">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-196">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="fdcc3-197">**컴파일** 탭에서 **Option Strict** 상자에 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-197">On the **Compile** tab, set the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set-warning-configurations-in-the-ide"></a><a name="conditions"></a> <span data-ttu-id="fdcc3-198">IDE에서 경고 구성을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="fdcc3-198">To set warning configurations in the IDE</span></span>  

 <span data-ttu-id="fdcc3-199">컴파일 페이지를 사용 하는 경우 문 대신 [프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) 를 사용 하면 `Option Strict` 오류를 생성 하는 조건을 추가로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-199">When you use the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) instead of an `Option Strict` statement, you have additional control over the conditions that generate errors.</span></span> <span data-ttu-id="fdcc3-200">**컴파일 페이지** 의 **경고 구성** 섹션에 `Option Strict` 는가 on 인 경우 컴파일 시간 오류를 발생 시키는 세 가지 조건에 해당 하는 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-200">The **Warning configurations** section of the **Compile Page** has settings that correspond to the three conditions that cause a compile-time error when `Option Strict` is on.</span></span> <span data-ttu-id="fdcc3-201">이러한 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-201">Following are these settings:</span></span>  
  
- <span data-ttu-id="fdcc3-202">**암시적 변환**</span><span class="sxs-lookup"><span data-stu-id="fdcc3-202">**Implicit conversion**</span></span>  
  
- <span data-ttu-id="fdcc3-203">**런타임에 바인딩; 호출이 실패할 수 있음**</span><span class="sxs-lookup"><span data-stu-id="fdcc3-203">**Late binding; call could fail at run time**</span></span>  
  
- <span data-ttu-id="fdcc3-204">**암시적 형식; 개체로 간주**</span><span class="sxs-lookup"><span data-stu-id="fdcc3-204">**Implicit type; object assumed**</span></span>  
  
 <span data-ttu-id="fdcc3-205">**Option Strict**를 **On**으로 설정하는 경우 이러한 세 가지 경고 구성 설정은 모두 **Error**로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-205">When you set **Option Strict** to **On**, all three of these warning configuration settings are set to **Error**.</span></span> <span data-ttu-id="fdcc3-206">**Option Strict**를 **Off**로 설정하는 경우 세 가지 설정은 모두 **None**으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-206">When you set **Option Strict** to **Off**, all three settings are set to **None**.</span></span>  
  
 <span data-ttu-id="fdcc3-207">각 경고 구성 설정은 **None**, **Warning** 또는 **Error**로 개별적으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-207">You can individually change each warning configuration setting to **None**, **Warning**, or **Error**.</span></span> <span data-ttu-id="fdcc3-208">세 가지 경고 구성 설정이 모두 **Error**로 설정 된 경우이 `On` 상자에 나타납니다 `Option strict` .</span><span class="sxs-lookup"><span data-stu-id="fdcc3-208">If all three warning configuration settings are set to **Error**, `On` appears in the `Option strict` box.</span></span> <span data-ttu-id="fdcc3-209">3 개가 모두 **없음**으로 설정 된 경우 `Off` 이 상자에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-209">If all three are set to **None**, `Off` appears in this box.</span></span> <span data-ttu-id="fdcc3-210">이러한 설정의 다른 조합의 경우 **(사용자 지정)** 이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-210">For any other combination of these settings, **(custom)** appears.</span></span>  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a><span data-ttu-id="fdcc3-211">새 프로젝트에 대 한 Strict 기본 설정 옵션을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="fdcc3-211">To set the Option Strict default setting for new projects</span></span>  

 <span data-ttu-id="fdcc3-212">프로젝트를 만들 때 **컴파일** 탭의 **옵션 strict** 설정이 **옵션** 대화 상자의 **option strict** 설정으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-212">When you create a project, the **Option Strict** setting on the **Compile** tab is set to the **Option Strict** setting in the **Options** dialog box.</span></span>  
  
 <span data-ttu-id="fdcc3-213">`Option Strict`이 대화 상자에서 설정 하려면 **도구** 메뉴에서 **옵션**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-213">To set `Option Strict` in this dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="fdcc3-214">**옵션** 대화 상자에서 **프로젝트 및 솔루션**을 확장하고 **VB 기본값**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-214">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="fdcc3-215">**VB 기본값** 의 초기 기본 설정은 `Off` 입니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-215">The initial default setting in **VB Defaults** is `Off`.</span></span>  
  
### <a name="to-set-option-strict-on-the-command-line"></a><span data-ttu-id="fdcc3-216">명령줄에서 Option Strict를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="fdcc3-216">To set Option Strict on the command line</span></span>  

 <span data-ttu-id="fdcc3-217">**Vbc** 명령에 [-옵션 strict](../../reference/command-line-compiler/optionstrict.md) 컴파일러 옵션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-217">Include the [-optionstrict](../../reference/command-line-compiler/optionstrict.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdcc3-218">예제</span><span class="sxs-lookup"><span data-stu-id="fdcc3-218">Example</span></span>  

 <span data-ttu-id="fdcc3-219">다음 예제에서는 축소 변환 인 암시적 형식 변환으로 인해 발생 하는 컴파일 시간 오류를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-219">The following examples demonstrate compile-time errors caused by implicit type conversions that are narrowing conversions.</span></span> <span data-ttu-id="fdcc3-220">이 범주의 오류는 **컴파일 페이지**의 **암시적 변환** 조건에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-220">This category of errors corresponds to the **Implicit conversion** condition on the **Compile Page**.</span></span>  
  
 [!code-vb[VbVbalrStatements#161](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#161)]  
  
## <a name="example"></a><span data-ttu-id="fdcc3-221">예제</span><span class="sxs-lookup"><span data-stu-id="fdcc3-221">Example</span></span>  

 <span data-ttu-id="fdcc3-222">다음 예제에서는 런타임에 바인딩으로 인해 발생 하는 컴파일 시간 오류를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-222">The following example demonstrates a compile-time error caused by late binding.</span></span> <span data-ttu-id="fdcc3-223">이 범주의 오류는 런타임에 바인딩과 일치 합니다. **컴파일 페이지**에서 **런타임에 호출이 실패할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-223">This category of errors corresponds to the **Late binding; call could fail at run time** condition on the **Compile Page**.</span></span>  
  
 [!code-vb[VbVbalrStatements#162](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#162)]  
  
## <a name="example"></a><span data-ttu-id="fdcc3-224">예제</span><span class="sxs-lookup"><span data-stu-id="fdcc3-224">Example</span></span>  

 <span data-ttu-id="fdcc3-225">다음 예제에서는의 암시적 형식으로 선언 된 변수에 의해 발생 하는 오류를 보여 줍니다 `Object` .</span><span class="sxs-lookup"><span data-stu-id="fdcc3-225">The following examples demonstrate errors caused by variables that are declared with an implicit type of `Object`.</span></span> <span data-ttu-id="fdcc3-226">이 범주의 오류는 **컴파일 페이지**에서 **암시적 형식, 개체를 사용한** 조건에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcc3-226">This category of errors corresponds to the **Implicit type; object assumed** condition on the **Compile Page**.</span></span>  
  
 [!code-vb[VbVbalrStatements#163](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#163)]  
  
 [!code-vb[VbVbalrStatements#164](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#164)]  
  
## <a name="see-also"></a><span data-ttu-id="fdcc3-227">참조</span><span class="sxs-lookup"><span data-stu-id="fdcc3-227">See also</span></span>

- [<span data-ttu-id="fdcc3-228">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="fdcc3-228">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="fdcc3-229">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="fdcc3-229">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="fdcc3-230">프로젝트 디자이너, 컴파일 페이지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fdcc3-230">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="fdcc3-231">Option Explicit 문</span><span class="sxs-lookup"><span data-stu-id="fdcc3-231">Option Explicit Statement</span></span>](option-explicit-statement.md)
- [<span data-ttu-id="fdcc3-232">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="fdcc3-232">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="fdcc3-233">방법: 개체의 멤버에 액세스</span><span class="sxs-lookup"><span data-stu-id="fdcc3-233">How to: Access Members of an Object</span></span>](../../programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [<span data-ttu-id="fdcc3-234">XML의 포함 식</span><span class="sxs-lookup"><span data-stu-id="fdcc3-234">Embedded Expressions in XML</span></span>](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="fdcc3-235">완화된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="fdcc3-235">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="fdcc3-236">Office 솔루션에서 런타임에 바인딩</span><span class="sxs-lookup"><span data-stu-id="fdcc3-236">Late Binding in Office Solutions</span></span>](/visualstudio/vsto/late-binding-in-office-solutions)
- [<span data-ttu-id="fdcc3-237">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="fdcc3-237">-optionstrict</span></span>](../../reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="fdcc3-238">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="fdcc3-238">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
