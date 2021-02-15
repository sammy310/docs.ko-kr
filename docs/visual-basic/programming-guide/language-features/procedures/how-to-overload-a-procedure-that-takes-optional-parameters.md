---
description: '자세한 정보: 방법: 선택적 매개 변수를 사용 하는 프로시저 오버 로드 (Visual Basic)'
title: '방법: 선택적 매개 변수를 사용하는 프로시저 오버로드'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], optional parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
ms.openlocfilehash: dccef9d27c08ede2f35edc02c8bd5116aa6969b2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472945"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a><span data-ttu-id="2a9f7-103">방법: 선택적 매개 변수를 사용하는 프로시저 오버로드(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a9f7-103">How to: Overload a Procedure that Takes Optional Parameters (Visual Basic)</span></span>

<span data-ttu-id="2a9f7-104">프로시저에 하나 이상의 [선택적](../../../language-reference/modifiers/optional.md) 매개 변수가 있는 경우 해당 암시적 오버 로드와 일치 하는 오버 로드 된 버전을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-104">If a procedure has one or more [Optional](../../../language-reference/modifiers/optional.md) parameters, you cannot define an overloaded version matching any of its implicit overloads.</span></span> <span data-ttu-id="2a9f7-105">자세한 내용은 [오버 로드 절차의 고려 사항](./considerations-in-overloading-procedures.md)에서 "선택적 매개 변수에 대 한 암시적 오버 로드"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-105">For more information, see "Implicit Overloads for Optional Parameters" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="one-optional-parameter"></a><span data-ttu-id="2a9f7-106">하나의 선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="2a9f7-106">One Optional Parameter</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a><span data-ttu-id="2a9f7-107">선택적 매개 변수 하나를 사용 하는 프로시저를 오버 로드 하려면</span><span class="sxs-lookup"><span data-stu-id="2a9f7-107">To overload a procedure that takes one optional parameter</span></span>  
  
1. <span data-ttu-id="2a9f7-108">`Sub` `Function` 매개 변수 목록에서 선택적 매개 변수를 포함 하는 또는 선언문을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-108">Write a `Sub` or `Function` declaration statement that includes the optional parameter in the parameter list.</span></span> <span data-ttu-id="2a9f7-109">`Optional`이 오버 로드 된 버전에는 키워드를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-109">Do not use the `Optional` keyword in this overloaded version.</span></span>  
  
2. <span data-ttu-id="2a9f7-110">`Sub`Or 키워드 앞에 `Function` [Overloads](../../../language-reference/modifiers/overloads.md) 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-110">Precede the `Sub` or `Function` keyword with the [Overloads](../../../language-reference/modifiers/overloads.md) keyword.</span></span>  
  
3. <span data-ttu-id="2a9f7-111">호출 코드에서 선택적 인수를 제공할 때 실행 되어야 하는 프로시저 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-111">Write the procedure code that should execute when the calling code supplies the optional argument.</span></span>  
  
4. <span data-ttu-id="2a9f7-112">또는 문을 사용 하 여 프로시저를 적절 하 게 종료 `End Sub` `End Function` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-112">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
5. <span data-ttu-id="2a9f7-113">매개 변수 목록에 선택적 매개 변수를 포함 하지 않는 경우를 제외 하 고 첫 번째 선언과 동일한 두 번째 선언문을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-113">Write a second declaration statement that is identical to the first declaration except that it does not include the optional parameter in the parameter list.</span></span>  
  
