---
title: RemoveHandler 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 3a839a7d05d05066f6c0f774a683c8fc83c19643
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957721"
---
# <a name="removehandler-statement"></a><span data-ttu-id="bae45-102">RemoveHandler 문</span><span class="sxs-lookup"><span data-stu-id="bae45-102">RemoveHandler Statement</span></span>
<span data-ttu-id="bae45-103">이벤트와 이벤트 처리기 간의 연결을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae45-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bae45-104">구문</span><span class="sxs-lookup"><span data-stu-id="bae45-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="bae45-105">요소</span><span class="sxs-lookup"><span data-stu-id="bae45-105">Parts</span></span>  
  
|<span data-ttu-id="bae45-106">용어</span><span class="sxs-lookup"><span data-stu-id="bae45-106">Term</span></span>|<span data-ttu-id="bae45-107">정의</span><span class="sxs-lookup"><span data-stu-id="bae45-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="bae45-108">처리 되는 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bae45-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="bae45-109">현재 이벤트를 처리 하는 프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bae45-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bae45-110">설명</span><span class="sxs-lookup"><span data-stu-id="bae45-110">Remarks</span></span>  
 <span data-ttu-id="bae45-111">`AddHandler` 및`RemoveHandler` 문을 사용 하면 프로그램을 실행 하는 동안 언제 든 지 특정 이벤트에 대 한 이벤트 처리를 시작 하 고 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae45-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bae45-112">사용자 지정 이벤트 `RemoveHandler` 의 경우 문은 이벤트의 `RemoveHandler` 접근자를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae45-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="bae45-113">사용자 지정 이벤트에 대 한 자세한 내용은 [이벤트 문](../../../visual-basic/language-reference/statements/event-statement.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bae45-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bae45-114">예제</span><span class="sxs-lookup"><span data-stu-id="bae45-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="bae45-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="bae45-115">See also</span></span>

- [<span data-ttu-id="bae45-116">AddHandler 문</span><span class="sxs-lookup"><span data-stu-id="bae45-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="bae45-117">Handles</span><span class="sxs-lookup"><span data-stu-id="bae45-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="bae45-118">Event 문</span><span class="sxs-lookup"><span data-stu-id="bae45-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="bae45-119">이벤트</span><span class="sxs-lookup"><span data-stu-id="bae45-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
