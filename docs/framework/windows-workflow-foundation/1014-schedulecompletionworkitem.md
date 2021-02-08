---
description: '자세한 정보: 1014-ScheduleCompletionWorkItem'
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 85bbd9b749c1dd34d026d90d708ea7f880665fbb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792936"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="94f6e-103">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="94f6e-103">1014 - ScheduleCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="94f6e-104">속성</span><span class="sxs-lookup"><span data-stu-id="94f6e-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="94f6e-105">ID</span><span class="sxs-lookup"><span data-stu-id="94f6e-105">ID</span></span>|<span data-ttu-id="94f6e-106">1014</span><span class="sxs-lookup"><span data-stu-id="94f6e-106">1014</span></span>|  
|<span data-ttu-id="94f6e-107">키워드</span><span class="sxs-lookup"><span data-stu-id="94f6e-107">Keywords</span></span>|<span data-ttu-id="94f6e-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="94f6e-108">WFRuntime</span></span>|  
|<span data-ttu-id="94f6e-109">Level</span><span class="sxs-lookup"><span data-stu-id="94f6e-109">Level</span></span>|<span data-ttu-id="94f6e-110">자세히</span><span class="sxs-lookup"><span data-stu-id="94f6e-110">Verbose</span></span>|  
|<span data-ttu-id="94f6e-111">채널</span><span class="sxs-lookup"><span data-stu-id="94f6e-111">Channel</span></span>|<span data-ttu-id="94f6e-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="94f6e-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="94f6e-113">설명</span><span class="sxs-lookup"><span data-stu-id="94f6e-113">Description</span></span>  

 <span data-ttu-id="94f6e-114">CompletionWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94f6e-114">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="94f6e-115">메시지</span><span class="sxs-lookup"><span data-stu-id="94f6e-115">Message</span></span>  

 <span data-ttu-id="94f6e-116">부모 작업 ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '에 대해 작업 항목을 예약 했습니다.</span><span class="sxs-lookup"><span data-stu-id="94f6e-116">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="94f6e-117">작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="94f6e-117">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="94f6e-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="94f6e-118">Details</span></span>  
  
|<span data-ttu-id="94f6e-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="94f6e-119">Data Item Name</span></span>|<span data-ttu-id="94f6e-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="94f6e-120">Data Item Type</span></span>|<span data-ttu-id="94f6e-121">설명</span><span class="sxs-lookup"><span data-stu-id="94f6e-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="94f6e-122">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="94f6e-122">ParentActivity</span></span>|<span data-ttu-id="94f6e-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="94f6e-123">xs:string</span></span>|<span data-ttu-id="94f6e-124">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="94f6e-124">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="94f6e-125">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="94f6e-125">ParentDisplayName</span></span>|<span data-ttu-id="94f6e-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="94f6e-126">xs:string</span></span>|<span data-ttu-id="94f6e-127">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="94f6e-127">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="94f6e-128">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="94f6e-128">ParentInstanceId</span></span>|<span data-ttu-id="94f6e-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="94f6e-129">xs:string</span></span>|<span data-ttu-id="94f6e-130">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="94f6e-130">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="94f6e-131">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="94f6e-131">CompletedActivity</span></span>|<span data-ttu-id="94f6e-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="94f6e-132">xs:string</span></span>|<span data-ttu-id="94f6e-133">완료된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="94f6e-133">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="94f6e-134">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="94f6e-134">CompletedActivityDisplayName</span></span>|<span data-ttu-id="94f6e-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="94f6e-135">xs:string</span></span>|<span data-ttu-id="94f6e-136">완료된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="94f6e-136">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="94f6e-137">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="94f6e-137">CompletedActivityInstanceId</span></span>|<span data-ttu-id="94f6e-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="94f6e-138">xs:string</span></span>|<span data-ttu-id="94f6e-139">완료된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="94f6e-139">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="94f6e-140">AppDomain</span><span class="sxs-lookup"><span data-stu-id="94f6e-140">AppDomain</span></span>|<span data-ttu-id="94f6e-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="94f6e-141">xs:string</span></span>|<span data-ttu-id="94f6e-142">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="94f6e-142">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
