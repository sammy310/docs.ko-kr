---
title: '방법: 선택적 매개 변수 (Visual Basic)를 사용 하는 프로시저 오버 로드'
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
ms.openlocfilehash: 070d641d5a8b683ddfe06039117cc4a8507102df
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827635"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a><span data-ttu-id="1ce9b-102">방법: 선택적 매개 변수 (Visual Basic)를 사용 하는 프로시저 오버 로드</span><span class="sxs-lookup"><span data-stu-id="1ce9b-102">How to: Overload a Procedure that Takes Optional Parameters (Visual Basic)</span></span>
<span data-ttu-id="1ce9b-103">프로시저에 있는 경우 하나 이상의 [선택 사항](../../../../visual-basic/language-reference/modifiers/optional.md) 매개 변수를 암시적 오버 로드 중 하 나와 일치 하는 오버 로드 된 버전을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-103">If a procedure has one or more [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameters, you cannot define an overloaded version matching any of its implicit overloads.</span></span> <span data-ttu-id="1ce9b-104">자세한 내용은 "암시적 오버 로드에 대 한 선택적 매개 변수"를 참조 하세요 [프로시저 오버 로드의 고려 사항](./considerations-in-overloading-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-104">For more information, see "Implicit Overloads for Optional Parameters" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="one-optional-parameter"></a><span data-ttu-id="1ce9b-105">하나의 선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ce9b-105">One Optional Parameter</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a><span data-ttu-id="1ce9b-106">하나의 선택적 매개 변수를 사용 하는 프로시저 오버 로드</span><span class="sxs-lookup"><span data-stu-id="1ce9b-106">To overload a procedure that takes one optional parameter</span></span>  
  
1.  <span data-ttu-id="1ce9b-107">작성 한 `Sub` 또는 `Function` 매개 변수 목록의 선택적 매개 변수를 포함 하는 선언문입니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-107">Write a `Sub` or `Function` declaration statement that includes the optional parameter in the parameter list.</span></span> <span data-ttu-id="1ce9b-108">사용 하지 마십시오는 `Optional` 이 오버 로드 된 버전의 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-108">Do not use the `Optional` keyword in this overloaded version.</span></span>  
  
