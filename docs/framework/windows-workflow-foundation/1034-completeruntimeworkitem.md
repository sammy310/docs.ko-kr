---
description: '자세한 정보: 1034-CompleteRuntimeWorkItem'
title: 1034 - CompleteRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
ms.openlocfilehash: dd8a9fcb2fb692ab3b69df8f07f6a96cf48fc806
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667969"
---
# <a name="1034---completeruntimeworkitem"></a><span data-ttu-id="0535a-103">1034 - CompleteRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="0535a-103">1034 - CompleteRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="0535a-104">속성</span><span class="sxs-lookup"><span data-stu-id="0535a-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0535a-105">ID</span><span class="sxs-lookup"><span data-stu-id="0535a-105">ID</span></span>|<span data-ttu-id="0535a-106">1034</span><span class="sxs-lookup"><span data-stu-id="0535a-106">1034</span></span>|  
|<span data-ttu-id="0535a-107">키워드</span><span class="sxs-lookup"><span data-stu-id="0535a-107">Keywords</span></span>|<span data-ttu-id="0535a-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0535a-108">WFRuntime</span></span>|  
|<span data-ttu-id="0535a-109">Level</span><span class="sxs-lookup"><span data-stu-id="0535a-109">Level</span></span>|<span data-ttu-id="0535a-110">자세히</span><span class="sxs-lookup"><span data-stu-id="0535a-110">Verbose</span></span>|  
|<span data-ttu-id="0535a-111">채널</span><span class="sxs-lookup"><span data-stu-id="0535a-111">Channel</span></span>|<span data-ttu-id="0535a-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="0535a-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0535a-113">설명</span><span class="sxs-lookup"><span data-stu-id="0535a-113">Description</span></span>  

 <span data-ttu-id="0535a-114">RuntimeWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0535a-114">Indicates a RuntimeWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0535a-115">메시지</span><span class="sxs-lookup"><span data-stu-id="0535a-115">Message</span></span>  

 <span data-ttu-id="0535a-116">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0535a-116">A runtime work item has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0535a-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="0535a-117">Details</span></span>  
  
|<span data-ttu-id="0535a-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="0535a-118">Data Item Name</span></span>|<span data-ttu-id="0535a-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="0535a-119">Data Item Type</span></span>|<span data-ttu-id="0535a-120">설명</span><span class="sxs-lookup"><span data-stu-id="0535a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0535a-121">활동</span><span class="sxs-lookup"><span data-stu-id="0535a-121">Activity</span></span>|<span data-ttu-id="0535a-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0535a-122">xs:string</span></span>|<span data-ttu-id="0535a-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0535a-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="0535a-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0535a-124">DisplayName</span></span>|<span data-ttu-id="0535a-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0535a-125">xs:string</span></span>|<span data-ttu-id="0535a-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0535a-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="0535a-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0535a-127">InstanceId</span></span>|<span data-ttu-id="0535a-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0535a-128">xs:string</span></span>|<span data-ttu-id="0535a-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0535a-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0535a-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0535a-130">AppDomain</span></span>|<span data-ttu-id="0535a-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="0535a-131">xs:string</span></span>|<span data-ttu-id="0535a-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0535a-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
