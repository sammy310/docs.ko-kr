---
description: '자세한 정보: 프로시저 매개 변수 및 인수 (Visual Basic)'
title: 프로시저 매개 변수 및 인수
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], argument lists
- values [Visual Basic], passing to procedures
- arguments [Visual Basic], passing
- procedures [Visual Basic], parameters
- Visual Basic code, argument lists
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic procedures
- parameters [Visual Basic], lists
- arguments [Visual Basic], Visual Basic procedures
- arguments [Visual Basic], procedures
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- argument lists [Visual Basic]
- procedures [Visual Basic], parameter lists
ms.assetid: ff275aff-aa13-40df-bd4c-63486db8c1e9
ms.openlocfilehash: c2239c76450f503e74dbf5f191cd212e05d11600
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100423162"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a><span data-ttu-id="e564e-103">프로시저 매개 변수 및 인수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e564e-103">Procedure Parameters and Arguments (Visual Basic)</span></span>

<span data-ttu-id="e564e-104">대부분의 경우 프로시저에는 호출 된 상황에 대 한 일부 정보가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-104">In most cases, a procedure needs some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="e564e-105">반복 되거나 공유 된 작업을 수행 하는 프로시저는 각 호출에 대해 서로 다른 정보를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-105">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="e564e-106">이 정보는 프로시저를 호출할 때 프로시저에 전달 하는 변수, 상수 및 식으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-106">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="e564e-107">*매개 변수* 는 프로시저에서 호출할 때 제공할 것으로 예상 하는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-107">A *parameter* represents a value that the procedure expects you to supply when you call it.</span></span> <span data-ttu-id="e564e-108">프로시저의 선언에서 매개 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-108">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="e564e-109">매개 변수 없이 프로시저를 정의 하거나, 매개 변수를 하나 이상 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-109">You can define a procedure with no parameters, one parameter, or more than one.</span></span> <span data-ttu-id="e564e-110">매개 변수를 지정 하는 프로시저 정의의 일부를 *매개 변수 목록* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-110">The part of the procedure definition that specifies the parameters is called the *parameter list*.</span></span>  
  
 <span data-ttu-id="e564e-111">*인수* 는 프로시저를 호출할 때 프로시저 매개 변수에 제공 하는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-111">An *argument* represents the value you supply to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="e564e-112">호출 코드는 프로시저를 호출할 때 인수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-112">The calling code supplies the arguments when it calls the procedure.</span></span> <span data-ttu-id="e564e-113">인수를 지정 하는 프로시저 호출의 일부를 *인수 목록* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-113">The part of the procedure call that specifies the arguments is called the *argument list*.</span></span>  
  
 <span data-ttu-id="e564e-114">다음 그림에서는 `safeSquareRoot` 서로 다른 두 위치에서 프로시저를 호출 하는 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-114">The following illustration shows code calling the procedure `safeSquareRoot` from two different places.</span></span> <span data-ttu-id="e564e-115">첫 번째 호출은 변수 값 `x` (4.0)을 매개 변수에 전달 `number` 하 고 `root` (2.0)의 반환 값이 변수에 할당 됩니다 `y` .</span><span class="sxs-lookup"><span data-stu-id="e564e-115">The first call passes the value of the variable `x` (4.0) to the parameter `number`, and the return value in `root` (2.0) is assigned to the variable `y`.</span></span> <span data-ttu-id="e564e-116">두 번째 호출은 리터럴 값 9.0를에 전달 하 `number` 고 반환 값 (3.0)을 변수에 할당 합니다 `z` .</span><span class="sxs-lookup"><span data-stu-id="e564e-116">The second call passes the literal value 9.0 to `number`, and assigns the return value (3.0) to variable `z`.</span></span>  
  
 ![매개 변수에 인수를 전달 하는 방법을 보여 주는 다이어그램](./media/procedure-parameters-and-arguments/pass-argument-parameter.gif)  
  
 <span data-ttu-id="e564e-118">자세한 내용은 [매개 변수와 인수 간의 차이점](./differences-between-parameters-and-arguments.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e564e-118">For more information, see [Differences Between Parameters and Arguments](./differences-between-parameters-and-arguments.md).</span></span>  
  
## <a name="parameter-data-type"></a><span data-ttu-id="e564e-119">매개 변수 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e564e-119">Parameter Data Type</span></span>  

 <span data-ttu-id="e564e-120">선언에서 절을 사용 하 여 매개 변수의 데이터 형식을 정의 `As` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-120">You define a data type for a parameter by using the `As` clause in its declaration.</span></span> <span data-ttu-id="e564e-121">예를 들어 다음 함수는 문자열과 정수를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-121">For example, the following function accepts a string and an integer.</span></span>  
  
 [!code-vb[VbVbcnProcedures#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#32)]  
  
 <span data-ttu-id="e564e-122">형식 검사 스위치 ([Option Strict 문](../../../language-reference/statements/option-strict-statement.md))가 절 인 경우에는 모든 매개 변수가 사용 하는 경우를 제외 하 고는 `Off,` `As` 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-122">If the type checking switch ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) is `Off,` the `As` clause is optional, except that if any one parameter uses it, all parameters must use it.</span></span> <span data-ttu-id="e564e-123">형식 검사가 인 경우 `On` `As` 모든 프로시저 매개 변수에 절이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-123">If type checking is `On`, the `As` clause is required for all procedure parameters.</span></span>  
  
 <span data-ttu-id="e564e-124">호출 코드에서 매개 변수와 같이 해당 매개 변수와 다른 데이터 형식의 인수를 제공할 것으로 예상 하는 경우 다음 중 `Byte` 하나를 `String` 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-124">If the calling code expects to supply an argument with a data type different from that of its corresponding parameter, such as `Byte` to a `String` parameter, it must do one of the following:</span></span>  
  
- <span data-ttu-id="e564e-125">매개 변수 데이터 형식으로 확장 되는 데이터 형식의 인수만 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-125">Supply only arguments with data types that widen to the parameter data type;</span></span>  
  
- <span data-ttu-id="e564e-126">`Option Strict Off`암시적 축소 변환을 허용 하도록 설정 합니다. 또는</span><span class="sxs-lookup"><span data-stu-id="e564e-126">Set `Option Strict Off` to allow implicit narrowing conversions; or</span></span>  
  
- <span data-ttu-id="e564e-127">변환 키워드를 사용 하 여 데이터 형식을 명시적으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-127">Use a conversion keyword to explicitly convert the data type.</span></span>  
  
### <a name="type-parameters"></a><span data-ttu-id="e564e-128">형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="e564e-128">Type Parameters</span></span>  

 <span data-ttu-id="e564e-129">*제네릭 프로시저* 는 일반 매개 변수 외에도 하나 이상의 *형식 매개 변수도* 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-129">A *generic procedure* also defines one or more *type parameters* in addition to its normal parameters.</span></span> <span data-ttu-id="e564e-130">제네릭 프로시저를 사용 하면 호출 코드가 프로시저를 호출할 때마다 서로 다른 데이터 형식을 전달할 수 있으므로 각 개별 호출의 요구 사항에 맞게 데이터 형식을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e564e-130">A generic procedure allows the calling code to pass different data types each time it calls the procedure, so it can tailor the data types to the requirements of each individual call.</span></span> <span data-ttu-id="e564e-131">[Generic Procedures in Visual Basic](../data-types/generic-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e564e-131">See [Generic Procedures in Visual Basic](../data-types/generic-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e564e-132">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e564e-132">See also</span></span>

- [<span data-ttu-id="e564e-133">절차</span><span class="sxs-lookup"><span data-stu-id="e564e-133">Procedures</span></span>](./index.md)
- [<span data-ttu-id="e564e-134">하위 프로시저</span><span class="sxs-lookup"><span data-stu-id="e564e-134">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="e564e-135">함수 프로시저</span><span class="sxs-lookup"><span data-stu-id="e564e-135">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="e564e-136">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="e564e-136">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="e564e-137">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="e564e-137">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="e564e-138">방법: 프로시저의 매개 변수 정의</span><span class="sxs-lookup"><span data-stu-id="e564e-138">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="e564e-139">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="e564e-139">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="e564e-140">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="e564e-140">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="e564e-141">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="e564e-141">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="e564e-142">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="e564e-142">Type Conversions in Visual Basic</span></span>](../data-types/type-conversions.md)
