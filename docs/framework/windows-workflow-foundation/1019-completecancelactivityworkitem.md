---
description: '자세한 정보: 1019-CompleteCancelActivityWorkItem'
title: 1019 - CompleteCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
ms.openlocfilehash: 33e58931562d7244987dd8c0d9cf5d34fb894190
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792871"
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="cfa82-103">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="cfa82-103">1019 - CompleteCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="cfa82-104">속성</span><span class="sxs-lookup"><span data-stu-id="cfa82-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cfa82-105">ID</span><span class="sxs-lookup"><span data-stu-id="cfa82-105">ID</span></span>|<span data-ttu-id="cfa82-106">1019</span><span class="sxs-lookup"><span data-stu-id="cfa82-106">1019</span></span>|  
|<span data-ttu-id="cfa82-107">키워드</span><span class="sxs-lookup"><span data-stu-id="cfa82-107">Keywords</span></span>|<span data-ttu-id="cfa82-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="cfa82-108">WFRuntime</span></span>|  
|<span data-ttu-id="cfa82-109">Level</span><span class="sxs-lookup"><span data-stu-id="cfa82-109">Level</span></span>|<span data-ttu-id="cfa82-110">자세히</span><span class="sxs-lookup"><span data-stu-id="cfa82-110">Verbose</span></span>|  
|<span data-ttu-id="cfa82-111">채널</span><span class="sxs-lookup"><span data-stu-id="cfa82-111">Channel</span></span>|<span data-ttu-id="cfa82-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="cfa82-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cfa82-113">설명</span><span class="sxs-lookup"><span data-stu-id="cfa82-113">Description</span></span>  

 <span data-ttu-id="cfa82-114">CancelActivityWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cfa82-114">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cfa82-115">메시지</span><span class="sxs-lookup"><span data-stu-id="cfa82-115">Message</span></span>  

 <span data-ttu-id="cfa82-116">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CancelActivityWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cfa82-116">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cfa82-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="cfa82-117">Details</span></span>  
  
|<span data-ttu-id="cfa82-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="cfa82-118">Data Item Name</span></span>|<span data-ttu-id="cfa82-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="cfa82-119">Data Item Type</span></span>|<span data-ttu-id="cfa82-120">설명</span><span class="sxs-lookup"><span data-stu-id="cfa82-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cfa82-121">활동</span><span class="sxs-lookup"><span data-stu-id="cfa82-121">Activity</span></span>|<span data-ttu-id="cfa82-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="cfa82-122">xs:string</span></span>|<span data-ttu-id="cfa82-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cfa82-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="cfa82-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="cfa82-124">DisplayName</span></span>|<span data-ttu-id="cfa82-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="cfa82-125">xs:string</span></span>|<span data-ttu-id="cfa82-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cfa82-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="cfa82-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="cfa82-127">InstanceId</span></span>|<span data-ttu-id="cfa82-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="cfa82-128">xs:string</span></span>|<span data-ttu-id="cfa82-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="cfa82-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="cfa82-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cfa82-130">AppDomain</span></span>|<span data-ttu-id="cfa82-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="cfa82-131">xs:string</span></span>|<span data-ttu-id="cfa82-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="cfa82-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
