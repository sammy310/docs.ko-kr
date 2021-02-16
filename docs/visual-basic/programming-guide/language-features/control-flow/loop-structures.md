---
description: '자세한 정보: 루프 구조 (Visual Basic)'
title: 루프 구조체
ms.date: 07/20/2015
helpviewer_keywords:
- control flow [Visual Basic], loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures [Visual Basic]
- statements [Visual Basic], loop
- Do statement [Visual Basic], Do loops
- conditional statements [Visual Basic], loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
ms.openlocfilehash: 82ff36d8f5c05501fcff0f1d564e2613c9b78953
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480650"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="247c3-103">루프 구조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="247c3-103">Loop Structures (Visual Basic)</span></span>

<span data-ttu-id="247c3-104">Visual Basic 루프 구조를 사용 하면 하나 이상의 코드 줄을 반복적으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247c3-104">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="247c3-105">조건이 `True` 이거나, 조건이 `False` 이거나, 지정 된 횟수 만큼 또는 컬렉션의 각 요소에 대해 한 번까지 루프 구조에서 문을 반복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247c3-105">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="247c3-106">다음 그림은 조건이 true가 될 때까지 문 집합을 실행 하는 루프 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="247c3-106">The following illustration shows a loop structure that runs a set of statements until a condition becomes true:</span></span>  
  
 ![Do ...를 보여 주는 순서도 ... Until 루프.](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a><span data-ttu-id="247c3-108">While 루프</span><span class="sxs-lookup"><span data-stu-id="247c3-108">While Loops</span></span>  

 <span data-ttu-id="247c3-109">`While`... `End While` 생성은 문에 지정 된 조건이 인 한 문 집합을 실행 합니다 `While` `True` .</span><span class="sxs-lookup"><span data-stu-id="247c3-109">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="247c3-110">자세한 내용은 While 항목을 참조 하세요. [ End While 문](../../../language-reference/statements/while-end-while-statement.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="247c3-110">For more information, see [While...End While Statement](../../../language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="247c3-111">Do 루프</span><span class="sxs-lookup"><span data-stu-id="247c3-111">Do Loops</span></span>  

 <span data-ttu-id="247c3-112">`Do`... `Loop` 생성을 사용 하면 루프 구조의 시작 부분 또는 끝 부분에서 조건을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247c3-112">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="247c3-113">조건이 유지 되는 동안 `True` 또는 상태가 될 때까지 루프를 반복할지 여부도 지정할 수 있습니다 `True` .</span><span class="sxs-lookup"><span data-stu-id="247c3-113">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="247c3-114">자세한 내용은 다음 [을 참조 하세요. Loop 문](../../../language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="247c3-114">For more information, see [Do...Loop Statement](../../../language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="247c3-115">For 루프</span><span class="sxs-lookup"><span data-stu-id="247c3-115">For Loops</span></span>  

 <span data-ttu-id="247c3-116">`For`... 생성은 설정 된 횟수 만큼 루프를 수행 합니다. `Next`</span><span class="sxs-lookup"><span data-stu-id="247c3-116">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="247c3-117">루프 제어 변수 ( *카운터* 라고도 함)를 사용 하 여 반복을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="247c3-117">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="247c3-118">이 카운터에 대 한 시작 값과 끝 값을 지정 하 고, 필요에 따라 반복에서 다음 반복까지 늘리는 크기를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247c3-118">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="247c3-119">자세한 내용은 다음 [을 참조 하세요. 다음 문](../../../language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="247c3-119">For more information, see [For...Next Statement](../../../language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="247c3-120">For Each 루프</span><span class="sxs-lookup"><span data-stu-id="247c3-120">For Each Loops</span></span>  

 <span data-ttu-id="247c3-121">`For Each`... `Next` 생성은 컬렉션의 각 요소에 대해 문 집합을 한 번씩 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="247c3-121">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="247c3-122">루프 제어 변수를 지정 하지만 해당 변수를 시작 하거나 종료 하는 값을 결정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="247c3-122">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="247c3-123">자세한 내용은 For Each ...를 참조 하십시오. [ 다음 문](../../../language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="247c3-123">For more information, see [For Each...Next Statement](../../../language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="247c3-124">추가 정보</span><span class="sxs-lookup"><span data-stu-id="247c3-124">See also</span></span>

- [<span data-ttu-id="247c3-125">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="247c3-125">Control Flow</span></span>](index.md)
- [<span data-ttu-id="247c3-126">판단 구조체</span><span class="sxs-lookup"><span data-stu-id="247c3-126">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="247c3-127">기타 제어 구조체</span><span class="sxs-lookup"><span data-stu-id="247c3-127">Other Control Structures</span></span>](other-control-structures.md)
- [<span data-ttu-id="247c3-128">중첩 제어 구조체</span><span class="sxs-lookup"><span data-stu-id="247c3-128">Nested Control Structures</span></span>](nested-control-structures.md)
