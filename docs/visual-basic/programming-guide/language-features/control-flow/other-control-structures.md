---
title: 기타 제어 구조(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: c42070ce2ea866e59e1b2e190f7c05e1ee7cc922
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907844"
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="c8678-102">기타 제어 구조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8678-102">Other Control Structures (Visual Basic)</span></span>
<span data-ttu-id="c8678-103">Visual Basic에는 제어 구조 도움이 되는 리소스를 삭제 또는 개체 참조를 반복 해야 하는 횟수를 줄일 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8678-103">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="c8678-104">사용 하는 중... 생성을 사용 하 여 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8678-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="c8678-105">`Using...End Using` 생성 설정 확인 하는 문 블록 SQL 연결과 같은 리소스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8678-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="c8678-106">사용 하 여 리소스를 선택적으로 가져올 수는 `Using` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="c8678-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="c8678-107">종료 하는 경우는 `Using` 블록, Visual Basic 리소스의 다른 코드를 사용 하 여 사용할 수 있도록 자동으로 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8678-107">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="c8678-108">리소스는 로컬 및 삭제 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8678-108">The resource must be local and disposable.</span></span> <span data-ttu-id="c8678-109">자세한 내용은 [using 문](../../../../visual-basic/language-reference/statements/using-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8678-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="c8678-110">사용 하 여는 중... 생성 된 종료</span><span class="sxs-lookup"><span data-stu-id="c8678-110">With...End With Construction</span></span>  
 <span data-ttu-id="c8678-111">`With...End With` 생성 개체 참조를 한 번만 지정할 수 있습니다 다음 일련의 해당 멤버에 액세스 하는 문 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8678-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="c8678-112">이 코드를 단순화 하 고 Visual Basic 액세스 하는 각 문에 대 한 참조를 다시 설정할 필요가 없기 때문에 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8678-112">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="c8678-113">자세한 내용은 참조 하세요. [사용 하 여는 중... 문을 사용 하 여 종료](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c8678-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8678-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="c8678-114">See also</span></span>

- [<span data-ttu-id="c8678-115">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="c8678-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="c8678-116">판단 구조</span><span class="sxs-lookup"><span data-stu-id="c8678-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="c8678-117">루프 구조</span><span class="sxs-lookup"><span data-stu-id="c8678-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="c8678-118">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="c8678-118">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="c8678-119">Using 문</span><span class="sxs-lookup"><span data-stu-id="c8678-119">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
- [<span data-ttu-id="c8678-120">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="c8678-120">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
