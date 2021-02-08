---
description: '자세한 정보: 1018-StartCancelActivityWorkItem'
title: 1018 - StartCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
ms.openlocfilehash: 99da17bd2fb75d9ed3a41e95ec1929df66964ffd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792884"
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="2da5e-103">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="2da5e-103">1018 - StartCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="2da5e-104">속성</span><span class="sxs-lookup"><span data-stu-id="2da5e-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2da5e-105">ID</span><span class="sxs-lookup"><span data-stu-id="2da5e-105">ID</span></span>|<span data-ttu-id="2da5e-106">1018</span><span class="sxs-lookup"><span data-stu-id="2da5e-106">1018</span></span>|  
|<span data-ttu-id="2da5e-107">키워드</span><span class="sxs-lookup"><span data-stu-id="2da5e-107">Keywords</span></span>|<span data-ttu-id="2da5e-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2da5e-108">WFRuntime</span></span>|  
|<span data-ttu-id="2da5e-109">Level</span><span class="sxs-lookup"><span data-stu-id="2da5e-109">Level</span></span>|<span data-ttu-id="2da5e-110">자세히</span><span class="sxs-lookup"><span data-stu-id="2da5e-110">Verbose</span></span>|  
|<span data-ttu-id="2da5e-111">채널</span><span class="sxs-lookup"><span data-stu-id="2da5e-111">Channel</span></span>|<span data-ttu-id="2da5e-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="2da5e-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2da5e-113">설명</span><span class="sxs-lookup"><span data-stu-id="2da5e-113">Description</span></span>  

 <span data-ttu-id="2da5e-114">CancelActivityWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-114">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2da5e-115">메시지</span><span class="sxs-lookup"><span data-stu-id="2da5e-115">Message</span></span>  

 <span data-ttu-id="2da5e-116">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CancelActivityWorkItem의 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-116">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2da5e-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="2da5e-117">Details</span></span>  
  
|<span data-ttu-id="2da5e-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="2da5e-118">Data Item Name</span></span>|<span data-ttu-id="2da5e-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="2da5e-119">Data Item Type</span></span>|<span data-ttu-id="2da5e-120">설명</span><span class="sxs-lookup"><span data-stu-id="2da5e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2da5e-121">활동</span><span class="sxs-lookup"><span data-stu-id="2da5e-121">Activity</span></span>|<span data-ttu-id="2da5e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="2da5e-122">xs:string</span></span>|<span data-ttu-id="2da5e-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="2da5e-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2da5e-124">DisplayName</span></span>|<span data-ttu-id="2da5e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="2da5e-125">xs:string</span></span>|<span data-ttu-id="2da5e-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="2da5e-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="2da5e-127">InstanceId</span></span>|<span data-ttu-id="2da5e-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="2da5e-128">xs:string</span></span>|<span data-ttu-id="2da5e-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="2da5e-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2da5e-130">AppDomain</span></span>|<span data-ttu-id="2da5e-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="2da5e-131">xs:string</span></span>|<span data-ttu-id="2da5e-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
