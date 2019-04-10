---
title: '방법: 무한 개수의 매개 변수 (Visual Basic)를 사용 하는 프로시저 오버 로드'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
ms.openlocfilehash: 3cf75fc6221364704379eb23d308481c34e6c0d6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316455"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="39125-102">방법: 무한 개수의 매개 변수 (Visual Basic)를 사용 하는 프로시저 오버 로드</span><span class="sxs-lookup"><span data-stu-id="39125-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="39125-103">프로시저에 있는 경우는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 매개 변수를 1 차원 배열을 매개 변수 배열에 대 한 오버 로드 된 버전을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39125-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="39125-104">자세한 내용은 "암시적 오버 로드는 ParamArray 매개 변수"를 참조 하세요 [프로시저 오버 로드의 고려 사항](./considerations-in-overloading-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="39125-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="39125-105">가변 개수의 매개 변수를 사용 하는 프로시저 오버 로드</span><span class="sxs-lookup"><span data-stu-id="39125-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1. <span data-ttu-id="39125-106">절차 및 코드 논리 이점을 호출 버전 두 개를 오버 로드 확인을 `ParamArray` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="39125-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="39125-107">"오버 로드 및 ParamArrays"를 참조 하세요 [프로시저를 오버 로드할 고려 사항](./considerations-in-overloading-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="39125-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2. <span data-ttu-id="39125-108">제공 된 값의 숫자 프로시저 매개 변수 목록의 변수 부분에 적용 해야 할 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39125-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="39125-109">이 값이 없는 경우 포함 하 고 단일 1 차원 배열의 경우를 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39125-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3. <span data-ttu-id="39125-110">제공 된 값의 각 허용 되는 번호를 작성 한 `Sub` 또는 `Function` 해당 매개 변수 목록을 정의 하는 선언문입니다.</span><span class="sxs-lookup"><span data-stu-id="39125-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="39125-111">사용 하지 마세요 합니다 `Optional` 또는 `ParamArray` 이 오버 로드 된 버전의 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="39125-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4. <span data-ttu-id="39125-112">각 선언 앞에 `Sub` 또는 `Function` 키워드를 사용 합니다 [오버 로드](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="39125-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5. <span data-ttu-id="39125-113">각 선언 다음 호출 하는 코드는 선언의 매개 변수 목록에 해당 하는 값을 제공 하는 경우 실행 해야 하는 프로시저 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="39125-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6. <span data-ttu-id="39125-114">각 프로시저를 종료 합니다 `End Sub` 또는 `End Function` 문으로 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="39125-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39125-115">예제</span><span class="sxs-lookup"><span data-stu-id="39125-115">Example</span></span>  
 <span data-ttu-id="39125-116">다음 예제에서는 사용 하 여 정의 된 프로시저를 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 매개 변수 및 오버 로드 된 프로시저의 해당 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="39125-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="39125-117">매개 변수 배열은 1 차원 배열의 사용 하는 매개 변수 목록 사용 하 여 이러한 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39125-117">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="39125-118">그러나 다른 암시적 오버 로드의 시그니처를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39125-118">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="39125-119">다음 선언은이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="39125-119">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 <span data-ttu-id="39125-120">오버 로드 된 버전의에서 코드 호출 코드에 대 한 하나 이상의 값을 제공 했는지 여부를 테스트 하지 않아도 `ParamArray` 매개 변수를 그렇다면 또는 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="39125-120">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> <span data-ttu-id="39125-121">Visual Basic에서는 호출 인수 목록과 일치 하는 버전 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="39125-121">Visual Basic passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="39125-122">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="39125-122">Compiling the Code</span></span>  
 <span data-ttu-id="39125-123">때문에 사용 하 여 프로시저를 `ParamArray` 매개 변수는 오버 로드 된 버전의 집합, 이러한 암시적 오버 로드 중 하나에 해당 하는 매개 변수 목록을 사용 하 여 이러한 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39125-123">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="39125-124">자세한 내용은 [프로시저 오버 로드의 고려 사항](./considerations-in-overloading-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="39125-124">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="39125-125">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="39125-125">.NET Framework Security</span></span>  
 <span data-ttu-id="39125-126">무한정 커질 수 있는 배열을 사용 하 여 처리할 때마다 응용 프로그램의 일부 내부 용량 오버런이 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39125-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="39125-127">매개 변수 배열에 동의 하는 경우 호출 코드에 전달 된 배열의 길이 대 한 테스트 하 고 응용 프로그램에 비해 너무 큰 경우 적절 한 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39125-127">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39125-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="39125-128">See also</span></span>

- [<span data-ttu-id="39125-129">절차</span><span class="sxs-lookup"><span data-stu-id="39125-129">Procedures</span></span>](./index.md)
- [<span data-ttu-id="39125-130">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="39125-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="39125-131">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="39125-131">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="39125-132">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="39125-132">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="39125-133">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="39125-133">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="39125-134">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="39125-134">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="39125-135">방법: 여러 버전의 프로시저 정의</span><span class="sxs-lookup"><span data-stu-id="39125-135">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="39125-136">방법: 오버로드된 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="39125-136">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="39125-137">방법: 선택적 매개 변수를 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="39125-137">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="39125-138">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="39125-138">Overload Resolution</span></span>](./overload-resolution.md)
