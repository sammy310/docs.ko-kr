---
description: '자세한 정보: 1017-ScheduleCancelActivityWorkItem'
title: 1017 - ScheduleCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
ms.openlocfilehash: 04dc4f663ceed1d7350dd14867e4926042bd11af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792897"
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="f75ee-103">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="f75ee-103">1017 - ScheduleCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="f75ee-104">속성</span><span class="sxs-lookup"><span data-stu-id="f75ee-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f75ee-105">ID</span><span class="sxs-lookup"><span data-stu-id="f75ee-105">ID</span></span>|<span data-ttu-id="f75ee-106">1017</span><span class="sxs-lookup"><span data-stu-id="f75ee-106">1017</span></span>|  
|<span data-ttu-id="f75ee-107">키워드</span><span class="sxs-lookup"><span data-stu-id="f75ee-107">Keywords</span></span>|<span data-ttu-id="f75ee-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f75ee-108">WFRuntime</span></span>|  
|<span data-ttu-id="f75ee-109">Level</span><span class="sxs-lookup"><span data-stu-id="f75ee-109">Level</span></span>|<span data-ttu-id="f75ee-110">자세히</span><span class="sxs-lookup"><span data-stu-id="f75ee-110">Verbose</span></span>|  
|<span data-ttu-id="f75ee-111">채널</span><span class="sxs-lookup"><span data-stu-id="f75ee-111">Channel</span></span>|<span data-ttu-id="f75ee-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="f75ee-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f75ee-113">설명</span><span class="sxs-lookup"><span data-stu-id="f75ee-113">Description</span></span>  

 <span data-ttu-id="f75ee-114">CancelActivityWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f75ee-114">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f75ee-115">메시지</span><span class="sxs-lookup"><span data-stu-id="f75ee-115">Message</span></span>  

 <span data-ttu-id="f75ee-116">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CancelActivityWorkItem이 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f75ee-116">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f75ee-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="f75ee-117">Details</span></span>  
  
|<span data-ttu-id="f75ee-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f75ee-118">Data Item Name</span></span>|<span data-ttu-id="f75ee-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f75ee-119">Data Item Type</span></span>|<span data-ttu-id="f75ee-120">설명</span><span class="sxs-lookup"><span data-stu-id="f75ee-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f75ee-121">활동</span><span class="sxs-lookup"><span data-stu-id="f75ee-121">Activity</span></span>|<span data-ttu-id="f75ee-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f75ee-122">xs:string</span></span>|<span data-ttu-id="f75ee-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f75ee-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="f75ee-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f75ee-124">DisplayName</span></span>|<span data-ttu-id="f75ee-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f75ee-125">xs:string</span></span>|<span data-ttu-id="f75ee-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f75ee-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="f75ee-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f75ee-127">InstanceId</span></span>|<span data-ttu-id="f75ee-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f75ee-128">xs:string</span></span>|<span data-ttu-id="f75ee-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f75ee-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f75ee-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f75ee-130">AppDomain</span></span>|<span data-ttu-id="f75ee-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="f75ee-131">xs:string</span></span>|<span data-ttu-id="f75ee-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f75ee-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
