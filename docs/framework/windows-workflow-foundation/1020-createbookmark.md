---
description: '자세한 정보: 1020-CreateBookmark'
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 39796eaf68d9cb52e9faa2605fc21955a2c167ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792845"
---
# <a name="1020---createbookmark"></a><span data-ttu-id="192ca-103">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="192ca-103">1020 - CreateBookmark</span></span>

## <a name="properties"></a><span data-ttu-id="192ca-104">속성</span><span class="sxs-lookup"><span data-stu-id="192ca-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="192ca-105">ID</span><span class="sxs-lookup"><span data-stu-id="192ca-105">ID</span></span>|<span data-ttu-id="192ca-106">1020</span><span class="sxs-lookup"><span data-stu-id="192ca-106">1020</span></span>|  
|<span data-ttu-id="192ca-107">키워드</span><span class="sxs-lookup"><span data-stu-id="192ca-107">Keywords</span></span>|<span data-ttu-id="192ca-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="192ca-108">WFRuntime</span></span>|  
|<span data-ttu-id="192ca-109">Level</span><span class="sxs-lookup"><span data-stu-id="192ca-109">Level</span></span>|<span data-ttu-id="192ca-110">자세히</span><span class="sxs-lookup"><span data-stu-id="192ca-110">Verbose</span></span>|  
|<span data-ttu-id="192ca-111">채널</span><span class="sxs-lookup"><span data-stu-id="192ca-111">Channel</span></span>|<span data-ttu-id="192ca-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="192ca-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="192ca-113">설명</span><span class="sxs-lookup"><span data-stu-id="192ca-113">Description</span></span>  

 <span data-ttu-id="192ca-114">작업에 대한 책갈피가 만들어졌음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="192ca-114">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="192ca-115">메시지</span><span class="sxs-lookup"><span data-stu-id="192ca-115">Message</span></span>  

 <span data-ttu-id="192ca-116">작업 ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '에 대 한 책갈피를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="192ca-116">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="192ca-117">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="192ca-117">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="192ca-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="192ca-118">Details</span></span>  
  
|<span data-ttu-id="192ca-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="192ca-119">Data Item Name</span></span>|<span data-ttu-id="192ca-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="192ca-120">Data Item Type</span></span>|<span data-ttu-id="192ca-121">설명</span><span class="sxs-lookup"><span data-stu-id="192ca-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="192ca-122">활동</span><span class="sxs-lookup"><span data-stu-id="192ca-122">Activity</span></span>|<span data-ttu-id="192ca-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="192ca-123">xs:string</span></span>|<span data-ttu-id="192ca-124">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="192ca-124">The type name of the activity.</span></span>|  
|<span data-ttu-id="192ca-125">DisplayName</span><span class="sxs-lookup"><span data-stu-id="192ca-125">DisplayName</span></span>|<span data-ttu-id="192ca-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="192ca-126">xs:string</span></span>|<span data-ttu-id="192ca-127">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="192ca-127">The display name of the activity.</span></span>|  
|<span data-ttu-id="192ca-128">InstanceId</span><span class="sxs-lookup"><span data-stu-id="192ca-128">InstanceId</span></span>|<span data-ttu-id="192ca-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="192ca-129">xs:string</span></span>|<span data-ttu-id="192ca-130">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="192ca-130">The instance id of the activity.</span></span>|  
|<span data-ttu-id="192ca-131">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="192ca-131">BookmarkName</span></span>|<span data-ttu-id="192ca-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="192ca-132">xs:string</span></span>|<span data-ttu-id="192ca-133">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="192ca-133">The name of the bookmark.</span></span>|  
|<span data-ttu-id="192ca-134">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="192ca-134">BookmarkScope</span></span>|<span data-ttu-id="192ca-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="192ca-135">xs:string</span></span>|<span data-ttu-id="192ca-136">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="192ca-136">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="192ca-137">AppDomain</span><span class="sxs-lookup"><span data-stu-id="192ca-137">AppDomain</span></span>|<span data-ttu-id="192ca-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="192ca-138">xs:string</span></span>|<span data-ttu-id="192ca-139">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="192ca-139">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
