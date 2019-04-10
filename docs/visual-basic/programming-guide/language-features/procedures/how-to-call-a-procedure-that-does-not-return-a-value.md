---
title: '방법: (Visual Basic) 값을 반환 하지 않는 프로시저 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 6e3ce2a184ca5411a6a016929a16bf3d67e669ca
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335474"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="19eff-102">방법: (Visual Basic) 값을 반환 하지 않는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="19eff-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="19eff-103">`Sub` 프로시저가 호출 코드에 값을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19eff-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="19eff-104">호출 명시적으로 독립 실행형 호출 문을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="19eff-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="19eff-105">식 내에서 해당 이름을 사용 하 여 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19eff-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="19eff-106">Sub 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="19eff-106">To call a Sub procedure</span></span>  
  
1. <span data-ttu-id="19eff-107">이름을 지정 합니다 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="19eff-107">Specify the name of the `Sub` procedure.</span></span>  
  
2. <span data-ttu-id="19eff-108">괄호로 묶어 인수 목록에 프로시저 이름 뒤에.</span><span class="sxs-lookup"><span data-stu-id="19eff-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="19eff-109">인수가 없는 경우에 필요에 따라 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19eff-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="19eff-110">그러나 괄호를 사용 하 여 쉽게 코드 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19eff-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="19eff-111">쉼표로 구분 하 여 괄호 안에 인수 목록의 인수를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="19eff-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="19eff-112">같은 순서로 인수를 지정 해야 하는 `Sub` 프로시저는 해당 매개 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="19eff-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="19eff-113">다음 예제에서는 Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> 응용 프로그램 창을 활성화 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="19eff-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> <span data-ttu-id="19eff-114">창 제목이 유일한 인수로 변수로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="19eff-114">takes the window title as its sole argument.</span></span> <span data-ttu-id="19eff-115">호출 코드에 값을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19eff-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="19eff-116">이 예제에서는 throw Notepad 프로세스를 실행 하지 않는 경우는 <xref:System.ArgumentException>합니다.</span><span class="sxs-lookup"><span data-stu-id="19eff-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="19eff-117">`Shell` 절차에서는 응용 프로그램을 지정 된 경로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="19eff-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="19eff-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="19eff-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [<span data-ttu-id="19eff-119">절차</span><span class="sxs-lookup"><span data-stu-id="19eff-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="19eff-120">하위 프로시저</span><span class="sxs-lookup"><span data-stu-id="19eff-120">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="19eff-121">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="19eff-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="19eff-122">Sub 문</span><span class="sxs-lookup"><span data-stu-id="19eff-122">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="19eff-123">방법: 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="19eff-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="19eff-124">방법: 값을 반환하는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="19eff-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="19eff-125">방법: Visual Basic의 이벤트 처리기를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="19eff-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
