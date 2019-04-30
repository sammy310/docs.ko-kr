---
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 50b00a49ea73dcbe09e8f4c4195cbce8c1cbf615
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982269"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="fa126-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="fa126-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="fa126-103">속성</span><span class="sxs-lookup"><span data-stu-id="fa126-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fa126-104">ID</span><span class="sxs-lookup"><span data-stu-id="fa126-104">ID</span></span>|<span data-ttu-id="fa126-105">1014</span><span class="sxs-lookup"><span data-stu-id="fa126-105">1014</span></span>|  
|<span data-ttu-id="fa126-106">키워드</span><span class="sxs-lookup"><span data-stu-id="fa126-106">Keywords</span></span>|<span data-ttu-id="fa126-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fa126-107">WFRuntime</span></span>|  
|<span data-ttu-id="fa126-108">수준</span><span class="sxs-lookup"><span data-stu-id="fa126-108">Level</span></span>|<span data-ttu-id="fa126-109">자세히</span><span class="sxs-lookup"><span data-stu-id="fa126-109">Verbose</span></span>|  
|<span data-ttu-id="fa126-110">채널</span><span class="sxs-lookup"><span data-stu-id="fa126-110">Channel</span></span>|<span data-ttu-id="fa126-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="fa126-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fa126-112">설명</span><span class="sxs-lookup"><span data-stu-id="fa126-112">Description</span></span>  
 <span data-ttu-id="fa126-113">CompletionWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fa126-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fa126-114">메시지</span><span class="sxs-lookup"><span data-stu-id="fa126-114">Message</span></span>  
 <span data-ttu-id="fa126-115">CompletionWorkItem이 예약 된 부모 작업 '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="fa126-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="fa126-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fa126-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fa126-117">설명</span><span class="sxs-lookup"><span data-stu-id="fa126-117">Details</span></span>  
  
|<span data-ttu-id="fa126-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="fa126-118">Data Item Name</span></span>|<span data-ttu-id="fa126-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="fa126-119">Data Item Type</span></span>|<span data-ttu-id="fa126-120">설명</span><span class="sxs-lookup"><span data-stu-id="fa126-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fa126-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="fa126-121">ParentActivity</span></span>|<span data-ttu-id="fa126-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa126-122">xs:string</span></span>|<span data-ttu-id="fa126-123">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fa126-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="fa126-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="fa126-124">ParentDisplayName</span></span>|<span data-ttu-id="fa126-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa126-125">xs:string</span></span>|<span data-ttu-id="fa126-126">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fa126-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="fa126-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="fa126-127">ParentInstanceId</span></span>|<span data-ttu-id="fa126-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa126-128">xs:string</span></span>|<span data-ttu-id="fa126-129">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fa126-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="fa126-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="fa126-130">CompletedActivity</span></span>|<span data-ttu-id="fa126-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa126-131">xs:string</span></span>|<span data-ttu-id="fa126-132">완료된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fa126-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="fa126-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="fa126-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="fa126-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa126-134">xs:string</span></span>|<span data-ttu-id="fa126-135">완료된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fa126-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="fa126-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="fa126-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="fa126-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa126-137">xs:string</span></span>|<span data-ttu-id="fa126-138">완료된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fa126-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="fa126-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fa126-139">AppDomain</span></span>|<span data-ttu-id="fa126-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa126-140">xs:string</span></span>|<span data-ttu-id="fa126-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fa126-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
