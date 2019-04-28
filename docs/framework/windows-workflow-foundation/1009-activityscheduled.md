---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 0e3ea53a7b0509fcb8b73b61193742d615ac7e91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924659"
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="8488b-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="8488b-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="8488b-103">속성</span><span class="sxs-lookup"><span data-stu-id="8488b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8488b-104">ID</span><span class="sxs-lookup"><span data-stu-id="8488b-104">ID</span></span>|<span data-ttu-id="8488b-105">1009</span><span class="sxs-lookup"><span data-stu-id="8488b-105">1009</span></span>|  
|<span data-ttu-id="8488b-106">키워드</span><span class="sxs-lookup"><span data-stu-id="8488b-106">Keywords</span></span>|<span data-ttu-id="8488b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8488b-107">WFRuntime</span></span>|  
|<span data-ttu-id="8488b-108">수준</span><span class="sxs-lookup"><span data-stu-id="8488b-108">Level</span></span>|<span data-ttu-id="8488b-109">정보</span><span class="sxs-lookup"><span data-stu-id="8488b-109">Information</span></span>|  
|<span data-ttu-id="8488b-110">채널</span><span class="sxs-lookup"><span data-stu-id="8488b-110">Channel</span></span>|<span data-ttu-id="8488b-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="8488b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8488b-112">설명</span><span class="sxs-lookup"><span data-stu-id="8488b-112">Description</span></span>  
 <span data-ttu-id="8488b-113">실행 예약되는 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8488b-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8488b-114">메시지</span><span class="sxs-lookup"><span data-stu-id="8488b-114">Message</span></span>  
 <span data-ttu-id="8488b-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="8488b-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8488b-116">설명</span><span class="sxs-lookup"><span data-stu-id="8488b-116">Details</span></span>  
  
|<span data-ttu-id="8488b-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="8488b-117">Data Item Name</span></span>|<span data-ttu-id="8488b-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="8488b-118">Data Item Type</span></span>|<span data-ttu-id="8488b-119">설명</span><span class="sxs-lookup"><span data-stu-id="8488b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8488b-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="8488b-120">ParentActivity</span></span>|<span data-ttu-id="8488b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8488b-121">xs:string</span></span>|<span data-ttu-id="8488b-122">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8488b-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="8488b-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="8488b-123">ParentDisplayName</span></span>|<span data-ttu-id="8488b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8488b-124">xs:string</span></span>|<span data-ttu-id="8488b-125">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8488b-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="8488b-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="8488b-126">ParentInstanceId</span></span>|<span data-ttu-id="8488b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8488b-127">xs:string</span></span>|<span data-ttu-id="8488b-128">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8488b-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="8488b-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="8488b-129">ChildActivity</span></span>|<span data-ttu-id="8488b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8488b-130">xs:string</span></span>|<span data-ttu-id="8488b-131">예약된 자식 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8488b-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="8488b-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="8488b-132">ChildDisplayName</span></span>|<span data-ttu-id="8488b-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="8488b-133">xs:string</span></span>|<span data-ttu-id="8488b-134">예약된 자식 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8488b-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="8488b-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="8488b-135">ChildInstanceId</span></span>|<span data-ttu-id="8488b-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="8488b-136">xs:string</span></span>|<span data-ttu-id="8488b-137">예약된 자식 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8488b-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="8488b-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8488b-138">AppDomain</span></span>|<span data-ttu-id="8488b-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="8488b-139">xs:string</span></span>|<span data-ttu-id="8488b-140">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8488b-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
