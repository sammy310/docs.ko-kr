---
title: 명시적 대리자 형식 없이 선언된 이벤트에는 'Custom' 한정자를 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 0c5a4188fedf9685afdd1cde4c1de93a0b43b919
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409787"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="c9db7-102">명시적 대리자 형식 없이 선언된 이벤트에는 'Custom' 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9db7-102">'Custom' modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="c9db7-103">사용자 지정 이벤트가 아닌 이벤트와 달리 선언에는 이벤트 `Custom Event` `As` 의 대리자 형식을 명시적으로 지정 하는 이벤트 이름 다음에 절이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9db7-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="c9db7-104">사용자 지정이 아닌 이벤트는 `As` 절과 명시적 대리자 형식을 사용 하 여 정의 하거나 이벤트 이름 바로 뒤에 매개 변수 목록을 사용 하 여 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9db7-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="c9db7-105">**오류 ID:** BC31122</span><span class="sxs-lookup"><span data-stu-id="c9db7-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c9db7-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c9db7-106">To correct this error</span></span>  
  
1. <span data-ttu-id="c9db7-107">사용자 지정 이벤트와 동일한 매개 변수 목록을 사용 하 여 대리자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9db7-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="c9db7-108">예를 들어 `Custom Event` 가로 정의 된 경우 `Custom Event Test(ByVal sender As Object, ByVal i As Integer)` 해당 대리자는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9db7-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]  
  
2. <span data-ttu-id="c9db7-109">사용자 지정 이벤트의 매개 변수 목록을 `As` 대리자 형식을 지정 하는 절로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c9db7-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="c9db7-110">예제를 계속 하면 `Custom Event` 선언이 다음과 같이 다시 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9db7-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="c9db7-111">예제</span><span class="sxs-lookup"><span data-stu-id="c9db7-111">Example</span></span>  
 <span data-ttu-id="c9db7-112">이 예제에서는을 선언 `Custom Event` 하 고 `As` 대리자 형식을 사용 하 여 필수 절을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9db7-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c9db7-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9db7-113">See also</span></span>

- [<span data-ttu-id="c9db7-114">Event 문</span><span class="sxs-lookup"><span data-stu-id="c9db7-114">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="c9db7-115">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="c9db7-115">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="c9db7-116">이벤트</span><span class="sxs-lookup"><span data-stu-id="c9db7-116">Events</span></span>](../../programming-guide/language-features/events/index.md)
