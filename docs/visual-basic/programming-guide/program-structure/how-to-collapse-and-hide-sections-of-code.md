---
title: '방법: (Visual Basic) 코드 섹션 축소 및 숨기기'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: 367527fd638f6855077caf8ff5911edb333dfcbf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648774"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="93b8c-102">방법: (Visual Basic) 코드 섹션 축소 및 숨기기</span><span class="sxs-lookup"><span data-stu-id="93b8c-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="93b8c-103">`#Region` 지시문을 사용 하면 Visual Basic 파일에서 코드 섹션 축소 및 숨기기 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93b8c-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="93b8c-104">`#Region` 지시문을 사용 하면 Visual Studio 코드 편집기를 사용 하는 경우 축소 또는 확장할 수 있는 코드 블록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93b8c-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="93b8c-105">코드를 선택적으로 숨길 수 있습니다 파일을 보다 관리 가능 하 고 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93b8c-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="93b8c-106">자세한 내용은 [개요](/visualstudio/ide/outlining)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93b8c-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="93b8c-107">`#Region` 지시문이 같은 코드 블록 의미 체계를 지원 `#If...#End If`합니다.</span><span class="sxs-lookup"><span data-stu-id="93b8c-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="93b8c-108">즉, 하나의 블록 시작 없습니다 하며 다른; 종료 시작 및 끝 동일한 블록에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93b8c-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="93b8c-109">`#Region` 지시문 함수 내에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93b8c-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="93b8c-110">축소 하 고 코드 부분을 숨기려면</span><span class="sxs-lookup"><span data-stu-id="93b8c-110">To collapse and hide a section of code</span></span>  
  
- <span data-ttu-id="93b8c-111">부분 사이 코드를 배치 합니다 `#Region` 및 `#End Region` 문을 다음 예제와 같이:</span><span class="sxs-lookup"><span data-stu-id="93b8c-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]  
  
     <span data-ttu-id="93b8c-112">`#Region` 사용자 고유의 블록을 절차와를 차례로 축소할 수 있는 클래스를 정의할 수 있습니다 따라서; 블록이 코드 파일에서 여러 번 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93b8c-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="93b8c-113">`#Region` 블록 내의 다른 중첩 될 수도 있습니다 `#Region` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="93b8c-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="93b8c-114">코드에서 컴파일되는 하지 않는 숨기고 영향을 주지 않습니다 `#If...#End If` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="93b8c-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93b8c-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="93b8c-115">See also</span></span>

- [<span data-ttu-id="93b8c-116">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="93b8c-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="93b8c-117">#Region 지시문</span><span class="sxs-lookup"><span data-stu-id="93b8c-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="93b8c-118">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="93b8c-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="93b8c-119">개요</span><span class="sxs-lookup"><span data-stu-id="93b8c-119">Outlining</span></span>](/visualstudio/ide/outlining)
