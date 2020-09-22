---
title: "'<eventname>'은(는) 이벤트이므로 직접 호출할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 3366bc215a45cd7de9dc2de285758a78144df509
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874311"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="c1580-102">'\<eventname>'은(는) 이벤트이므로 직접 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1580-102">'\<eventname>' is an event, and cannot be called directly</span></span>

<span data-ttu-id="c1580-103">' <`eventname`> '은 (는) 이벤트 이므로 직접 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1580-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="c1580-104">문을 사용 `RaiseEvent` 하 여 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c1580-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="c1580-105">프로시저 호출은 프로시저 이름에 대 한 이벤트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1580-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="c1580-106">이벤트 처리기는 프로시저 이지만 이벤트 자체는 발생 하 고 처리 해야 하는 신호 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="c1580-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="c1580-107">**오류 ID:** BC32022</span><span class="sxs-lookup"><span data-stu-id="c1580-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c1580-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c1580-108">To correct this error</span></span>  
  
1. <span data-ttu-id="c1580-109">문을 사용 `RaiseEvent` 하 여 이벤트를 알리고 이벤트를 처리 하는 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1580-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1580-110">참조</span><span class="sxs-lookup"><span data-stu-id="c1580-110">See also</span></span>

- [<span data-ttu-id="c1580-111">RaiseEvent 문</span><span class="sxs-lookup"><span data-stu-id="c1580-111">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
