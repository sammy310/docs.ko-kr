---
description: '자세한 정보: 1033-StartRuntimeWorkItem'
title: 1033 - StartRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
ms.openlocfilehash: 31e664070b7592d3350a2f6f84f0493cc8f11ea1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668008"
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="30bb6-103">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="30bb6-103">1033 - StartRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="30bb6-104">속성</span><span class="sxs-lookup"><span data-stu-id="30bb6-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="30bb6-105">ID</span><span class="sxs-lookup"><span data-stu-id="30bb6-105">ID</span></span>|<span data-ttu-id="30bb6-106">1033</span><span class="sxs-lookup"><span data-stu-id="30bb6-106">1033</span></span>|  
|<span data-ttu-id="30bb6-107">키워드</span><span class="sxs-lookup"><span data-stu-id="30bb6-107">Keywords</span></span>|<span data-ttu-id="30bb6-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="30bb6-108">WFRuntime</span></span>|  
|<span data-ttu-id="30bb6-109">Level</span><span class="sxs-lookup"><span data-stu-id="30bb6-109">Level</span></span>|<span data-ttu-id="30bb6-110">자세히</span><span class="sxs-lookup"><span data-stu-id="30bb6-110">Verbose</span></span>|  
|<span data-ttu-id="30bb6-111">채널</span><span class="sxs-lookup"><span data-stu-id="30bb6-111">Channel</span></span>|<span data-ttu-id="30bb6-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="30bb6-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="30bb6-113">설명</span><span class="sxs-lookup"><span data-stu-id="30bb6-113">Description</span></span>  

 <span data-ttu-id="30bb6-114">RuntimeWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="30bb6-114">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="30bb6-115">메시지</span><span class="sxs-lookup"><span data-stu-id="30bb6-115">Message</span></span>  

 <span data-ttu-id="30bb6-116">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목의 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="30bb6-116">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="30bb6-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="30bb6-117">Details</span></span>  
  
|<span data-ttu-id="30bb6-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="30bb6-118">Data Item Name</span></span>|<span data-ttu-id="30bb6-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="30bb6-119">Data Item Type</span></span>|<span data-ttu-id="30bb6-120">설명</span><span class="sxs-lookup"><span data-stu-id="30bb6-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="30bb6-121">활동</span><span class="sxs-lookup"><span data-stu-id="30bb6-121">Activity</span></span>|<span data-ttu-id="30bb6-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="30bb6-122">xs:string</span></span>|<span data-ttu-id="30bb6-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="30bb6-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="30bb6-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="30bb6-124">DisplayName</span></span>|<span data-ttu-id="30bb6-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="30bb6-125">xs:string</span></span>|<span data-ttu-id="30bb6-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="30bb6-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="30bb6-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="30bb6-127">InstanceId</span></span>|<span data-ttu-id="30bb6-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="30bb6-128">xs:string</span></span>|<span data-ttu-id="30bb6-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="30bb6-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="30bb6-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="30bb6-130">AppDomain</span></span>|<span data-ttu-id="30bb6-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="30bb6-131">xs:string</span></span>|<span data-ttu-id="30bb6-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="30bb6-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
