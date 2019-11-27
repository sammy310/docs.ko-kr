---
title: '방법: 프로시저의 매개 변수 정의'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
ms.openlocfilehash: 411959a7be92ea49a59558b508e992bfba8eff95
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344878"
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a><span data-ttu-id="fa9bf-102">방법: 프로시저의 매개 변수 정의(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa9bf-102">How to: Define a Parameter for a Procedure (Visual Basic)</span></span>
<span data-ttu-id="fa9bf-103">*매개 변수* 를 사용 하면 호출 코드에서 호출 시 프로시저에 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-103">A *parameter* allows the calling code to pass a value to the procedure when it calls it.</span></span> <span data-ttu-id="fa9bf-104">변수를 선언 하는 것과 동일한 방식으로 프로시저에 대 한 각 매개 변수를 선언 하 고 해당 이름 및 데이터 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-104">You declare each parameter for a procedure the same way you declare a variable, specifying its name and data type.</span></span> <span data-ttu-id="fa9bf-105">또한 전달 메커니즘과 매개 변수가 선택적인 지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-105">You also specify the passing mechanism, and whether the parameter is optional.</span></span>  
  
 <span data-ttu-id="fa9bf-106">자세한 내용은 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-106">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-define-a-procedure-parameter"></a><span data-ttu-id="fa9bf-107">프로시저 매개 변수를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="fa9bf-107">To define a procedure parameter</span></span>  
  
1. <span data-ttu-id="fa9bf-108">프로시저 선언에서 매개 변수 이름을 다른 매개 변수에서 쉼표로 구분 하 여 프로시저의 매개 변수 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-108">In the procedure declaration, add the parameter name to the procedure's parameter list, separating it from other parameters by commas.</span></span>  
  
2. <span data-ttu-id="fa9bf-109">매개 변수의 데이터 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-109">Decide the data type of the parameter.</span></span>  
  
3. <span data-ttu-id="fa9bf-110">매개 변수 이름 뒤에 `As` 절을 사용 하 여 데이터 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-110">Follow the parameter name with an `As` clause to specify the data type.</span></span>  
  
4. <span data-ttu-id="fa9bf-111">매개 변수에 대해 원하는 전달 메커니즘을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-111">Decide the passing mechanism you want for the parameter.</span></span> <span data-ttu-id="fa9bf-112">프로시저에서 호출 코드의 값을 변경할 수 없도록 하려면 일반적으로 매개 변수를 값으로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-112">Normally you pass a parameter by value, unless you want the procedure to be able to change its value in the calling code.</span></span>  
  
5. <span data-ttu-id="fa9bf-113">매개 변수 이름 앞에 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 를 사용 하 여 전달 메커니즘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-113">Precede the parameter name with [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) to specify the passing mechanism.</span></span> <span data-ttu-id="fa9bf-114">자세한 내용은 [값으로 인수를 전달 하는 것과 참조로 인수를 전달 하는 차이점](./differences-between-passing-an-argument-by-value-and-by-reference.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-114">For more information, see [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
6. <span data-ttu-id="fa9bf-115">매개 변수가 선택적 요소 이면 전달 메커니즘 앞에 [옵션](../../../../visual-basic/language-reference/modifiers/optional.md) 을 추가 하 고 매개 변수 데이터 형식에 등호 (`=`)와 기본값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-115">If the parameter is optional, precede the passing mechanism with [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) and follow the parameter data type with an equal sign (`=`) and a default value.</span></span>  
  
     <span data-ttu-id="fa9bf-116">다음 예에서는 세 개의 매개 변수를 사용 하 여 `Sub` 프로시저의 개요를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-116">The following example defines the outline of a `Sub` procedure with three parameters.</span></span> <span data-ttu-id="fa9bf-117">처음 두 개는 필수 항목이 며 세 번째는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-117">The first two are required and the third is optional.</span></span> <span data-ttu-id="fa9bf-118">매개 변수 선언은 매개 변수 목록에서 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-118">The parameter declarations are separated in the parameter list by commas.</span></span>  
  
     [!code-vb[VbVbcnProcedures#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#33)]  
  
     <span data-ttu-id="fa9bf-119">첫 번째 매개 변수는 `customer` 개체를 수락 하 고, 인수가 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)로 전달 되기 때문에 `c`에 전달 된 변수를 직접 업데이트할 수 `updateCustomer`.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-119">The first parameter accepts a `customer` object, and `updateCustomer` can directly update the variable passed to `c` because the argument is passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="fa9bf-120">이 프로시저는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)로 전달 되기 때문에 마지막 두 인수 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-120">The procedure cannot change the values of the last two arguments because they are passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
     <span data-ttu-id="fa9bf-121">호출 코드가 `level` 매개 변수에 대 한 값을 제공 하지 않으면 Visual Basic 기본값 0으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-121">If the calling code does not supply a value for the `level` parameter, Visual Basic sets it to the default value of 0.</span></span>  
  
     <span data-ttu-id="fa9bf-122">형식 검사 스위치 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))가 `Off`경우 매개 변수를 정의할 때 `As` 절은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-122">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off`, the `As` clause is optional when you define a parameter.</span></span> <span data-ttu-id="fa9bf-123">그러나 한 매개 변수가 `As` 절을 사용 하는 경우 모든 매개 변수가이를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-123">However, if any one parameter uses an `As` clause, all of them must use it.</span></span> <span data-ttu-id="fa9bf-124">형식 검사 스위치가 `On`경우 모든 매개 변수 정의에 대해 `As` 절이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-124">If the type checking switch is `On`, the `As` clause is required for every parameter definition.</span></span>  
  
     <span data-ttu-id="fa9bf-125">모든 프로그래밍 요소에 대 한 데이터 형식을 지정 하는 것을 *강력한 형식화*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-125">Specifying data types for all your programming elements is known as *strong typing*.</span></span> <span data-ttu-id="fa9bf-126">`Option Strict On`를 설정 하는 경우 Visual Basic 강력한 입력을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-126">When you set `Option Strict On`, Visual Basic enforces strong typing.</span></span> <span data-ttu-id="fa9bf-127">다음과 같은 이유로이 작업을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-127">This is strongly recommended, for the following reasons:</span></span>  
  
    - <span data-ttu-id="fa9bf-128">변수 및 매개 변수에 대해 IntelliSense를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-128">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="fa9bf-129">이렇게 하면 코드에 입력할 때 해당 속성 및 기타 멤버를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-129">This allows you to see their properties and other members as you type in your code.</span></span>  
  
    - <span data-ttu-id="fa9bf-130">컴파일러에서 형식 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-130">It allows the compiler to perform type checking.</span></span> <span data-ttu-id="fa9bf-131">이렇게 하면 오버플로와 같은 오류로 인해 런타임에 실패할 수 있는 문을 catch 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-131">This helps catch statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="fa9bf-132">또한 지원 하지 않는 개체의 메서드에 대 한 호출을 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-132">It also catches calls to methods on objects that do not support them.</span></span>  
  
    - <span data-ttu-id="fa9bf-133">그러면 코드 실행 속도가 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-133">It results in faster execution of your code.</span></span> <span data-ttu-id="fa9bf-134">한 가지 이유는 프로그래밍 요소에 대 한 데이터 형식을 지정 하지 않는 경우 Visual Basic 컴파일러에서 `Object` 형식을 할당 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-134">One reason for this is that if you do not specify a data type for a programming element, the Visual Basic compiler assigns it the `Object` type.</span></span> <span data-ttu-id="fa9bf-135">컴파일된 코드에서 `Object`와 다른 데이터 형식 간에 변환을 수행 해야 하 여 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa9bf-135">Your compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa9bf-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa9bf-136">See also</span></span>

- [<span data-ttu-id="fa9bf-137">절차</span><span class="sxs-lookup"><span data-stu-id="fa9bf-137">Procedures</span></span>](./index.md)
- [<span data-ttu-id="fa9bf-138">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="fa9bf-138">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="fa9bf-139">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="fa9bf-139">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="fa9bf-140">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="fa9bf-140">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="fa9bf-141">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="fa9bf-141">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="fa9bf-142">재귀 프로시저</span><span class="sxs-lookup"><span data-stu-id="fa9bf-142">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="fa9bf-143">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="fa9bf-143">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="fa9bf-144">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="fa9bf-144">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="fa9bf-145">개체 지향 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa9bf-145">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
