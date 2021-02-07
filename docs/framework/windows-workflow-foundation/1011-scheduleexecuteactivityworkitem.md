---
description: '자세한 정보: 1011-ScheduleExecuteActivityWorkItem'
title: 1011 - ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: 81010390de2ad01ec3063f2ac89608b97dcb713e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703356"
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="a259a-103">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="a259a-103">1011 - ScheduleExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="a259a-104">속성</span><span class="sxs-lookup"><span data-stu-id="a259a-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a259a-105">ID</span><span class="sxs-lookup"><span data-stu-id="a259a-105">ID</span></span>|<span data-ttu-id="a259a-106">1011</span><span class="sxs-lookup"><span data-stu-id="a259a-106">1011</span></span>|  
|<span data-ttu-id="a259a-107">키워드</span><span class="sxs-lookup"><span data-stu-id="a259a-107">Keywords</span></span>|<span data-ttu-id="a259a-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a259a-108">WFRuntime</span></span>|  
|<span data-ttu-id="a259a-109">Level</span><span class="sxs-lookup"><span data-stu-id="a259a-109">Level</span></span>|<span data-ttu-id="a259a-110">자세히</span><span class="sxs-lookup"><span data-stu-id="a259a-110">Verbose</span></span>|  
|<span data-ttu-id="a259a-111">채널</span><span class="sxs-lookup"><span data-stu-id="a259a-111">Channel</span></span>|<span data-ttu-id="a259a-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="a259a-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a259a-113">설명</span><span class="sxs-lookup"><span data-stu-id="a259a-113">Description</span></span>  

 <span data-ttu-id="a259a-114">ExecuteActivityWorkItem이 예약되어 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a259a-114">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a259a-115">메시지</span><span class="sxs-lookup"><span data-stu-id="a259a-115">Message</span></span>  

 <span data-ttu-id="a259a-116">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem이 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a259a-116">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a259a-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="a259a-117">Details</span></span>  
  
|<span data-ttu-id="a259a-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="a259a-118">Data Item Name</span></span>|<span data-ttu-id="a259a-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="a259a-119">Data Item Type</span></span>|<span data-ttu-id="a259a-120">설명</span><span class="sxs-lookup"><span data-stu-id="a259a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a259a-121">활동</span><span class="sxs-lookup"><span data-stu-id="a259a-121">Activity</span></span>|<span data-ttu-id="a259a-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="a259a-122">xs:string</span></span>|<span data-ttu-id="a259a-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a259a-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="a259a-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a259a-124">DisplayName</span></span>|<span data-ttu-id="a259a-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="a259a-125">xs:string</span></span>|<span data-ttu-id="a259a-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a259a-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="a259a-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="a259a-127">InstanceId</span></span>|<span data-ttu-id="a259a-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="a259a-128">xs:string</span></span>|<span data-ttu-id="a259a-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a259a-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="a259a-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a259a-130">AppDomain</span></span>|<span data-ttu-id="a259a-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="a259a-131">xs:string</span></span>|<span data-ttu-id="a259a-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a259a-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
