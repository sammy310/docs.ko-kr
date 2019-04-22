---
title: 하위 식(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: 5b26a091dc8eb7415702c3c2853a569324def7d5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824613"
---
# <a name="sub-expression-visual-basic"></a><span data-ttu-id="6c012-102">하위 식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c012-102">Sub Expression (Visual Basic)</span></span>
<span data-ttu-id="6c012-103">매개 변수 및 서브루틴 람다 식을 정의 하는 코드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-103">Declares the parameters and code that define a subroutine lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c012-104">구문</span><span class="sxs-lookup"><span data-stu-id="6c012-104">Syntax</span></span>  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="6c012-105">요소</span><span class="sxs-lookup"><span data-stu-id="6c012-105">Parts</span></span>  
  
|<span data-ttu-id="6c012-106">용어</span><span class="sxs-lookup"><span data-stu-id="6c012-106">Term</span></span>|<span data-ttu-id="6c012-107">정의</span><span class="sxs-lookup"><span data-stu-id="6c012-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="6c012-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-108">Optional.</span></span> <span data-ttu-id="6c012-109">프로시저의 매개 변수를 나타내는 로컬 변수 이름의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-109">A list of local variable names that represent the parameters of the procedure.</span></span> <span data-ttu-id="6c012-110">괄호는 목록이 비어 있는 경우에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="6c012-111">자세한 내용은 [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c012-111">For more information, see [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`statement`|<span data-ttu-id="6c012-112">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="6c012-112">Required.</span></span> <span data-ttu-id="6c012-113">단일 문입니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-113">A single statement.</span></span>|  
|`statements`|<span data-ttu-id="6c012-114">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="6c012-114">Required.</span></span> <span data-ttu-id="6c012-115">문 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-115">A list of statements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c012-116">설명</span><span class="sxs-lookup"><span data-stu-id="6c012-116">Remarks</span></span>  
 <span data-ttu-id="6c012-117">A *람다 식* 이름을 없는 서브루틴 이며 하나 이상의 문을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-117">A *lambda expression* is a subroutine that does not have a name and that executes one or more statements.</span></span> <span data-ttu-id="6c012-118">어디서 나 람다 식을 사용할 수 있습니다는 사용할 수는 대리자 형식을 제외 하 고 인수로 `RemoveHandler`합니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-118">You can use a lambda expression anywhere that you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="6c012-119">대리자 및 람다 식 대리자를 사용 하 여 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [대리자 문](../../../visual-basic/language-reference/statements/delegate-statement.md) 하 고 [완화 된 대리자 변환](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-119">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="6c012-120">람다 식 구문</span><span class="sxs-lookup"><span data-stu-id="6c012-120">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="6c012-121">람다 식의 구문은 유사 표준 서브루틴의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-121">The syntax of a lambda expression resembles that of a standard subroutine.</span></span> <span data-ttu-id="6c012-122">차이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-122">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="6c012-123">람다 식에 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-123">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="6c012-124">람다 식을와 같은 한정자를 사용할 수 없습니다 `Overloads` 또는 `Overrides`합니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-124">A lambda expression cannot have a modifier, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="6c012-125">한 줄 람다 식의 본문에는 식이 아닌 문 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-125">The body of a single-line lambda expression must be a statement, not an expression.</span></span> <span data-ttu-id="6c012-126">Sub 프로시저를 호출 하지만 function 프로시저를 호출 하지 본문 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-126">The body can consist of a call to a sub procedure, but not a call to a function procedure.</span></span>  
  
-   <span data-ttu-id="6c012-127">람다 식에서 모든 매개 변수에 지정 된 데이터 형식 또는 모든 매개 변수를 유추할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-127">In a lambda expression, either all parameters must have specified data types or all parameters must be inferred.</span></span>  
  
-   <span data-ttu-id="6c012-128">선택 사항 및 `ParamArray` 매개 변수는 람다 식에서 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-128">Optional and `ParamArray` parameters are not permitted in lambda expressions.</span></span>  
  
-   <span data-ttu-id="6c012-129">제네릭 매개 변수 람다 식에서 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-129">Generic parameters are not permitted in lambda expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c012-130">예제</span><span class="sxs-lookup"><span data-stu-id="6c012-130">Example</span></span>  
 <span data-ttu-id="6c012-131">다음은 콘솔에 값을 기록 하는 람다 식의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-131">Following is an example of a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="6c012-132">두 줄 및 여러 줄 람다 식 구문은 서브루틴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-132">The example shows both the single-line and multiline lambda expression syntax for a subroutine.</span></span> <span data-ttu-id="6c012-133">더 많은 예제를 참조 하세요 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c012-133">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="6c012-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="6c012-134">See also</span></span>

- [<span data-ttu-id="6c012-135">Sub 문</span><span class="sxs-lookup"><span data-stu-id="6c012-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="6c012-136">람다 식</span><span class="sxs-lookup"><span data-stu-id="6c012-136">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="6c012-137">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="6c012-137">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="6c012-138">문(C++)</span><span class="sxs-lookup"><span data-stu-id="6c012-138">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="6c012-139">완화된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="6c012-139">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
