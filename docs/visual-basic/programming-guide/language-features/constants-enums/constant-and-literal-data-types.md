---
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
ms.openlocfilehash: 8ebecddfab0724023c269e92c1fc5534f096bf1c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333726"
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="f785e-102">상수 및 리터럴 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f785e-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="f785e-103">리터럴은 변수 값 또는 식의 결과 (예: 숫자 3 또는 문자열 "Hello")가 아니라 자체로 표현 되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f785e-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="f785e-104">상수는 리터럴 자리를 사용 하 고 값이 변경 될 수 있는 변수와 달리 프로그램 전체에서 동일한 값을 유지 하는 의미 있는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f785e-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="f785e-105">[옵션 유추](../../../../visual-basic/language-reference/statements/option-infer-statement.md) 가 `Off` 되 고 [option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 가 `On`경우 데이터 형식을 사용 하 여 명시적으로 모든 상수를 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f785e-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="f785e-106">다음 예에서는 `MyByte` 데이터 형식이 명시적으로 `Byte`데이터 형식으로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f785e-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 <span data-ttu-id="f785e-107">`Option Infer` `On` 또는 `Option Strict` `Off`경우에는 `As` 절을 사용 하 여 데이터 형식을 지정 하지 않고 상수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f785e-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="f785e-108">컴파일러는 식의 형식에서 상수의 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f785e-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="f785e-109">숫자 정수 리터럴은 기본적으로 `Integer` 데이터 형식으로 캐스팅 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f785e-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="f785e-110">부동 소수점 숫자의 기본 데이터 형식은 `Double`되며 키워드 `True` 및 `False` `Boolean` 상수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f785e-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="f785e-111">리터럴 및 형식 강제 변환</span><span class="sxs-lookup"><span data-stu-id="f785e-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="f785e-112">경우에 따라 리터럴을 특정 데이터 형식으로 강제 지정할 수 있습니다. 예를 들어 `Decimal`형식의 변수에 특히 긴 정수 리터럴 값을 할당 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="f785e-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="f785e-113">다음 예에서는 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f785e-113">The following example produces an error:</span></span>  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="f785e-114">리터럴 표현에서 발생 하는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="f785e-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="f785e-115">`Decimal` 데이터 형식에는이 값이 너무 클 수 있지만 리터럴은 암시적으로 `Long`으로 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f785e-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="f785e-116">리터럴를 특정 데이터 형식으로 강제 변환할 수 있습니다. 여기에는 형식 문자를 추가 하거나 묶기 문자 내에 배치 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f785e-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="f785e-117">형식 문자 또는 바깥쪽 문자는 문자를 사용 하지 않고 리터럴 앞뒤에 바로 앞 이나 뒤에와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f785e-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="f785e-118">이전 예제를 사용 하려면 `D` 형식 문자를 리터럴에 추가 하 여 `Decimal`으로 표시 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f785e-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 <span data-ttu-id="f785e-119">다음 예제에서는 형식 문자 및 묶기 문자를 올바르게 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f785e-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 <span data-ttu-id="f785e-120">다음 표에서는 Visual Basic에서 사용할 수 있는 바깥쪽 문자 및 형식 문자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f785e-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="f785e-121">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f785e-121">Data type</span></span>|<span data-ttu-id="f785e-122">묶기 문자</span><span class="sxs-lookup"><span data-stu-id="f785e-122">Enclosing character</span></span>|<span data-ttu-id="f785e-123">추가 된 형식 문자</span><span class="sxs-lookup"><span data-stu-id="f785e-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="f785e-124">(없음)</span><span class="sxs-lookup"><span data-stu-id="f785e-124">(none)</span></span>|<span data-ttu-id="f785e-125">(없음)</span><span class="sxs-lookup"><span data-stu-id="f785e-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="f785e-126">(없음)</span><span class="sxs-lookup"><span data-stu-id="f785e-126">(none)</span></span>|<span data-ttu-id="f785e-127">(없음)</span><span class="sxs-lookup"><span data-stu-id="f785e-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="f785e-128">"</span><span class="sxs-lookup"><span data-stu-id="f785e-128">"</span></span>|<span data-ttu-id="f785e-129">C</span><span class="sxs-lookup"><span data-stu-id="f785e-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="f785e-130">(없음)</span><span class="sxs-lookup"><span data-stu-id="f785e-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="f785e-131">(없음)</span><span class="sxs-lookup"><span data-stu-id="f785e-131">(none)</span></span>|<span data-ttu-id="f785e-132">D 또는 @</span><span class="sxs-lookup"><span data-stu-id="f785e-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="f785e-133">(없음)</span><span class="sxs-lookup"><span data-stu-id="f785e-133">(none)</span></span>|<span data-ttu-id="f785e-134">R 또는 #</span><span class="sxs-lookup"><span data-stu-id="f785e-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="f785e-135">(없음)</span><span class="sxs-lookup"><span data-stu-id="f785e-135">(none)</span></span>|<span data-ttu-id="f785e-136">I 또는%</span><span class="sxs-lookup"><span data-stu-id="f785e-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="f785e-137">(없음)</span><span class="sxs-lookup"><span data-stu-id="f785e-137">(none)</span></span>|<span data-ttu-id="f785e-138">L 또는 &</span><span class="sxs-lookup"><span data-stu-id="f785e-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="f785e-139">(없음)</span><span class="sxs-lookup"><span data-stu-id="f785e-139">(none)</span></span>|<span data-ttu-id="f785e-140">S</span><span class="sxs-lookup"><span data-stu-id="f785e-140">S</span></span>|  
|`Single`|<span data-ttu-id="f785e-141">(없음)</span><span class="sxs-lookup"><span data-stu-id="f785e-141">(none)</span></span>|<span data-ttu-id="f785e-142">F 또는!</span><span class="sxs-lookup"><span data-stu-id="f785e-142">F or !</span></span>|  
|`String`|<span data-ttu-id="f785e-143">"</span><span class="sxs-lookup"><span data-stu-id="f785e-143">"</span></span>|<span data-ttu-id="f785e-144">(없음)</span><span class="sxs-lookup"><span data-stu-id="f785e-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f785e-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f785e-145">See also</span></span>

- [<span data-ttu-id="f785e-146">사용자 정의 상수</span><span class="sxs-lookup"><span data-stu-id="f785e-146">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)
- [<span data-ttu-id="f785e-147">방법: 상수 선언</span><span class="sxs-lookup"><span data-stu-id="f785e-147">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)
- [<span data-ttu-id="f785e-148">상수 개요</span><span class="sxs-lookup"><span data-stu-id="f785e-148">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="f785e-149">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="f785e-149">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="f785e-150">Option Explicit 문</span><span class="sxs-lookup"><span data-stu-id="f785e-150">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="f785e-151">열거형 개요</span><span class="sxs-lookup"><span data-stu-id="f785e-151">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [<span data-ttu-id="f785e-152">방법: 열거형 선언</span><span class="sxs-lookup"><span data-stu-id="f785e-152">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="f785e-153">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="f785e-153">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="f785e-154">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f785e-154">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="f785e-155">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="f785e-155">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
