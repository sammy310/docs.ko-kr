---
title: 완화된 대리자 변환
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: ffb242842553382ba26121333c38fc65eaa168a9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345226"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="64458-102">완화된 대리자 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64458-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="64458-103">완화 된 대리자 변환을 사용 하면 시그니처가 동일 하지 않더라도 sub 및 함수를 대리자나 처리기에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64458-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="64458-104">따라서 대리자에 대 한 바인딩은 이미 메서드 호출에 대해 허용 되는 바인딩과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="64458-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="64458-105">매개 변수 및 반환 형식</span><span class="sxs-lookup"><span data-stu-id="64458-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="64458-106">정확 하 게 일치 하는 시그니처를 사용 하는 대신, 완화 된 변환을 수행 하려면 `Option Strict`이 `On`으로 설정 된 경우 다음 조건이 충족 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64458-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
- <span data-ttu-id="64458-107">각 대리자 매개 변수의 데이터 형식에서 할당 된 함수 또는 `Sub`의 해당 매개 변수에 대 한 데이터 형식으로 확대 변환이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64458-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="64458-108">다음 예제에서는 대리자 `Del1`에 `Integer`하나의 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64458-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="64458-109">할당 된 람다 식의 매개 변수 `m`에는 `Integer`(예: `Long` 또는 `Double`)의 확대 변환이 있는 데이터 형식이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64458-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     <span data-ttu-id="64458-110">축소 변환은 `Option Strict`이 `Off`으로 설정 된 경우에만 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64458-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- <span data-ttu-id="64458-111">확대 변환은 할당 된 함수의 반환 형식이 나 대리자의 반환 형식에 대 한 `Sub` 반대 방향으로 존재 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64458-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="64458-112">다음 예제에서는 `del1`의 반환 형식이 `Integer`되기 때문에 할당 된 각 람다 식의 본문이 `Integer`으로 확대 되는 데이터 형식으로 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64458-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 <span data-ttu-id="64458-113">`Option Strict`을 `Off`로 설정 하면 확대 제한이 양방향으로 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64458-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="64458-114">매개 변수 사양을 생략 합니다.</span><span class="sxs-lookup"><span data-stu-id="64458-114">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="64458-115">완화 된 대리자를 사용 하 여 할당 된 메서드에서 매개 변수 사양을 완전히 생략할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64458-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 <span data-ttu-id="64458-116">일부 매개 변수를 지정 하 고 다른 매개 변수는 생략할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64458-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 <span data-ttu-id="64458-117">매개 변수를 생략 하는 기능은 몇 가지 복잡 한 매개 변수가 관련 된 이벤트 처리기를 정의 하는 경우와 같은 상황에서 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="64458-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="64458-118">일부 이벤트 처리기에 대 한 인수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64458-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="64458-119">대신 처리기는 이벤트가 등록 된 컨트롤의 상태에 직접 액세스 하 여 인수를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="64458-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="64458-120">완화 된 대리자를 사용 하면 모호성 결과가 없을 때 이러한 선언에서 인수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64458-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="64458-121">다음 예제에서는 완전히 지정 된 `OnClick` 메서드를 `RelaxedOnClick`으로 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64458-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="64458-122">AddressOf 예제</span><span class="sxs-lookup"><span data-stu-id="64458-122">AddressOf Examples</span></span>  
 <span data-ttu-id="64458-123">람다 식은 이전 예제에서 형식 관계를 쉽게 볼 수 있도록 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64458-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="64458-124">그러나 `AddressOf`, `Handles`또는 `AddHandler`를 사용 하는 대리자 할당에 대해서도 동일한 relaxation 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64458-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="64458-125">다음 예에서는 `f1`, `f2`, `f3`및 `f4` 함수를 모두 `Del1`에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64458-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 <span data-ttu-id="64458-126">다음 예는 `Option Strict`이 `Off`으로 설정 된 경우에만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="64458-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="64458-127">함수 반환 삭제</span><span class="sxs-lookup"><span data-stu-id="64458-127">Dropping Function Returns</span></span>  
 <span data-ttu-id="64458-128">완화 된 대리자 변환을 사용 하면 함수를 `Sub` 대리자에 할당 하 여 함수의 반환 값을 효과적으로 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64458-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="64458-129">그러나 `Sub`를 함수 대리자에 할당할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64458-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="64458-130">다음 예제에서는 함수 `doubler`의 주소가 `Sub` 대리자 `Del3`에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64458-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="64458-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64458-131">See also</span></span>

- [<span data-ttu-id="64458-132">람다 식</span><span class="sxs-lookup"><span data-stu-id="64458-132">Lambda Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="64458-133">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="64458-133">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="64458-134">대리자</span><span class="sxs-lookup"><span data-stu-id="64458-134">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="64458-135">방법: Visual Basic에서 프로시저에 다른 프로시저 전달</span><span class="sxs-lookup"><span data-stu-id="64458-135">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="64458-136">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="64458-136">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="64458-137">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="64458-137">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
