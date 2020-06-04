---
title: '방법: 코드 섹션 축소 및 숨기기'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: c11affe9c4dd4251ba8ff4b87029d314970b5fcb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404851"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="72f46-102">방법: 코드 섹션 축소 및 숨기기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72f46-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>

<span data-ttu-id="72f46-103">`#Region`지시문을 사용 하면 Visual Basic 파일에서 코드 섹션을 축소 하 고 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72f46-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="72f46-104">`#Region`지시문을 사용 하면 Visual Studio 코드 편집기를 사용할 때 확장 하거나 축소할 수 있는 코드 블록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72f46-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="72f46-105">코드를 선택적으로 숨기는 기능을 통해 파일을 보다 쉽게 관리 하 고 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72f46-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="72f46-106">자세한 내용은 [개요](/visualstudio/ide/outlining)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72f46-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>

<span data-ttu-id="72f46-107">`#Region`지시문은와 같은 코드 블록 의미 체계를 지원 `#If...#End If` 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f46-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="72f46-108">즉, 한 블록에서 시작 하 여 다른 블록에서 끝날 수 없습니다. start 및 end는 동일한 블록에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f46-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="72f46-109">`#Region`지시문은 함수 내에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72f46-109">`#Region` directives are not supported within functions.</span></span>

## <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="72f46-110">코드 섹션을 축소 하 고 숨기려면</span><span class="sxs-lookup"><span data-stu-id="72f46-110">To collapse and hide a section of code</span></span>

<span data-ttu-id="72f46-111">`#Region`다음 예제와 같이 및 문 사이에 코드 섹션을 놓습니다 `#End Region` .</span><span class="sxs-lookup"><span data-stu-id="72f46-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

<span data-ttu-id="72f46-112">`#Region`블록은 코드 파일에서 여러 번 사용할 수 있습니다. 따라서 사용자는 프로시저 및 클래스의 고유한 블록을 정의 하 여 축소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72f46-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="72f46-113">`#Region`블록은 다른 블록 내에 중첩 될 수도 있습니다 `#Region` .</span><span class="sxs-lookup"><span data-stu-id="72f46-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>

> [!NOTE]
> <span data-ttu-id="72f46-114">코드를 숨기면 문이 컴파일되지 않으며 문에 영향을 주지 않습니다 `#If...#End If` .</span><span class="sxs-lookup"><span data-stu-id="72f46-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>

## <a name="see-also"></a><span data-ttu-id="72f46-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72f46-115">See also</span></span>

- [<span data-ttu-id="72f46-116">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="72f46-116">Conditional Compilation</span></span>](conditional-compilation.md)
- [<span data-ttu-id="72f46-117">#Region 지시문</span><span class="sxs-lookup"><span data-stu-id="72f46-117">#Region Directive</span></span>](../../language-reference/directives/region-directive.md)
- [<span data-ttu-id="72f46-118">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="72f46-118">#If...Then...#Else Directives</span></span>](../../language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="72f46-119">개요</span><span class="sxs-lookup"><span data-stu-id="72f46-119">Outlining</span></span>](/visualstudio/ide/outlining)
