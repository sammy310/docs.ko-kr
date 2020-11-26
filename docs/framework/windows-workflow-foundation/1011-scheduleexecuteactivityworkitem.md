---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: dc209fc41dc6b076dfb897880f753be51f7fb0ce
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239694"
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="eae0f-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="eae0f-102">1011 - ScheduleExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="eae0f-103">속성</span><span class="sxs-lookup"><span data-stu-id="eae0f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eae0f-104">ID</span><span class="sxs-lookup"><span data-stu-id="eae0f-104">ID</span></span>|<span data-ttu-id="eae0f-105">1011</span><span class="sxs-lookup"><span data-stu-id="eae0f-105">1011</span></span>|  
|<span data-ttu-id="eae0f-106">키워드</span><span class="sxs-lookup"><span data-stu-id="eae0f-106">Keywords</span></span>|<span data-ttu-id="eae0f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="eae0f-107">WFRuntime</span></span>|  
|<span data-ttu-id="eae0f-108">Level</span><span class="sxs-lookup"><span data-stu-id="eae0f-108">Level</span></span>|<span data-ttu-id="eae0f-109">자세히</span><span class="sxs-lookup"><span data-stu-id="eae0f-109">Verbose</span></span>|  
|<span data-ttu-id="eae0f-110">채널</span><span class="sxs-lookup"><span data-stu-id="eae0f-110">Channel</span></span>|<span data-ttu-id="eae0f-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="eae0f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="eae0f-112">Description</span><span class="sxs-lookup"><span data-stu-id="eae0f-112">Description</span></span>  

 <span data-ttu-id="eae0f-113">ExecuteActivityWorkItem이 예약되어 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eae0f-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="eae0f-114">메시지</span><span class="sxs-lookup"><span data-stu-id="eae0f-114">Message</span></span>  

 <span data-ttu-id="eae0f-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem이 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eae0f-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="eae0f-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="eae0f-116">Details</span></span>  
  
|<span data-ttu-id="eae0f-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="eae0f-117">Data Item Name</span></span>|<span data-ttu-id="eae0f-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="eae0f-118">Data Item Type</span></span>|<span data-ttu-id="eae0f-119">Description</span><span class="sxs-lookup"><span data-stu-id="eae0f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="eae0f-120">활동</span><span class="sxs-lookup"><span data-stu-id="eae0f-120">Activity</span></span>|<span data-ttu-id="eae0f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="eae0f-121">xs:string</span></span>|<span data-ttu-id="eae0f-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eae0f-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="eae0f-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="eae0f-123">DisplayName</span></span>|<span data-ttu-id="eae0f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="eae0f-124">xs:string</span></span>|<span data-ttu-id="eae0f-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eae0f-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="eae0f-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="eae0f-126">InstanceId</span></span>|<span data-ttu-id="eae0f-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="eae0f-127">xs:string</span></span>|<span data-ttu-id="eae0f-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="eae0f-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="eae0f-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="eae0f-129">AppDomain</span></span>|<span data-ttu-id="eae0f-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="eae0f-130">xs:string</span></span>|<span data-ttu-id="eae0f-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="eae0f-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
