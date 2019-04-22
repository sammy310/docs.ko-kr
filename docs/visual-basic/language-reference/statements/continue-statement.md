---
title: Continue 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 5523be69f2901851c86f6c0263548e3577507ff9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835390"
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="3332e-102">Continue 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3332e-102">Continue Statement (Visual Basic)</span></span>
<span data-ttu-id="3332e-103">루프의 다음 반복으로 즉시 제어를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="3332e-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3332e-104">구문</span><span class="sxs-lookup"><span data-stu-id="3332e-104">Syntax</span></span>  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="3332e-105">설명</span><span class="sxs-lookup"><span data-stu-id="3332e-105">Remarks</span></span>  
 <span data-ttu-id="3332e-106">전송할 수 있습니다 내부를 `Do`, `For`, 또는 `While` 루프의 다음 반복 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="3332e-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="3332e-107">제어를 전송 하는 것과 같은 루프 조건 테스트를 즉시 전달 합니다 `For` 또는 `While` 문 또는 `Do` 또는 `Loop` 문을 포함 하는 `Until` 또는 `While` 절.</span><span class="sxs-lookup"><span data-stu-id="3332e-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="3332e-108">사용할 수 있습니다 `Continue` 전송 허용 되는 루프의 모든 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3332e-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="3332e-109">컨트롤의 전송을 허용 규칙은 동일 하 게 합니다 [GoTo 문](../../../visual-basic/language-reference/statements/goto-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3332e-109">The rules allowing transfer of control are the same as with the [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md).</span></span>  
  
 <span data-ttu-id="3332e-110">예를 들어 루프 내에 완전히 포함 되어는 `Try` 블록을 `Catch` 블록 또는 `Finally` 블록을 사용할 수 있습니다 `Continue` 루프 밖으로 전송할 합니다.</span><span class="sxs-lookup"><span data-stu-id="3332e-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="3332e-111">반면, 경우에는 `Try`... `End Try` 루프 내에서 포함 된 구조를 사용할 수 없습니다 `Continue` 밖으로 제어를 전송 하는 `Finally` 블록 하는 데 사용할 수 / 전송를 `Try` 또는 `Catch` 개 완전히 전송 하는 경우에 차단 합니다 `Try`... `End Try` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="3332e-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="3332e-112">동일한 형식의 중첩 된 루프 예를 들어 있는지를 `Do` 루프 내에서 다른 `Do` 루프를 `Continue Do` 문은 가장 안쪽의 다음 반복으로 건너뜁니다 `Do` 포함 하는 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="3332e-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="3332e-113">사용할 수 없습니다 `Continue` 동일한 형식의 포함 된 루프의 다음 반복으로 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3332e-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="3332e-114">다양 한 유형의 중첩 된 루프 예를 들어 있는지를 `Do` 내에서 반복을 `For` 루프를 건너뛸 수 있습니다 하거나 루프의 다음 반복을 사용 하 여 `Continue Do` 또는 `Continue For`합니다.</span><span class="sxs-lookup"><span data-stu-id="3332e-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3332e-115">예제</span><span class="sxs-lookup"><span data-stu-id="3332e-115">Example</span></span>  
 <span data-ttu-id="3332e-116">다음 코드 예제에서는 `Continue While` 제수가 0 인 경우 배열에 포함 된 다음 열을 건너뛰려면 문입니다.</span><span class="sxs-lookup"><span data-stu-id="3332e-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="3332e-117">합니다 `Continue While` 안에 `For` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="3332e-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="3332e-118">전송 된 `While col < lastcol` 가장 안쪽의 다음 반복 문을 `While` 포함 하는 루프를 `For` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="3332e-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="3332e-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="3332e-119">See also</span></span>

- [<span data-ttu-id="3332e-120">Do...Loop 문</span><span class="sxs-lookup"><span data-stu-id="3332e-120">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="3332e-121">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="3332e-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="3332e-122">While...End While 문</span><span class="sxs-lookup"><span data-stu-id="3332e-122">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="3332e-123">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="3332e-123">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
