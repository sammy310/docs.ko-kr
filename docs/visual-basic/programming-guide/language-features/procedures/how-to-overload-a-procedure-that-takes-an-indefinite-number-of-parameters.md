---
title: '방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드'
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
ms.openlocfilehash: 10cd7d11b0efe9fa5eb3ae24269a4cdbe33bc08a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071549"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="7960e-102">방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7960e-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>

<span data-ttu-id="7960e-103">프로시저에 [ParamArray](../../../language-reference/modifiers/paramarray.md) 매개 변수가 있는 경우 매개 변수 배열에 1 차원 배열을 가져오는 오버 로드 된 버전을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7960e-103">If a procedure has a [ParamArray](../../../language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="7960e-104">자세한 내용은 [오버 로드 절차의 고려 사항](./considerations-in-overloading-procedures.md)에서 "ParamArray 매개 변수에 대 한 암시적 오버 로드"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7960e-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="7960e-105">가변적인 개수의 매개 변수를 사용 하는 프로시저를 오버 로드 하려면</span><span class="sxs-lookup"><span data-stu-id="7960e-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1. <span data-ttu-id="7960e-106">프로시저와 호출 코드 논리가 매개 변수에서 오버 로드 된 버전 보다 더 많은 이점을 제공 하는지 확인 합니다 `ParamArray` .</span><span class="sxs-lookup"><span data-stu-id="7960e-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="7960e-107">[오버 로드 프로시저에서 고려할 사항은](./considerations-in-overloading-procedures.md)"오버 로드 및 paramarrays"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7960e-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2. <span data-ttu-id="7960e-108">프로시저에서 매개 변수 목록의 변수 부분에 허용 해야 하는 제공 된 값의 개수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7960e-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="7960e-109">여기에는 값이 없는 경우이 포함 될 수 있으며, 1 차원 배열의 대/소문자가 포함 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7960e-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3. <span data-ttu-id="7960e-110">제공 된 값의 허용 되는 개수에는 `Sub` `Function` 해당 하는 매개 변수 목록을 정의 하는 또는 선언문을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7960e-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="7960e-111">`Optional` `ParamArray` 이 오버 로드 된 버전에서 또는 키워드를 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7960e-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4. <span data-ttu-id="7960e-112">각 선언에서 `Sub` 또는 키워드 앞에 `Function` [Overloads](../../../language-reference/modifiers/overloads.md) 키워드를 붙입니다.</span><span class="sxs-lookup"><span data-stu-id="7960e-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5. <span data-ttu-id="7960e-113">각 선언 후에 호출 코드에서 해당 선언의 매개 변수 목록에 해당 하는 값을 제공할 때 실행 되어야 하는 프로시저 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7960e-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6. <span data-ttu-id="7960e-114">또는 문을 사용 하 여 각 프로시저를 적절 하 게 종료 `End Sub` `End Function` 합니다.</span><span class="sxs-lookup"><span data-stu-id="7960e-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7960e-115">예제</span><span class="sxs-lookup"><span data-stu-id="7960e-115">Example</span></span>  

 <span data-ttu-id="7960e-116">다음 예에서는 [ParamArray](../../../language-reference/modifiers/paramarray.md) 매개 변수를 사용 하 여 정의 된 프로시저와 해당 하는 오버 로드 된 프로시저 집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7960e-116">The following example shows a procedure defined with a [ParamArray](../../../language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="7960e-117">매개 변수 배열에 1 차원 배열을 사용 하는 매개 변수 목록을 사용 하 여 이러한 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7960e-117">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="7960e-118">그러나 다른 암시적 오버 로드의 시그니처를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7960e-118">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="7960e-119">다음 선언에서는이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7960e-119">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 <span data-ttu-id="7960e-120">오버 로드 된 버전의 코드는 호출 코드에서 매개 변수에 대해 하나 이상의 값을 제공 했는지 여부를 테스트 하지 않아도 `ParamArray` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7960e-120">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> <span data-ttu-id="7960e-121">Visual Basic 호출 하는 인수 목록과 일치 하는 버전으로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="7960e-121">Visual Basic passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="7960e-122">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7960e-122">Compile the code</span></span>  

 <span data-ttu-id="7960e-123">매개 변수가 있는 프로시저는 `ParamArray` 오버 로드 된 버전 집합과 동일 하므로 이러한 암시적 오버 로드에 해당 하는 매개 변수 목록을 사용 하 여 이러한 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7960e-123">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="7960e-124">자세한 내용은 [오버 로드 절차의 고려 사항](./considerations-in-overloading-procedures.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7960e-124">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7960e-125">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="7960e-125">.NET Framework Security</span></span>  

 <span data-ttu-id="7960e-126">무한정 클 수 있는 배열을 처리할 때마다 응용 프로그램의 내부 용량을 overrunning 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7960e-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="7960e-127">매개 변수 배열을 허용 하는 경우, 호출 코드가 전달 된 배열의 길이를 테스트 하 고, 응용 프로그램에 비해 너무 클 경우 적절 한 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7960e-127">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7960e-128">참조</span><span class="sxs-lookup"><span data-stu-id="7960e-128">See also</span></span>

- [<span data-ttu-id="7960e-129">절차</span><span class="sxs-lookup"><span data-stu-id="7960e-129">Procedures</span></span>](./index.md)
- [<span data-ttu-id="7960e-130">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="7960e-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="7960e-131">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="7960e-131">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="7960e-132">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="7960e-132">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="7960e-133">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="7960e-133">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="7960e-134">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7960e-134">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="7960e-135">방법: 여러 버전의 프로시저 정의</span><span class="sxs-lookup"><span data-stu-id="7960e-135">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="7960e-136">방법: 오버로드된 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="7960e-136">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="7960e-137">방법: 선택적 매개 변수를 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="7960e-137">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="7960e-138">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="7960e-138">Overload Resolution</span></span>](./overload-resolution.md)
