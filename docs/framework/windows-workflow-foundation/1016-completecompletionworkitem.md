---
description: '자세한 정보: 1016-CompleteCompletionWorkItem'
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: 849e192d63b5db19e5beea31befcdc38d4340c6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792910"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="20ea8-103">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="20ea8-103">1016 - CompleteCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="20ea8-104">속성</span><span class="sxs-lookup"><span data-stu-id="20ea8-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="20ea8-105">ID</span><span class="sxs-lookup"><span data-stu-id="20ea8-105">ID</span></span>|<span data-ttu-id="20ea8-106">1016</span><span class="sxs-lookup"><span data-stu-id="20ea8-106">1016</span></span>|  
|<span data-ttu-id="20ea8-107">키워드</span><span class="sxs-lookup"><span data-stu-id="20ea8-107">Keywords</span></span>|<span data-ttu-id="20ea8-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="20ea8-108">WFRuntime</span></span>|  
|<span data-ttu-id="20ea8-109">Level</span><span class="sxs-lookup"><span data-stu-id="20ea8-109">Level</span></span>|<span data-ttu-id="20ea8-110">자세히</span><span class="sxs-lookup"><span data-stu-id="20ea8-110">Verbose</span></span>|  
|<span data-ttu-id="20ea8-111">채널</span><span class="sxs-lookup"><span data-stu-id="20ea8-111">Channel</span></span>|<span data-ttu-id="20ea8-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="20ea8-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="20ea8-113">설명</span><span class="sxs-lookup"><span data-stu-id="20ea8-113">Description</span></span>  

 <span data-ttu-id="20ea8-114">CompletionWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="20ea8-114">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="20ea8-115">메시지</span><span class="sxs-lookup"><span data-stu-id="20ea8-115">Message</span></span>  

 <span data-ttu-id="20ea8-116">부모 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CompletionWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="20ea8-116">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="20ea8-117">작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="20ea8-117">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="20ea8-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="20ea8-118">Details</span></span>  
  
|<span data-ttu-id="20ea8-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="20ea8-119">Data Item Name</span></span>|<span data-ttu-id="20ea8-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="20ea8-120">Data Item Type</span></span>|<span data-ttu-id="20ea8-121">설명</span><span class="sxs-lookup"><span data-stu-id="20ea8-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="20ea8-122">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="20ea8-122">ParentActivity</span></span>|<span data-ttu-id="20ea8-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="20ea8-123">xs:string</span></span>|<span data-ttu-id="20ea8-124">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="20ea8-124">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="20ea8-125">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="20ea8-125">ParentDisplayName</span></span>|<span data-ttu-id="20ea8-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="20ea8-126">xs:string</span></span>|<span data-ttu-id="20ea8-127">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="20ea8-127">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="20ea8-128">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="20ea8-128">ParentInstanceId</span></span>|<span data-ttu-id="20ea8-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="20ea8-129">xs:string</span></span>|<span data-ttu-id="20ea8-130">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="20ea8-130">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="20ea8-131">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="20ea8-131">CompletedActivity</span></span>|<span data-ttu-id="20ea8-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="20ea8-132">xs:string</span></span>|<span data-ttu-id="20ea8-133">완료된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="20ea8-133">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="20ea8-134">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="20ea8-134">CompletedActivityDisplayName</span></span>|<span data-ttu-id="20ea8-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="20ea8-135">xs:string</span></span>|<span data-ttu-id="20ea8-136">완료된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="20ea8-136">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="20ea8-137">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="20ea8-137">CompletedActivityInstanceId</span></span>|<span data-ttu-id="20ea8-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="20ea8-138">xs:string</span></span>|<span data-ttu-id="20ea8-139">완료된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="20ea8-139">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="20ea8-140">AppDomain</span><span class="sxs-lookup"><span data-stu-id="20ea8-140">AppDomain</span></span>|<span data-ttu-id="20ea8-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="20ea8-141">xs:string</span></span>|<span data-ttu-id="20ea8-142">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="20ea8-142">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
