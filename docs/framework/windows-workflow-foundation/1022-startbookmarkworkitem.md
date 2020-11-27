---
title: 1022 - StartBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
ms.openlocfilehash: ca1f4244fb1a5144cb2d86eaacb9b31137d317c2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275338"
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="d4f42-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="d4f42-102">1022 - StartBookmarkWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="d4f42-103">속성</span><span class="sxs-lookup"><span data-stu-id="d4f42-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4f42-104">ID</span><span class="sxs-lookup"><span data-stu-id="d4f42-104">ID</span></span>|<span data-ttu-id="d4f42-105">1022</span><span class="sxs-lookup"><span data-stu-id="d4f42-105">1022</span></span>|  
|<span data-ttu-id="d4f42-106">키워드</span><span class="sxs-lookup"><span data-stu-id="d4f42-106">Keywords</span></span>|<span data-ttu-id="d4f42-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d4f42-107">WFRuntime</span></span>|  
|<span data-ttu-id="d4f42-108">Level</span><span class="sxs-lookup"><span data-stu-id="d4f42-108">Level</span></span>|<span data-ttu-id="d4f42-109">자세히</span><span class="sxs-lookup"><span data-stu-id="d4f42-109">Verbose</span></span>|  
|<span data-ttu-id="d4f42-110">채널</span><span class="sxs-lookup"><span data-stu-id="d4f42-110">Channel</span></span>|<span data-ttu-id="d4f42-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="d4f42-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d4f42-112">Description</span><span class="sxs-lookup"><span data-stu-id="d4f42-112">Description</span></span>  

 <span data-ttu-id="d4f42-113">BookmarkWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d4f42-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d4f42-114">메시지</span><span class="sxs-lookup"><span data-stu-id="d4f42-114">Message</span></span>  

 <span data-ttu-id="d4f42-115">작업 ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '에 대 한 책갈피 작업 항목의 실행을 시작 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d4f42-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="d4f42-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="d4f42-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d4f42-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d4f42-117">Details</span></span>  
  
|<span data-ttu-id="d4f42-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="d4f42-118">Data Item Name</span></span>|<span data-ttu-id="d4f42-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="d4f42-119">Data Item Type</span></span>|<span data-ttu-id="d4f42-120">Description</span><span class="sxs-lookup"><span data-stu-id="d4f42-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d4f42-121">활동</span><span class="sxs-lookup"><span data-stu-id="d4f42-121">Activity</span></span>|<span data-ttu-id="d4f42-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4f42-122">xs:string</span></span>|<span data-ttu-id="d4f42-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d4f42-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="d4f42-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d4f42-124">DisplayName</span></span>|<span data-ttu-id="d4f42-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4f42-125">xs:string</span></span>|<span data-ttu-id="d4f42-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d4f42-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="d4f42-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d4f42-127">InstanceId</span></span>|<span data-ttu-id="d4f42-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4f42-128">xs:string</span></span>|<span data-ttu-id="d4f42-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d4f42-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="d4f42-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="d4f42-130">BookmarkName</span></span>|<span data-ttu-id="d4f42-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4f42-131">xs:string</span></span>|<span data-ttu-id="d4f42-132">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d4f42-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="d4f42-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="d4f42-133">BookmarkScope</span></span>|<span data-ttu-id="d4f42-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4f42-134">xs:string</span></span>|<span data-ttu-id="d4f42-135">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="d4f42-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="d4f42-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d4f42-136">AppDomain</span></span>|<span data-ttu-id="d4f42-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4f42-137">xs:string</span></span>|<span data-ttu-id="d4f42-138">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d4f42-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
