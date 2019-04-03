---
title: 명시적 대리자 형식 없이 선언된 이벤트에는 'Custom' 한정자를 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 0fc645671eb899faff0dbb5c6d745ba23faf4557
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827226"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="e8c51-102">명시적 대리자 형식 없이 선언된 이벤트에는 'Custom' 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8c51-102">'Custom' modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="e8c51-103">사용자 지정이 아닌 경우와 달리를 `Custom Event` 선언에 필요는 `As` 절과 이벤트에 대 한 대리자 형식을 명시적으로 지정 하는 이벤트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e8c51-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="e8c51-104">비-사용자 지정 이벤트 수 사용 하 여 정의 `As` 절 및 명시적 대리자 형식 또는 매개 변수를 사용 하 여 목록 바로 이벤트 이름 다음에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8c51-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="e8c51-105">**오류 ID:** BC31122</span><span class="sxs-lookup"><span data-stu-id="e8c51-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e8c51-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="e8c51-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="e8c51-107">사용자 지정 이벤트와 동일한 매개 변수 목록 사용 하 여 대리자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c51-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="e8c51-108">예를 들어 경우는 `Custom Event` 정의한 `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, 해당 대리자는 다음 것을 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c51-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]  
  
2.  <span data-ttu-id="e8c51-109">대체 매개 변수 목록을 사용 하 여 사용자 지정 이벤트는 `As` 절 대리자 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c51-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="e8c51-110">예를 사용 하 여 계속 `Custom Event` 선언을 다음과 같이 다시 작성할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8c51-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="e8c51-111">예제</span><span class="sxs-lookup"><span data-stu-id="e8c51-111">Example</span></span>  
 <span data-ttu-id="e8c51-112">이 예제에서는 선언 된 `Custom Event` 필요한 지정 `As` 대리자 형식으로는 절.</span><span class="sxs-lookup"><span data-stu-id="e8c51-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e8c51-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="e8c51-113">See also</span></span>

- [<span data-ttu-id="e8c51-114">Event 문</span><span class="sxs-lookup"><span data-stu-id="e8c51-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="e8c51-115">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="e8c51-115">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="e8c51-116">이벤트</span><span class="sxs-lookup"><span data-stu-id="e8c51-116">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
