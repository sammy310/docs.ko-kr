---
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 2a382a2f12f4800cd70286a553af253e2af64c9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924750"
---
# <a name="1020---createbookmark"></a><span data-ttu-id="d26f1-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="d26f1-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="d26f1-103">속성</span><span class="sxs-lookup"><span data-stu-id="d26f1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d26f1-104">ID</span><span class="sxs-lookup"><span data-stu-id="d26f1-104">ID</span></span>|<span data-ttu-id="d26f1-105">1020</span><span class="sxs-lookup"><span data-stu-id="d26f1-105">1020</span></span>|  
|<span data-ttu-id="d26f1-106">키워드</span><span class="sxs-lookup"><span data-stu-id="d26f1-106">Keywords</span></span>|<span data-ttu-id="d26f1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d26f1-107">WFRuntime</span></span>|  
|<span data-ttu-id="d26f1-108">수준</span><span class="sxs-lookup"><span data-stu-id="d26f1-108">Level</span></span>|<span data-ttu-id="d26f1-109">자세히</span><span class="sxs-lookup"><span data-stu-id="d26f1-109">Verbose</span></span>|  
|<span data-ttu-id="d26f1-110">채널</span><span class="sxs-lookup"><span data-stu-id="d26f1-110">Channel</span></span>|<span data-ttu-id="d26f1-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="d26f1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d26f1-112">설명</span><span class="sxs-lookup"><span data-stu-id="d26f1-112">Description</span></span>  
 <span data-ttu-id="d26f1-113">작업에 대한 책갈피가 만들어졌음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d26f1-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d26f1-114">메시지</span><span class="sxs-lookup"><span data-stu-id="d26f1-114">Message</span></span>  
 <span data-ttu-id="d26f1-115">작업 '%1', DisplayName에 대 한 책갈피를 만들었습니다. '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="d26f1-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="d26f1-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="d26f1-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d26f1-117">설명</span><span class="sxs-lookup"><span data-stu-id="d26f1-117">Details</span></span>  
  
|<span data-ttu-id="d26f1-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="d26f1-118">Data Item Name</span></span>|<span data-ttu-id="d26f1-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="d26f1-119">Data Item Type</span></span>|<span data-ttu-id="d26f1-120">설명</span><span class="sxs-lookup"><span data-stu-id="d26f1-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d26f1-121">활동</span><span class="sxs-lookup"><span data-stu-id="d26f1-121">Activity</span></span>|<span data-ttu-id="d26f1-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="d26f1-122">xs:string</span></span>|<span data-ttu-id="d26f1-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d26f1-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="d26f1-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d26f1-124">DisplayName</span></span>|<span data-ttu-id="d26f1-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="d26f1-125">xs:string</span></span>|<span data-ttu-id="d26f1-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d26f1-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="d26f1-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d26f1-127">InstanceId</span></span>|<span data-ttu-id="d26f1-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="d26f1-128">xs:string</span></span>|<span data-ttu-id="d26f1-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d26f1-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="d26f1-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="d26f1-130">BookmarkName</span></span>|<span data-ttu-id="d26f1-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="d26f1-131">xs:string</span></span>|<span data-ttu-id="d26f1-132">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d26f1-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="d26f1-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="d26f1-133">BookmarkScope</span></span>|<span data-ttu-id="d26f1-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="d26f1-134">xs:string</span></span>|<span data-ttu-id="d26f1-135">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="d26f1-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="d26f1-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d26f1-136">AppDomain</span></span>|<span data-ttu-id="d26f1-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="d26f1-137">xs:string</span></span>|<span data-ttu-id="d26f1-138">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d26f1-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
