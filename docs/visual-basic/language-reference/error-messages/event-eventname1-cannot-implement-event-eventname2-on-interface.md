---
title: 대리자 형식 '<eventname1>'과(와) '<eventname2>'이(가) 일치하지 않으므로 '<interface>' 이벤트에서 '<delegate1>' 인터페이스에 대해 '<delegate2>' 이벤트를 구현할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: d0b2b095ed355b420b28e87ed0b9d6a31f049ebf
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162026"
---
# <a name="bc31423-event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a><span data-ttu-id="f7399-102">BC31423: ' ' \<eventname1> \<eventname2> 인터페이스의 \<interface> 대리자 형식 ' \<delegate1> ' 및 ' '이 (가) \<delegate2> 일치 하지 않으므로 ' ' 이벤트에서 ' ' 이벤트를 구현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7399-102">BC31423: Event '\<eventname1>' cannot implement event '\<eventname2>' on interface '\<interface>' because their delegate types '\<delegate1>' and '\<delegate2>' do not match</span></span>

<span data-ttu-id="f7399-103">이벤트의 대리자 형식이 인터페이스에 있는 이벤트의 대리자 형식과 일치 하지 않으므로 Visual Basic에서 이벤트를 구현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7399-103">Visual Basic cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="f7399-104">이 오류는 인터페이스에서 여러 이벤트를 정의한 다음 동일한 이벤트로 함께 구현하려고 하는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7399-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="f7399-105">구현된 모든 이벤트가 `As` 구문을 사용하여 선언되고 동일한 대리자 형식을 지정하는 경우에만 이벤트에서 둘 이상의 이벤트를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7399-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>

 <span data-ttu-id="f7399-106">**오류 ID:** BC31423</span><span class="sxs-lookup"><span data-stu-id="f7399-106">**Error ID:** BC31423</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="f7399-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f7399-107">To correct this error</span></span>

- <span data-ttu-id="f7399-108">이벤트를 개별적으로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f7399-108">Implement the events separately.</span></span>

     <span data-ttu-id="f7399-109">또는</span><span class="sxs-lookup"><span data-stu-id="f7399-109">—or—</span></span>

- <span data-ttu-id="f7399-110">구문을 사용 하 여 인터페이스에서 이벤트를 정의 `As` 하 고 동일한 대리자 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7399-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7399-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7399-111">See also</span></span>

- [<span data-ttu-id="f7399-112">Event 문</span><span class="sxs-lookup"><span data-stu-id="f7399-112">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="f7399-113">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="f7399-113">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="f7399-114">이벤트</span><span class="sxs-lookup"><span data-stu-id="f7399-114">Events</span></span>](../../programming-guide/language-features/events/index.md)
