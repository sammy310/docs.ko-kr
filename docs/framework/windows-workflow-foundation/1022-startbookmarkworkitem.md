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
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="30dad-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="30dad-102">1022 - StartBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="30dad-103">속성</span><span class="sxs-lookup"><span data-stu-id="30dad-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="30dad-104">ID</span><span class="sxs-lookup"><span data-stu-id="30dad-104">ID</span></span>|<span data-ttu-id="30dad-105">1022</span><span class="sxs-lookup"><span data-stu-id="30dad-105">1022</span></span>|  
|<span data-ttu-id="30dad-106">키워드</span><span class="sxs-lookup"><span data-stu-id="30dad-106">Keywords</span></span>|<span data-ttu-id="30dad-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="30dad-107">WFRuntime</span></span>|  
|<span data-ttu-id="30dad-108">수준</span><span class="sxs-lookup"><span data-stu-id="30dad-108">Level</span></span>|<span data-ttu-id="30dad-109">자세히</span><span class="sxs-lookup"><span data-stu-id="30dad-109">Verbose</span></span>|  
|<span data-ttu-id="30dad-110">채널</span><span class="sxs-lookup"><span data-stu-id="30dad-110">Channel</span></span>|<span data-ttu-id="30dad-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="30dad-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="30dad-112">설명</span><span class="sxs-lookup"><span data-stu-id="30dad-112">Description</span></span>  
 <span data-ttu-id="30dad-113">BookmarkWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="30dad-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="30dad-114">메시지</span><span class="sxs-lookup"><span data-stu-id="30dad-114">Message</span></span>  
 <span data-ttu-id="30dad-115">작업 '%1', DisplayName에 대해 BookmarkWorkItem의 실행을 시작 합니다. '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="30dad-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="30dad-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="30dad-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="30dad-117">설명</span><span class="sxs-lookup"><span data-stu-id="30dad-117">Details</span></span>  
  
|<span data-ttu-id="30dad-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="30dad-118">Data Item Name</span></span>|<span data-ttu-id="30dad-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="30dad-119">Data Item Type</span></span>|<span data-ttu-id="30dad-120">설명</span><span class="sxs-lookup"><span data-stu-id="30dad-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="30dad-121">활동</span><span class="sxs-lookup"><span data-stu-id="30dad-121">Activity</span></span>|<span data-ttu-id="30dad-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="30dad-122">xs:string</span></span>|<span data-ttu-id="30dad-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="30dad-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="30dad-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="30dad-124">DisplayName</span></span>|<span data-ttu-id="30dad-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="30dad-125">xs:string</span></span>|<span data-ttu-id="30dad-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="30dad-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="30dad-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="30dad-127">InstanceId</span></span>|<span data-ttu-id="30dad-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="30dad-128">xs:string</span></span>|<span data-ttu-id="30dad-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="30dad-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="30dad-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="30dad-130">BookmarkName</span></span>|<span data-ttu-id="30dad-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="30dad-131">xs:string</span></span>|<span data-ttu-id="30dad-132">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="30dad-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="30dad-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="30dad-133">BookmarkScope</span></span>|<span data-ttu-id="30dad-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="30dad-134">xs:string</span></span>|<span data-ttu-id="30dad-135">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="30dad-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="30dad-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="30dad-136">AppDomain</span></span>|<span data-ttu-id="30dad-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="30dad-137">xs:string</span></span>|<span data-ttu-id="30dad-138">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="30dad-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
