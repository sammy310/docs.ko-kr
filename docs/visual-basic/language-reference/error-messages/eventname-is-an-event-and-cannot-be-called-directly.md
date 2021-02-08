---
description: "자세한 정보: BC32022: ' <eventname> '은 (는) 이벤트 이므로 직접 호출할 수 없습니다."
title: "'<eventname>'은(는) 이벤트이므로 직접 호출할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: f9d4b8fe54e1101e7963933f871cf5af2c1af903
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796446"
---
# <a name="bc32022-eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="08f1e-103">BC32022: ' \<eventname> '은 (는) 이벤트 이므로 직접 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08f1e-103">BC32022: '\<eventname>' is an event, and cannot be called directly</span></span>

<span data-ttu-id="08f1e-104">' <`eventname`> '은 (는) 이벤트 이므로 직접 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08f1e-104">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="08f1e-105">문을 사용 `RaiseEvent` 하 여 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="08f1e-105">Use a `RaiseEvent` statement to raise an event.</span></span>

 <span data-ttu-id="08f1e-106">프로시저 호출은 프로시저 이름에 대 한 이벤트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f1e-106">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="08f1e-107">이벤트 처리기는 프로시저 이지만 이벤트 자체는 발생 하 고 처리 해야 하는 신호 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="08f1e-107">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>

 <span data-ttu-id="08f1e-108">**오류 ID:** BC32022</span><span class="sxs-lookup"><span data-stu-id="08f1e-108">**Error ID:** BC32022</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="08f1e-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="08f1e-109">To correct this error</span></span>

- <span data-ttu-id="08f1e-110">문을 사용 `RaiseEvent` 하 여 이벤트를 알리고 이벤트를 처리 하는 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f1e-110">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>

## <a name="see-also"></a><span data-ttu-id="08f1e-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08f1e-111">See also</span></span>

- [<span data-ttu-id="08f1e-112">RaiseEvent 문</span><span class="sxs-lookup"><span data-stu-id="08f1e-112">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
