---
title: 중첩 제어 구조
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
ms.openlocfilehash: 5818b13661fb4415c6f531b741b8a963a80bd2b8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348147"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="3dd49-102">중첩 제어 구조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3dd49-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="3dd49-103">다른 제어 문 내에 제어 문을 추가할 수 있습니다. 예를 들어 `For...Next` 루프 내의 `If...Then...Else` 블록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="3dd49-104">다른 제어 문 내에 배치 된 제어 문은 *중첩*된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="3dd49-105">중첩 수준</span><span class="sxs-lookup"><span data-stu-id="3dd49-105">Nesting Levels</span></span>  
 <span data-ttu-id="3dd49-106">Visual Basic의 제어 구조는 원하는 만큼 수준으로 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="3dd49-107">각각의 본문을 들여쓰기 하 여 중첩 된 구조를 더 읽기 쉽게 만드는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="3dd49-108">IDE (통합 개발 환경) 편집기에서 자동으로이를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="3dd49-109">다음 예에서는 `sumRows` 프로시저에서 행렬의 각 행에 대 한 긍정 요소를 함께 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="3dd49-110">앞의 예제에서 첫 번째 `Next` 문은 내부 `For` 루프를 닫고 마지막 `Next` 문은 외부 `For` 루프를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="3dd49-111">마찬가지로, 중첩 된 `If` 문에서 `End If` 문은 가장 가까운 이전 `If` 문에 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="3dd49-112">중첩 된 `Do` 루프는 가장 안쪽의 `Do` 문과 일치 하는 가장 안쪽의 `Loop` 문을 사용 하 여 비슷한 방식으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3dd49-113">많은 컨트롤 구조에서 키워드를 클릭 하면 구조에 있는 모든 키워드가 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="3dd49-114">예를 들어 `If...Then...Else` 생성에서 `If`를 클릭 하면 생성 시 `If`, `Then`, `ElseIf`, `Else`및 `End If` 인스턴스가 모두 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="3dd49-115">다음 또는 이전 강조 표시 된 키워드로 이동 하려면 CTRL + SHIFT + 아래쪽 화살표 또는 CTRL + SHIFT + 위쪽 화살표를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="3dd49-116">여러 종류의 제어 구조 중첩</span><span class="sxs-lookup"><span data-stu-id="3dd49-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="3dd49-117">한 종류의 제어 구조를 다른 종류 내에 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="3dd49-118">다음 예제에서는 `For Each` 루프 내에 `With` 블록을 사용 하 고 `With` 블록 내에 중첩 된 `If` 블록을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="3dd49-119">겹치는 제어 구조</span><span class="sxs-lookup"><span data-stu-id="3dd49-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="3dd49-120">제어 구조는 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-120">You cannot overlap control structures.</span></span> <span data-ttu-id="3dd49-121">즉, 중첩 된 구조는 다음의 가장 안쪽 구조 내에 완전히 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="3dd49-122">예를 들어 다음 정렬은 내부 `With` 블록이 종료 되기 전에 `For` 루프가 종료 되기 때문에 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![잘못 된 중첩의 예를 보여 주는 다이어그램입니다.](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 <span data-ttu-id="3dd49-124">Visual Basic 컴파일러는 이러한 겹치는 제어 구조를 검색 하 고 컴파일 시간 오류를 신호로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3dd49-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dd49-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3dd49-125">See also</span></span>

- [<span data-ttu-id="3dd49-126">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="3dd49-126">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="3dd49-127">판단 구조</span><span class="sxs-lookup"><span data-stu-id="3dd49-127">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="3dd49-128">루프 구조</span><span class="sxs-lookup"><span data-stu-id="3dd49-128">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="3dd49-129">기타 제어 구조</span><span class="sxs-lookup"><span data-stu-id="3dd49-129">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
