---
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: f5beab91f7dd39a3f8ed3b76d6c0a1ddd9bd77c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924360"
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="f0f9b-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="f0f9b-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="f0f9b-103">속성</span><span class="sxs-lookup"><span data-stu-id="f0f9b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0f9b-104">ID</span><span class="sxs-lookup"><span data-stu-id="f0f9b-104">ID</span></span>|<span data-ttu-id="f0f9b-105">1029</span><span class="sxs-lookup"><span data-stu-id="f0f9b-105">1029</span></span>|  
|<span data-ttu-id="f0f9b-106">키워드</span><span class="sxs-lookup"><span data-stu-id="f0f9b-106">Keywords</span></span>|<span data-ttu-id="f0f9b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f0f9b-107">WFRuntime</span></span>|  
|<span data-ttu-id="f0f9b-108">수준</span><span class="sxs-lookup"><span data-stu-id="f0f9b-108">Level</span></span>|<span data-ttu-id="f0f9b-109">자세히</span><span class="sxs-lookup"><span data-stu-id="f0f9b-109">Verbose</span></span>|  
|<span data-ttu-id="f0f9b-110">채널</span><span class="sxs-lookup"><span data-stu-id="f0f9b-110">Channel</span></span>|<span data-ttu-id="f0f9b-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="f0f9b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f0f9b-112">설명</span><span class="sxs-lookup"><span data-stu-id="f0f9b-112">Description</span></span>  
 <span data-ttu-id="f0f9b-113">FaultWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f0f9b-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f0f9b-114">메시지</span><span class="sxs-lookup"><span data-stu-id="f0f9b-114">Message</span></span>  
 <span data-ttu-id="f0f9b-115">FaultWorkItem이 예약 된 작업 '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="f0f9b-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="f0f9b-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f9b-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f0f9b-117">설명</span><span class="sxs-lookup"><span data-stu-id="f0f9b-117">Details</span></span>  
  
|<span data-ttu-id="f0f9b-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f0f9b-118">Data Item Name</span></span>|<span data-ttu-id="f0f9b-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f0f9b-119">Data Item Type</span></span>|<span data-ttu-id="f0f9b-120">설명</span><span class="sxs-lookup"><span data-stu-id="f0f9b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f0f9b-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="f0f9b-121">FaultActivity</span></span>|<span data-ttu-id="f0f9b-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f0f9b-122">xs:string</span></span>|<span data-ttu-id="f0f9b-123">오류 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f0f9b-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="f0f9b-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="f0f9b-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="f0f9b-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f0f9b-125">xs:string</span></span>|<span data-ttu-id="f0f9b-126">오류 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f0f9b-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="f0f9b-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="f0f9b-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="f0f9b-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f0f9b-128">xs:string</span></span>|<span data-ttu-id="f0f9b-129">오류 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f0f9b-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="f0f9b-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="f0f9b-130">ExceptionActivity</span></span>|<span data-ttu-id="f0f9b-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="f0f9b-131">xs:string</span></span>|<span data-ttu-id="f0f9b-132">예외를 throw한 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f0f9b-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="f0f9b-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="f0f9b-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="f0f9b-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="f0f9b-134">xs:string</span></span>|<span data-ttu-id="f0f9b-135">예외를 throw한 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f0f9b-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="f0f9b-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="f0f9b-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="f0f9b-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="f0f9b-137">xs:string</span></span>|<span data-ttu-id="f0f9b-138">예외를 throw한 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f0f9b-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="f0f9b-139">예외</span><span class="sxs-lookup"><span data-stu-id="f0f9b-139">Exception</span></span>|<span data-ttu-id="f0f9b-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="f0f9b-140">xs:string</span></span>|<span data-ttu-id="f0f9b-141">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="f0f9b-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="f0f9b-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f0f9b-142">AppDomain</span></span>|<span data-ttu-id="f0f9b-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="f0f9b-143">xs:string</span></span>|<span data-ttu-id="f0f9b-144">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f0f9b-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
