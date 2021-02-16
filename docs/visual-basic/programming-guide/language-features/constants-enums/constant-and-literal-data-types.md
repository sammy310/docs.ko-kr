---
description: '다음에 대 한 자세한 정보: 상수 및 리터럴 데이터 형식 (Visual Basic)'
title: 상수 및 리터럴 데이터 형식
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: e750b1e5746f935c7878e186d064060d0fa055dc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475437"
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="7206c-103">상수 및 리터럴 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7206c-103">Constant and Literal Data Types (Visual Basic)</span></span>

<span data-ttu-id="7206c-104">리터럴은 변수 값 또는 식의 결과 (예: 숫자 3 또는 문자열 "Hello")가 아니라 자체로 표현 되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7206c-104">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="7206c-105">상수는 리터럴 자리를 사용 하 고 값이 변경 될 수 있는 변수와 달리 프로그램 전체에서 동일한 값을 유지 하는 의미 있는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7206c-105">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="7206c-106">[Option 유추](../../../language-reference/statements/option-infer-statement.md) 는이 `Off` 고 [option Strict](../../../language-reference/statements/option-strict-statement.md) 는 이면 `On` 모든 상수를 데이터 형식으로 명시적으로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7206c-106">When [Option Infer](../../../language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="7206c-107">다음 예제에서의 데이터 형식은 `MyByte` 데이터 형식으로 명시적으로 선언 됩니다 `Byte` .</span><span class="sxs-lookup"><span data-stu-id="7206c-107">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 <span data-ttu-id="7206c-108">`Option Infer`가 `On` 이거나 `Option Strict` 가 인 경우 `Off` 절을 사용 하 여 데이터 형식을 지정 하지 않고 상수를 선언할 수 있습니다 `As` .</span><span class="sxs-lookup"><span data-stu-id="7206c-108">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="7206c-109">컴파일러는 식의 형식에서 상수의 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7206c-109">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="7206c-110">숫자 정수 리터럴은 기본적으로 데이터 형식으로 캐스팅 됩니다 `Integer` .</span><span class="sxs-lookup"><span data-stu-id="7206c-110">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="7206c-111">부동 소수점 숫자의 기본 데이터 형식은이 `Double` 고 키워드 `True` 와는 `False` 상수를 지정 합니다 `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="7206c-111">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="7206c-112">리터럴 및 형식 강제 변환</span><span class="sxs-lookup"><span data-stu-id="7206c-112">Literals and Type Coercion</span></span>  

 <span data-ttu-id="7206c-113">경우에 따라 리터럴을 특정 데이터 형식으로 강제 지정할 수 있습니다. 예를 들어, 형식의 변수에 특히 긴 정수 리터럴 값을 할당 하는 경우 `Decimal` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7206c-113">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="7206c-114">다음 예에서는 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7206c-114">The following example produces an error:</span></span>  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="7206c-115">리터럴 표현에서 발생 하는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="7206c-115">The error results from the representation of the literal.</span></span> <span data-ttu-id="7206c-116">`Decimal`이 값은 데이터 형식에 포함 될 수 있지만 리터럴은 암시적으로로 표현 될 `Long` 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7206c-116">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="7206c-117">리터럴를 특정 데이터 형식으로 강제 변환할 수 있습니다. 여기에는 형식 문자를 추가 하거나 묶기 문자 내에 배치 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="7206c-117">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="7206c-118">형식 문자 또는 바깥쪽 문자는 문자를 사용 하지 않고 리터럴 앞뒤에 바로 앞 이나 뒤에와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7206c-118">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="7206c-119">이전 예제가 작동 하도록 하려면 형식 문자를 리터럴에 추가 하면 `D` 됩니다. 그러면 다음과 같이 표시 됩니다 `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="7206c-119">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 <span data-ttu-id="7206c-120">다음 예제에서는 형식 문자 및 묶기 문자를 올바르게 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7206c-120">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 <span data-ttu-id="7206c-121">다음 표에서는 Visual Basic에서 사용할 수 있는 바깥쪽 문자 및 형식 문자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7206c-121">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="7206c-122">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7206c-122">Data type</span></span>|<span data-ttu-id="7206c-123">묶기 문자</span><span class="sxs-lookup"><span data-stu-id="7206c-123">Enclosing character</span></span>|<span data-ttu-id="7206c-124">추가 된 형식 문자</span><span class="sxs-lookup"><span data-stu-id="7206c-124">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="7206c-125">(없음)</span><span class="sxs-lookup"><span data-stu-id="7206c-125">(none)</span></span>|<span data-ttu-id="7206c-126">(없음)</span><span class="sxs-lookup"><span data-stu-id="7206c-126">(none)</span></span>|  
