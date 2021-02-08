---
description: '자세한 정보: 1015-Start작업 항목'
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: 6c79a02b144aa1176eb1cb334c8430c8f0babc3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792923"
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="9ddd7-103">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="9ddd7-103">1015 - StartCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="9ddd7-104">속성</span><span class="sxs-lookup"><span data-stu-id="9ddd7-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9ddd7-105">ID</span><span class="sxs-lookup"><span data-stu-id="9ddd7-105">ID</span></span>|<span data-ttu-id="9ddd7-106">1015</span><span class="sxs-lookup"><span data-stu-id="9ddd7-106">1015</span></span>|  
|<span data-ttu-id="9ddd7-107">키워드</span><span class="sxs-lookup"><span data-stu-id="9ddd7-107">Keywords</span></span>|<span data-ttu-id="9ddd7-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9ddd7-108">WFRuntime</span></span>|  
|<span data-ttu-id="9ddd7-109">Level</span><span class="sxs-lookup"><span data-stu-id="9ddd7-109">Level</span></span>|<span data-ttu-id="9ddd7-110">자세히</span><span class="sxs-lookup"><span data-stu-id="9ddd7-110">Verbose</span></span>|  
|<span data-ttu-id="9ddd7-111">채널</span><span class="sxs-lookup"><span data-stu-id="9ddd7-111">Channel</span></span>|<span data-ttu-id="9ddd7-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="9ddd7-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9ddd7-113">설명</span><span class="sxs-lookup"><span data-stu-id="9ddd7-113">Description</span></span>  

 <span data-ttu-id="9ddd7-114">CompletionWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ddd7-114">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9ddd7-115">메시지</span><span class="sxs-lookup"><span data-stu-id="9ddd7-115">Message</span></span>  

 <span data-ttu-id="9ddd7-116">부모 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CompletionWorkItem의 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9ddd7-116">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="9ddd7-117">작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9ddd7-117">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9ddd7-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="9ddd7-118">Details</span></span>  
  
|<span data-ttu-id="9ddd7-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="9ddd7-119">Data Item Name</span></span>|<span data-ttu-id="9ddd7-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="9ddd7-120">Data Item Type</span></span>|<span data-ttu-id="9ddd7-121">설명</span><span class="sxs-lookup"><span data-stu-id="9ddd7-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9ddd7-122">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="9ddd7-122">ParentActivity</span></span>|<span data-ttu-id="9ddd7-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="9ddd7-123">xs:string</span></span>|<span data-ttu-id="9ddd7-124">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9ddd7-124">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="9ddd7-125">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="9ddd7-125">ParentDisplayName</span></span>|<span data-ttu-id="9ddd7-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="9ddd7-126">xs:string</span></span>|<span data-ttu-id="9ddd7-127">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9ddd7-127">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="9ddd7-128">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="9ddd7-128">ParentInstanceId</span></span>|<span data-ttu-id="9ddd7-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="9ddd7-129">xs:string</span></span>|<span data-ttu-id="9ddd7-130">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9ddd7-130">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="9ddd7-131">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="9ddd7-131">CompletedActivity</span></span>|<span data-ttu-id="9ddd7-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="9ddd7-132">xs:string</span></span>|<span data-ttu-id="9ddd7-133">완료된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9ddd7-133">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="9ddd7-134">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="9ddd7-134">CompletedActivityDisplayName</span></span>|<span data-ttu-id="9ddd7-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="9ddd7-135">xs:string</span></span>|<span data-ttu-id="9ddd7-136">완료된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9ddd7-136">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="9ddd7-137">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="9ddd7-137">CompletedActivityInstanceId</span></span>|<span data-ttu-id="9ddd7-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="9ddd7-138">xs:string</span></span>|<span data-ttu-id="9ddd7-139">완료된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9ddd7-139">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="9ddd7-140">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9ddd7-140">AppDomain</span></span>|<span data-ttu-id="9ddd7-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="9ddd7-141">xs:string</span></span>|<span data-ttu-id="9ddd7-142">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9ddd7-142">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
