---
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 7fd93683851c5a8c4ab253272c3f2129b3f0bb49
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275559"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="333e0-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="333e0-102">1014 - ScheduleCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="333e0-103">속성</span><span class="sxs-lookup"><span data-stu-id="333e0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="333e0-104">ID</span><span class="sxs-lookup"><span data-stu-id="333e0-104">ID</span></span>|<span data-ttu-id="333e0-105">1014</span><span class="sxs-lookup"><span data-stu-id="333e0-105">1014</span></span>|  
|<span data-ttu-id="333e0-106">키워드</span><span class="sxs-lookup"><span data-stu-id="333e0-106">Keywords</span></span>|<span data-ttu-id="333e0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="333e0-107">WFRuntime</span></span>|  
|<span data-ttu-id="333e0-108">Level</span><span class="sxs-lookup"><span data-stu-id="333e0-108">Level</span></span>|<span data-ttu-id="333e0-109">자세히</span><span class="sxs-lookup"><span data-stu-id="333e0-109">Verbose</span></span>|  
|<span data-ttu-id="333e0-110">채널</span><span class="sxs-lookup"><span data-stu-id="333e0-110">Channel</span></span>|<span data-ttu-id="333e0-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="333e0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="333e0-112">Description</span><span class="sxs-lookup"><span data-stu-id="333e0-112">Description</span></span>  

 <span data-ttu-id="333e0-113">CompletionWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="333e0-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="333e0-114">메시지</span><span class="sxs-lookup"><span data-stu-id="333e0-114">Message</span></span>  

 <span data-ttu-id="333e0-115">부모 작업 ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '에 대해 작업 항목을 예약 했습니다.</span><span class="sxs-lookup"><span data-stu-id="333e0-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="333e0-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="333e0-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="333e0-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="333e0-117">Details</span></span>  
  
|<span data-ttu-id="333e0-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="333e0-118">Data Item Name</span></span>|<span data-ttu-id="333e0-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="333e0-119">Data Item Type</span></span>|<span data-ttu-id="333e0-120">Description</span><span class="sxs-lookup"><span data-stu-id="333e0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="333e0-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="333e0-121">ParentActivity</span></span>|<span data-ttu-id="333e0-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="333e0-122">xs:string</span></span>|<span data-ttu-id="333e0-123">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="333e0-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="333e0-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="333e0-124">ParentDisplayName</span></span>|<span data-ttu-id="333e0-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="333e0-125">xs:string</span></span>|<span data-ttu-id="333e0-126">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="333e0-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="333e0-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="333e0-127">ParentInstanceId</span></span>|<span data-ttu-id="333e0-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="333e0-128">xs:string</span></span>|<span data-ttu-id="333e0-129">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="333e0-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="333e0-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="333e0-130">CompletedActivity</span></span>|<span data-ttu-id="333e0-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="333e0-131">xs:string</span></span>|<span data-ttu-id="333e0-132">완료된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="333e0-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="333e0-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="333e0-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="333e0-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="333e0-134">xs:string</span></span>|<span data-ttu-id="333e0-135">완료된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="333e0-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="333e0-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="333e0-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="333e0-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="333e0-137">xs:string</span></span>|<span data-ttu-id="333e0-138">완료된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="333e0-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="333e0-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="333e0-139">AppDomain</span></span>|<span data-ttu-id="333e0-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="333e0-140">xs:string</span></span>|<span data-ttu-id="333e0-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="333e0-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
