---
title: 기타 제어 구조
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: 758df361f421684655147ae288af3f350e53c4d7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348127"
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="14a47-102">기타 제어 구조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14a47-102">Other Control Structures (Visual Basic)</span></span>
<span data-ttu-id="14a47-103">Visual Basic는 리소스를 삭제 하거나 개체 참조를 반복 해야 하는 횟수를 줄이는 데 도움이 되는 제어 구조를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a47-103">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="14a47-104">Using ... 생성 사용 종료</span><span class="sxs-lookup"><span data-stu-id="14a47-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="14a47-105">`Using...End Using` 생성은 SQL 연결과 같은 리소스를 사용 하는 문 블록을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a47-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="14a47-106">필요에 따라 `Using` 문을 사용 하 여 리소스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a47-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="14a47-107">`Using` 블록을 종료 하면 Visual Basic 다른 코드에서 사용할 수 있도록 리소스를 자동으로 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a47-107">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="14a47-108">리소스는 로컬 이며 삭제 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a47-108">The resource must be local and disposable.</span></span> <span data-ttu-id="14a47-109">자세한 내용은 [using 문](../../../../visual-basic/language-reference/statements/using-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14a47-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="14a47-110">... 생성으로 종료</span><span class="sxs-lookup"><span data-stu-id="14a47-110">With...End With Construction</span></span>  
 <span data-ttu-id="14a47-111">`With...End With` 생성을 사용 하면 개체 참조를 한 번 지정한 다음 해당 멤버에 액세스 하는 일련의 문을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a47-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="14a47-112">이를 통해 Visual Basic는 코드를 단순화 하 고 성능을 향상 시킬 수 있습니다 .이를 통해 액세스 하는 각 문에 대 한 참조를 다시 설정할 필요가 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="14a47-112">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="14a47-113">자세한 내용은 다음 [을 참조 하세요. End With 문](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span><span class="sxs-lookup"><span data-stu-id="14a47-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14a47-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="14a47-114">See also</span></span>

- [<span data-ttu-id="14a47-115">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="14a47-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="14a47-116">판단 구조</span><span class="sxs-lookup"><span data-stu-id="14a47-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="14a47-117">루프 구조</span><span class="sxs-lookup"><span data-stu-id="14a47-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="14a47-118">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="14a47-118">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="14a47-119">Using 문</span><span class="sxs-lookup"><span data-stu-id="14a47-119">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
- [<span data-ttu-id="14a47-120">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="14a47-120">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
