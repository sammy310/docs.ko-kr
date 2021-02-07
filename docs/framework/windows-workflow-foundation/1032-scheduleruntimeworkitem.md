---
description: '자세한 정보: 1032-ScheduleRuntimeWorkItem'
title: 1032 - ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: d96226b4ab0f856218d292c9c2481bca6c463c8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668047"
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="1f6d3-103">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="1f6d3-103">1032 - ScheduleRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="1f6d3-104">속성</span><span class="sxs-lookup"><span data-stu-id="1f6d3-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1f6d3-105">ID</span><span class="sxs-lookup"><span data-stu-id="1f6d3-105">ID</span></span>|<span data-ttu-id="1f6d3-106">1032</span><span class="sxs-lookup"><span data-stu-id="1f6d3-106">1032</span></span>|  
|<span data-ttu-id="1f6d3-107">키워드</span><span class="sxs-lookup"><span data-stu-id="1f6d3-107">Keywords</span></span>|<span data-ttu-id="1f6d3-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1f6d3-108">WFRuntime</span></span>|  
|<span data-ttu-id="1f6d3-109">Level</span><span class="sxs-lookup"><span data-stu-id="1f6d3-109">Level</span></span>|<span data-ttu-id="1f6d3-110">자세히</span><span class="sxs-lookup"><span data-stu-id="1f6d3-110">Verbose</span></span>|  
|<span data-ttu-id="1f6d3-111">채널</span><span class="sxs-lookup"><span data-stu-id="1f6d3-111">Channel</span></span>|<span data-ttu-id="1f6d3-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="1f6d3-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1f6d3-113">설명</span><span class="sxs-lookup"><span data-stu-id="1f6d3-113">Description</span></span>  

 <span data-ttu-id="1f6d3-114">RuntimeWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1f6d3-114">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1f6d3-115">메시지</span><span class="sxs-lookup"><span data-stu-id="1f6d3-115">Message</span></span>  

 <span data-ttu-id="1f6d3-116">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목이 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6d3-116">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1f6d3-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="1f6d3-117">Details</span></span>  
  
|<span data-ttu-id="1f6d3-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="1f6d3-118">Data Item Name</span></span>|<span data-ttu-id="1f6d3-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="1f6d3-119">Data Item Type</span></span>|<span data-ttu-id="1f6d3-120">설명</span><span class="sxs-lookup"><span data-stu-id="1f6d3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1f6d3-121">활동</span><span class="sxs-lookup"><span data-stu-id="1f6d3-121">Activity</span></span>|<span data-ttu-id="1f6d3-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="1f6d3-122">xs:string</span></span>|<span data-ttu-id="1f6d3-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1f6d3-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="1f6d3-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1f6d3-124">DisplayName</span></span>|<span data-ttu-id="1f6d3-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="1f6d3-125">xs:string</span></span>|<span data-ttu-id="1f6d3-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1f6d3-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="1f6d3-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="1f6d3-127">InstanceId</span></span>|<span data-ttu-id="1f6d3-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="1f6d3-128">xs:string</span></span>|<span data-ttu-id="1f6d3-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1f6d3-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="1f6d3-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1f6d3-130">AppDomain</span></span>|<span data-ttu-id="1f6d3-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="1f6d3-131">xs:string</span></span>|<span data-ttu-id="1f6d3-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f6d3-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
