---
title: 위치 및 이름으로 인수 전달(Visual Basic)
ms.date: 02/01/2018
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
ms.openlocfilehash: b872eda97d1e349ad781b12810e4b166d6e46fe1
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58837314"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="f1746-102">위치 및 이름으로 인수 전달(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1746-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>
<span data-ttu-id="f1746-103">호출 하는 경우는 `Sub` 또는 `Function` 프로시저 인수를 전달할 수 있습니다 *위치별* -프로시저의 정의에 나타나는 순서로-또는 전달할 수 있습니다 *이름별*를 하지 않고 위치에 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>  
  
 <span data-ttu-id="f1746-104">인수 선언 된 이름에 콜론 및 등호 뒤에 지정할 이름으로 인수를 전달 하는 경우 (`:=`), 인수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="f1746-105">순서에 관계 없이 명명 된 인수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-105">You can supply named arguments in any order.</span></span>  
  
 <span data-ttu-id="f1746-106">예를 들어, 다음 `Sub` 프로시저에 3 개 인수:</span><span class="sxs-lookup"><span data-stu-id="f1746-106">For example, the following `Sub` procedure takes three arguments:</span></span>  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 <span data-ttu-id="f1746-107">이 프로시저를 호출할 때 위치, 이름 또는 둘 모두를 사용 하 여 인수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>  
  
## <a name="passing-arguments-by-position"></a><span data-ttu-id="f1746-108">위치 인수 전달</span><span class="sxs-lookup"><span data-stu-id="f1746-108">Passing Arguments by Position</span></span>  
 <span data-ttu-id="f1746-109">호출할 수 있습니다는 `Display` 메서드 인수를 사용 하 여 위치로 전달 하 고 다음 예제에서와 같이 쉼표로 구분 된:</span><span class="sxs-lookup"><span data-stu-id="f1746-109">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 <span data-ttu-id="f1746-110">위치 인수 목록에는 선택적 인수를 생략할 경우 쉼표를 사용 하 여 해당 위치를 보유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="f1746-111">다음 예제에서는 합니다 `Display` 없이 메서드를 `age` 인수:</span><span class="sxs-lookup"><span data-stu-id="f1746-111">The following example calls the `Display` method without the `age` argument:</span></span>  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a><span data-ttu-id="f1746-112">이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="f1746-112">Passing Arguments by Name</span></span>  
 <span data-ttu-id="f1746-113">호출할 수 있습니다 `Display` 이름으로 전달 된 인수를 사용 하 여 또한 쉼표로 분리 하 여 다음 예와에서 같이:</span><span class="sxs-lookup"><span data-stu-id="f1746-113">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 <span data-ttu-id="f1746-114">이러한 방식으로 이름으로 인수를 전달 합니다. 선택적 인수를 둘 이상 있는 프로시저를 호출할 때 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-114">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="f1746-115">이름으로 인수를 제공 하는 경우 연속 된 쉼표를 사용 하 여 생략 된 위치 인수를 나타내는 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-115">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="f1746-116">이름으로 인수를 전달 합니다. 또한 쉽게 전달 하는 생략 되는 시나리오는 인수를 추적 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-116">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>  
  
## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="f1746-117">이름 및 위치 인수 혼합</span><span class="sxs-lookup"><span data-stu-id="f1746-117">Mixing Arguments by Position and by Name</span></span>  

<span data-ttu-id="f1746-118">다음 예제에서와 같이 위치 및 단일 프로시저 호출에서 이름으로 인수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-118">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 <span data-ttu-id="f1746-119">앞의 예에서 없습니다 여분의 쉼표는 생략 된 위치를 포함 하는 데 필요한 `age` 인수를 있으므로 `birth` 이름으로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-119">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>  
  
<span data-ttu-id="f1746-120">15.5 이전 버전의 Visual Basic의 위치 및 이름, 위치 인수를 사용 하 여 인수를 제공 하는 경우 모든 첫 번째 항목 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-120">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="f1746-121">이름으로 인수를 제공한 후 모든 나머지 인수 모두 전달 되어야 합니다 이름별.</span><span class="sxs-lookup"><span data-stu-id="f1746-121">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="f1746-122">다음을 호출 하는 예를 들어 합니다 `Display` 컴파일러 오류를 표시 하는 메서드 [BC30241: 명명 된 인수가 필요](../../../misc/bc30241.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-122">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

<span data-ttu-id="f1746-123">Visual Basic 15.5부터 위치 인수 수에 따라 명명 된 인수 끝 위치 인수를 올바른 위치에 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="f1746-123">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="f1746-124">Visual Basic 15.5 이전 호출에서 컴파일된 경우에 `Display` 메서드가 성공적으로 컴파일되고 컴파일러 오류가 더 이상 [BC30241](../../../misc/bc30241.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-124">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>  

<span data-ttu-id="f1746-125">명명 되 고 위치 인수를 사용 하는 순서에 맞게 조정할 수는이 기능은 코드를 더 쉽게 읽을 수 있도록 명명된 된 인수를 사용 하려는 경우에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-125">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="f1746-126">다음 예를 들어 `Person` 클래스 생성자를 사용 하려면 두 인수 `Person`, 둘 다 수 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-126">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span> 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

<span data-ttu-id="f1746-127">코드의 의도 할 수 있습니다 시기의 선택을 취소 하는 혼합된 명명 되 고 위치 인수를 사용 하 여 값을 `father` 하 고 `mother` 인수는 `Nothing`:</span><span class="sxs-lookup"><span data-stu-id="f1746-127">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

<span data-ttu-id="f1746-128">명명 된 인수를 사용 하 여 위치 인수를 수행 하려면 Visual Basic 프로젝트에 다음 요소를 추가 해야 합니다 (\*.vbproj) 파일:</span><span class="sxs-lookup"><span data-stu-id="f1746-128">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="f1746-129">자세한 내용은 참조 [Visual Basic 언어 버전을 설정](../../../language-reference/configure-language-version.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-129">For more information see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="f1746-130">이름으로 인수에 대 한 제한</span><span class="sxs-lookup"><span data-stu-id="f1746-130">Restrictions on Supplying Arguments by Name</span></span>  

<span data-ttu-id="f1746-131">필수 인수를 입력 하지 않으려면 이름별 인수를 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-131">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="f1746-132">선택적 인수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-132">You can omit only the optional arguments.</span></span>  
  
<span data-ttu-id="f1746-133">매개 변수 배열을 이름으로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-133">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="f1746-134">프로시저를 호출 하면 불특정 개수의 매개 변수 배열에 대 한 쉼표로 구분 된 인수를 제공 하 고 컴파일러가 단일 이름으로 둘 이상의 인수를 연결할 수 없습니다 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f1746-134">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1746-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="f1746-135">See also</span></span>

- [<span data-ttu-id="f1746-136">절차</span><span class="sxs-lookup"><span data-stu-id="f1746-136">Procedures</span></span>](./index.md)
- [<span data-ttu-id="f1746-137">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="f1746-137">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="f1746-138">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="f1746-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="f1746-139">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="f1746-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="f1746-140">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="f1746-140">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="f1746-141">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="f1746-141">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="f1746-142">선택 사항</span><span class="sxs-lookup"><span data-stu-id="f1746-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
- [<span data-ttu-id="f1746-143">ParamArray</span><span class="sxs-lookup"><span data-stu-id="f1746-143">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
