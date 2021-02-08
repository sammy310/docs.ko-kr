---
description: '자세한 정보: 1021-ScheduleBookmarkWorkItem'
title: 1021 - ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: 5153d2e90a75bab90c76ee8786dc82d4ddac19a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792819"
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="42a01-103">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="42a01-103">1021 - ScheduleBookmarkWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="42a01-104">속성</span><span class="sxs-lookup"><span data-stu-id="42a01-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42a01-105">ID</span><span class="sxs-lookup"><span data-stu-id="42a01-105">ID</span></span>|<span data-ttu-id="42a01-106">1021</span><span class="sxs-lookup"><span data-stu-id="42a01-106">1021</span></span>|  
|<span data-ttu-id="42a01-107">키워드</span><span class="sxs-lookup"><span data-stu-id="42a01-107">Keywords</span></span>|<span data-ttu-id="42a01-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="42a01-108">WFRuntime</span></span>|  
|<span data-ttu-id="42a01-109">Level</span><span class="sxs-lookup"><span data-stu-id="42a01-109">Level</span></span>|<span data-ttu-id="42a01-110">자세히</span><span class="sxs-lookup"><span data-stu-id="42a01-110">Verbose</span></span>|  
|<span data-ttu-id="42a01-111">채널</span><span class="sxs-lookup"><span data-stu-id="42a01-111">Channel</span></span>|<span data-ttu-id="42a01-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="42a01-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="42a01-113">설명</span><span class="sxs-lookup"><span data-stu-id="42a01-113">Description</span></span>  

 <span data-ttu-id="42a01-114">BookmarkWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="42a01-114">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="42a01-115">메시지</span><span class="sxs-lookup"><span data-stu-id="42a01-115">Message</span></span>  

 <span data-ttu-id="42a01-116">작업 ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '에 대 한 책갈피 작업 항목을 예약 했습니다.</span><span class="sxs-lookup"><span data-stu-id="42a01-116">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="42a01-117">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="42a01-117">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="42a01-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="42a01-118">Details</span></span>  
  
|<span data-ttu-id="42a01-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="42a01-119">Data Item Name</span></span>|<span data-ttu-id="42a01-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="42a01-120">Data Item Type</span></span>|<span data-ttu-id="42a01-121">설명</span><span class="sxs-lookup"><span data-stu-id="42a01-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="42a01-122">활동</span><span class="sxs-lookup"><span data-stu-id="42a01-122">Activity</span></span>|<span data-ttu-id="42a01-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="42a01-123">xs:string</span></span>|<span data-ttu-id="42a01-124">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="42a01-124">The type name of the activity.</span></span>|  
|<span data-ttu-id="42a01-125">DisplayName</span><span class="sxs-lookup"><span data-stu-id="42a01-125">DisplayName</span></span>|<span data-ttu-id="42a01-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="42a01-126">xs:string</span></span>|<span data-ttu-id="42a01-127">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="42a01-127">The display name of the activity.</span></span>|  
|<span data-ttu-id="42a01-128">InstanceId</span><span class="sxs-lookup"><span data-stu-id="42a01-128">InstanceId</span></span>|<span data-ttu-id="42a01-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="42a01-129">xs:string</span></span>|<span data-ttu-id="42a01-130">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="42a01-130">The instance id of the activity.</span></span>|  
|<span data-ttu-id="42a01-131">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="42a01-131">BookmarkName</span></span>|<span data-ttu-id="42a01-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="42a01-132">xs:string</span></span>|<span data-ttu-id="42a01-133">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="42a01-133">The name of the bookmark.</span></span>|  
|<span data-ttu-id="42a01-134">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="42a01-134">BookmarkScope</span></span>|<span data-ttu-id="42a01-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="42a01-135">xs:string</span></span>|<span data-ttu-id="42a01-136">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="42a01-136">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="42a01-137">AppDomain</span><span class="sxs-lookup"><span data-stu-id="42a01-137">AppDomain</span></span>|<span data-ttu-id="42a01-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="42a01-138">xs:string</span></span>|<span data-ttu-id="42a01-139">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="42a01-139">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
