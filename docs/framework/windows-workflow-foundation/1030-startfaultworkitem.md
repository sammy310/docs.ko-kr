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
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="3771a-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="3771a-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="3771a-103">속성</span><span class="sxs-lookup"><span data-stu-id="3771a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3771a-104">ID</span><span class="sxs-lookup"><span data-stu-id="3771a-104">ID</span></span>|<span data-ttu-id="3771a-105">1030</span><span class="sxs-lookup"><span data-stu-id="3771a-105">1030</span></span>|  
|<span data-ttu-id="3771a-106">키워드</span><span class="sxs-lookup"><span data-stu-id="3771a-106">Keywords</span></span>|<span data-ttu-id="3771a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3771a-107">WFRuntime</span></span>|  
|<span data-ttu-id="3771a-108">수준</span><span class="sxs-lookup"><span data-stu-id="3771a-108">Level</span></span>|<span data-ttu-id="3771a-109">자세히</span><span class="sxs-lookup"><span data-stu-id="3771a-109">Verbose</span></span>|  
|<span data-ttu-id="3771a-110">채널</span><span class="sxs-lookup"><span data-stu-id="3771a-110">Channel</span></span>|<span data-ttu-id="3771a-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="3771a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3771a-112">설명</span><span class="sxs-lookup"><span data-stu-id="3771a-112">Description</span></span>  
 <span data-ttu-id="3771a-113">FaultWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3771a-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3771a-114">메시지</span><span class="sxs-lookup"><span data-stu-id="3771a-114">Message</span></span>  
 <span data-ttu-id="3771a-115">작업 '%1', DisplayName에 대해 FaultWorkItem의 실행을 시작 합니다. '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="3771a-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="3771a-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3771a-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3771a-117">설명</span><span class="sxs-lookup"><span data-stu-id="3771a-117">Details</span></span>  
  
|<span data-ttu-id="3771a-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="3771a-118">Data Item Name</span></span>|<span data-ttu-id="3771a-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="3771a-119">Data Item Type</span></span>|<span data-ttu-id="3771a-120">설명</span><span class="sxs-lookup"><span data-stu-id="3771a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3771a-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="3771a-121">FaultActivity</span></span>|<span data-ttu-id="3771a-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="3771a-122">xs:string</span></span>|<span data-ttu-id="3771a-123">오류 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3771a-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="3771a-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="3771a-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="3771a-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="3771a-125">xs:string</span></span>|<span data-ttu-id="3771a-126">오류 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3771a-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="3771a-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="3771a-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="3771a-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="3771a-128">xs:string</span></span>|<span data-ttu-id="3771a-129">오류 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3771a-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="3771a-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="3771a-130">ExceptionActivity</span></span>|<span data-ttu-id="3771a-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="3771a-131">xs:string</span></span>|<span data-ttu-id="3771a-132">예외를 throw한 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3771a-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="3771a-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="3771a-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="3771a-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="3771a-134">xs:string</span></span>|<span data-ttu-id="3771a-135">예외를 throw한 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3771a-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="3771a-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="3771a-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="3771a-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="3771a-137">xs:string</span></span>|<span data-ttu-id="3771a-138">예외를 throw한 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3771a-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="3771a-139">예외</span><span class="sxs-lookup"><span data-stu-id="3771a-139">Exception</span></span>|<span data-ttu-id="3771a-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="3771a-140">xs:string</span></span>|<span data-ttu-id="3771a-141">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="3771a-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="3771a-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3771a-142">AppDomain</span></span>|<span data-ttu-id="3771a-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="3771a-143">xs:string</span></span>|<span data-ttu-id="3771a-144">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3771a-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
