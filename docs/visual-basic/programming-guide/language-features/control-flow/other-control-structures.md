---
title: 기타 제어 구조체
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: c6d80b237c7c3512c2904547842fdeb3c69bef68
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402020"
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="eff3e-102">기타 제어 구조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eff3e-102">Other Control Structures (Visual Basic)</span></span>
<span data-ttu-id="eff3e-103">Visual Basic는 리소스를 삭제 하거나 개체 참조를 반복 해야 하는 횟수를 줄이는 데 도움이 되는 제어 구조를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eff3e-103">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="eff3e-104">Using ... 생성 사용 종료</span><span class="sxs-lookup"><span data-stu-id="eff3e-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="eff3e-105">`Using...End Using`생성은 SQL 연결과 같은 리소스를 사용 하는 문 블록을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eff3e-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="eff3e-106">필요에 따라 문을 사용 하 여 리소스를 가져올 수 있습니다 `Using` .</span><span class="sxs-lookup"><span data-stu-id="eff3e-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="eff3e-107">블록을 종료 하면 `Using` Visual Basic 다른 코드에서 사용할 수 있도록 리소스를 자동으로 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="eff3e-107">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="eff3e-108">리소스는 로컬 이며 삭제 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eff3e-108">The resource must be local and disposable.</span></span> <span data-ttu-id="eff3e-109">자세한 내용은 [Using 문](../../../language-reference/statements/using-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eff3e-109">For more information, see [Using Statement](../../../language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="eff3e-110">... 생성으로 종료</span><span class="sxs-lookup"><span data-stu-id="eff3e-110">With...End With Construction</span></span>  
 <span data-ttu-id="eff3e-111">생성을 통해 `With...End With` 개체 참조를 한 번 지정한 다음 해당 멤버에 액세스 하는 일련의 문을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eff3e-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="eff3e-112">이를 통해 Visual Basic는 코드를 단순화 하 고 성능을 향상 시킬 수 있습니다 .이를 통해 액세스 하는 각 문에 대 한 참조를 다시 설정할 필요가 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="eff3e-112">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="eff3e-113">자세한 내용은 다음 [을 참조 하세요. End With 문](../../../language-reference/statements/with-end-with-statement.md)</span><span class="sxs-lookup"><span data-stu-id="eff3e-113">For more information, see [With...End With Statement](../../../language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eff3e-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eff3e-114">See also</span></span>

- [<span data-ttu-id="eff3e-115">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="eff3e-115">Control Flow</span></span>](index.md)
- [<span data-ttu-id="eff3e-116">판단 구조체</span><span class="sxs-lookup"><span data-stu-id="eff3e-116">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="eff3e-117">루프 구조체</span><span class="sxs-lookup"><span data-stu-id="eff3e-117">Loop Structures</span></span>](loop-structures.md)
- [<span data-ttu-id="eff3e-118">중첩 제어 구조체</span><span class="sxs-lookup"><span data-stu-id="eff3e-118">Nested Control Structures</span></span>](nested-control-structures.md)
- [<span data-ttu-id="eff3e-119">Using 문</span><span class="sxs-lookup"><span data-stu-id="eff3e-119">Using Statement</span></span>](../../../language-reference/statements/using-statement.md)
- [<span data-ttu-id="eff3e-120">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="eff3e-120">With...End With Statement</span></span>](../../../language-reference/statements/with-end-with-statement.md)