6. <span data-ttu-id="2a9f7-114">호출 코드에서 선택적 인수를 제공 하지 않는 경우 실행 되는 프로시저 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-114">Write the procedure code that should execute when the calling code does not supply the optional argument.</span></span> <span data-ttu-id="2a9f7-115">또는 문을 사용 하 여 프로시저를 적절 하 게 종료 `End Sub` `End Function` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-115">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
     <span data-ttu-id="2a9f7-116">다음 예에서는 선택적 매개 변수를 사용 하 여 정의 된 프로시저, 두 오버 로드 된 프로시저의 동등한 집합 및 유효 하지 않은 오버 로드 된 버전의 마지막 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-116">The following example shows a procedure defined with an optional parameter,  an equivalent set of two overloaded procedures, and finally examples of both invalid and valid overloaded versions.</span></span>  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a><span data-ttu-id="2a9f7-117">여러 선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="2a9f7-117">Multiple Optional Parameters</span></span>  

 <span data-ttu-id="2a9f7-118">둘 이상의 선택적 매개 변수가 있는 프로시저의 경우 일반적으로 두 개 이상의 오버 로드 된 버전이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-118">For a procedure with more than one optional parameter, you normally need more than two overloaded versions.</span></span> <span data-ttu-id="2a9f7-119">예를 들어 두 개의 선택적 매개 변수가 있고 호출 코드에서 서로 독립적으로 각 매개 변수를 제공 하거나 생략할 수 있는 경우 제공 된 인수의 가능한 각 조합에 대해 하나씩 4 개의 오버 로드 된 버전이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-119">For example, if there are two optional parameters, and the calling code can supply or omit each one independently of the other, you need four overloaded versions, one for each possible combination of supplied arguments.</span></span>  
  
 <span data-ttu-id="2a9f7-120">선택적 매개 변수 수가 늘어나면 오버 로드의 복잡성이 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-120">As the number of optional parameters increases, the complexity of the overloading increases.</span></span> <span data-ttu-id="2a9f7-121">제공 된 인수의 일부 조합이 허용 되지 않는 한, N 개의 선택적 매개 변수에는 2 ^ N 개의 오버 로드 된 버전이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-121">Unless some combinations of supplied arguments are not acceptable, for N optional parameters you need 2 ^ N overloaded versions.</span></span> <span data-ttu-id="2a9f7-122">프로시저의 특성에 따라 논리의 명확성은 오버 로드 된 모든 버전을 정의 하는 추가 작업을 정렬 하는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-122">Depending on the nature of the procedure, you might find that the clarity of logic justifies the extra effort of defining all the overloaded versions.</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a><span data-ttu-id="2a9f7-123">둘 이상의 선택적 매개 변수를 사용 하는 프로시저를 오버 로드 하려면</span><span class="sxs-lookup"><span data-stu-id="2a9f7-123">To overload a procedure that takes more than one optional parameter</span></span>  
  
1. <span data-ttu-id="2a9f7-124">제공 된 선택적 인수의 조합을 프로시저 논리에 허용 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-124">Determine which combinations of supplied optional arguments are acceptable to the logic of the procedure.</span></span> <span data-ttu-id="2a9f7-125">하나의 선택적 매개 변수가 다른 매개 변수에 종속 되는 경우 허용 되지 않는 조합이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-125">An unacceptable combination might arise if one optional parameter depends on another.</span></span> <span data-ttu-id="2a9f7-126">예를 들어 한 매개 변수가 개인의 이름을 허용 하 고 다른 매개 변수가 해당 사용자의 연령를 수락 하는 경우 나이를 제공 하지만 이름을 생략 하는 인수를 조합 하 여 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-126">For example, if one parameter accepts a person's name and another accepts the person's age, a combination of arguments supplying the age but omitting the name is unacceptable.</span></span>  
  
2. <span data-ttu-id="2a9f7-127">제공 되는 선택적 인수의 각 조합에 대해 해당 하 `Sub` 는 `Function` 매개 변수 목록을 정의 하는 또는 선언문을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-127">For each acceptable combination of supplied optional arguments, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="2a9f7-128">키워드를 사용 하지 마십시오 `Optional` .</span><span class="sxs-lookup"><span data-stu-id="2a9f7-128">Do not use the `Optional` keyword.</span></span>  
  
3. <span data-ttu-id="2a9f7-129">각 선언에서 `Sub` 또는 키워드 앞에 `Function` [Overloads](../../../language-reference/modifiers/overloads.md) 키워드를 붙입니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-129">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../language-reference/modifiers/overloads.md) keyword.</span></span>  
  
4. <span data-ttu-id="2a9f7-130">각 선언 후에 호출 코드에서 해당 선언의 매개 변수 목록에 해당 하는 인수 목록을 제공할 때 실행 해야 하는 프로시저 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-130">Following each declaration, write the procedure code that should execute when the calling code supplies an argument list corresponding to that declaration's parameter list.</span></span>  
  
5. <span data-ttu-id="2a9f7-131">또는 문을 사용 하 여 각 프로시저를 적절 하 게 종료 `End Sub` `End Function` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9f7-131">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9f7-132">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2a9f7-132">See also</span></span>

- [<span data-ttu-id="2a9f7-133">절차</span><span class="sxs-lookup"><span data-stu-id="2a9f7-133">Procedures</span></span>](./index.md)
- [<span data-ttu-id="2a9f7-134">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="2a9f7-134">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="2a9f7-135">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="2a9f7-135">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="2a9f7-136">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="2a9f7-136">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="2a9f7-137">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="2a9f7-137">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="2a9f7-138">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2a9f7-138">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="2a9f7-139">방법: 여러 버전의 프로시저 정의</span><span class="sxs-lookup"><span data-stu-id="2a9f7-139">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="2a9f7-140">방법: 오버로드된 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="2a9f7-140">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="2a9f7-141">방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="2a9f7-141">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="2a9f7-142">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="2a9f7-142">Overload Resolution</span></span>](./overload-resolution.md)
