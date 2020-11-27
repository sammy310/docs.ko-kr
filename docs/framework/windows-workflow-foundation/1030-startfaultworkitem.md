---
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 52034f7cc7c6f6749fbbbf06db9267ecb6279ee1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281861"
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="19a60-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="19a60-102">1030 - StartFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="19a60-103">속성</span><span class="sxs-lookup"><span data-stu-id="19a60-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="19a60-104">ID</span><span class="sxs-lookup"><span data-stu-id="19a60-104">ID</span></span>|<span data-ttu-id="19a60-105">1030</span><span class="sxs-lookup"><span data-stu-id="19a60-105">1030</span></span>|  
|<span data-ttu-id="19a60-106">키워드</span><span class="sxs-lookup"><span data-stu-id="19a60-106">Keywords</span></span>|<span data-ttu-id="19a60-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="19a60-107">WFRuntime</span></span>|  
|<span data-ttu-id="19a60-108">Level</span><span class="sxs-lookup"><span data-stu-id="19a60-108">Level</span></span>|<span data-ttu-id="19a60-109">자세히</span><span class="sxs-lookup"><span data-stu-id="19a60-109">Verbose</span></span>|  
|<span data-ttu-id="19a60-110">채널</span><span class="sxs-lookup"><span data-stu-id="19a60-110">Channel</span></span>|<span data-ttu-id="19a60-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="19a60-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="19a60-112">Description</span><span class="sxs-lookup"><span data-stu-id="19a60-112">Description</span></span>  

 <span data-ttu-id="19a60-113">FaultWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="19a60-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="19a60-114">메시지</span><span class="sxs-lookup"><span data-stu-id="19a60-114">Message</span></span>  

 <span data-ttu-id="19a60-115">작업 ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '에 대해 FaultWorkItem의 실행을 시작 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="19a60-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="19a60-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.</span><span class="sxs-lookup"><span data-stu-id="19a60-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="19a60-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="19a60-117">Details</span></span>  
  
|<span data-ttu-id="19a60-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="19a60-118">Data Item Name</span></span>|<span data-ttu-id="19a60-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="19a60-119">Data Item Type</span></span>|<span data-ttu-id="19a60-120">Description</span><span class="sxs-lookup"><span data-stu-id="19a60-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="19a60-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="19a60-121">FaultActivity</span></span>|<span data-ttu-id="19a60-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="19a60-122">xs:string</span></span>|<span data-ttu-id="19a60-123">오류 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="19a60-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="19a60-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="19a60-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="19a60-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="19a60-125">xs:string</span></span>|<span data-ttu-id="19a60-126">오류 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="19a60-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="19a60-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="19a60-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="19a60-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="19a60-128">xs:string</span></span>|<span data-ttu-id="19a60-129">오류 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="19a60-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="19a60-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="19a60-130">ExceptionActivity</span></span>|<span data-ttu-id="19a60-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="19a60-131">xs:string</span></span>|<span data-ttu-id="19a60-132">예외를 throw한 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="19a60-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="19a60-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="19a60-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="19a60-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="19a60-134">xs:string</span></span>|<span data-ttu-id="19a60-135">예외를 throw한 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="19a60-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="19a60-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="19a60-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="19a60-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="19a60-137">xs:string</span></span>|<span data-ttu-id="19a60-138">예외를 throw한 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="19a60-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="19a60-139">예외</span><span class="sxs-lookup"><span data-stu-id="19a60-139">Exception</span></span>|<span data-ttu-id="19a60-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="19a60-140">xs:string</span></span>|<span data-ttu-id="19a60-141">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="19a60-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="19a60-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="19a60-142">AppDomain</span></span>|<span data-ttu-id="19a60-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="19a60-143">xs:string</span></span>|<span data-ttu-id="19a60-144">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="19a60-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
