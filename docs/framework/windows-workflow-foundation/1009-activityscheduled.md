---
description: '자세히 알아보기: 1009-ActivityScheduled 됨'
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 80ee250955a03927fb9db2b1242d420be77a6df8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755553"
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="0e95f-103">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="0e95f-103">1009 - ActivityScheduled</span></span>

## <a name="properties"></a><span data-ttu-id="0e95f-104">속성</span><span class="sxs-lookup"><span data-stu-id="0e95f-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0e95f-105">ID</span><span class="sxs-lookup"><span data-stu-id="0e95f-105">ID</span></span>|<span data-ttu-id="0e95f-106">1009</span><span class="sxs-lookup"><span data-stu-id="0e95f-106">1009</span></span>|  
|<span data-ttu-id="0e95f-107">키워드</span><span class="sxs-lookup"><span data-stu-id="0e95f-107">Keywords</span></span>|<span data-ttu-id="0e95f-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0e95f-108">WFRuntime</span></span>|  
|<span data-ttu-id="0e95f-109">Level</span><span class="sxs-lookup"><span data-stu-id="0e95f-109">Level</span></span>|<span data-ttu-id="0e95f-110">정보</span><span class="sxs-lookup"><span data-stu-id="0e95f-110">Information</span></span>|  
|<span data-ttu-id="0e95f-111">채널</span><span class="sxs-lookup"><span data-stu-id="0e95f-111">Channel</span></span>|<span data-ttu-id="0e95f-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="0e95f-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0e95f-113">설명</span><span class="sxs-lookup"><span data-stu-id="0e95f-113">Description</span></span>  

 <span data-ttu-id="0e95f-114">실행 예약되는 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e95f-114">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0e95f-115">메시지</span><span class="sxs-lookup"><span data-stu-id="0e95f-115">Message</span></span>  

 <span data-ttu-id="0e95f-116">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="0e95f-116">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0e95f-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="0e95f-117">Details</span></span>  
  
|<span data-ttu-id="0e95f-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="0e95f-118">Data Item Name</span></span>|<span data-ttu-id="0e95f-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="0e95f-119">Data Item Type</span></span>|<span data-ttu-id="0e95f-120">설명</span><span class="sxs-lookup"><span data-stu-id="0e95f-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0e95f-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="0e95f-121">ParentActivity</span></span>|<span data-ttu-id="0e95f-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0e95f-122">xs:string</span></span>|<span data-ttu-id="0e95f-123">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0e95f-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="0e95f-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="0e95f-124">ParentDisplayName</span></span>|<span data-ttu-id="0e95f-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0e95f-125">xs:string</span></span>|<span data-ttu-id="0e95f-126">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0e95f-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="0e95f-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="0e95f-127">ParentInstanceId</span></span>|<span data-ttu-id="0e95f-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0e95f-128">xs:string</span></span>|<span data-ttu-id="0e95f-129">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0e95f-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="0e95f-130">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="0e95f-130">ChildActivity</span></span>|<span data-ttu-id="0e95f-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="0e95f-131">xs:string</span></span>|<span data-ttu-id="0e95f-132">예약된 자식 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0e95f-132">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="0e95f-133">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="0e95f-133">ChildDisplayName</span></span>|<span data-ttu-id="0e95f-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="0e95f-134">xs:string</span></span>|<span data-ttu-id="0e95f-135">예약된 자식 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0e95f-135">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="0e95f-136">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="0e95f-136">ChildInstanceId</span></span>|<span data-ttu-id="0e95f-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="0e95f-137">xs:string</span></span>|<span data-ttu-id="0e95f-138">예약된 자식 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0e95f-138">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="0e95f-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0e95f-139">AppDomain</span></span>|<span data-ttu-id="0e95f-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="0e95f-140">xs:string</span></span>|<span data-ttu-id="0e95f-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0e95f-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
