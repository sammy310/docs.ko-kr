---
title: '방법: (Visual Basic) 값을 반환 하는 프로시저 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 6f45f01489ee84b6addb1f7c7c8dc584332f38dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59333888"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="95383-102">방법: (Visual Basic) 값을 반환 하는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="95383-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="95383-103">`Function` 프로시저가 호출 코드에 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="95383-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="95383-104">식 또는 대입문의 오른쪽에 있는 이름과 인수를 포함 하 여 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="95383-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="95383-105">식 내에서 함수 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="95383-105">To call a Function procedure within an expression</span></span>  
  
1. <span data-ttu-id="95383-106">사용 하 여는 `Function` 프로시저 변수를 사용할 때 동일한 방식으로 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="95383-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="95383-107">사용할 수는 `Function` 식에서 변수 또는 상수를 사용할 수 있습니다 원격 프로시저 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="95383-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2. <span data-ttu-id="95383-108">괄호로 묶어 인수 목록에 프로시저 이름 뒤에.</span><span class="sxs-lookup"><span data-stu-id="95383-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="95383-109">인수가 없는 경우에 필요에 따라 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95383-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="95383-110">그러나 괄호를 사용 하 여 쉽게 코드 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95383-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="95383-111">쉼표로 구분 하 여 괄호 안에 인수 목록의 인수를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="95383-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="95383-112">같은 순서로 인수를 지정 해야 하는 `Function` 프로시저는 해당 매개 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="95383-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="95383-113">또는 이름으로 하나 이상의 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95383-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="95383-114">자세한 내용은 [위치 및 이름별 인수 전달](./passing-arguments-by-position-and-by-name.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="95383-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4. <span data-ttu-id="95383-115">변수 값 처럼 식에 참여 하는 프로시저에서 반환 되는 값 또는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="95383-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="95383-116">대입문에서 함수 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="95383-116">To call a Function procedure in an assignment statement</span></span>  
  
1. <span data-ttu-id="95383-117">사용 된 `Function` 프로시저 이름 다음에 오는 (`=`) 대입문은 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="95383-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2. <span data-ttu-id="95383-118">괄호로 묶어 인수 목록에 프로시저 이름 뒤에.</span><span class="sxs-lookup"><span data-stu-id="95383-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="95383-119">인수가 없는 경우에 필요에 따라 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95383-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="95383-120">그러나 괄호를 사용 하 여 쉽게 코드 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95383-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="95383-121">쉼표로 구분 하 여 괄호 안에 인수 목록의 인수를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="95383-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="95383-122">같은 순서로 인수를 지정 해야 하는 `Function` 프로시저 이름으로 전달 하려는 경우가 아니면 해당 매개 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="95383-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4. <span data-ttu-id="95383-123">프로시저에서 반환 되는 값은 변수 또는 대입문의 왼쪽에는 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95383-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95383-124">예제</span><span class="sxs-lookup"><span data-stu-id="95383-124">Example</span></span>  
 <span data-ttu-id="95383-125">다음 예제에서는 Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> 운영 체제 환경 변수의 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="95383-125">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="95383-126">첫 번째 줄에서는 `Environ` 내에서 식과 두 번째 줄에서에서 호출 대입문 합니다.</span><span class="sxs-lookup"><span data-stu-id="95383-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="95383-127">`Environ` 변수 이름을 유일한 인수로 변수로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="95383-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="95383-128">호출 코드에 변수 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="95383-128">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="95383-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="95383-129">See also</span></span>

- [<span data-ttu-id="95383-130">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="95383-130">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="95383-131">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="95383-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="95383-132">Function 문</span><span class="sxs-lookup"><span data-stu-id="95383-132">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="95383-133">방법: 값을 반환 하는 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="95383-133">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="95383-134">방법: 프로시저에서 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="95383-134">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="95383-135">방법: 값을 반환 하지 않는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="95383-135">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
