---
title: 스택 ETW 이벤트
description: 이벤트가 발생 한 후 스택 추적을 생성 하기 위해 다른 이벤트와 함께 사용 해야 하는 stack ETW 이벤트에 대해 읽어 보십시오.
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
ms.openlocfilehash: 3b890e587abd5cb1b7315fe41897f24638fd4604
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236210"
---
# <a name="stack-etw-event"></a><span data-ttu-id="514eb-103">스택 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="514eb-103">Stack ETW Event</span></span>

<span data-ttu-id="514eb-104">스택 이벤트는 이벤트가 발생한 후 스택 추적을 생성하기 위해 다른 이벤트와 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="514eb-104">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="514eb-105">런타임 공급자가 사용하도록 설정된 경우에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="514eb-105">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="514eb-106">다른 런타임 이벤트가 발생할 때마다 이벤트가 발생하기 때문에 빈도가 매우 높은 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="514eb-106">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="514eb-107">이러한 이유로 이 이벤트를 사용할 때는 주의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="514eb-107">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="514eb-108">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="514eb-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="514eb-109">자세한 내용은 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="514eb-109">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="514eb-110">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="514eb-110">Keyword for raising the event</span></span>|<span data-ttu-id="514eb-111">Level</span><span class="sxs-lookup"><span data-stu-id="514eb-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="514eb-112">`StackKeyword`(0x40000000)</span><span class="sxs-lookup"><span data-stu-id="514eb-112">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="514eb-113">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="514eb-113">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="514eb-114">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="514eb-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="514eb-115">이벤트</span><span class="sxs-lookup"><span data-stu-id="514eb-115">Event</span></span>|<span data-ttu-id="514eb-116">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="514eb-116">Event ID</span></span>|<span data-ttu-id="514eb-117">발생 시기</span><span class="sxs-lookup"><span data-stu-id="514eb-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="514eb-118">82</span><span class="sxs-lookup"><span data-stu-id="514eb-118">82</span></span>|<span data-ttu-id="514eb-119">다른 이벤트와 더불어 이벤트 다음에 스택 추적을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="514eb-119">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="514eb-120">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="514eb-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="514eb-121">필드 이름</span><span class="sxs-lookup"><span data-stu-id="514eb-121">Field name</span></span>|<span data-ttu-id="514eb-122">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="514eb-122">Data Type</span></span>|<span data-ttu-id="514eb-123">Description</span><span class="sxs-lookup"><span data-stu-id="514eb-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="514eb-124">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="514eb-124">ClrInstanceID</span></span>|<span data-ttu-id="514eb-125">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="514eb-125">win:Uint16</span></span>|<span data-ttu-id="514eb-126">고유한 런타임 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="514eb-126">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="514eb-127">Reserved1</span><span class="sxs-lookup"><span data-stu-id="514eb-127">Reserved1</span></span>|<span data-ttu-id="514eb-128">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="514eb-128">win:UInt8</span></span>|<span data-ttu-id="514eb-129">예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="514eb-129">Reserved.</span></span>|  
|<span data-ttu-id="514eb-130">Reserved2</span><span class="sxs-lookup"><span data-stu-id="514eb-130">Reserved2</span></span>|<span data-ttu-id="514eb-131">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="514eb-131">win:UInt8</span></span>|<span data-ttu-id="514eb-132">예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="514eb-132">Reserved.</span></span>|  
|<span data-ttu-id="514eb-133">FrameCount</span><span class="sxs-lookup"><span data-stu-id="514eb-133">FrameCount</span></span>|<span data-ttu-id="514eb-134">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="514eb-134">win:UInt32</span></span>|<span data-ttu-id="514eb-135">스택 추적의 프레임 수입니다.</span><span class="sxs-lookup"><span data-stu-id="514eb-135">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="514eb-136">스택</span><span class="sxs-lookup"><span data-stu-id="514eb-136">Stack</span></span>|<span data-ttu-id="514eb-137">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="514eb-137">win:Pointer</span></span>|<span data-ttu-id="514eb-138">명령 포인터의 열입니다.</span><span class="sxs-lookup"><span data-stu-id="514eb-138">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="514eb-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="514eb-139">See also</span></span>

- [<span data-ttu-id="514eb-140">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="514eb-140">CLR ETW Events</span></span>](clr-etw-events.md)
