---
title: 1034 - CompleteRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
ms.openlocfilehash: 837adc9e143060284f2373a049bc9ad9c8cee336
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294289"
---
# <a name="1034---completeruntimeworkitem"></a><span data-ttu-id="22ce1-102">1034 - CompleteRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="22ce1-102">1034 - CompleteRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="22ce1-103">속성</span><span class="sxs-lookup"><span data-stu-id="22ce1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="22ce1-104">ID</span><span class="sxs-lookup"><span data-stu-id="22ce1-104">ID</span></span>|<span data-ttu-id="22ce1-105">1034</span><span class="sxs-lookup"><span data-stu-id="22ce1-105">1034</span></span>|  
|<span data-ttu-id="22ce1-106">키워드</span><span class="sxs-lookup"><span data-stu-id="22ce1-106">Keywords</span></span>|<span data-ttu-id="22ce1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="22ce1-107">WFRuntime</span></span>|  
|<span data-ttu-id="22ce1-108">Level</span><span class="sxs-lookup"><span data-stu-id="22ce1-108">Level</span></span>|<span data-ttu-id="22ce1-109">자세히</span><span class="sxs-lookup"><span data-stu-id="22ce1-109">Verbose</span></span>|  
|<span data-ttu-id="22ce1-110">채널</span><span class="sxs-lookup"><span data-stu-id="22ce1-110">Channel</span></span>|<span data-ttu-id="22ce1-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="22ce1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="22ce1-112">Description</span><span class="sxs-lookup"><span data-stu-id="22ce1-112">Description</span></span>  

 <span data-ttu-id="22ce1-113">RuntimeWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="22ce1-113">Indicates a RuntimeWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="22ce1-114">메시지</span><span class="sxs-lookup"><span data-stu-id="22ce1-114">Message</span></span>  

 <span data-ttu-id="22ce1-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="22ce1-115">A runtime work item has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="22ce1-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="22ce1-116">Details</span></span>  
  
|<span data-ttu-id="22ce1-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="22ce1-117">Data Item Name</span></span>|<span data-ttu-id="22ce1-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="22ce1-118">Data Item Type</span></span>|<span data-ttu-id="22ce1-119">Description</span><span class="sxs-lookup"><span data-stu-id="22ce1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="22ce1-120">활동</span><span class="sxs-lookup"><span data-stu-id="22ce1-120">Activity</span></span>|<span data-ttu-id="22ce1-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="22ce1-121">xs:string</span></span>|<span data-ttu-id="22ce1-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="22ce1-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="22ce1-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="22ce1-123">DisplayName</span></span>|<span data-ttu-id="22ce1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="22ce1-124">xs:string</span></span>|<span data-ttu-id="22ce1-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="22ce1-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="22ce1-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="22ce1-126">InstanceId</span></span>|<span data-ttu-id="22ce1-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="22ce1-127">xs:string</span></span>|<span data-ttu-id="22ce1-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="22ce1-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="22ce1-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="22ce1-129">AppDomain</span></span>|<span data-ttu-id="22ce1-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="22ce1-130">xs:string</span></span>|<span data-ttu-id="22ce1-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="22ce1-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
