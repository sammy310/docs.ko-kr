---
description: '자세한 정보: 1150-CompensationState'
title: 1150 - CompensationState
ms.date: 03/30/2017
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
ms.openlocfilehash: 4adc246cbe46dee3594bc6c0330c8e0306489219
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703343"
---
# <a name="1150---compensationstate"></a><span data-ttu-id="954e2-103">1150 - CompensationState</span><span class="sxs-lookup"><span data-stu-id="954e2-103">1150 - CompensationState</span></span>

## <a name="properties"></a><span data-ttu-id="954e2-104">속성</span><span class="sxs-lookup"><span data-stu-id="954e2-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="954e2-105">ID</span><span class="sxs-lookup"><span data-stu-id="954e2-105">ID</span></span>|<span data-ttu-id="954e2-106">1150</span><span class="sxs-lookup"><span data-stu-id="954e2-106">1150</span></span>|  
|<span data-ttu-id="954e2-107">키워드</span><span class="sxs-lookup"><span data-stu-id="954e2-107">Keywords</span></span>|<span data-ttu-id="954e2-108">WFActivities</span><span class="sxs-lookup"><span data-stu-id="954e2-108">WFActivities</span></span>|  
|<span data-ttu-id="954e2-109">Level</span><span class="sxs-lookup"><span data-stu-id="954e2-109">Level</span></span>|<span data-ttu-id="954e2-110">정보</span><span class="sxs-lookup"><span data-stu-id="954e2-110">Information</span></span>|  
|<span data-ttu-id="954e2-111">채널</span><span class="sxs-lookup"><span data-stu-id="954e2-111">Channel</span></span>|<span data-ttu-id="954e2-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="954e2-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="954e2-113">설명</span><span class="sxs-lookup"><span data-stu-id="954e2-113">Description</span></span>  

 <span data-ttu-id="954e2-114">CompensableActivity에서 상태 변경을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="954e2-114">Indicates a change of state in a CompensableActivity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="954e2-115">메시지</span><span class="sxs-lookup"><span data-stu-id="954e2-115">Message</span></span>  

 <span data-ttu-id="954e2-116">CompensableActivity '%1'은(는) '%2' 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="954e2-116">CompensableActivity '%1' is in the '%2' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="954e2-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="954e2-117">Details</span></span>  
  
|<span data-ttu-id="954e2-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="954e2-118">Data Item Name</span></span>|<span data-ttu-id="954e2-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="954e2-119">Data Item Type</span></span>|<span data-ttu-id="954e2-120">Description</span><span class="sxs-lookup"><span data-stu-id="954e2-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="954e2-121">DisplayName</span><span class="sxs-lookup"><span data-stu-id="954e2-121">DisplayName</span></span>|<span data-ttu-id="954e2-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="954e2-122">xs:string</span></span>|<span data-ttu-id="954e2-123">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="954e2-123">The display name of the activity.</span></span>|  
|<span data-ttu-id="954e2-124">시스템 상태</span><span class="sxs-lookup"><span data-stu-id="954e2-124">State</span></span>|<span data-ttu-id="954e2-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="954e2-125">xs:string</span></span>|<span data-ttu-id="954e2-126">보정 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="954e2-126">The compensation state.</span></span>|  
|<span data-ttu-id="954e2-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="954e2-127">AppDomain</span></span>|<span data-ttu-id="954e2-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="954e2-128">xs:string</span></span>|<span data-ttu-id="954e2-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="954e2-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