2.  <span data-ttu-id="1ce9b-109">앞에 야 합니다 `Sub` 또는 `Function` 키워드를 사용 합니다 [오버 로드](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-109">Precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
3.  <span data-ttu-id="1ce9b-110">호출 코드는 선택적 인수를 제공 하는 경우 실행 해야 하는 프로시저 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-110">Write the procedure code that should execute when the calling code supplies the optional argument.</span></span>  
  
4.  <span data-ttu-id="1ce9b-111">사용 하 여 프로시저를 종료 합니다 `End Sub` 또는 `End Function` 문으로 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-111">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
5.  <span data-ttu-id="1ce9b-112">첫 번째 선언에 동일한 점을 제외 하 고 선택적 매개 변수는 매개 변수 목록에 포함 되지 않습니다 하는 두 번째 선언문을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-112">Write a second declaration statement that is identical to the first declaration except that it does not include the optional parameter in the parameter list.</span></span>  
  
6.  <span data-ttu-id="1ce9b-113">호출 코드 선택적 인수를 제공 하지 않는 경우 실행 해야 하는 프로시저 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-113">Write the procedure code that should execute when the calling code does not supply the optional argument.</span></span> <span data-ttu-id="1ce9b-114">사용 하 여 프로시저를 종료 합니다 `End Sub` 또는 `End Function` 문으로 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-114">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
     <span data-ttu-id="1ce9b-115">다음 예제에서는 두 오버 로드 된 프로시저 및 마지막으로 잘못 된 및 유효한 오버 로드 된 버전의 예제 집합을 해당 하는 선택적 매개 변수를 사용 하 여 정의 된 프로시저를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-115">The following example shows a procedure defined with an optional parameter,  an equivalent set of two overloaded procedures, and finally examples of both invalid and valid overloaded versions.</span></span>  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a><span data-ttu-id="1ce9b-116">여러 선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ce9b-116">Multiple Optional Parameters</span></span>  
 <span data-ttu-id="1ce9b-117">일반적으로 둘 이상의 선택적 매개 변수를 사용 하 여 프로시저를 두 개 이상의 오버 로드 된 버전이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-117">For a procedure with more than one optional parameter, you normally need more than two overloaded versions.</span></span> <span data-ttu-id="1ce9b-118">예를 들어, 두 가지 선택적 매개 변수를 호출 하는 코드 수 제공 또는 서로 독립적으로 각각을 생략 하는 경우 제공 된 인수의 가능한 각 조합에 대해 하나씩 네 개의 오버 로드 된 버전이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-118">For example, if there are two optional parameters, and the calling code can supply or omit each one independently of the other, you need four overloaded versions, one for each possible combination of supplied arguments.</span></span>  
  
 <span data-ttu-id="1ce9b-119">선택적 매개 변수 수가 늘어나면 오버 로드의 복잡성이 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-119">As the number of optional parameters increases, the complexity of the overloading increases.</span></span> <span data-ttu-id="1ce9b-120">이 아닌 경우 제공 된 인수의 일부 조합은 허용 되지 않는 선택적 매개 변수 N 필요 2 ^ N 오버 로드 된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-120">Unless some combinations of supplied arguments are not acceptable, for N optional parameters you need 2 ^ N overloaded versions.</span></span> <span data-ttu-id="1ce9b-121">프로시저의 특성에 따라는 논리의 명확성 들여야 모든 오버 로드 된 버전을 정의 하는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-121">Depending on the nature of the procedure, you might find that the clarity of logic justifies the extra effort of defining all the overloaded versions.</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a><span data-ttu-id="1ce9b-122">둘 이상의 선택적 매개 변수를 사용 하는 프로시저 오버 로드</span><span class="sxs-lookup"><span data-stu-id="1ce9b-122">To overload a procedure that takes more than one optional parameter</span></span>  
  
1.  <span data-ttu-id="1ce9b-123">프로시저의 논리를 제공 된 선택적 인수의 조합을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-123">Determine which combinations of supplied optional arguments are acceptable to the logic of the procedure.</span></span> <span data-ttu-id="1ce9b-124">허용 된 조합이 하나의 선택적 매개 변수는 다른 종속 된 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-124">An unacceptable combination might arise if one optional parameter depends on another.</span></span> <span data-ttu-id="1ce9b-125">예를 들어, 1 개의 매개 변수가 배우자의 이름은 허용 하 고 배우자의 시대를 허용 하는 다른, 보존 기간을 제공 하지만 이름을 생략 인수의 조합을 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-125">For example, if one parameter accepts a spouse's name and another accepts the spouse's age, a combination of arguments supplying the age but omitting the name is unacceptable.</span></span>  
  
2.  <span data-ttu-id="1ce9b-126">선택적 인수를 제공 된 각 허용 가능한 조합에 대해 작성 된 `Sub` 또는 `Function` 해당 매개 변수 목록을 정의 하는 선언문입니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-126">For each acceptable combination of supplied optional arguments, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="1ce9b-127">사용 하지 마십시오는 `Optional` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-127">Do not use the `Optional` keyword.</span></span>  
  
3.  <span data-ttu-id="1ce9b-128">각 선언 앞에 `Sub` 또는 `Function` 키워드를 사용 합니다 [오버 로드](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-128">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
4.  <span data-ttu-id="1ce9b-129">각 선언 다음 호출 코드를 해당 선언 매개 변수 목록에 해당 하는 인수 목록을 제공 하는 경우 실행 해야 하는 프로시저 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-129">Following each declaration, write the procedure code that should execute when the calling code supplies an argument list corresponding to that declaration's parameter list.</span></span>  
  
5.  <span data-ttu-id="1ce9b-130">각 프로시저를 종료 합니다 `End Sub` 또는 `End Function` 문으로 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce9b-130">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ce9b-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="1ce9b-131">See also</span></span>

- [<span data-ttu-id="1ce9b-132">절차</span><span class="sxs-lookup"><span data-stu-id="1ce9b-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="1ce9b-133">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="1ce9b-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="1ce9b-134">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ce9b-134">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="1ce9b-135">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="1ce9b-135">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="1ce9b-136">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="1ce9b-136">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="1ce9b-137">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1ce9b-137">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="1ce9b-138">방법: 여러 버전의 프로시저 정의</span><span class="sxs-lookup"><span data-stu-id="1ce9b-138">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="1ce9b-139">방법: 오버 로드 된 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="1ce9b-139">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="1ce9b-140">방법: 무한 개수의 매개 변수를 사용 하는 프로시저 오버 로드</span><span class="sxs-lookup"><span data-stu-id="1ce9b-140">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="1ce9b-141">오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="1ce9b-141">Overload Resolution</span></span>](./overload-resolution.md)
