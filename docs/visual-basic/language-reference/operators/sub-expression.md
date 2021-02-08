---
description: '자세한 정보: 하위 식 (Visual Basic)'
title: 하위 식
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: e47aa8f9707701b5fd9d90fb3fabb31e9c052b53
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795289"
---
# <a name="sub-expression-visual-basic"></a><span data-ttu-id="6ae58-103">하위 식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ae58-103">Sub Expression (Visual Basic)</span></span>

<span data-ttu-id="6ae58-104">서브루틴 람다 식을 정의 하는 매개 변수 및 코드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-104">Declares the parameters and code that define a subroutine lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ae58-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ae58-105">Syntax</span></span>  
  
```vb  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="6ae58-106">부분</span><span class="sxs-lookup"><span data-stu-id="6ae58-106">Parts</span></span>  
  
|<span data-ttu-id="6ae58-107">용어</span><span class="sxs-lookup"><span data-stu-id="6ae58-107">Term</span></span>|<span data-ttu-id="6ae58-108">정의</span><span class="sxs-lookup"><span data-stu-id="6ae58-108">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="6ae58-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-109">Optional.</span></span> <span data-ttu-id="6ae58-110">프로시저의 매개 변수를 나타내는 지역 변수 이름 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-110">A list of local variable names that represent the parameters of the procedure.</span></span> <span data-ttu-id="6ae58-111">목록이 비어 있는 경우에도 괄호가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-111">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="6ae58-112">자세한 내용은 [Parameter List](../statements/parameter-list.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ae58-112">For more information, see [Parameter List](../statements/parameter-list.md).</span></span>|  
|`statement`|<span data-ttu-id="6ae58-113">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-113">Required.</span></span> <span data-ttu-id="6ae58-114">단일 문입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-114">A single statement.</span></span>|  
|`statements`|<span data-ttu-id="6ae58-115">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-115">Required.</span></span> <span data-ttu-id="6ae58-116">문 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-116">A list of statements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ae58-117">설명</span><span class="sxs-lookup"><span data-stu-id="6ae58-117">Remarks</span></span>  

 <span data-ttu-id="6ae58-118">*람다 식은* 이름이 없고 하나 이상의 문을 실행 하는 서브루틴입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-118">A *lambda expression* is a subroutine that does not have a name and that executes one or more statements.</span></span> <span data-ttu-id="6ae58-119">에 대 한 인수를 제외 하 고 대리자 형식을 사용할 수 있는 모든 위치에서 람다 식을 사용할 수 있습니다 `RemoveHandler` .</span><span class="sxs-lookup"><span data-stu-id="6ae58-119">You can use a lambda expression anywhere that you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="6ae58-120">대리자에 대 한 자세한 내용과 대리자에 람다 식을 사용 하는 방법에 대 한 자세한 내용은 [Delegate 문](../statements/delegate-statement.md) 및 [완화 된 대리자 변환](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6ae58-120">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="6ae58-121">람다 식 구문</span><span class="sxs-lookup"><span data-stu-id="6ae58-121">Lambda Expression Syntax</span></span>  

 <span data-ttu-id="6ae58-122">람다 식의 구문은 표준 서브루틴의 구문과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-122">The syntax of a lambda expression resembles that of a standard subroutine.</span></span> <span data-ttu-id="6ae58-123">차이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-123">The differences are as follows:</span></span>  
  
- <span data-ttu-id="6ae58-124">람다 식에 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-124">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="6ae58-125">람다 식에는 또는와 같은 한정자를 사용할 수 없습니다 `Overloads` `Overrides` .</span><span class="sxs-lookup"><span data-stu-id="6ae58-125">A lambda expression cannot have a modifier, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="6ae58-126">한 줄로 된 람다 식의 본문은 식이 아니라 문 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-126">The body of a single-line lambda expression must be a statement, not an expression.</span></span> <span data-ttu-id="6ae58-127">본문은 sub 프로시저에 대 한 호출로 구성 될 수 있지만 함수 프로시저에 대 한 호출로 구성 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-127">The body can consist of a call to a sub procedure, but not a call to a function procedure.</span></span>  
  
- <span data-ttu-id="6ae58-128">람다 식에서 모든 매개 변수에는 지정 된 데이터 형식이 있어야 합니다. 그렇지 않으면 모든 매개 변수가 유추 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-128">In a lambda expression, either all parameters must have specified data types or all parameters must be inferred.</span></span>  
  
- <span data-ttu-id="6ae58-129">`ParamArray`람다 식에는 선택적 매개 변수와 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-129">Optional and `ParamArray` parameters are not permitted in lambda expressions.</span></span>  
  
- <span data-ttu-id="6ae58-130">람다 식에는 제네릭 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-130">Generic parameters are not permitted in lambda expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ae58-131">예제</span><span class="sxs-lookup"><span data-stu-id="6ae58-131">Example</span></span>  

 <span data-ttu-id="6ae58-132">다음은 값을 콘솔에 쓰는 람다 식의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-132">Following is an example of a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="6ae58-133">이 예제에서는 서브루틴의 단일 줄 및 여러 줄 람다 식 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ae58-133">The example shows both the single-line and multiline lambda expression syntax for a subroutine.</span></span> <span data-ttu-id="6ae58-134">더 많은 예제는 [람다 식](../../programming-guide/language-features/procedures/lambda-expressions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6ae58-134">For more examples, see [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="6ae58-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ae58-135">See also</span></span>

- [<span data-ttu-id="6ae58-136">Sub 문</span><span class="sxs-lookup"><span data-stu-id="6ae58-136">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="6ae58-137">람다 식</span><span class="sxs-lookup"><span data-stu-id="6ae58-137">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="6ae58-138">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="6ae58-138">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="6ae58-139">문</span><span class="sxs-lookup"><span data-stu-id="6ae58-139">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="6ae58-140">완화된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="6ae58-140">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
