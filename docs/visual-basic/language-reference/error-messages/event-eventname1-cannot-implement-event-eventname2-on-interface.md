---
description: "' ' <eventname1> <eventname2> <interface> <delegate1> 및 ' ' 대리자 형식이 <delegate2> 일치 하지 않기 때문에 BC31423: event ' '에서 ' ' 인터페이스에 대해 ' ' 이벤트를 구현할 수 없습니다."
title: 대리자 형식 '<eventname1>'과(와) '<eventname2>'이(가) 일치하지 않으므로 '<interface>' 이벤트에서 '<delegate1>' 인터페이스에 대해 '<delegate2>' 이벤트를 구현할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: cfb967d2b43ce1f34f56f3d019a9a663b000296c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796459"
---
# <a name="bc31423-event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a><span data-ttu-id="46e4e-103">BC31423: ' ' \<eventname1> \<eventname2> 인터페이스의 \<interface> 대리자 형식 ' \<delegate1> ' 및 ' '이 (가) \<delegate2> 일치 하지 않으므로 ' ' 이벤트에서 ' ' 이벤트를 구현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46e4e-103">BC31423: Event '\<eventname1>' cannot implement event '\<eventname2>' on interface '\<interface>' because their delegate types '\<delegate1>' and '\<delegate2>' do not match</span></span>

<span data-ttu-id="46e4e-104">이벤트의 대리자 형식이 인터페이스에 있는 이벤트의 대리자 형식과 일치 하지 않으므로 Visual Basic에서 이벤트를 구현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46e4e-104">Visual Basic cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="46e4e-105">이 오류는 인터페이스에서 여러 이벤트를 정의한 다음 동일한 이벤트로 함께 구현하려고 하는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e4e-105">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="46e4e-106">구현된 모든 이벤트가 `As` 구문을 사용하여 선언되고 동일한 대리자 형식을 지정하는 경우에만 이벤트에서 둘 이상의 이벤트를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e4e-106">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>

 <span data-ttu-id="46e4e-107">**오류 ID:** BC31423</span><span class="sxs-lookup"><span data-stu-id="46e4e-107">**Error ID:** BC31423</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="46e4e-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="46e4e-108">To correct this error</span></span>

- <span data-ttu-id="46e4e-109">이벤트를 개별적으로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="46e4e-109">Implement the events separately.</span></span>

     <span data-ttu-id="46e4e-110">또는</span><span class="sxs-lookup"><span data-stu-id="46e4e-110">—or—</span></span>

- <span data-ttu-id="46e4e-111">구문을 사용 하 여 인터페이스에서 이벤트를 정의 `As` 하 고 동일한 대리자 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e4e-111">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>

## <a name="see-also"></a><span data-ttu-id="46e4e-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46e4e-112">See also</span></span>

- [<span data-ttu-id="46e4e-113">Event 문</span><span class="sxs-lookup"><span data-stu-id="46e4e-113">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="46e4e-114">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="46e4e-114">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="46e4e-115">이벤트</span><span class="sxs-lookup"><span data-stu-id="46e4e-115">Events</span></span>](../../programming-guide/language-features/events/index.md)
