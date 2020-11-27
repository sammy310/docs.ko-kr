---
title: 1021 - ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: 42ed23654622e29df8ffc210c8d5ba572fa69fd4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275351"
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="55f99-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="55f99-102">1021 - ScheduleBookmarkWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="55f99-103">속성</span><span class="sxs-lookup"><span data-stu-id="55f99-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55f99-104">ID</span><span class="sxs-lookup"><span data-stu-id="55f99-104">ID</span></span>|<span data-ttu-id="55f99-105">1021</span><span class="sxs-lookup"><span data-stu-id="55f99-105">1021</span></span>|  
|<span data-ttu-id="55f99-106">키워드</span><span class="sxs-lookup"><span data-stu-id="55f99-106">Keywords</span></span>|<span data-ttu-id="55f99-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="55f99-107">WFRuntime</span></span>|  
|<span data-ttu-id="55f99-108">Level</span><span class="sxs-lookup"><span data-stu-id="55f99-108">Level</span></span>|<span data-ttu-id="55f99-109">자세히</span><span class="sxs-lookup"><span data-stu-id="55f99-109">Verbose</span></span>|  
|<span data-ttu-id="55f99-110">채널</span><span class="sxs-lookup"><span data-stu-id="55f99-110">Channel</span></span>|<span data-ttu-id="55f99-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="55f99-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="55f99-112">Description</span><span class="sxs-lookup"><span data-stu-id="55f99-112">Description</span></span>  

 <span data-ttu-id="55f99-113">BookmarkWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="55f99-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="55f99-114">메시지</span><span class="sxs-lookup"><span data-stu-id="55f99-114">Message</span></span>  

 <span data-ttu-id="55f99-115">작업 ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '에 대 한 책갈피 작업 항목을 예약 했습니다.</span><span class="sxs-lookup"><span data-stu-id="55f99-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="55f99-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="55f99-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="55f99-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="55f99-117">Details</span></span>  
  
|<span data-ttu-id="55f99-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="55f99-118">Data Item Name</span></span>|<span data-ttu-id="55f99-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="55f99-119">Data Item Type</span></span>|<span data-ttu-id="55f99-120">Description</span><span class="sxs-lookup"><span data-stu-id="55f99-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="55f99-121">활동</span><span class="sxs-lookup"><span data-stu-id="55f99-121">Activity</span></span>|<span data-ttu-id="55f99-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="55f99-122">xs:string</span></span>|<span data-ttu-id="55f99-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="55f99-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="55f99-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="55f99-124">DisplayName</span></span>|<span data-ttu-id="55f99-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="55f99-125">xs:string</span></span>|<span data-ttu-id="55f99-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="55f99-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="55f99-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="55f99-127">InstanceId</span></span>|<span data-ttu-id="55f99-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="55f99-128">xs:string</span></span>|<span data-ttu-id="55f99-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="55f99-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="55f99-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="55f99-130">BookmarkName</span></span>|<span data-ttu-id="55f99-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="55f99-131">xs:string</span></span>|<span data-ttu-id="55f99-132">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="55f99-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="55f99-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="55f99-133">BookmarkScope</span></span>|<span data-ttu-id="55f99-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="55f99-134">xs:string</span></span>|<span data-ttu-id="55f99-135">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="55f99-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="55f99-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="55f99-136">AppDomain</span></span>|<span data-ttu-id="55f99-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="55f99-137">xs:string</span></span>|<span data-ttu-id="55f99-138">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="55f99-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
