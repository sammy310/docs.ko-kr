---
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 3848d644e77041a62a52eb2eae5eeef286dfe334
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924321"
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="c623d-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="c623d-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="c623d-103">속성</span><span class="sxs-lookup"><span data-stu-id="c623d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c623d-104">ID</span><span class="sxs-lookup"><span data-stu-id="c623d-104">ID</span></span>|<span data-ttu-id="c623d-105">1030</span><span class="sxs-lookup"><span data-stu-id="c623d-105">1030</span></span>|  
|<span data-ttu-id="c623d-106">키워드</span><span class="sxs-lookup"><span data-stu-id="c623d-106">Keywords</span></span>|<span data-ttu-id="c623d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c623d-107">WFRuntime</span></span>|  
|<span data-ttu-id="c623d-108">수준</span><span class="sxs-lookup"><span data-stu-id="c623d-108">Level</span></span>|<span data-ttu-id="c623d-109">자세히</span><span class="sxs-lookup"><span data-stu-id="c623d-109">Verbose</span></span>|  
|<span data-ttu-id="c623d-110">채널</span><span class="sxs-lookup"><span data-stu-id="c623d-110">Channel</span></span>|<span data-ttu-id="c623d-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="c623d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c623d-112">설명</span><span class="sxs-lookup"><span data-stu-id="c623d-112">Description</span></span>  
 <span data-ttu-id="c623d-113">FaultWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c623d-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c623d-114">메시지</span><span class="sxs-lookup"><span data-stu-id="c623d-114">Message</span></span>  
 <span data-ttu-id="c623d-115">작업 '%1', DisplayName에 대해 FaultWorkItem의 실행을 시작 합니다. '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="c623d-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="c623d-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c623d-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c623d-117">설명</span><span class="sxs-lookup"><span data-stu-id="c623d-117">Details</span></span>  
  
|<span data-ttu-id="c623d-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="c623d-118">Data Item Name</span></span>|<span data-ttu-id="c623d-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="c623d-119">Data Item Type</span></span>|<span data-ttu-id="c623d-120">설명</span><span class="sxs-lookup"><span data-stu-id="c623d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c623d-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="c623d-121">FaultActivity</span></span>|<span data-ttu-id="c623d-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="c623d-122">xs:string</span></span>|<span data-ttu-id="c623d-123">오류 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c623d-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="c623d-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="c623d-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="c623d-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="c623d-125">xs:string</span></span>|<span data-ttu-id="c623d-126">오류 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c623d-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="c623d-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="c623d-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="c623d-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="c623d-128">xs:string</span></span>|<span data-ttu-id="c623d-129">오류 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c623d-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="c623d-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="c623d-130">ExceptionActivity</span></span>|<span data-ttu-id="c623d-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="c623d-131">xs:string</span></span>|<span data-ttu-id="c623d-132">예외를 throw한 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c623d-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="c623d-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="c623d-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="c623d-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="c623d-134">xs:string</span></span>|<span data-ttu-id="c623d-135">예외를 throw한 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c623d-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="c623d-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="c623d-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="c623d-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="c623d-137">xs:string</span></span>|<span data-ttu-id="c623d-138">예외를 throw한 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c623d-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="c623d-139">예외</span><span class="sxs-lookup"><span data-stu-id="c623d-139">Exception</span></span>|<span data-ttu-id="c623d-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="c623d-140">xs:string</span></span>|<span data-ttu-id="c623d-141">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="c623d-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="c623d-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c623d-142">AppDomain</span></span>|<span data-ttu-id="c623d-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="c623d-143">xs:string</span></span>|<span data-ttu-id="c623d-144">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c623d-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
