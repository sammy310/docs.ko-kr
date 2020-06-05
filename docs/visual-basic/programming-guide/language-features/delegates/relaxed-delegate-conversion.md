---
title: 완화된 대리자 변환
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: a581ffae77c496908d2e4e38df53491a54ae2ab8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410672"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="a8d7e-102">완화된 대리자 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8d7e-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="a8d7e-103">완화 된 대리자 변환을 사용 하면 시그니처가 동일 하지 않더라도 sub 및 함수를 대리자나 처리기에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7e-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="a8d7e-104">따라서 대리자에 대 한 바인딩은 이미 메서드 호출에 대해 허용 되는 바인딩과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7e-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="a8d7e-105">매개 변수 및 반환 형식</span><span class="sxs-lookup"><span data-stu-id="a8d7e-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="a8d7e-106">정확히 일치 하는 시그니처 대신, 완화 된 변환을 수행 하려면가로 설정 된 경우 다음 조건이 충족 되어야 합니다 `Option Strict` `On` .</span><span class="sxs-lookup"><span data-stu-id="a8d7e-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
- <span data-ttu-id="a8d7e-107">각 대리자 매개 변수의 데이터 형식에서 할당 된 함수 또는의 해당 매개 변수에 대 한 데이터 형식으로 확대 변환이 있어야 합니다 `Sub` .</span><span class="sxs-lookup"><span data-stu-id="a8d7e-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="a8d7e-108">다음 예제에서 대리자에 `Del1` 는 하나의 매개 변수 ()가 있습니다 `Integer` .</span><span class="sxs-lookup"><span data-stu-id="a8d7e-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="a8d7e-109">`m`할당 된 람다 식의 매개 변수에는 `Integer` 또는와 같은 확대 변환이 있는 데이터 형식이 있어야 합니다 `Long` `Double` .</span><span class="sxs-lookup"><span data-stu-id="a8d7e-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     <span data-ttu-id="a8d7e-110">축소 변환은가로 설정 된 경우에만 허용 됩니다 `Option Strict` `Off` .</span><span class="sxs-lookup"><span data-stu-id="a8d7e-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- <span data-ttu-id="a8d7e-111">확대 변환은 할당 된 함수의 반환 형식이 나 `Sub` 대리자의 반환 형식에서 반대 방향으로 존재 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7e-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="a8d7e-112">다음 예제에서의 반환 형식이 이므로 할당 된 각 람다 식의 본문은로 확대 되는 데이터 형식으로 계산 되어야 합니다 `Integer` `del1` `Integer` .</span><span class="sxs-lookup"><span data-stu-id="a8d7e-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 <span data-ttu-id="a8d7e-113">`Option Strict`가로 설정 되어 있으면 `Off` 확대 제한이 양방향으로 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7e-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="a8d7e-114">매개 변수 사양을 생략 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7e-114">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="a8d7e-115">완화 된 대리자를 사용 하 여 할당 된 메서드에서 매개 변수 사양을 완전히 생략할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7e-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 <span data-ttu-id="a8d7e-116">일부 매개 변수를 지정 하 고 다른 매개 변수는 생략할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7e-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 <span data-ttu-id="a8d7e-117">매개 변수를 생략 하는 기능은 몇 가지 복잡 한 매개 변수가 관련 된 이벤트 처리기를 정의 하는 경우와 같은 상황에서 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7e-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="a8d7e-118">일부 이벤트 처리기에 대 한 인수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7e-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="a8d7e-119">대신 처리기는 이벤트가 등록 된 컨트롤의 상태에 직접 액세스 하 여 인수를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7e-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="a8d7e-120">완화 된 대리자를 사용 하면 모호성 결과가 없을 때 이러한 선언에서 인수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7e-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="a8d7e-121">다음 예제에서는 완전히 지정 된 메서드를 `OnClick` 로 다시 작성할 수 있습니다 `RelaxedOnClick` .</span><span class="sxs-lookup"><span data-stu-id="a8d7e-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="a8d7e-122">AddressOf 예제</span><span class="sxs-lookup"><span data-stu-id="a8d7e-122">AddressOf Examples</span></span>  
 <span data-ttu-id="a8d7e-123">람다 식은 이전 예제에서 형식 관계를 쉽게 볼 수 있도록 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7e-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="a8d7e-124">그러나, 또는를 사용 하는 대리자 할당에는 동일한 relaxation 허용 됩니다 `AddressOf` `Handles` `AddHandler` .</span><span class="sxs-lookup"><span data-stu-id="a8d7e-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="a8d7e-125">다음 예제에서는,, `f1` 및 함수 `f2` 를 `f3` `f4` 모두에 할당할 수 있습니다 `Del1` .</span><span class="sxs-lookup"><span data-stu-id="a8d7e-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 <span data-ttu-id="a8d7e-126">다음 예는 `Option Strict` 가로 설정 된 경우에만 유효 `Off` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7e-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="a8d7e-127">함수 반환 삭제</span><span class="sxs-lookup"><span data-stu-id="a8d7e-127">Dropping Function Returns</span></span>  
 <span data-ttu-id="a8d7e-128">완화 된 대리자 변환을 사용 하면 함수를 대리자에 할당 하 여 `Sub` 함수의 반환 값을 효과적으로 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8d7e-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="a8d7e-129">그러나를 함수 대리자에 할당할 수는 없습니다 `Sub` .</span><span class="sxs-lookup"><span data-stu-id="a8d7e-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="a8d7e-130">다음 예제에서는 함수 주소가 `doubler` delegate에 할당 됩니다 `Sub` `Del3` .</span><span class="sxs-lookup"><span data-stu-id="a8d7e-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="a8d7e-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8d7e-131">See also</span></span>

- [<span data-ttu-id="a8d7e-132">람다 식</span><span class="sxs-lookup"><span data-stu-id="a8d7e-132">Lambda Expressions</span></span>](../procedures/lambda-expressions.md)
- [<span data-ttu-id="a8d7e-133">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="a8d7e-133">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="a8d7e-134">대리자</span><span class="sxs-lookup"><span data-stu-id="a8d7e-134">Delegates</span></span>](index.md)
- [<span data-ttu-id="a8d7e-135">방법: Visual Basic에서 프로시저에 다른 프로시저 전달</span><span class="sxs-lookup"><span data-stu-id="a8d7e-135">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="a8d7e-136">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="a8d7e-136">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="a8d7e-137">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="a8d7e-137">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
