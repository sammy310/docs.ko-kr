---
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 8c9c20fd4fb74f80779c1d2ef8f29ac3d44050d9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275377"
---
# <a name="1020---createbookmark"></a><span data-ttu-id="24465-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="24465-102">1020 - CreateBookmark</span></span>

## <a name="properties"></a><span data-ttu-id="24465-103">속성</span><span class="sxs-lookup"><span data-stu-id="24465-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="24465-104">ID</span><span class="sxs-lookup"><span data-stu-id="24465-104">ID</span></span>|<span data-ttu-id="24465-105">1020</span><span class="sxs-lookup"><span data-stu-id="24465-105">1020</span></span>|  
|<span data-ttu-id="24465-106">키워드</span><span class="sxs-lookup"><span data-stu-id="24465-106">Keywords</span></span>|<span data-ttu-id="24465-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="24465-107">WFRuntime</span></span>|  
|<span data-ttu-id="24465-108">Level</span><span class="sxs-lookup"><span data-stu-id="24465-108">Level</span></span>|<span data-ttu-id="24465-109">자세히</span><span class="sxs-lookup"><span data-stu-id="24465-109">Verbose</span></span>|  
|<span data-ttu-id="24465-110">채널</span><span class="sxs-lookup"><span data-stu-id="24465-110">Channel</span></span>|<span data-ttu-id="24465-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="24465-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="24465-112">Description</span><span class="sxs-lookup"><span data-stu-id="24465-112">Description</span></span>  

 <span data-ttu-id="24465-113">작업에 대한 책갈피가 만들어졌음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="24465-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="24465-114">메시지</span><span class="sxs-lookup"><span data-stu-id="24465-114">Message</span></span>  

 <span data-ttu-id="24465-115">작업 ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '에 대 한 책갈피를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="24465-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="24465-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="24465-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="24465-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="24465-117">Details</span></span>  
  
|<span data-ttu-id="24465-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="24465-118">Data Item Name</span></span>|<span data-ttu-id="24465-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="24465-119">Data Item Type</span></span>|<span data-ttu-id="24465-120">Description</span><span class="sxs-lookup"><span data-stu-id="24465-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="24465-121">활동</span><span class="sxs-lookup"><span data-stu-id="24465-121">Activity</span></span>|<span data-ttu-id="24465-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="24465-122">xs:string</span></span>|<span data-ttu-id="24465-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="24465-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="24465-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="24465-124">DisplayName</span></span>|<span data-ttu-id="24465-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="24465-125">xs:string</span></span>|<span data-ttu-id="24465-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="24465-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="24465-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="24465-127">InstanceId</span></span>|<span data-ttu-id="24465-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="24465-128">xs:string</span></span>|<span data-ttu-id="24465-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="24465-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="24465-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="24465-130">BookmarkName</span></span>|<span data-ttu-id="24465-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="24465-131">xs:string</span></span>|<span data-ttu-id="24465-132">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="24465-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="24465-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="24465-133">BookmarkScope</span></span>|<span data-ttu-id="24465-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="24465-134">xs:string</span></span>|<span data-ttu-id="24465-135">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="24465-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="24465-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="24465-136">AppDomain</span></span>|<span data-ttu-id="24465-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="24465-137">xs:string</span></span>|<span data-ttu-id="24465-138">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="24465-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
