---
title: 경합 ETW 이벤트-.NET
description: 경합 ETW 이벤트에 대 한 세부 정보를 가져옵니다 .이 이벤트는 런타임에 사용 되는 시스템. 모니터 잠금 또는 네이티브 잠금에 대 한 경합이 있을 때마다 발생 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
ms.openlocfilehash: a36b091e0896562fffdb66e895d70049ce0667d7
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309601"
---
# <a name="contention-etw-events"></a><span data-ttu-id="bc827-103">경합 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="bc827-103">Contention ETW events</span></span>

<span data-ttu-id="bc827-104">런타임에서 사용되는 <xref:System.Threading.Monitor?displayProperty=nameWithType> 잠금 또는 네이티브 잠금에 대한 경합이 있을 때마다 경합 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bc827-104">Contention events are raised whenever there is contention for <xref:System.Threading.Monitor?displayProperty=nameWithType> locks or native locks used by the runtime.</span></span> <span data-ttu-id="bc827-105">스레드가 잠금을 소유하는 동안 또 다른 스레드가 잠금을 기다리고 있으면 경합이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bc827-105">Contention occurs when a thread is waiting for a lock while another thread possesses the lock.</span></span>

<span data-ttu-id="bc827-106">다음 표에서는 경합 이벤트가 발생하는 키워드 및 이벤트 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc827-106">The following table shows the keyword under which contention events are raised, and the level of the events.</span></span> <span data-ttu-id="bc827-107">자세한 내용은 [CLR ETW 키워드 및 수준](clr-etw-keywords-and-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc827-107">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="bc827-108">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="bc827-108">Keyword for raising the event</span></span>|<span data-ttu-id="bc827-109">수준</span><span class="sxs-lookup"><span data-stu-id="bc827-109">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="bc827-110">`ContentionKeyword`(0x4000)</span><span class="sxs-lookup"><span data-stu-id="bc827-110">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="bc827-111">정보(4)</span><span class="sxs-lookup"><span data-stu-id="bc827-111">Informational (4)</span></span>|

<span data-ttu-id="bc827-112">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc827-112">The following table shows event information:</span></span>

|<span data-ttu-id="bc827-113">Event</span><span class="sxs-lookup"><span data-stu-id="bc827-113">Event</span></span>|<span data-ttu-id="bc827-114">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="bc827-114">Event ID</span></span>|<span data-ttu-id="bc827-115">발생 시기</span><span class="sxs-lookup"><span data-stu-id="bc827-115">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|<span data-ttu-id="bc827-116">81</span><span class="sxs-lookup"><span data-stu-id="bc827-116">81</span></span>|<span data-ttu-id="bc827-117">경합이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc827-117">Contention starts.</span></span> <span data-ttu-id="bc827-118">이 이벤트에는 스레드가 잠금을 획득하기 위해 대기하기 전의 회전 시간이 포함되지 않습니다. 이 이벤트는 스레드가 잠금을 획득하기 위해 대기하는 경우에만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bc827-118">This event does not include the amount of spinning time before a thread waits to acquire a lock; it is raised only when the thread waits to acquire a lock.</span></span>|
|`ContentionStop`|<span data-ttu-id="bc827-119">91</span><span class="sxs-lookup"><span data-stu-id="bc827-119">91</span></span>|<span data-ttu-id="bc827-120">경합이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc827-120">Contention ends.</span></span>|

<span data-ttu-id="bc827-121">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc827-121">The following table shows event data:</span></span>

|<span data-ttu-id="bc827-122">필드 이름</span><span class="sxs-lookup"><span data-stu-id="bc827-122">Field name</span></span>|<span data-ttu-id="bc827-123">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bc827-123">Data type</span></span>|<span data-ttu-id="bc827-124">Description</span><span class="sxs-lookup"><span data-stu-id="bc827-124">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="bc827-125">플래그</span><span class="sxs-lookup"><span data-stu-id="bc827-125">Flags</span></span>|<span data-ttu-id="bc827-126">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="bc827-126">win:UInt8</span></span>|<span data-ttu-id="bc827-127">0(관리), 1(네이티브).</span><span class="sxs-lookup"><span data-stu-id="bc827-127">0 for managed; 1 for native.</span></span>|
|<span data-ttu-id="bc827-128">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="bc827-128">ClrInstanceID</span></span>|<span data-ttu-id="bc827-129">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="bc827-129">win:UInt16</span></span>|<span data-ttu-id="bc827-130">CLR 인스턴스의 고유 ID.</span><span class="sxs-lookup"><span data-stu-id="bc827-130">Unique ID for the instance of CLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="bc827-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc827-131">See also</span></span>

- [<span data-ttu-id="bc827-132">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="bc827-132">CLR ETW Events</span></span>](clr-etw-events.md)
