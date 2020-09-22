---
title: RemoveHandler 문
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: a815241f20be12b3b7b4f2b87d50a8965021bbf0
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871939"
---
# <a name="removehandler-statement"></a><span data-ttu-id="d6a5c-102">RemoveHandler 문</span><span class="sxs-lookup"><span data-stu-id="d6a5c-102">RemoveHandler Statement</span></span>

<span data-ttu-id="d6a5c-103">이벤트와 이벤트 처리기 간의 연결을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6a5c-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6a5c-104">구문</span><span class="sxs-lookup"><span data-stu-id="d6a5c-104">Syntax</span></span>  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="d6a5c-105">부분</span><span class="sxs-lookup"><span data-stu-id="d6a5c-105">Parts</span></span>  
  
|<span data-ttu-id="d6a5c-106">용어</span><span class="sxs-lookup"><span data-stu-id="d6a5c-106">Term</span></span>|<span data-ttu-id="d6a5c-107">정의</span><span class="sxs-lookup"><span data-stu-id="d6a5c-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="d6a5c-108">처리 되는 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6a5c-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="d6a5c-109">현재 이벤트를 처리 하는 프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6a5c-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6a5c-110">설명</span><span class="sxs-lookup"><span data-stu-id="d6a5c-110">Remarks</span></span>  

 <span data-ttu-id="d6a5c-111">`AddHandler`및 `RemoveHandler` 문을 사용 하면 프로그램을 실행 하는 동안 언제 든 지 특정 이벤트에 대 한 이벤트 처리를 시작 하 고 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6a5c-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6a5c-112">사용자 지정 이벤트의 경우 `RemoveHandler` 문은 이벤트의 접근자를 호출 합니다 `RemoveHandler` .</span><span class="sxs-lookup"><span data-stu-id="d6a5c-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="d6a5c-113">사용자 지정 이벤트에 대 한 자세한 내용은 [이벤트 문](event-statement.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6a5c-113">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6a5c-114">예제</span><span class="sxs-lookup"><span data-stu-id="d6a5c-114">Example</span></span>  

 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="d6a5c-115">참조</span><span class="sxs-lookup"><span data-stu-id="d6a5c-115">See also</span></span>

- [<span data-ttu-id="d6a5c-116">AddHandler 문</span><span class="sxs-lookup"><span data-stu-id="d6a5c-116">AddHandler Statement</span></span>](addhandler-statement.md)
- [<span data-ttu-id="d6a5c-117">핸들</span><span class="sxs-lookup"><span data-stu-id="d6a5c-117">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="d6a5c-118">Event 문</span><span class="sxs-lookup"><span data-stu-id="d6a5c-118">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="d6a5c-119">이벤트</span><span class="sxs-lookup"><span data-stu-id="d6a5c-119">Events</span></span>](../../programming-guide/language-features/events/index.md)
