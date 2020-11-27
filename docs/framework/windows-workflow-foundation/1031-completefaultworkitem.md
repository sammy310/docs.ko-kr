---
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: 557155fab35a37bdbaa45efb26d6bc025ad825c4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281835"
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="ddadf-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="ddadf-102">1031 - CompleteFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="ddadf-103">속성</span><span class="sxs-lookup"><span data-stu-id="ddadf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ddadf-104">ID</span><span class="sxs-lookup"><span data-stu-id="ddadf-104">ID</span></span>|<span data-ttu-id="ddadf-105">1031</span><span class="sxs-lookup"><span data-stu-id="ddadf-105">1031</span></span>|  
|<span data-ttu-id="ddadf-106">키워드</span><span class="sxs-lookup"><span data-stu-id="ddadf-106">Keywords</span></span>|<span data-ttu-id="ddadf-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ddadf-107">WFRuntime</span></span>|  
|<span data-ttu-id="ddadf-108">Level</span><span class="sxs-lookup"><span data-stu-id="ddadf-108">Level</span></span>|<span data-ttu-id="ddadf-109">자세히</span><span class="sxs-lookup"><span data-stu-id="ddadf-109">Verbose</span></span>|  
|<span data-ttu-id="ddadf-110">채널</span><span class="sxs-lookup"><span data-stu-id="ddadf-110">Channel</span></span>|<span data-ttu-id="ddadf-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="ddadf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ddadf-112">Description</span><span class="sxs-lookup"><span data-stu-id="ddadf-112">Description</span></span>  

 <span data-ttu-id="ddadf-113">FaultWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ddadf-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ddadf-114">메시지</span><span class="sxs-lookup"><span data-stu-id="ddadf-114">Message</span></span>  

 <span data-ttu-id="ddadf-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 FaultWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ddadf-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="ddadf-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ddadf-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ddadf-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="ddadf-117">Details</span></span>  
  
|<span data-ttu-id="ddadf-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="ddadf-118">Data Item Name</span></span>|<span data-ttu-id="ddadf-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="ddadf-119">Data Item Type</span></span>|<span data-ttu-id="ddadf-120">Description</span><span class="sxs-lookup"><span data-stu-id="ddadf-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ddadf-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="ddadf-121">FaultActivity</span></span>|<span data-ttu-id="ddadf-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="ddadf-122">xs:string</span></span>|<span data-ttu-id="ddadf-123">오류 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ddadf-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="ddadf-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ddadf-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="ddadf-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="ddadf-125">xs:string</span></span>|<span data-ttu-id="ddadf-126">오류 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ddadf-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="ddadf-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ddadf-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="ddadf-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="ddadf-128">xs:string</span></span>|<span data-ttu-id="ddadf-129">오류 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ddadf-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="ddadf-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="ddadf-130">ExceptionActivity</span></span>|<span data-ttu-id="ddadf-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="ddadf-131">xs:string</span></span>|<span data-ttu-id="ddadf-132">예외를 throw한 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ddadf-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ddadf-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ddadf-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="ddadf-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="ddadf-134">xs:string</span></span>|<span data-ttu-id="ddadf-135">예외를 throw한 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ddadf-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ddadf-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ddadf-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="ddadf-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="ddadf-137">xs:string</span></span>|<span data-ttu-id="ddadf-138">예외를 throw한 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ddadf-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ddadf-139">예외</span><span class="sxs-lookup"><span data-stu-id="ddadf-139">Exception</span></span>|<span data-ttu-id="ddadf-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="ddadf-140">xs:string</span></span>|<span data-ttu-id="ddadf-141">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="ddadf-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="ddadf-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ddadf-142">AppDomain</span></span>|<span data-ttu-id="ddadf-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="ddadf-143">xs:string</span></span>|<span data-ttu-id="ddadf-144">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ddadf-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
