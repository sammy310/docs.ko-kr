---
description: '자세한 정보: 1010-ActivityCompleted'
title: 1010 - ActivityCompleted
ms.date: 03/30/2017
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
ms.openlocfilehash: c72339449b94b0ea5d6d8fa227b606cc25c29704
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755540"
---
# <a name="1010---activitycompleted"></a><span data-ttu-id="0c86d-103">1010 - ActivityCompleted</span><span class="sxs-lookup"><span data-stu-id="0c86d-103">1010 - ActivityCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="0c86d-104">속성</span><span class="sxs-lookup"><span data-stu-id="0c86d-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0c86d-105">ID</span><span class="sxs-lookup"><span data-stu-id="0c86d-105">ID</span></span>|<span data-ttu-id="0c86d-106">1010</span><span class="sxs-lookup"><span data-stu-id="0c86d-106">1010</span></span>|  
|<span data-ttu-id="0c86d-107">키워드</span><span class="sxs-lookup"><span data-stu-id="0c86d-107">Keywords</span></span>|<span data-ttu-id="0c86d-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0c86d-108">WFRuntime</span></span>|  
|<span data-ttu-id="0c86d-109">Level</span><span class="sxs-lookup"><span data-stu-id="0c86d-109">Level</span></span>|<span data-ttu-id="0c86d-110">정보</span><span class="sxs-lookup"><span data-stu-id="0c86d-110">Information</span></span>|  
|<span data-ttu-id="0c86d-111">채널</span><span class="sxs-lookup"><span data-stu-id="0c86d-111">Channel</span></span>|<span data-ttu-id="0c86d-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="0c86d-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0c86d-113">설명</span><span class="sxs-lookup"><span data-stu-id="0c86d-113">Description</span></span>  

 <span data-ttu-id="0c86d-114">작업의 실행이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0c86d-114">Indicates an activity has completed execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0c86d-115">메시지</span><span class="sxs-lookup"><span data-stu-id="0c86d-115">Message</span></span>  

 <span data-ttu-id="0c86d-116">Activity '%1', DisplayName: '%2', InstanceId: '%3'이(가) '%4' 상태로 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0c86d-116">Activity '%1', DisplayName: '%2', InstanceId: '%3' has completed in the '%4' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0c86d-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="0c86d-117">Details</span></span>  
  
|<span data-ttu-id="0c86d-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="0c86d-118">Data Item Name</span></span>|<span data-ttu-id="0c86d-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="0c86d-119">Data Item Type</span></span>|<span data-ttu-id="0c86d-120">설명</span><span class="sxs-lookup"><span data-stu-id="0c86d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0c86d-121">활동</span><span class="sxs-lookup"><span data-stu-id="0c86d-121">Activity</span></span>|<span data-ttu-id="0c86d-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0c86d-122">xs:string</span></span>|<span data-ttu-id="0c86d-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0c86d-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="0c86d-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0c86d-124">DisplayName</span></span>|<span data-ttu-id="0c86d-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0c86d-125">xs:string</span></span>|<span data-ttu-id="0c86d-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0c86d-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="0c86d-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0c86d-127">InstanceId</span></span>|<span data-ttu-id="0c86d-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0c86d-128">xs:string</span></span>|<span data-ttu-id="0c86d-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0c86d-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0c86d-130">시스템 상태</span><span class="sxs-lookup"><span data-stu-id="0c86d-130">State</span></span>|<span data-ttu-id="0c86d-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="0c86d-131">xs:string</span></span>|<span data-ttu-id="0c86d-132">작업의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="0c86d-132">The state of the activity.</span></span>|  
|<span data-ttu-id="0c86d-133">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0c86d-133">AppDomain</span></span>|<span data-ttu-id="0c86d-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="0c86d-134">xs:string</span></span>|<span data-ttu-id="0c86d-135">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c86d-135">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
