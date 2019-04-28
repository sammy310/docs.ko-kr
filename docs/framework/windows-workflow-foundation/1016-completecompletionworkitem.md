---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: 3f0904a561a242cd3be528c9707a409b6f98e0fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925088"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="88444-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="88444-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="88444-103">속성</span><span class="sxs-lookup"><span data-stu-id="88444-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="88444-104">ID</span><span class="sxs-lookup"><span data-stu-id="88444-104">ID</span></span>|<span data-ttu-id="88444-105">1016</span><span class="sxs-lookup"><span data-stu-id="88444-105">1016</span></span>|  
|<span data-ttu-id="88444-106">키워드</span><span class="sxs-lookup"><span data-stu-id="88444-106">Keywords</span></span>|<span data-ttu-id="88444-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="88444-107">WFRuntime</span></span>|  
|<span data-ttu-id="88444-108">수준</span><span class="sxs-lookup"><span data-stu-id="88444-108">Level</span></span>|<span data-ttu-id="88444-109">자세히</span><span class="sxs-lookup"><span data-stu-id="88444-109">Verbose</span></span>|  
|<span data-ttu-id="88444-110">채널</span><span class="sxs-lookup"><span data-stu-id="88444-110">Channel</span></span>|<span data-ttu-id="88444-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="88444-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="88444-112">설명</span><span class="sxs-lookup"><span data-stu-id="88444-112">Description</span></span>  
 <span data-ttu-id="88444-113">CompletionWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88444-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="88444-114">메시지</span><span class="sxs-lookup"><span data-stu-id="88444-114">Message</span></span>  
 <span data-ttu-id="88444-115">부모 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CompletionWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="88444-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="88444-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="88444-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="88444-117">설명</span><span class="sxs-lookup"><span data-stu-id="88444-117">Details</span></span>  
  
|<span data-ttu-id="88444-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="88444-118">Data Item Name</span></span>|<span data-ttu-id="88444-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="88444-119">Data Item Type</span></span>|<span data-ttu-id="88444-120">설명</span><span class="sxs-lookup"><span data-stu-id="88444-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="88444-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="88444-121">ParentActivity</span></span>|<span data-ttu-id="88444-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="88444-122">xs:string</span></span>|<span data-ttu-id="88444-123">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="88444-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="88444-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="88444-124">ParentDisplayName</span></span>|<span data-ttu-id="88444-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="88444-125">xs:string</span></span>|<span data-ttu-id="88444-126">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="88444-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="88444-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="88444-127">ParentInstanceId</span></span>|<span data-ttu-id="88444-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="88444-128">xs:string</span></span>|<span data-ttu-id="88444-129">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="88444-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="88444-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="88444-130">CompletedActivity</span></span>|<span data-ttu-id="88444-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="88444-131">xs:string</span></span>|<span data-ttu-id="88444-132">완료된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="88444-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="88444-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="88444-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="88444-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="88444-134">xs:string</span></span>|<span data-ttu-id="88444-135">완료된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="88444-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="88444-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="88444-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="88444-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="88444-137">xs:string</span></span>|<span data-ttu-id="88444-138">완료된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="88444-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="88444-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="88444-139">AppDomain</span></span>|<span data-ttu-id="88444-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="88444-140">xs:string</span></span>|<span data-ttu-id="88444-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="88444-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
