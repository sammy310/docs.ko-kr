---
title: 1032 - ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: da35201f2b3e3bc07e0b9139b0584ce37011e168
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294315"
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="629a3-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="629a3-102">1032 - ScheduleRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="629a3-103">속성</span><span class="sxs-lookup"><span data-stu-id="629a3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="629a3-104">ID</span><span class="sxs-lookup"><span data-stu-id="629a3-104">ID</span></span>|<span data-ttu-id="629a3-105">1032</span><span class="sxs-lookup"><span data-stu-id="629a3-105">1032</span></span>|  
|<span data-ttu-id="629a3-106">키워드</span><span class="sxs-lookup"><span data-stu-id="629a3-106">Keywords</span></span>|<span data-ttu-id="629a3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="629a3-107">WFRuntime</span></span>|  
|<span data-ttu-id="629a3-108">Level</span><span class="sxs-lookup"><span data-stu-id="629a3-108">Level</span></span>|<span data-ttu-id="629a3-109">자세히</span><span class="sxs-lookup"><span data-stu-id="629a3-109">Verbose</span></span>|  
|<span data-ttu-id="629a3-110">채널</span><span class="sxs-lookup"><span data-stu-id="629a3-110">Channel</span></span>|<span data-ttu-id="629a3-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="629a3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="629a3-112">Description</span><span class="sxs-lookup"><span data-stu-id="629a3-112">Description</span></span>  

 <span data-ttu-id="629a3-113">RuntimeWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="629a3-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="629a3-114">메시지</span><span class="sxs-lookup"><span data-stu-id="629a3-114">Message</span></span>  

 <span data-ttu-id="629a3-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목이 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="629a3-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="629a3-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="629a3-116">Details</span></span>  
  
|<span data-ttu-id="629a3-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="629a3-117">Data Item Name</span></span>|<span data-ttu-id="629a3-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="629a3-118">Data Item Type</span></span>|<span data-ttu-id="629a3-119">Description</span><span class="sxs-lookup"><span data-stu-id="629a3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="629a3-120">활동</span><span class="sxs-lookup"><span data-stu-id="629a3-120">Activity</span></span>|<span data-ttu-id="629a3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="629a3-121">xs:string</span></span>|<span data-ttu-id="629a3-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="629a3-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="629a3-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="629a3-123">DisplayName</span></span>|<span data-ttu-id="629a3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="629a3-124">xs:string</span></span>|<span data-ttu-id="629a3-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="629a3-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="629a3-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="629a3-126">InstanceId</span></span>|<span data-ttu-id="629a3-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="629a3-127">xs:string</span></span>|<span data-ttu-id="629a3-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="629a3-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="629a3-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="629a3-129">AppDomain</span></span>|<span data-ttu-id="629a3-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="629a3-130">xs:string</span></span>|<span data-ttu-id="629a3-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="629a3-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
