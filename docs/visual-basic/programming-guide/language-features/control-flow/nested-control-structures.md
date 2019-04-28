---
title: 중첩 제어 구조(Visual Basic)
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
ms.openlocfilehash: c016722332dafa3d3be91a1e9e98cc0ce9a49717
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907996"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="c5065-102">중첩 제어 구조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5065-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="c5065-103">예를 들어 다른 제어 문의 내부에 제어 문을 배치할 수 있습니다는 `If...Then...Else` 내에서 차단 된 `For...Next` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="c5065-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="c5065-104">다른 제어 문 내에 배치 하는 제어 문 이라고 *중첩 된*합니다.</span><span class="sxs-lookup"><span data-stu-id="c5065-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="c5065-105">중첩 수준</span><span class="sxs-lookup"><span data-stu-id="c5065-105">Nesting Levels</span></span>  
 <span data-ttu-id="c5065-106">Visual Basic의 제어 구조를 원하는 만큼 많은 수준으로 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5065-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="c5065-107">각각의 본문을 들여쓰기 하 여 중첩 된 구조를 보다 쉽게 읽을 수 있도록 일반적으로 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5065-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="c5065-108">통합된 개발 환경 (IDE) 편집기를 자동으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5065-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="c5065-109">다음 예제에서는 절차의에서 `sumRows` 행렬의 각 행의 양의 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5065-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="c5065-110">앞의 예제에서 첫 번째 `Next` 문 내부 닫습니다 `For` 루프 및 마지막 `Next` 문을 닫습니다 외부 `For` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="c5065-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="c5065-111">마찬가지로, 중첩 된 `If` 문에서 `End If` 문은 가장 가까운 이전에 자동으로 적용 `If` 문.</span><span class="sxs-lookup"><span data-stu-id="c5065-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="c5065-112">중첩 `Do` 루프는 가장 안쪽의 유사한 방식으로 작동 `Loop` 가장 안쪽의 일치 하는 문을 `Do` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="c5065-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5065-113">많은 컨트롤 구조체에 대 한 키워드를 클릭 하면 모든 구조의 키워드 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5065-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="c5065-114">예를 들어 클릭 하면 `If` 에 `If...Then...Else` 생성, 모든 인스턴스의 `If`, `Then`, `ElseIf`, `Else`, 및 `End If` 생성에서의 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5065-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="c5065-115">다음 또는 이전 강조 표시 된 키워드를 이동 하려면 CTRL + SHIFT + 아래쪽 화살표 또는 CTRL + SHIFT + 위쪽 화살표를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c5065-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="c5065-116">다른 종류의 제어 구조를 중첩합니다.</span><span class="sxs-lookup"><span data-stu-id="c5065-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="c5065-117">한 가지 다른 종류의 제어 구조를 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5065-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="c5065-118">다음 예제에서는 `With` 내에서 블록을 `For Each` 루프 및 중첩 `If` 블록 내는 `With` 블록.</span><span class="sxs-lookup"><span data-stu-id="c5065-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="c5065-119">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="c5065-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="c5065-120">제어 구조를 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5065-120">You cannot overlap control structures.</span></span> <span data-ttu-id="c5065-121">즉, 모든 중첩 된 구조는 다음 가장 안쪽 구조 내에 완전히 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5065-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="c5065-122">예를 들어, 다음과 같은 배치 올바르지 때문에 `For` 내부 전에 루프 종료 `With` 블록을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5065-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![잘못 된 중첩의 예제를 보여 주는 다이어그램입니다.](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 <span data-ttu-id="c5065-124">Visual Basic 컴파일러는 이러한 겹치는 제어 구조를 검색 하 고 컴파일 시간 오류를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c5065-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5065-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="c5065-125">See also</span></span>

- [<span data-ttu-id="c5065-126">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="c5065-126">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="c5065-127">판단 구조</span><span class="sxs-lookup"><span data-stu-id="c5065-127">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="c5065-128">루프 구조</span><span class="sxs-lookup"><span data-stu-id="c5065-128">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="c5065-129">기타 제어 구조</span><span class="sxs-lookup"><span data-stu-id="c5065-129">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
