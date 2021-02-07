---
description: '자세한 정보: 1031-CompleteFaultWorkItem'
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: dc5cb4988df2aab9710fd7ec875d9b4004bfa7af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668073"
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="c199b-103">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="c199b-103">1031 - CompleteFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="c199b-104">속성</span><span class="sxs-lookup"><span data-stu-id="c199b-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c199b-105">ID</span><span class="sxs-lookup"><span data-stu-id="c199b-105">ID</span></span>|<span data-ttu-id="c199b-106">1031</span><span class="sxs-lookup"><span data-stu-id="c199b-106">1031</span></span>|  
|<span data-ttu-id="c199b-107">키워드</span><span class="sxs-lookup"><span data-stu-id="c199b-107">Keywords</span></span>|<span data-ttu-id="c199b-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c199b-108">WFRuntime</span></span>|  
|<span data-ttu-id="c199b-109">Level</span><span class="sxs-lookup"><span data-stu-id="c199b-109">Level</span></span>|<span data-ttu-id="c199b-110">자세히</span><span class="sxs-lookup"><span data-stu-id="c199b-110">Verbose</span></span>|  
|<span data-ttu-id="c199b-111">채널</span><span class="sxs-lookup"><span data-stu-id="c199b-111">Channel</span></span>|<span data-ttu-id="c199b-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="c199b-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c199b-113">설명</span><span class="sxs-lookup"><span data-stu-id="c199b-113">Description</span></span>  

 <span data-ttu-id="c199b-114">FaultWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c199b-114">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c199b-115">메시지</span><span class="sxs-lookup"><span data-stu-id="c199b-115">Message</span></span>  

 <span data-ttu-id="c199b-116">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 FaultWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c199b-116">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="c199b-117">작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c199b-117">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c199b-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="c199b-118">Details</span></span>  
  
|<span data-ttu-id="c199b-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="c199b-119">Data Item Name</span></span>|<span data-ttu-id="c199b-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="c199b-120">Data Item Type</span></span>|<span data-ttu-id="c199b-121">설명</span><span class="sxs-lookup"><span data-stu-id="c199b-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c199b-122">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="c199b-122">FaultActivity</span></span>|<span data-ttu-id="c199b-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="c199b-123">xs:string</span></span>|<span data-ttu-id="c199b-124">오류 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c199b-124">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="c199b-125">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="c199b-125">FaultActivityDisplayName</span></span>|<span data-ttu-id="c199b-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="c199b-126">xs:string</span></span>|<span data-ttu-id="c199b-127">오류 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c199b-127">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="c199b-128">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="c199b-128">FaultActivityInstanceId</span></span>|<span data-ttu-id="c199b-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="c199b-129">xs:string</span></span>|<span data-ttu-id="c199b-130">오류 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c199b-130">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="c199b-131">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="c199b-131">ExceptionActivity</span></span>|<span data-ttu-id="c199b-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="c199b-132">xs:string</span></span>|<span data-ttu-id="c199b-133">예외를 throw한 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c199b-133">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="c199b-134">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="c199b-134">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="c199b-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="c199b-135">xs:string</span></span>|<span data-ttu-id="c199b-136">예외를 throw한 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c199b-136">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="c199b-137">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="c199b-137">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="c199b-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="c199b-138">xs:string</span></span>|<span data-ttu-id="c199b-139">예외를 throw한 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c199b-139">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="c199b-140">예외</span><span class="sxs-lookup"><span data-stu-id="c199b-140">Exception</span></span>|<span data-ttu-id="c199b-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="c199b-141">xs:string</span></span>|<span data-ttu-id="c199b-142">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="c199b-142">The exception details for the exception</span></span>|  
|<span data-ttu-id="c199b-143">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c199b-143">AppDomain</span></span>|<span data-ttu-id="c199b-144">xs:string</span><span class="sxs-lookup"><span data-stu-id="c199b-144">xs:string</span></span>|<span data-ttu-id="c199b-145">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c199b-145">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
