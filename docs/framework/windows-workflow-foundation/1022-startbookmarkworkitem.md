---
title: 1022 - StartBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
ms.openlocfilehash: 93d906b32b51effaa709da6763f535708cd6f821
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924724"
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="f2479-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="f2479-102">1022 - StartBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="f2479-103">속성</span><span class="sxs-lookup"><span data-stu-id="f2479-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f2479-104">ID</span><span class="sxs-lookup"><span data-stu-id="f2479-104">ID</span></span>|<span data-ttu-id="f2479-105">1022</span><span class="sxs-lookup"><span data-stu-id="f2479-105">1022</span></span>|  
|<span data-ttu-id="f2479-106">키워드</span><span class="sxs-lookup"><span data-stu-id="f2479-106">Keywords</span></span>|<span data-ttu-id="f2479-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f2479-107">WFRuntime</span></span>|  
|<span data-ttu-id="f2479-108">수준</span><span class="sxs-lookup"><span data-stu-id="f2479-108">Level</span></span>|<span data-ttu-id="f2479-109">자세히</span><span class="sxs-lookup"><span data-stu-id="f2479-109">Verbose</span></span>|  
|<span data-ttu-id="f2479-110">채널</span><span class="sxs-lookup"><span data-stu-id="f2479-110">Channel</span></span>|<span data-ttu-id="f2479-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="f2479-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f2479-112">설명</span><span class="sxs-lookup"><span data-stu-id="f2479-112">Description</span></span>  
 <span data-ttu-id="f2479-113">BookmarkWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2479-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f2479-114">메시지</span><span class="sxs-lookup"><span data-stu-id="f2479-114">Message</span></span>  
 <span data-ttu-id="f2479-115">작업 '%1', DisplayName에 대해 BookmarkWorkItem의 실행을 시작 합니다. '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="f2479-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="f2479-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="f2479-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f2479-117">설명</span><span class="sxs-lookup"><span data-stu-id="f2479-117">Details</span></span>  
  
|<span data-ttu-id="f2479-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f2479-118">Data Item Name</span></span>|<span data-ttu-id="f2479-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f2479-119">Data Item Type</span></span>|<span data-ttu-id="f2479-120">설명</span><span class="sxs-lookup"><span data-stu-id="f2479-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f2479-121">활동</span><span class="sxs-lookup"><span data-stu-id="f2479-121">Activity</span></span>|<span data-ttu-id="f2479-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2479-122">xs:string</span></span>|<span data-ttu-id="f2479-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f2479-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="f2479-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f2479-124">DisplayName</span></span>|<span data-ttu-id="f2479-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2479-125">xs:string</span></span>|<span data-ttu-id="f2479-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f2479-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="f2479-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f2479-127">InstanceId</span></span>|<span data-ttu-id="f2479-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2479-128">xs:string</span></span>|<span data-ttu-id="f2479-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f2479-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f2479-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="f2479-130">BookmarkName</span></span>|<span data-ttu-id="f2479-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2479-131">xs:string</span></span>|<span data-ttu-id="f2479-132">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f2479-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="f2479-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="f2479-133">BookmarkScope</span></span>|<span data-ttu-id="f2479-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2479-134">xs:string</span></span>|<span data-ttu-id="f2479-135">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="f2479-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="f2479-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f2479-136">AppDomain</span></span>|<span data-ttu-id="f2479-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2479-137">xs:string</span></span>|<span data-ttu-id="f2479-138">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f2479-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
