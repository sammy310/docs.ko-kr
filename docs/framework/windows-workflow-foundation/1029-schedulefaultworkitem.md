---
description: '자세한 정보: 1029-ScheduleFaultWorkItem'
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: e5f0463626882d6c8c48412326582fafa7be4670
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755449"
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="904fd-103">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="904fd-103">1029 - ScheduleFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="904fd-104">속성</span><span class="sxs-lookup"><span data-stu-id="904fd-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="904fd-105">ID</span><span class="sxs-lookup"><span data-stu-id="904fd-105">ID</span></span>|<span data-ttu-id="904fd-106">1029</span><span class="sxs-lookup"><span data-stu-id="904fd-106">1029</span></span>|  
|<span data-ttu-id="904fd-107">키워드</span><span class="sxs-lookup"><span data-stu-id="904fd-107">Keywords</span></span>|<span data-ttu-id="904fd-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="904fd-108">WFRuntime</span></span>|  
|<span data-ttu-id="904fd-109">Level</span><span class="sxs-lookup"><span data-stu-id="904fd-109">Level</span></span>|<span data-ttu-id="904fd-110">자세히</span><span class="sxs-lookup"><span data-stu-id="904fd-110">Verbose</span></span>|  
|<span data-ttu-id="904fd-111">채널</span><span class="sxs-lookup"><span data-stu-id="904fd-111">Channel</span></span>|<span data-ttu-id="904fd-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="904fd-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="904fd-113">설명</span><span class="sxs-lookup"><span data-stu-id="904fd-113">Description</span></span>  

 <span data-ttu-id="904fd-114">FaultWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904fd-114">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="904fd-115">메시지</span><span class="sxs-lookup"><span data-stu-id="904fd-115">Message</span></span>  

 <span data-ttu-id="904fd-116">작업 ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '에 대해 FaultWorkItem이 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="904fd-116">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="904fd-117">작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.</span><span class="sxs-lookup"><span data-stu-id="904fd-117">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="904fd-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="904fd-118">Details</span></span>  
  
|<span data-ttu-id="904fd-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="904fd-119">Data Item Name</span></span>|<span data-ttu-id="904fd-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="904fd-120">Data Item Type</span></span>|<span data-ttu-id="904fd-121">설명</span><span class="sxs-lookup"><span data-stu-id="904fd-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="904fd-122">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="904fd-122">FaultActivity</span></span>|<span data-ttu-id="904fd-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="904fd-123">xs:string</span></span>|<span data-ttu-id="904fd-124">오류 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="904fd-124">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="904fd-125">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="904fd-125">FaultActivityDisplayName</span></span>|<span data-ttu-id="904fd-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="904fd-126">xs:string</span></span>|<span data-ttu-id="904fd-127">오류 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="904fd-127">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="904fd-128">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="904fd-128">FaultActivityInstanceId</span></span>|<span data-ttu-id="904fd-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="904fd-129">xs:string</span></span>|<span data-ttu-id="904fd-130">오류 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="904fd-130">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="904fd-131">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="904fd-131">ExceptionActivity</span></span>|<span data-ttu-id="904fd-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="904fd-132">xs:string</span></span>|<span data-ttu-id="904fd-133">예외를 throw한 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="904fd-133">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="904fd-134">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="904fd-134">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="904fd-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="904fd-135">xs:string</span></span>|<span data-ttu-id="904fd-136">예외를 throw한 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="904fd-136">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="904fd-137">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="904fd-137">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="904fd-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="904fd-138">xs:string</span></span>|<span data-ttu-id="904fd-139">예외를 throw한 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="904fd-139">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="904fd-140">예외</span><span class="sxs-lookup"><span data-stu-id="904fd-140">Exception</span></span>|<span data-ttu-id="904fd-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="904fd-141">xs:string</span></span>|<span data-ttu-id="904fd-142">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="904fd-142">The exception details for the exception</span></span>|  
|<span data-ttu-id="904fd-143">AppDomain</span><span class="sxs-lookup"><span data-stu-id="904fd-143">AppDomain</span></span>|<span data-ttu-id="904fd-144">xs:string</span><span class="sxs-lookup"><span data-stu-id="904fd-144">xs:string</span></span>|<span data-ttu-id="904fd-145">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="904fd-145">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
