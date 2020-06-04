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
ms.openlocfilehash: de995a13b34678410e2af74b59f2d0c467982b75
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408486"
---
# <a name="addhandler-statement"></a><span data-ttu-id="536a1-102">AddHandler 문</span><span class="sxs-lookup"><span data-stu-id="536a1-102">AddHandler Statement</span></span>
<span data-ttu-id="536a1-103">런타임에 이벤트를 이벤트 처리기와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="536a1-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="536a1-104">구문</span><span class="sxs-lookup"><span data-stu-id="536a1-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="536a1-105">부분</span><span class="sxs-lookup"><span data-stu-id="536a1-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="536a1-106">event</span><span class="sxs-lookup"><span data-stu-id="536a1-106">event</span></span>|<span data-ttu-id="536a1-107">처리할 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="536a1-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="536a1-108">이벤트를 처리 하는 프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="536a1-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="536a1-109">설명</span><span class="sxs-lookup"><span data-stu-id="536a1-109">Remarks</span></span>  
 <span data-ttu-id="536a1-110">`AddHandler`및 `RemoveHandler` 문을 사용 하면 프로그램을 실행 하는 동안 언제 든 지 이벤트 처리를 시작 하 고 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="536a1-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="536a1-111">프로시저의 서명은 `eventhandler` 이벤트의 시그니처와 일치 해야 합니다 `event` .</span><span class="sxs-lookup"><span data-stu-id="536a1-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="536a1-112">`Handles` 키워드와 `AddHandler` 문 모두 특정 프로시저에서 특정 이벤트를 처리하도록 지정하는 데 사용할 수 있지만 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="536a1-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="536a1-113">`AddHandler` 문은 런타임에 프로시저를 이벤트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="536a1-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="536a1-114">특정 이벤트를 처리하도록 지정하는 프로시저를 정의할 때 `Handles` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="536a1-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="536a1-115">자세한 내용은 [핸들](handles-clause.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="536a1-115">For more information, see [Handles](handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="536a1-116">사용자 지정 이벤트의 경우 `AddHandler` 문은 이벤트의 접근자를 호출 합니다 `AddHandler` .</span><span class="sxs-lookup"><span data-stu-id="536a1-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="536a1-117">사용자 지정 이벤트에 대 한 자세한 내용은 [이벤트 문](event-statement.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="536a1-117">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="536a1-118">예제</span><span class="sxs-lookup"><span data-stu-id="536a1-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="536a1-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="536a1-119">See also</span></span>

- [<span data-ttu-id="536a1-120">RemoveHandler 문</span><span class="sxs-lookup"><span data-stu-id="536a1-120">RemoveHandler Statement</span></span>](removehandler-statement.md)
- [<span data-ttu-id="536a1-121">핸들</span><span class="sxs-lookup"><span data-stu-id="536a1-121">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="536a1-122">Event 문</span><span class="sxs-lookup"><span data-stu-id="536a1-122">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="536a1-123">이벤트</span><span class="sxs-lookup"><span data-stu-id="536a1-123">Events</span></span>](../../programming-guide/language-features/events/index.md)
