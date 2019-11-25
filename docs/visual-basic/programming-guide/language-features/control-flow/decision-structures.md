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
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="4f2ab-102">판단 구조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f2ab-102">Decision Structures (Visual Basic)</span></span>
<span data-ttu-id="4f2ab-103">Visual Basic lets you test conditions and perform different operations depending on the results of that test.</span><span class="sxs-lookup"><span data-stu-id="4f2ab-103">Visual Basic lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="4f2ab-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span><span class="sxs-lookup"><span data-stu-id="4f2ab-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="4f2ab-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span><span class="sxs-lookup"><span data-stu-id="4f2ab-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 ![A flow chart of an If...Then...Else construction.](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="4f2ab-107">If...Then...Else Construction</span><span class="sxs-lookup"><span data-stu-id="4f2ab-107">If...Then...Else Construction</span></span>  
 <span data-ttu-id="4f2ab-108">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span><span class="sxs-lookup"><span data-stu-id="4f2ab-108">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="4f2ab-109">You can test conditions and take actions in the following ways:</span><span class="sxs-lookup"><span data-stu-id="4f2ab-109">You can test conditions and take actions in the following ways:</span></span>  
  
- <span data-ttu-id="4f2ab-110">Run one or more statements if a condition is `True`</span><span class="sxs-lookup"><span data-stu-id="4f2ab-110">Run one or more statements if a condition is `True`</span></span>  
  
- <span data-ttu-id="4f2ab-111">Run one or more statements if a condition is `False`</span><span class="sxs-lookup"><span data-stu-id="4f2ab-111">Run one or more statements if a condition is `False`</span></span>  
  
- <span data-ttu-id="4f2ab-112">Run some statements if a condition is `True` and others if it is `False`</span><span class="sxs-lookup"><span data-stu-id="4f2ab-112">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
- <span data-ttu-id="4f2ab-113">Test an additional condition if a prior condition is `False`</span><span class="sxs-lookup"><span data-stu-id="4f2ab-113">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="4f2ab-114">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4f2ab-114">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="4f2ab-115">You can use a single-line version if you have just one test and one statement to run.</span><span class="sxs-lookup"><span data-stu-id="4f2ab-115">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="4f2ab-116">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span><span class="sxs-lookup"><span data-stu-id="4f2ab-116">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="4f2ab-117">Select...Case Construction</span><span class="sxs-lookup"><span data-stu-id="4f2ab-117">Select...Case Construction</span></span>  
 <span data-ttu-id="4f2ab-118">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span><span class="sxs-lookup"><span data-stu-id="4f2ab-118">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="4f2ab-119">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4f2ab-119">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="4f2ab-120">Try...Catch...Finally Construction</span><span class="sxs-lookup"><span data-stu-id="4f2ab-120">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="4f2ab-121">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span><span class="sxs-lookup"><span data-stu-id="4f2ab-121">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="4f2ab-122">You can take different actions for different exceptions.</span><span class="sxs-lookup"><span data-stu-id="4f2ab-122">You can take different actions for different exceptions.</span></span> <span data-ttu-id="4f2ab-123">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span><span class="sxs-lookup"><span data-stu-id="4f2ab-123">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="4f2ab-124">자세한 내용은 [Try...Catch...Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f2ab-124">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f2ab-125">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span><span class="sxs-lookup"><span data-stu-id="4f2ab-125">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="4f2ab-126">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span><span class="sxs-lookup"><span data-stu-id="4f2ab-126">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="4f2ab-127">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span><span class="sxs-lookup"><span data-stu-id="4f2ab-127">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f2ab-128">참조</span><span class="sxs-lookup"><span data-stu-id="4f2ab-128">See also</span></span>

- [<span data-ttu-id="4f2ab-129">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="4f2ab-129">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="4f2ab-130">루프 구조</span><span class="sxs-lookup"><span data-stu-id="4f2ab-130">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="4f2ab-131">기타 제어 구조</span><span class="sxs-lookup"><span data-stu-id="4f2ab-131">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="4f2ab-132">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="4f2ab-132">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="4f2ab-133">If 연산자</span><span class="sxs-lookup"><span data-stu-id="4f2ab-133">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
