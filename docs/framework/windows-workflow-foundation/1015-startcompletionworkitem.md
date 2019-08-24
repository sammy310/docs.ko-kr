---
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: 6a2d4c866ec7d43e8ae40b5616a97c3b7adf1843
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032268"
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="5f9e2-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="5f9e2-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="5f9e2-103">속성</span><span class="sxs-lookup"><span data-stu-id="5f9e2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5f9e2-104">ID</span><span class="sxs-lookup"><span data-stu-id="5f9e2-104">ID</span></span>|<span data-ttu-id="5f9e2-105">1015</span><span class="sxs-lookup"><span data-stu-id="5f9e2-105">1015</span></span>|  
|<span data-ttu-id="5f9e2-106">키워드</span><span class="sxs-lookup"><span data-stu-id="5f9e2-106">Keywords</span></span>|<span data-ttu-id="5f9e2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5f9e2-107">WFRuntime</span></span>|  
|<span data-ttu-id="5f9e2-108">수준</span><span class="sxs-lookup"><span data-stu-id="5f9e2-108">Level</span></span>|<span data-ttu-id="5f9e2-109">자세히</span><span class="sxs-lookup"><span data-stu-id="5f9e2-109">Verbose</span></span>|  
|<span data-ttu-id="5f9e2-110">채널</span><span class="sxs-lookup"><span data-stu-id="5f9e2-110">Channel</span></span>|<span data-ttu-id="5f9e2-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="5f9e2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5f9e2-112">설명</span><span class="sxs-lookup"><span data-stu-id="5f9e2-112">Description</span></span>  
 <span data-ttu-id="5f9e2-113">CompletionWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5f9e2-114">메시지</span><span class="sxs-lookup"><span data-stu-id="5f9e2-114">Message</span></span>  
 <span data-ttu-id="5f9e2-115">부모 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CompletionWorkItem의 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="5f9e2-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5f9e2-117">설명</span><span class="sxs-lookup"><span data-stu-id="5f9e2-117">Details</span></span>  
  
|<span data-ttu-id="5f9e2-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="5f9e2-118">Data Item Name</span></span>|<span data-ttu-id="5f9e2-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="5f9e2-119">Data Item Type</span></span>|<span data-ttu-id="5f9e2-120">설명</span><span class="sxs-lookup"><span data-stu-id="5f9e2-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5f9e2-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="5f9e2-121">ParentActivity</span></span>|<span data-ttu-id="5f9e2-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="5f9e2-122">xs:string</span></span>|<span data-ttu-id="5f9e2-123">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="5f9e2-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="5f9e2-124">ParentDisplayName</span></span>|<span data-ttu-id="5f9e2-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="5f9e2-125">xs:string</span></span>|<span data-ttu-id="5f9e2-126">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="5f9e2-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="5f9e2-127">ParentInstanceId</span></span>|<span data-ttu-id="5f9e2-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="5f9e2-128">xs:string</span></span>|<span data-ttu-id="5f9e2-129">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="5f9e2-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="5f9e2-130">CompletedActivity</span></span>|<span data-ttu-id="5f9e2-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="5f9e2-131">xs:string</span></span>|<span data-ttu-id="5f9e2-132">완료된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="5f9e2-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="5f9e2-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="5f9e2-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="5f9e2-134">xs:string</span></span>|<span data-ttu-id="5f9e2-135">완료된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="5f9e2-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="5f9e2-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="5f9e2-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="5f9e2-137">xs:string</span></span>|<span data-ttu-id="5f9e2-138">완료된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="5f9e2-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5f9e2-139">AppDomain</span></span>|<span data-ttu-id="5f9e2-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="5f9e2-140">xs:string</span></span>|<span data-ttu-id="5f9e2-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5f9e2-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
