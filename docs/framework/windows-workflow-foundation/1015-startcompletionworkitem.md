---
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: c0d8572f192a8faa22327fd671cd9ea49c5054ca
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275546"
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="54fcf-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="54fcf-102">1015 - StartCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="54fcf-103">속성</span><span class="sxs-lookup"><span data-stu-id="54fcf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="54fcf-104">ID</span><span class="sxs-lookup"><span data-stu-id="54fcf-104">ID</span></span>|<span data-ttu-id="54fcf-105">1015</span><span class="sxs-lookup"><span data-stu-id="54fcf-105">1015</span></span>|  
|<span data-ttu-id="54fcf-106">키워드</span><span class="sxs-lookup"><span data-stu-id="54fcf-106">Keywords</span></span>|<span data-ttu-id="54fcf-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="54fcf-107">WFRuntime</span></span>|  
|<span data-ttu-id="54fcf-108">Level</span><span class="sxs-lookup"><span data-stu-id="54fcf-108">Level</span></span>|<span data-ttu-id="54fcf-109">자세히</span><span class="sxs-lookup"><span data-stu-id="54fcf-109">Verbose</span></span>|  
|<span data-ttu-id="54fcf-110">채널</span><span class="sxs-lookup"><span data-stu-id="54fcf-110">Channel</span></span>|<span data-ttu-id="54fcf-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="54fcf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="54fcf-112">Description</span><span class="sxs-lookup"><span data-stu-id="54fcf-112">Description</span></span>  

 <span data-ttu-id="54fcf-113">CompletionWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54fcf-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="54fcf-114">메시지</span><span class="sxs-lookup"><span data-stu-id="54fcf-114">Message</span></span>  

 <span data-ttu-id="54fcf-115">부모 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CompletionWorkItem의 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="54fcf-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="54fcf-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="54fcf-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="54fcf-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="54fcf-117">Details</span></span>  
  
|<span data-ttu-id="54fcf-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="54fcf-118">Data Item Name</span></span>|<span data-ttu-id="54fcf-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="54fcf-119">Data Item Type</span></span>|<span data-ttu-id="54fcf-120">Description</span><span class="sxs-lookup"><span data-stu-id="54fcf-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="54fcf-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="54fcf-121">ParentActivity</span></span>|<span data-ttu-id="54fcf-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="54fcf-122">xs:string</span></span>|<span data-ttu-id="54fcf-123">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54fcf-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="54fcf-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="54fcf-124">ParentDisplayName</span></span>|<span data-ttu-id="54fcf-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="54fcf-125">xs:string</span></span>|<span data-ttu-id="54fcf-126">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54fcf-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="54fcf-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="54fcf-127">ParentInstanceId</span></span>|<span data-ttu-id="54fcf-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="54fcf-128">xs:string</span></span>|<span data-ttu-id="54fcf-129">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="54fcf-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="54fcf-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="54fcf-130">CompletedActivity</span></span>|<span data-ttu-id="54fcf-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="54fcf-131">xs:string</span></span>|<span data-ttu-id="54fcf-132">완료된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54fcf-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="54fcf-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="54fcf-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="54fcf-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="54fcf-134">xs:string</span></span>|<span data-ttu-id="54fcf-135">완료된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54fcf-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="54fcf-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="54fcf-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="54fcf-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="54fcf-137">xs:string</span></span>|<span data-ttu-id="54fcf-138">완료된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="54fcf-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="54fcf-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="54fcf-139">AppDomain</span></span>|<span data-ttu-id="54fcf-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="54fcf-140">xs:string</span></span>|<span data-ttu-id="54fcf-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="54fcf-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
