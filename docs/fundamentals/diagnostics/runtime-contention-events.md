---
title: 잠금 경합 런타임 이벤트 모니터링
description: 모니터 잠금 경합에 대 한 정보를 수집 하는 ETW 이벤트를 참조 하세요.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- monitor lock contention events (CoreCLR)
- ETW, EventPipe, LTTng contention events (CoreCLR)
ms.openlocfilehash: 38e5f493d4b223b4839dbd6f814cf656722189b2
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594052"
---
# <a name="net-runtime-contention-events"></a><span data-ttu-id="a61c0-103">.NET 런타임 경합 이벤트</span><span class="sxs-lookup"><span data-stu-id="a61c0-103">.NET runtime contention events</span></span>

<span data-ttu-id="a61c0-104">이러한 런타임 이벤트는 `Monitor.Enter` 또는 c # lock 키워드와 같은 모니터 잠금 경합에 대 한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-104">These runtime events capture information about monitor lock contentions such as with `Monitor.Enter` or the C# lock keyword.</span></span> <span data-ttu-id="a61c0-105">진단 목적으로 이러한 이벤트를 사용 하는 방법에 대 한 자세한 내용은 [.net 응용 프로그램 로깅 및 추적](../../core/diagnostics/logging-tracing.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a61c0-105">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="contentionstart_v1-event"></a><span data-ttu-id="a61c0-106">ContentionStart_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="a61c0-106">ContentionStart_V1 event</span></span>

<span data-ttu-id="a61c0-107">이 이벤트는 모니터 잠금 경합이 시작 될 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-107">This event is emitted at the start of a monitor lock contention.</span></span>

|<span data-ttu-id="a61c0-108">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a61c0-108">Keyword for raising the event</span></span>|<span data-ttu-id="a61c0-109">수준</span><span class="sxs-lookup"><span data-stu-id="a61c0-109">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a61c0-110">`ContentionKeyword`(0x4000)</span><span class="sxs-lookup"><span data-stu-id="a61c0-110">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="a61c0-111">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a61c0-111">Informational (4)</span></span>|

 <span data-ttu-id="a61c0-112">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-112">The following table shows event information.</span></span>

|<span data-ttu-id="a61c0-113">이벤트</span><span class="sxs-lookup"><span data-stu-id="a61c0-113">Event</span></span>|<span data-ttu-id="a61c0-114">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a61c0-114">Event ID</span></span>|<span data-ttu-id="a61c0-115">발생 시기</span><span class="sxs-lookup"><span data-stu-id="a61c0-115">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|<span data-ttu-id="a61c0-116">81</span><span class="sxs-lookup"><span data-stu-id="a61c0-116">81</span></span>|<span data-ttu-id="a61c0-117">모니터 잠금 경합이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-117">A monitor lock contention starts.</span></span>|

|<span data-ttu-id="a61c0-118">필드 이름</span><span class="sxs-lookup"><span data-stu-id="a61c0-118">Field name</span></span>|<span data-ttu-id="a61c0-119">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a61c0-119">Data type</span></span>|<span data-ttu-id="a61c0-120">Description</span><span class="sxs-lookup"><span data-stu-id="a61c0-120">Description</span></span>|
|----------------|---------------|-----------------|
|`Flags`|`win:UInt8`|<span data-ttu-id="a61c0-121">`0` 관리 되는 경우 `1` 네이티브의 경우</span><span class="sxs-lookup"><span data-stu-id="a61c0-121">`0` for managed; `1` for native.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="a61c0-122">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-122">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="contentionstop_v1-event"></a><span data-ttu-id="a61c0-123">ContentionStop_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="a61c0-123">ContentionStop_V1 event</span></span>

<span data-ttu-id="a61c0-124">이 이벤트는 모니터 잠금 경합이 끝날 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-124">This event is emitted at the end of a monitor lock contention.</span></span>

|<span data-ttu-id="a61c0-125">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a61c0-125">Keyword for raising the event</span></span>|<span data-ttu-id="a61c0-126">수준</span><span class="sxs-lookup"><span data-stu-id="a61c0-126">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a61c0-127">`ContentionKeyword`(0x4000)</span><span class="sxs-lookup"><span data-stu-id="a61c0-127">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="a61c0-128">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a61c0-128">Informational (4)</span></span>|

 <span data-ttu-id="a61c0-129">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-129">The following table shows event information.</span></span>

|<span data-ttu-id="a61c0-130">이벤트</span><span class="sxs-lookup"><span data-stu-id="a61c0-130">Event</span></span>|<span data-ttu-id="a61c0-131">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a61c0-131">Event ID</span></span>|<span data-ttu-id="a61c0-132">발생 시기</span><span class="sxs-lookup"><span data-stu-id="a61c0-132">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ContentionStop_V1`|<span data-ttu-id="a61c0-133">91</span><span class="sxs-lookup"><span data-stu-id="a61c0-133">91</span></span>|<span data-ttu-id="a61c0-134">모니터 잠금 경합이 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-134">A monitor lock contention ends.</span></span>|

|<span data-ttu-id="a61c0-135">필드 이름</span><span class="sxs-lookup"><span data-stu-id="a61c0-135">Field name</span></span>|<span data-ttu-id="a61c0-136">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a61c0-136">Data type</span></span>|<span data-ttu-id="a61c0-137">Description</span><span class="sxs-lookup"><span data-stu-id="a61c0-137">Description</span></span>|
|----------------|---------------|-----------------|
|`Flags`|`win:UInt8`|<span data-ttu-id="a61c0-138">`0` 관리 되는 경우 `1` 네이티브의 경우</span><span class="sxs-lookup"><span data-stu-id="a61c0-138">`0` for managed; `1` for native.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="a61c0-139">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-139">Unique ID for the instance of CoreCLR.</span></span>|
|`DurationNs`|`win:Double`|<span data-ttu-id="a61c0-140">경합의 시간 (나노초)입니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-140">Duration of the contention in nanoseconds.</span></span>|
