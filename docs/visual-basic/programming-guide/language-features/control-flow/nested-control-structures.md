---
title: 중첩 제어 구조체
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
ms.openlocfilehash: b696c79cd3cada4416b3f4b6cdf96f00b89a5a0a
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266926"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="fe882-102">중첩 제어 구조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe882-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="fe882-103">다른 컨트롤 문(예: 루프 내의 `If...Then...Else` 블록) `For...Next` 내에 제어 문을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="fe882-104">다른 제어 문 안에 배치된 제어 문이 *중첩되었다고*합니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="fe882-105">중첩 수준</span><span class="sxs-lookup"><span data-stu-id="fe882-105">Nesting Levels</span></span>  
 <span data-ttu-id="fe882-106">Visual Basic의 컨트롤 구조는 원하는 수의 레벨에 중첩될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="fe882-107">각 구조의 본문을 들여쓰기하여 중첩 된 구조를 더 읽기 쉽게 만드는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="fe882-108">통합 개발 환경(IDE) 편집기는 자동으로 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="fe882-109">다음 예제에서 프로시저는 `sumRows` 행렬의 각 행의 양수 요소를 함께 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
```vb
Public Sub sumRows(ByVal a(,) As Double, ByRef r() As Double)  
    Dim i, j As Integer  
    For i = 0 To UBound(a, 1)  
        r(i) = 0  
        For j = 0 To UBound(a, 2)  
            If a(i, j) > 0 Then  
                r(i) = r(i) + a(i, j)  
            End If  
        Next j  
    Next i  
End Sub  
```  
  
 <span data-ttu-id="fe882-110">앞의 예제에서 첫 `Next` 번째 문은 내부 `For` 루프를 `Next` 닫고 마지막 `For` 문은 외부 루프를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="fe882-111">마찬가지로 중첩 된 `If` 문에서 `End If` 문은 가장 가까운 이전 `If` 문에 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="fe882-112">중첩 `Do` 루프는 가장 안쪽 문과 일치하는 `Loop` `Do` 가장 안쪽 문과 비슷한 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe882-113">많은 컨트롤 구조의 경우 키워드를 클릭하면 구조의 모든 키워드가 강조 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="fe882-114">예를 들어 구성을 `If` `If...Then...Else` 클릭하면 `If`구성의 모든 `Then` `ElseIf` `Else` `End If` 인스턴스가 강조 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="fe882-115">강조 표시된 다음 또는 이전 키워드로 이동하려면 CTRL+SHIFT+DOWN 화살표 또는 CTRL+SHIFT+UP 화살표를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="fe882-116">다양한 종류의 제어 구조 중첩</span><span class="sxs-lookup"><span data-stu-id="fe882-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="fe882-117">한 종류의 제어 구조를 다른 종류 내에 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="fe882-118">다음 예제에서는 `With` `For Each` 루프 내부의 블록과 `If` `With` 블록 내부에 중첩된 블록을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
```vb
For Each ctl As System.Windows.Forms.Control In Me.Controls  
    With ctl  
        .BackColor = System.Drawing.Color.Yellow  
        .ForeColor = System.Drawing.Color.Black  
        If .CanFocus Then  
            .Text = "Colors changed"  
            If Not .Focus() Then  
                ' Insert code to process failed focus.  
            End If  
        End If  
    End With  
Next ctl  
```  
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="fe882-119">겹치는 제어 구조</span><span class="sxs-lookup"><span data-stu-id="fe882-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="fe882-120">컨트롤 구조를 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-120">You cannot overlap control structures.</span></span> <span data-ttu-id="fe882-121">즉, 중첩된 구조는 가장 안쪽 의 구조 내에 완전히 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="fe882-122">예를 들어 내부 `For` `With` 블록이 종료되기 전에 루프가 종료되므로 다음 배열이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![잘못된 중첩의 예를 보여 주는 다이어그램입니다.](./media/nested-control-structures/example-invalid-nesting.gif)
  
 <span data-ttu-id="fe882-124">Visual Basic 컴파일러는 이러한 겹치는 제어 구조를 감지하고 컴파일 타임 오류를 신호합니다.</span><span class="sxs-lookup"><span data-stu-id="fe882-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe882-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe882-125">See also</span></span>

- [<span data-ttu-id="fe882-126">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="fe882-126">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="fe882-127">판단 구조</span><span class="sxs-lookup"><span data-stu-id="fe882-127">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="fe882-128">루프 구조체</span><span class="sxs-lookup"><span data-stu-id="fe882-128">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="fe882-129">기타 제어 구조</span><span class="sxs-lookup"><span data-stu-id="fe882-129">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
