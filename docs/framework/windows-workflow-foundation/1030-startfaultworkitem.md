---
description: '자세한 정보: 1030-StartFaultWorkItem'
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 2d148277b2d593cfcf75e17662626f1f486e7c1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668099"
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="7d8e9-103">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="7d8e9-103">1030 - StartFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="7d8e9-104">속성</span><span class="sxs-lookup"><span data-stu-id="7d8e9-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7d8e9-105">ID</span><span class="sxs-lookup"><span data-stu-id="7d8e9-105">ID</span></span>|<span data-ttu-id="7d8e9-106">1030</span><span class="sxs-lookup"><span data-stu-id="7d8e9-106">1030</span></span>|  
|<span data-ttu-id="7d8e9-107">키워드</span><span class="sxs-lookup"><span data-stu-id="7d8e9-107">Keywords</span></span>|<span data-ttu-id="7d8e9-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7d8e9-108">WFRuntime</span></span>|  
|<span data-ttu-id="7d8e9-109">Level</span><span class="sxs-lookup"><span data-stu-id="7d8e9-109">Level</span></span>|<span data-ttu-id="7d8e9-110">자세히</span><span class="sxs-lookup"><span data-stu-id="7d8e9-110">Verbose</span></span>|  
|<span data-ttu-id="7d8e9-111">채널</span><span class="sxs-lookup"><span data-stu-id="7d8e9-111">Channel</span></span>|<span data-ttu-id="7d8e9-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="7d8e9-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7d8e9-113">설명</span><span class="sxs-lookup"><span data-stu-id="7d8e9-113">Description</span></span>  

 <span data-ttu-id="7d8e9-114">FaultWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e9-114">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7d8e9-115">메시지</span><span class="sxs-lookup"><span data-stu-id="7d8e9-115">Message</span></span>  

 <span data-ttu-id="7d8e9-116">작업 ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '에 대해 FaultWorkItem의 실행을 시작 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e9-116">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="7d8e9-117">작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e9-117">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7d8e9-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="7d8e9-118">Details</span></span>  
  
|<span data-ttu-id="7d8e9-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="7d8e9-119">Data Item Name</span></span>|<span data-ttu-id="7d8e9-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="7d8e9-120">Data Item Type</span></span>|<span data-ttu-id="7d8e9-121">설명</span><span class="sxs-lookup"><span data-stu-id="7d8e9-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7d8e9-122">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="7d8e9-122">FaultActivity</span></span>|<span data-ttu-id="7d8e9-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="7d8e9-123">xs:string</span></span>|<span data-ttu-id="7d8e9-124">오류 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e9-124">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="7d8e9-125">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="7d8e9-125">FaultActivityDisplayName</span></span>|<span data-ttu-id="7d8e9-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="7d8e9-126">xs:string</span></span>|<span data-ttu-id="7d8e9-127">오류 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e9-127">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="7d8e9-128">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="7d8e9-128">FaultActivityInstanceId</span></span>|<span data-ttu-id="7d8e9-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="7d8e9-129">xs:string</span></span>|<span data-ttu-id="7d8e9-130">오류 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e9-130">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="7d8e9-131">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="7d8e9-131">ExceptionActivity</span></span>|<span data-ttu-id="7d8e9-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="7d8e9-132">xs:string</span></span>|<span data-ttu-id="7d8e9-133">예외를 throw한 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e9-133">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="7d8e9-134">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="7d8e9-134">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="7d8e9-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="7d8e9-135">xs:string</span></span>|<span data-ttu-id="7d8e9-136">예외를 throw한 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e9-136">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="7d8e9-137">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="7d8e9-137">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="7d8e9-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="7d8e9-138">xs:string</span></span>|<span data-ttu-id="7d8e9-139">예외를 throw한 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e9-139">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="7d8e9-140">예외</span><span class="sxs-lookup"><span data-stu-id="7d8e9-140">Exception</span></span>|<span data-ttu-id="7d8e9-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="7d8e9-141">xs:string</span></span>|<span data-ttu-id="7d8e9-142">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="7d8e9-142">The exception details for the exception</span></span>|  
|<span data-ttu-id="7d8e9-143">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7d8e9-143">AppDomain</span></span>|<span data-ttu-id="7d8e9-144">xs:string</span><span class="sxs-lookup"><span data-stu-id="7d8e9-144">xs:string</span></span>|<span data-ttu-id="7d8e9-145">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e9-145">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
