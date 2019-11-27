---
title: AddHandler 문
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: c110116af75d4fb39c016b8d6afcdb707fa6599b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350184"
---
# <a name="addhandler-statement"></a><span data-ttu-id="c2e88-102">AddHandler 문</span><span class="sxs-lookup"><span data-stu-id="c2e88-102">AddHandler Statement</span></span>
<span data-ttu-id="c2e88-103">런타임에 이벤트를 이벤트 처리기와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e88-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2e88-104">구문</span><span class="sxs-lookup"><span data-stu-id="c2e88-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="c2e88-105">요소</span><span class="sxs-lookup"><span data-stu-id="c2e88-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="c2e88-106">이벤트</span><span class="sxs-lookup"><span data-stu-id="c2e88-106">event</span></span>|<span data-ttu-id="c2e88-107">처리할 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2e88-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="c2e88-108">이벤트를 처리 하는 프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2e88-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="c2e88-109">설명</span><span class="sxs-lookup"><span data-stu-id="c2e88-109">Remarks</span></span>  
 <span data-ttu-id="c2e88-110">`AddHandler` 및 `RemoveHandler` 문을 사용 하면 프로그램을 실행 하는 동안 언제 든 지 이벤트 처리를 시작 하 고 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2e88-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="c2e88-111">`eventhandler` 프로시저의 서명은 이벤트 `event`의 시그니처와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e88-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="c2e88-112">`Handles` 키워드와 `AddHandler` 문 모두 특정 프로시저에서 특정 이벤트를 처리하도록 지정하는 데 사용할 수 있지만 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2e88-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="c2e88-113">`AddHandler` 문은 런타임에 프로시저를 이벤트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e88-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="c2e88-114">특정 이벤트를 처리하도록 지정하는 프로시저를 정의할 때 `Handles` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e88-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="c2e88-115">자세한 내용은 [핸들](../../../visual-basic/language-reference/statements/handles-clause.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2e88-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2e88-116">사용자 지정 이벤트의 경우 `AddHandler` 문은 이벤트의 `AddHandler` 접근자를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e88-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="c2e88-117">사용자 지정 이벤트에 대 한 자세한 내용은 [이벤트 문](../../../visual-basic/language-reference/statements/event-statement.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c2e88-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2e88-118">예제</span><span class="sxs-lookup"><span data-stu-id="c2e88-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="c2e88-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="c2e88-119">See also</span></span>

- [<span data-ttu-id="c2e88-120">RemoveHandler 문</span><span class="sxs-lookup"><span data-stu-id="c2e88-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- <span data-ttu-id="c2e88-121">[!](../../../visual-basic/language-reference/statements/handles-clause.md)</span><span class="sxs-lookup"><span data-stu-id="c2e88-121">[Handles](../../../visual-basic/language-reference/statements/handles-clause.md)</span></span>
- [<span data-ttu-id="c2e88-122">Event 문</span><span class="sxs-lookup"><span data-stu-id="c2e88-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="c2e88-123">이벤트</span><span class="sxs-lookup"><span data-stu-id="c2e88-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
