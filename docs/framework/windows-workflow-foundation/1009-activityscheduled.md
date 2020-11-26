---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 812531d4206dfee20f183b9461330e71263b0bf8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239772"
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="6daa9-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="6daa9-102">1009 - ActivityScheduled</span></span>

## <a name="properties"></a><span data-ttu-id="6daa9-103">속성</span><span class="sxs-lookup"><span data-stu-id="6daa9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6daa9-104">ID</span><span class="sxs-lookup"><span data-stu-id="6daa9-104">ID</span></span>|<span data-ttu-id="6daa9-105">1009</span><span class="sxs-lookup"><span data-stu-id="6daa9-105">1009</span></span>|  
|<span data-ttu-id="6daa9-106">키워드</span><span class="sxs-lookup"><span data-stu-id="6daa9-106">Keywords</span></span>|<span data-ttu-id="6daa9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6daa9-107">WFRuntime</span></span>|  
|<span data-ttu-id="6daa9-108">Level</span><span class="sxs-lookup"><span data-stu-id="6daa9-108">Level</span></span>|<span data-ttu-id="6daa9-109">정보</span><span class="sxs-lookup"><span data-stu-id="6daa9-109">Information</span></span>|  
|<span data-ttu-id="6daa9-110">채널</span><span class="sxs-lookup"><span data-stu-id="6daa9-110">Channel</span></span>|<span data-ttu-id="6daa9-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="6daa9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6daa9-112">Description</span><span class="sxs-lookup"><span data-stu-id="6daa9-112">Description</span></span>  

 <span data-ttu-id="6daa9-113">실행 예약되는 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6daa9-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6daa9-114">메시지</span><span class="sxs-lookup"><span data-stu-id="6daa9-114">Message</span></span>  

 <span data-ttu-id="6daa9-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="6daa9-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6daa9-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="6daa9-116">Details</span></span>  
  
|<span data-ttu-id="6daa9-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="6daa9-117">Data Item Name</span></span>|<span data-ttu-id="6daa9-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="6daa9-118">Data Item Type</span></span>|<span data-ttu-id="6daa9-119">Description</span><span class="sxs-lookup"><span data-stu-id="6daa9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6daa9-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="6daa9-120">ParentActivity</span></span>|<span data-ttu-id="6daa9-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6daa9-121">xs:string</span></span>|<span data-ttu-id="6daa9-122">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6daa9-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="6daa9-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="6daa9-123">ParentDisplayName</span></span>|<span data-ttu-id="6daa9-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="6daa9-124">xs:string</span></span>|<span data-ttu-id="6daa9-125">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6daa9-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="6daa9-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="6daa9-126">ParentInstanceId</span></span>|<span data-ttu-id="6daa9-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="6daa9-127">xs:string</span></span>|<span data-ttu-id="6daa9-128">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6daa9-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="6daa9-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="6daa9-129">ChildActivity</span></span>|<span data-ttu-id="6daa9-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="6daa9-130">xs:string</span></span>|<span data-ttu-id="6daa9-131">예약된 자식 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6daa9-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="6daa9-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="6daa9-132">ChildDisplayName</span></span>|<span data-ttu-id="6daa9-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="6daa9-133">xs:string</span></span>|<span data-ttu-id="6daa9-134">예약된 자식 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6daa9-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="6daa9-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="6daa9-135">ChildInstanceId</span></span>|<span data-ttu-id="6daa9-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="6daa9-136">xs:string</span></span>|<span data-ttu-id="6daa9-137">예약된 자식 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6daa9-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="6daa9-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6daa9-138">AppDomain</span></span>|<span data-ttu-id="6daa9-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="6daa9-139">xs:string</span></span>|<span data-ttu-id="6daa9-140">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6daa9-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
