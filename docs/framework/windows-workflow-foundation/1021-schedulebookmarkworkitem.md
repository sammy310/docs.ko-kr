---
title: 1021 - ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: abc026165568d05faef619da28c94f27f37eea27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924425"
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="9b7b7-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="9b7b7-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="9b7b7-103">속성</span><span class="sxs-lookup"><span data-stu-id="9b7b7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9b7b7-104">ID</span><span class="sxs-lookup"><span data-stu-id="9b7b7-104">ID</span></span>|<span data-ttu-id="9b7b7-105">1021</span><span class="sxs-lookup"><span data-stu-id="9b7b7-105">1021</span></span>|  
|<span data-ttu-id="9b7b7-106">키워드</span><span class="sxs-lookup"><span data-stu-id="9b7b7-106">Keywords</span></span>|<span data-ttu-id="9b7b7-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9b7b7-107">WFRuntime</span></span>|  
|<span data-ttu-id="9b7b7-108">수준</span><span class="sxs-lookup"><span data-stu-id="9b7b7-108">Level</span></span>|<span data-ttu-id="9b7b7-109">자세히</span><span class="sxs-lookup"><span data-stu-id="9b7b7-109">Verbose</span></span>|  
|<span data-ttu-id="9b7b7-110">채널</span><span class="sxs-lookup"><span data-stu-id="9b7b7-110">Channel</span></span>|<span data-ttu-id="9b7b7-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="9b7b7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9b7b7-112">설명</span><span class="sxs-lookup"><span data-stu-id="9b7b7-112">Description</span></span>  
 <span data-ttu-id="9b7b7-113">BookmarkWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b7-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9b7b7-114">메시지</span><span class="sxs-lookup"><span data-stu-id="9b7b7-114">Message</span></span>  
 <span data-ttu-id="9b7b7-115">작업 '%1', DisplayName에 대해 BookmarkWorkItem이 예약 되었습니다. '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="9b7b7-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="9b7b7-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="9b7b7-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9b7b7-117">설명</span><span class="sxs-lookup"><span data-stu-id="9b7b7-117">Details</span></span>  
  
|<span data-ttu-id="9b7b7-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="9b7b7-118">Data Item Name</span></span>|<span data-ttu-id="9b7b7-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="9b7b7-119">Data Item Type</span></span>|<span data-ttu-id="9b7b7-120">설명</span><span class="sxs-lookup"><span data-stu-id="9b7b7-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9b7b7-121">활동</span><span class="sxs-lookup"><span data-stu-id="9b7b7-121">Activity</span></span>|<span data-ttu-id="9b7b7-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="9b7b7-122">xs:string</span></span>|<span data-ttu-id="9b7b7-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b7-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="9b7b7-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9b7b7-124">DisplayName</span></span>|<span data-ttu-id="9b7b7-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="9b7b7-125">xs:string</span></span>|<span data-ttu-id="9b7b7-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b7-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="9b7b7-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="9b7b7-127">InstanceId</span></span>|<span data-ttu-id="9b7b7-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="9b7b7-128">xs:string</span></span>|<span data-ttu-id="9b7b7-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b7-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="9b7b7-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="9b7b7-130">BookmarkName</span></span>|<span data-ttu-id="9b7b7-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="9b7b7-131">xs:string</span></span>|<span data-ttu-id="9b7b7-132">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b7-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="9b7b7-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="9b7b7-133">BookmarkScope</span></span>|<span data-ttu-id="9b7b7-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="9b7b7-134">xs:string</span></span>|<span data-ttu-id="9b7b7-135">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b7-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="9b7b7-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9b7b7-136">AppDomain</span></span>|<span data-ttu-id="9b7b7-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="9b7b7-137">xs:string</span></span>|<span data-ttu-id="9b7b7-138">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9b7b7-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
