---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: a192ffe19777ca3e2e9784f6506a0c2929ced000
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275533"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="bf059-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="bf059-102">1016 - CompleteCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="bf059-103">속성</span><span class="sxs-lookup"><span data-stu-id="bf059-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bf059-104">ID</span><span class="sxs-lookup"><span data-stu-id="bf059-104">ID</span></span>|<span data-ttu-id="bf059-105">1016</span><span class="sxs-lookup"><span data-stu-id="bf059-105">1016</span></span>|  
|<span data-ttu-id="bf059-106">키워드</span><span class="sxs-lookup"><span data-stu-id="bf059-106">Keywords</span></span>|<span data-ttu-id="bf059-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bf059-107">WFRuntime</span></span>|  
|<span data-ttu-id="bf059-108">Level</span><span class="sxs-lookup"><span data-stu-id="bf059-108">Level</span></span>|<span data-ttu-id="bf059-109">자세히</span><span class="sxs-lookup"><span data-stu-id="bf059-109">Verbose</span></span>|  
|<span data-ttu-id="bf059-110">채널</span><span class="sxs-lookup"><span data-stu-id="bf059-110">Channel</span></span>|<span data-ttu-id="bf059-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="bf059-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bf059-112">Description</span><span class="sxs-lookup"><span data-stu-id="bf059-112">Description</span></span>  

 <span data-ttu-id="bf059-113">CompletionWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bf059-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bf059-114">메시지</span><span class="sxs-lookup"><span data-stu-id="bf059-114">Message</span></span>  

 <span data-ttu-id="bf059-115">부모 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CompletionWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bf059-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="bf059-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bf059-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bf059-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="bf059-117">Details</span></span>  
  
|<span data-ttu-id="bf059-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="bf059-118">Data Item Name</span></span>|<span data-ttu-id="bf059-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="bf059-119">Data Item Type</span></span>|<span data-ttu-id="bf059-120">Description</span><span class="sxs-lookup"><span data-stu-id="bf059-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bf059-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="bf059-121">ParentActivity</span></span>|<span data-ttu-id="bf059-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="bf059-122">xs:string</span></span>|<span data-ttu-id="bf059-123">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bf059-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="bf059-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="bf059-124">ParentDisplayName</span></span>|<span data-ttu-id="bf059-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="bf059-125">xs:string</span></span>|<span data-ttu-id="bf059-126">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bf059-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="bf059-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="bf059-127">ParentInstanceId</span></span>|<span data-ttu-id="bf059-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="bf059-128">xs:string</span></span>|<span data-ttu-id="bf059-129">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="bf059-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="bf059-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="bf059-130">CompletedActivity</span></span>|<span data-ttu-id="bf059-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="bf059-131">xs:string</span></span>|<span data-ttu-id="bf059-132">완료된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bf059-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="bf059-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="bf059-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="bf059-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="bf059-134">xs:string</span></span>|<span data-ttu-id="bf059-135">완료된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bf059-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="bf059-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="bf059-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="bf059-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="bf059-137">xs:string</span></span>|<span data-ttu-id="bf059-138">완료된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="bf059-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="bf059-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bf059-139">AppDomain</span></span>|<span data-ttu-id="bf059-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="bf059-140">xs:string</span></span>|<span data-ttu-id="bf059-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bf059-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
