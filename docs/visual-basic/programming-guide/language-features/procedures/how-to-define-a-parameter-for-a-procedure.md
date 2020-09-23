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
ms.openlocfilehash: 73b53dcf7cd732af1a4f1d23cd0d3b9ef5b5529b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91087442"
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a><span data-ttu-id="39d5a-102">방법: 프로시저의 매개 변수 정의(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39d5a-102">How to: Define a Parameter for a Procedure (Visual Basic)</span></span>

<span data-ttu-id="39d5a-103">*매개 변수* 를 사용 하면 호출 코드에서 호출 시 프로시저에 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-103">A *parameter* allows the calling code to pass a value to the procedure when it calls it.</span></span> <span data-ttu-id="39d5a-104">변수를 선언 하는 것과 동일한 방식으로 프로시저에 대 한 각 매개 변수를 선언 하 고 해당 이름 및 데이터 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-104">You declare each parameter for a procedure the same way you declare a variable, specifying its name and data type.</span></span> <span data-ttu-id="39d5a-105">또한 전달 메커니즘과 매개 변수가 선택적인 지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-105">You also specify the passing mechanism, and whether the parameter is optional.</span></span>  
  
 <span data-ttu-id="39d5a-106">자세한 내용은 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39d5a-106">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-define-a-procedure-parameter"></a><span data-ttu-id="39d5a-107">프로시저 매개 변수를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="39d5a-107">To define a procedure parameter</span></span>  
  
1. <span data-ttu-id="39d5a-108">프로시저 선언에서 매개 변수 이름을 다른 매개 변수에서 쉼표로 구분 하 여 프로시저의 매개 변수 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-108">In the procedure declaration, add the parameter name to the procedure's parameter list, separating it from other parameters by commas.</span></span>  
  
2. <span data-ttu-id="39d5a-109">매개 변수의 데이터 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-109">Decide the data type of the parameter.</span></span>  
  
3. <span data-ttu-id="39d5a-110">`As`데이터 형식을 지정 하려면 매개 변수 이름 뒤에 절을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-110">Follow the parameter name with an `As` clause to specify the data type.</span></span>  
  
4. <span data-ttu-id="39d5a-111">매개 변수에 대해 원하는 전달 메커니즘을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-111">Decide the passing mechanism you want for the parameter.</span></span> <span data-ttu-id="39d5a-112">프로시저에서 호출 코드의 값을 변경할 수 없도록 하려면 일반적으로 매개 변수를 값으로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-112">Normally you pass a parameter by value, unless you want the procedure to be able to change its value in the calling code.</span></span>  
  
5. <span data-ttu-id="39d5a-113">매개 변수 이름 앞에 [ByVal](../../../language-reference/modifiers/byval.md) 또는 [ByRef](../../../language-reference/modifiers/byref.md) 를 사용 하 여 전달 메커니즘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-113">Precede the parameter name with [ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md) to specify the passing mechanism.</span></span> <span data-ttu-id="39d5a-114">자세한 내용은 [값으로 인수를 전달 하는 것과 참조로 인수를 전달 하는 차이점](./differences-between-passing-an-argument-by-value-and-by-reference.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39d5a-114">For more information, see [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
6. <span data-ttu-id="39d5a-115">매개 변수가 선택적 요소 이면 전달 메커니즘 앞에 [옵션](../../../language-reference/modifiers/optional.md) 을 추가 하 고 매개 변수 데이터 형식에 등호 ( `=` )와 기본값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-115">If the parameter is optional, precede the passing mechanism with [Optional](../../../language-reference/modifiers/optional.md) and follow the parameter data type with an equal sign (`=`) and a default value.</span></span>  
  
     <span data-ttu-id="39d5a-116">다음 예에서는 `Sub` 세 개의 매개 변수가 있는 프로시저의 개요를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-116">The following example defines the outline of a `Sub` procedure with three parameters.</span></span> <span data-ttu-id="39d5a-117">처음 두 개는 필수 항목이 며 세 번째는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-117">The first two are required and the third is optional.</span></span> <span data-ttu-id="39d5a-118">매개 변수 선언은 매개 변수 목록에서 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-118">The parameter declarations are separated in the parameter list by commas.</span></span>  
  
     [!code-vb[VbVbcnProcedures#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#33)]  
  
     <span data-ttu-id="39d5a-119">첫 번째 매개 변수는 `customer` 개체를 수락 하 고 `updateCustomer` `c` 인수가 [ByRef](../../../language-reference/modifiers/byref.md)로 전달 되기 때문에에 전달 된 변수를 직접 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-119">The first parameter accepts a `customer` object, and `updateCustomer` can directly update the variable passed to `c` because the argument is passed [ByRef](../../../language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="39d5a-120">이 프로시저는 [ByVal](../../../language-reference/modifiers/byval.md)로 전달 되기 때문에 마지막 두 인수 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-120">The procedure cannot change the values of the last two arguments because they are passed [ByVal](../../../language-reference/modifiers/byval.md).</span></span>  
  
     <span data-ttu-id="39d5a-121">호출 하는 코드에서 매개 변수의 값을 제공 하지 않으면이 값을 `level` 기본값인 0으로 설정 Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="39d5a-121">If the calling code does not supply a value for the `level` parameter, Visual Basic sets it to the default value of 0.</span></span>  
  
     <span data-ttu-id="39d5a-122">형식 검사 스위치 ([Option Strict 문](../../../language-reference/statements/option-strict-statement.md))가 인 경우 `Off` `As` 매개 변수를 정의할 때 절은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-122">If the type checking switch ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) is `Off`, the `As` clause is optional when you define a parameter.</span></span> <span data-ttu-id="39d5a-123">그러나 한 매개 변수에서 절을 사용 하는 경우 모든 매개 변수는 `As` 이를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-123">However, if any one parameter uses an `As` clause, all of them must use it.</span></span> <span data-ttu-id="39d5a-124">형식 검사 스위치가 인 경우 `On` `As` 모든 매개 변수 정의에 절이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-124">If the type checking switch is `On`, the `As` clause is required for every parameter definition.</span></span>  
  
     <span data-ttu-id="39d5a-125">모든 프로그래밍 요소에 대 한 데이터 형식을 지정 하는 것을 *강력한 형식화*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-125">Specifying data types for all your programming elements is known as *strong typing*.</span></span> <span data-ttu-id="39d5a-126">를 설정 하면 `Option Strict On` Visual Basic 강력한 형식을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-126">When you set `Option Strict On`, Visual Basic enforces strong typing.</span></span> <span data-ttu-id="39d5a-127">다음과 같은 이유로이 작업을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-127">This is strongly recommended, for the following reasons:</span></span>  
  
    - <span data-ttu-id="39d5a-128">변수 및 매개 변수에 대해 IntelliSense를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-128">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="39d5a-129">이렇게 하면 코드에 입력할 때 해당 속성 및 기타 멤버를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-129">This allows you to see their properties and other members as you type in your code.</span></span>  
  
    - <span data-ttu-id="39d5a-130">컴파일러에서 형식 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-130">It allows the compiler to perform type checking.</span></span> <span data-ttu-id="39d5a-131">이렇게 하면 오버플로와 같은 오류로 인해 런타임에 실패할 수 있는 문을 catch 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-131">This helps catch statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="39d5a-132">또한 지원 하지 않는 개체의 메서드에 대 한 호출을 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-132">It also catches calls to methods on objects that do not support them.</span></span>  
  
    - <span data-ttu-id="39d5a-133">그러면 코드 실행 속도가 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="39d5a-133">It results in faster execution of your code.</span></span> <span data-ttu-id="39d5a-134">한 가지 이유는 프로그래밍 요소에 대 한 데이터 형식을 지정 하지 않는 경우 Visual Basic 컴파일러에서 해당 형식을 할당 하는 것입니다 `Object` .</span><span class="sxs-lookup"><span data-stu-id="39d5a-134">One reason for this is that if you do not specify a data type for a programming element, the Visual Basic compiler assigns it the `Object` type.</span></span> <span data-ttu-id="39d5a-135">컴파일된 코드에서 및 기타 데이터 형식 사이를 변환 해야 하 여 성능이 저하 될 수 있습니다 `Object` .</span><span class="sxs-lookup"><span data-stu-id="39d5a-135">Your compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39d5a-136">참조</span><span class="sxs-lookup"><span data-stu-id="39d5a-136">See also</span></span>

- [<span data-ttu-id="39d5a-137">절차</span><span class="sxs-lookup"><span data-stu-id="39d5a-137">Procedures</span></span>](./index.md)
- [<span data-ttu-id="39d5a-138">하위 프로시저</span><span class="sxs-lookup"><span data-stu-id="39d5a-138">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="39d5a-139">함수 프로시저</span><span class="sxs-lookup"><span data-stu-id="39d5a-139">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="39d5a-140">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="39d5a-140">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="39d5a-141">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="39d5a-141">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="39d5a-142">재귀 프로시저</span><span class="sxs-lookup"><span data-stu-id="39d5a-142">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="39d5a-143">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="39d5a-143">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="39d5a-144">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="39d5a-144">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="39d5a-145">개체 지향 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39d5a-145">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