|`Byte`|<span data-ttu-id="7206c-127">(없음)</span><span class="sxs-lookup"><span data-stu-id="7206c-127">(none)</span></span>|<span data-ttu-id="7206c-128">(없음)</span><span class="sxs-lookup"><span data-stu-id="7206c-128">(none)</span></span>|  
|`Char`|<span data-ttu-id="7206c-129">"</span><span class="sxs-lookup"><span data-stu-id="7206c-129">"</span></span>|<span data-ttu-id="7206c-130">C</span><span class="sxs-lookup"><span data-stu-id="7206c-130">C</span></span>|  
|`Date`|#|<span data-ttu-id="7206c-131">(없음)</span><span class="sxs-lookup"><span data-stu-id="7206c-131">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="7206c-132">(없음)</span><span class="sxs-lookup"><span data-stu-id="7206c-132">(none)</span></span>|<span data-ttu-id="7206c-133">D 또는 @</span><span class="sxs-lookup"><span data-stu-id="7206c-133">D or @</span></span>|  
|`Double`|<span data-ttu-id="7206c-134">(없음)</span><span class="sxs-lookup"><span data-stu-id="7206c-134">(none)</span></span>|<span data-ttu-id="7206c-135">R 또는 #</span><span class="sxs-lookup"><span data-stu-id="7206c-135">R or #</span></span>|  
|`Integer`|<span data-ttu-id="7206c-136">(없음)</span><span class="sxs-lookup"><span data-stu-id="7206c-136">(none)</span></span>|<span data-ttu-id="7206c-137">I 또는%</span><span class="sxs-lookup"><span data-stu-id="7206c-137">I or %</span></span>|  
|`Long`|<span data-ttu-id="7206c-138">(없음)</span><span class="sxs-lookup"><span data-stu-id="7206c-138">(none)</span></span>|<span data-ttu-id="7206c-139">L 또는 &</span><span class="sxs-lookup"><span data-stu-id="7206c-139">L or &</span></span>|  
|`Short`|<span data-ttu-id="7206c-140">(없음)</span><span class="sxs-lookup"><span data-stu-id="7206c-140">(none)</span></span>|<span data-ttu-id="7206c-141">S</span><span class="sxs-lookup"><span data-stu-id="7206c-141">S</span></span>|  
|`Single`|<span data-ttu-id="7206c-142">(없음)</span><span class="sxs-lookup"><span data-stu-id="7206c-142">(none)</span></span>|<span data-ttu-id="7206c-143">F 또는!</span><span class="sxs-lookup"><span data-stu-id="7206c-143">F or !</span></span>|  
|`String`|<span data-ttu-id="7206c-144">"</span><span class="sxs-lookup"><span data-stu-id="7206c-144">"</span></span>|<span data-ttu-id="7206c-145">(없음)</span><span class="sxs-lookup"><span data-stu-id="7206c-145">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7206c-146">추가 정보</span><span class="sxs-lookup"><span data-stu-id="7206c-146">See also</span></span>

- [<span data-ttu-id="7206c-147">사용자 정의 상수</span><span class="sxs-lookup"><span data-stu-id="7206c-147">User-Defined Constants</span></span>](user-defined-constants.md)
- [<span data-ttu-id="7206c-148">방법: 상수 선언</span><span class="sxs-lookup"><span data-stu-id="7206c-148">How to: Declare A Constant</span></span>](how-to-declare-a-constant.md)
- [<span data-ttu-id="7206c-149">상수 개요</span><span class="sxs-lookup"><span data-stu-id="7206c-149">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="7206c-150">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="7206c-150">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="7206c-151">Option Explicit 문</span><span class="sxs-lookup"><span data-stu-id="7206c-151">Option Explicit Statement</span></span>](../../../language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="7206c-152">열거형 개요</span><span class="sxs-lookup"><span data-stu-id="7206c-152">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="7206c-153">방법: 열거형 선언</span><span class="sxs-lookup"><span data-stu-id="7206c-153">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="7206c-154">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="7206c-154">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="7206c-155">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7206c-155">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="7206c-156">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="7206c-156">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
