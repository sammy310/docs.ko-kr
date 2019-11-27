---
title: 판단 구조
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: d0d4039ff2edc61ee8b4b732c6adcb6e420d73ea
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353969"
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="a68c6-102">판단 구조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a68c6-102">Decision Structures (Visual Basic)</span></span>
<span data-ttu-id="a68c6-103">Visual Basic를 사용 하면 조건을 테스트 하 고 해당 테스트의 결과에 따라 다른 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c6-103">Visual Basic lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="a68c6-104">조건에 대해 true 또는 false, 식의 다양 한 값 또는 일련의 문을 실행할 때 생성 되는 다양 한 예외에 대해 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c6-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="a68c6-105">다음 그림은 조건이 true 인지 false 인지에 따라 조건이 true 인지 테스트 하 고 다른 작업을 수행 하는 의사 결정 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a68c6-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 ![If...Then...Else 생성.](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="a68c6-107">If...Then...Else 생성</span><span class="sxs-lookup"><span data-stu-id="a68c6-107">If...Then...Else Construction</span></span>  
 <span data-ttu-id="a68c6-108">`If...Then...Else` 구문을 사용 하면 하나 이상의 조건을 테스트 하 고 각 조건에 따라 하나 이상의 문을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c6-108">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="a68c6-109">조건을 테스트 하 고 다음과 같은 방법으로 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c6-109">You can test conditions and take actions in the following ways:</span></span>  
  
- <span data-ttu-id="a68c6-110">조건이 `True` 경우 하나 이상의 문을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c6-110">Run one or more statements if a condition is `True`</span></span>  
  
- <span data-ttu-id="a68c6-111">조건이 `False` 경우 하나 이상의 문을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c6-111">Run one or more statements if a condition is `False`</span></span>  
  
- <span data-ttu-id="a68c6-112">조건 `True` 경우 일부 문을 실행 하 고, 다른 경우에는 `False`</span><span class="sxs-lookup"><span data-stu-id="a68c6-112">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
- <span data-ttu-id="a68c6-113">이전 조건이 `False` 경우 추가 조건을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68c6-113">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="a68c6-114">이러한 모든 가능성을 제공 하는 컨트롤 구조는 다음과 같은 경우입니다. [ 그런 다음 ... Else 문](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a68c6-114">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="a68c6-115">하나의 테스트와 한 개의 문이 실행 되는 경우 한 줄 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c6-115">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="a68c6-116">더 복잡 한 조건 및 동작 집합이 있는 경우 여러 줄 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c6-116">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="a68c6-117">Select...Case 생성</span><span class="sxs-lookup"><span data-stu-id="a68c6-117">Select...Case Construction</span></span>  
 <span data-ttu-id="a68c6-118">`Select...Case` 생성을 사용 하면 식을 한 번 계산 하 고 가능한 다른 값에 따라 다른 문 집합을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c6-118">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="a68c6-119">자세한 내용은 Select ...를 참조 하세요. [ Case 문](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a68c6-119">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="a68c6-120">Try...Catch...Finally 생성</span><span class="sxs-lookup"><span data-stu-id="a68c6-120">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="a68c6-121">`Try...Catch...Finally` 구문을 사용 하면 문 중 하나에서 예외가 발생 하는 경우 제어를 유지 하는 환경에서 일련의 문을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c6-121">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="a68c6-122">다른 예외에 대해 다른 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c6-122">You can take different actions for different exceptions.</span></span> <span data-ttu-id="a68c6-123">필요한 작업에 관계 없이 전체 `Try...Catch...Finally` 생성을 끝내기 전에 실행 되는 코드 블록을 선택적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68c6-123">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="a68c6-124">자세한 내용은 [Try...Catch...Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a68c6-124">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a68c6-125">많은 컨트롤 구조에서 키워드를 클릭 하면 구조에 있는 모든 키워드가 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a68c6-125">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="a68c6-126">예를 들어 `If...Then...Else` 생성에서 `If`를 클릭 하면 생성 시 `If`, `Then`, `ElseIf`, `Else`및 `End If` 인스턴스가 모두 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a68c6-126">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="a68c6-127">다음 또는 이전 강조 표시 된 키워드로 이동 하려면 CTRL + SHIFT + 아래쪽 화살표 또는 CTRL + SHIFT + 위쪽 화살표를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a68c6-127">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a68c6-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a68c6-128">See also</span></span>

- [<span data-ttu-id="a68c6-129">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="a68c6-129">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="a68c6-130">루프 구조</span><span class="sxs-lookup"><span data-stu-id="a68c6-130">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="a68c6-131">기타 제어 구조</span><span class="sxs-lookup"><span data-stu-id="a68c6-131">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="a68c6-132">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="a68c6-132">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="a68c6-133">If 연산자</span><span class="sxs-lookup"><span data-stu-id="a68c6-133">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
