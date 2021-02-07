---
description: '다음에 대 한 자세한 정보: RemoveHandler 문'
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
ms.openlocfilehash: 699db9edfc029b4149246e8b654645040ae6d89e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741304"
---
# <a name="removehandler-statement"></a><span data-ttu-id="b4630-103">RemoveHandler 문</span><span class="sxs-lookup"><span data-stu-id="b4630-103">RemoveHandler Statement</span></span>

<span data-ttu-id="b4630-104">이벤트와 이벤트 처리기 간의 연결을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4630-104">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4630-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4630-105">Syntax</span></span>  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="b4630-106">부분</span><span class="sxs-lookup"><span data-stu-id="b4630-106">Parts</span></span>  
  
|<span data-ttu-id="b4630-107">용어</span><span class="sxs-lookup"><span data-stu-id="b4630-107">Term</span></span>|<span data-ttu-id="b4630-108">정의</span><span class="sxs-lookup"><span data-stu-id="b4630-108">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="b4630-109">처리 되는 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b4630-109">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="b4630-110">현재 이벤트를 처리 하는 프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b4630-110">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4630-111">설명</span><span class="sxs-lookup"><span data-stu-id="b4630-111">Remarks</span></span>  

 <span data-ttu-id="b4630-112">`AddHandler`및 `RemoveHandler` 문을 사용 하면 프로그램을 실행 하는 동안 언제 든 지 특정 이벤트에 대 한 이벤트 처리를 시작 하 고 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4630-112">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b4630-113">사용자 지정 이벤트의 경우 `RemoveHandler` 문은 이벤트의 접근자를 호출 합니다 `RemoveHandler` .</span><span class="sxs-lookup"><span data-stu-id="b4630-113">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="b4630-114">사용자 지정 이벤트에 대 한 자세한 내용은 [이벤트 문](event-statement.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4630-114">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4630-115">예제</span><span class="sxs-lookup"><span data-stu-id="b4630-115">Example</span></span>  

 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="b4630-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4630-116">See also</span></span>

- [<span data-ttu-id="b4630-117">AddHandler 문</span><span class="sxs-lookup"><span data-stu-id="b4630-117">AddHandler Statement</span></span>](addhandler-statement.md)
- [<span data-ttu-id="b4630-118">핸들</span><span class="sxs-lookup"><span data-stu-id="b4630-118">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="b4630-119">Event 문</span><span class="sxs-lookup"><span data-stu-id="b4630-119">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="b4630-120">이벤트</span><span class="sxs-lookup"><span data-stu-id="b4630-120">Events</span></span>](../../programming-guide/language-features/events/index.md)
