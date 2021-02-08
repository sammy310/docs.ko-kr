---
description: '자세한 정보: 3508-TrackingProfileNotFound'
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 3e97af1689a868fb103b06413a0c4f28b0c1f652
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778011"
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="fa1a9-103">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="fa1a9-103">3508 - TrackingProfileNotFound</span></span>

## <a name="properties"></a><span data-ttu-id="fa1a9-104">속성</span><span class="sxs-lookup"><span data-stu-id="fa1a9-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fa1a9-105">ID</span><span class="sxs-lookup"><span data-stu-id="fa1a9-105">ID</span></span>|<span data-ttu-id="fa1a9-106">3508</span><span class="sxs-lookup"><span data-stu-id="fa1a9-106">3508</span></span>|  
|<span data-ttu-id="fa1a9-107">키워드</span><span class="sxs-lookup"><span data-stu-id="fa1a9-107">Keywords</span></span>|<span data-ttu-id="fa1a9-108">WFServices</span><span class="sxs-lookup"><span data-stu-id="fa1a9-108">WFServices</span></span>|  
|<span data-ttu-id="fa1a9-109">Level</span><span class="sxs-lookup"><span data-stu-id="fa1a9-109">Level</span></span>|<span data-ttu-id="fa1a9-110">자세히</span><span class="sxs-lookup"><span data-stu-id="fa1a9-110">Verbose</span></span>|  
|<span data-ttu-id="fa1a9-111">채널</span><span class="sxs-lookup"><span data-stu-id="fa1a9-111">Channel</span></span>|<span data-ttu-id="fa1a9-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="fa1a9-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fa1a9-113">설명</span><span class="sxs-lookup"><span data-stu-id="fa1a9-113">Description</span></span>  

 <span data-ttu-id="fa1a9-114">구성 파일에 TrackingProfile이 없거나 ActivityDefinitionId가 프로필과 일치하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fa1a9-114">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fa1a9-115">메시지</span><span class="sxs-lookup"><span data-stu-id="fa1a9-115">Message</span></span>  

 <span data-ttu-id="fa1a9-116">ActivityDefinitionId '%2'에 대한 TrackingProfile '%1'을(를) 찾지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="fa1a9-116">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="fa1a9-117">구성 파일에 TrackingProfile이 없거나 ActivityDefinitionId가 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa1a9-117">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fa1a9-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="fa1a9-118">Details</span></span>  
  
|<span data-ttu-id="fa1a9-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="fa1a9-119">Data Item Name</span></span>|<span data-ttu-id="fa1a9-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="fa1a9-120">Data Item Type</span></span>|<span data-ttu-id="fa1a9-121">설명</span><span class="sxs-lookup"><span data-stu-id="fa1a9-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fa1a9-122">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="fa1a9-122">TrackingProfile</span></span>|<span data-ttu-id="fa1a9-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa1a9-123">xs:string</span></span>|<span data-ttu-id="fa1a9-124">추적 프로필의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fa1a9-124">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="fa1a9-125">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="fa1a9-125">ActivityDefinitionId</span></span>|<span data-ttu-id="fa1a9-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa1a9-126">xs:string</span></span>|<span data-ttu-id="fa1a9-127">작업 정의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fa1a9-127">The activity definition id.</span></span>|  
|<span data-ttu-id="fa1a9-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fa1a9-128">AppDomain</span></span>|<span data-ttu-id="fa1a9-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa1a9-129">xs:string</span></span>|<span data-ttu-id="fa1a9-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fa1a9-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
