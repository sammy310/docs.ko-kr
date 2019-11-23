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
# <a name="addhandler-statement"></a><span data-ttu-id="a0183-102">AddHandler 문</span><span class="sxs-lookup"><span data-stu-id="a0183-102">AddHandler Statement</span></span>
<span data-ttu-id="a0183-103">Associates an event with an event handler at run time.</span><span class="sxs-lookup"><span data-stu-id="a0183-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0183-104">구문</span><span class="sxs-lookup"><span data-stu-id="a0183-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="a0183-105">요소</span><span class="sxs-lookup"><span data-stu-id="a0183-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="a0183-106">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="a0183-106">event</span></span>|<span data-ttu-id="a0183-107">The name of the event to handle.</span><span class="sxs-lookup"><span data-stu-id="a0183-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="a0183-108">The name of a procedure that handles the event.</span><span class="sxs-lookup"><span data-stu-id="a0183-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="a0183-109">주의</span><span class="sxs-lookup"><span data-stu-id="a0183-109">Remarks</span></span>  
 <span data-ttu-id="a0183-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span><span class="sxs-lookup"><span data-stu-id="a0183-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="a0183-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span><span class="sxs-lookup"><span data-stu-id="a0183-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="a0183-112">`Handles` 키워드와 `AddHandler` 문 모두 특정 프로시저에서 특정 이벤트를 처리하도록 지정하는 데 사용할 수 있지만 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0183-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="a0183-113">`AddHandler` 문은 런타임에 프로시저를 이벤트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a0183-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="a0183-114">특정 이벤트를 처리하도록 지정하는 프로시저를 정의할 때 `Handles` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0183-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="a0183-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a0183-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0183-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span><span class="sxs-lookup"><span data-stu-id="a0183-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="a0183-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a0183-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0183-118">예제</span><span class="sxs-lookup"><span data-stu-id="a0183-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="a0183-119">참조</span><span class="sxs-lookup"><span data-stu-id="a0183-119">See also</span></span>

- [<span data-ttu-id="a0183-120">RemoveHandler 문</span><span class="sxs-lookup"><span data-stu-id="a0183-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="a0183-121">Handles</span><span class="sxs-lookup"><span data-stu-id="a0183-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="a0183-122">Event 문</span><span class="sxs-lookup"><span data-stu-id="a0183-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="a0183-123">이벤트</span><span class="sxs-lookup"><span data-stu-id="a0183-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
