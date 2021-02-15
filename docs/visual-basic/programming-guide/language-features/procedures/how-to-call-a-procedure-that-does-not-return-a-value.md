---
description: '자세히 알아보기: 방법: 값을 반환 하지 않는 프로시저 호출 (Visual Basic)'
title: '방법: 값을 반환하지 않는 프로시저 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 3aaa6b4358f0585323e6c8321eea7dbaa4906a44
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466772"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="857a8-103">방법: 값을 반환하지 않는 프로시저 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="857a8-103">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>

<span data-ttu-id="857a8-104">`Sub`프로시저는 호출 코드에 값을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="857a8-104">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="857a8-105">독립형 호출 문을 사용 하 여 명시적으로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="857a8-105">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="857a8-106">식 내에서 이름을 사용 하 여 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="857a8-106">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="857a8-107">Sub 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="857a8-107">To call a Sub procedure</span></span>  
  
1. <span data-ttu-id="857a8-108">프로시저의 이름을 지정 `Sub` 합니다.</span><span class="sxs-lookup"><span data-stu-id="857a8-108">Specify the name of the `Sub` procedure.</span></span>  
  
2. <span data-ttu-id="857a8-109">프로시저 이름에 괄호를 추가 하 여 인수 목록을 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="857a8-109">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="857a8-110">인수가 없으면 선택적으로 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="857a8-110">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="857a8-111">그러나 괄호를 사용 하면 코드를 더 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="857a8-111">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="857a8-112">인수 목록에서 인수를 쉼표로 구분 하 여 괄호 안에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="857a8-112">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="857a8-113">프로시저에서 해당 하는 매개 변수를 정의 하는 순서와 동일한 순서로 인수를 제공 해야 `Sub` 합니다.</span><span class="sxs-lookup"><span data-stu-id="857a8-113">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="857a8-114">다음 예제에서는 Visual Basic 함수를 호출 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> 하 여 응용 프로그램 창을 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="857a8-114">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="857a8-115"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> 창 제목을 유일한 인수로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="857a8-115"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="857a8-116">호출 코드에 값을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="857a8-116">It does not return a value to the calling code.</span></span> <span data-ttu-id="857a8-117">메모장 프로세스가 실행 되 고 있지 않으면이 예제는을 throw <xref:System.ArgumentException> 합니다.</span><span class="sxs-lookup"><span data-stu-id="857a8-117">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="857a8-118">`Shell` 절차에서는 애플리케이션을 지정 된 경로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="857a8-118">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="857a8-119">추가 정보</span><span class="sxs-lookup"><span data-stu-id="857a8-119">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [<span data-ttu-id="857a8-120">절차</span><span class="sxs-lookup"><span data-stu-id="857a8-120">Procedures</span></span>](./index.md)
- [<span data-ttu-id="857a8-121">하위 프로시저</span><span class="sxs-lookup"><span data-stu-id="857a8-121">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="857a8-122">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="857a8-122">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="857a8-123">Sub 문</span><span class="sxs-lookup"><span data-stu-id="857a8-123">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="857a8-124">방법: 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="857a8-124">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="857a8-125">방법: 값을 반환하는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="857a8-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="857a8-126">방법: Visual Basic에서 이벤트 처리기 호출</span><span class="sxs-lookup"><span data-stu-id="857a8-126">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
