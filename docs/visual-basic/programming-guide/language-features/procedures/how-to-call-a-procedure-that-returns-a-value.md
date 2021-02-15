---
description: '자세히 알아보기: 방법: 값을 반환 하는 프로시저 호출 (Visual Basic)'
title: '방법: 값을 반환하는 프로시저 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 74c7b6c9340537088ac631fc47f9ebf7b1a203cb
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466746"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="6e971-103">방법: 값을 반환하는 프로시저 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e971-103">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>

<span data-ttu-id="6e971-104">`Function`프로시저는 호출 코드에 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-104">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="6e971-105">해당 이름과 인수를 대입문의 오른쪽에 포함 하거나 식에 포함 하 여 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-105">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="6e971-106">식 내에서 함수 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="6e971-106">To call a Function procedure within an expression</span></span>  
  
1. <span data-ttu-id="6e971-107">`Function`변수를 사용 하는 것과 동일한 방식으로 프로시저 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-107">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="6e971-108">`Function`식에서 변수나 상수를 사용할 수 있는 모든 곳에서 프로시저 호출을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-108">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2. <span data-ttu-id="6e971-109">프로시저 이름에 괄호를 추가 하 여 인수 목록을 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-109">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="6e971-110">인수가 없으면 선택적으로 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-110">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="6e971-111">그러나 괄호를 사용 하면 코드를 더 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-111">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="6e971-112">인수 목록에서 인수를 쉼표로 구분 하 여 괄호 안에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-112">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="6e971-113">프로시저에서 해당 하는 매개 변수를 정의 하는 순서와 동일한 순서로 인수를 제공 해야 `Function` 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-113">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="6e971-114">또는 하나 이상의 인수를 이름으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-114">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="6e971-115">자세한 내용은 [위치 및 이름으로 인수 전달](./passing-arguments-by-position-and-by-name.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e971-115">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4. <span data-ttu-id="6e971-116">프로시저에서 반환 된 값은 변수 또는 상수 값과 마찬가지로 식에 참여 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-116">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="6e971-117">대입문에서 함수 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="6e971-117">To call a Function procedure in an assignment statement</span></span>  
  
1. <span data-ttu-id="6e971-118">`Function`대입문에 등호 () 기호를 사용 하 여 프로시저 이름을 사용 `=` 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-118">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2. <span data-ttu-id="6e971-119">프로시저 이름에 괄호를 추가 하 여 인수 목록을 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-119">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="6e971-120">인수가 없으면 선택적으로 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-120">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="6e971-121">그러나 괄호를 사용 하면 코드를 더 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-121">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="6e971-122">인수 목록에서 인수를 쉼표로 구분 하 여 괄호 안에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-122">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="6e971-123">`Function`이름을 기준으로 전달 하는 경우를 제외 하 고 프로시저에서 해당 매개 변수를 정의 하는 순서와 동일한 순서로 인수를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-123">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4. <span data-ttu-id="6e971-124">프로시저에서 반환 된 값은 대입문의 왼쪽에 있는 변수 또는 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-124">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e971-125">예</span><span class="sxs-lookup"><span data-stu-id="6e971-125">Example</span></span>  

 <span data-ttu-id="6e971-126">다음 예에서는 Visual Basic를 호출 <xref:Microsoft.VisualBasic.Interaction.Environ%2A> 하 여 운영 체제 환경 변수의 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-126">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="6e971-127">첫 번째 줄은 `Environ` 식 내에서를 호출 하 고 두 번째 줄은 대입문에서 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-127">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="6e971-128">`Environ` 변수 이름을 유일한 인수로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-128">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="6e971-129">이 메서드는 호출 코드에 변수의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e971-129">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="6e971-130">추가 정보</span><span class="sxs-lookup"><span data-stu-id="6e971-130">See also</span></span>

- [<span data-ttu-id="6e971-131">함수 프로시저</span><span class="sxs-lookup"><span data-stu-id="6e971-131">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="6e971-132">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="6e971-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="6e971-133">Function 문</span><span class="sxs-lookup"><span data-stu-id="6e971-133">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="6e971-134">방법: 값을 반환하는 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="6e971-134">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="6e971-135">방법: 프로시저에서 값 반환</span><span class="sxs-lookup"><span data-stu-id="6e971-135">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="6e971-136">방법: 값을 반환하지 않는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="6e971-136">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
