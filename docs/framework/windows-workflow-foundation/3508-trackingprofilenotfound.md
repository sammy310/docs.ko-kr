---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 23262427c3da730eaf930a8b483c7c4d4ec3a3a4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289843"
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="25594-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="25594-102">3508 - TrackingProfileNotFound</span></span>

## <a name="properties"></a><span data-ttu-id="25594-103">속성</span><span class="sxs-lookup"><span data-stu-id="25594-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25594-104">ID</span><span class="sxs-lookup"><span data-stu-id="25594-104">ID</span></span>|<span data-ttu-id="25594-105">3508</span><span class="sxs-lookup"><span data-stu-id="25594-105">3508</span></span>|  
|<span data-ttu-id="25594-106">키워드</span><span class="sxs-lookup"><span data-stu-id="25594-106">Keywords</span></span>|<span data-ttu-id="25594-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="25594-107">WFServices</span></span>|  
|<span data-ttu-id="25594-108">Level</span><span class="sxs-lookup"><span data-stu-id="25594-108">Level</span></span>|<span data-ttu-id="25594-109">자세히</span><span class="sxs-lookup"><span data-stu-id="25594-109">Verbose</span></span>|  
|<span data-ttu-id="25594-110">채널</span><span class="sxs-lookup"><span data-stu-id="25594-110">Channel</span></span>|<span data-ttu-id="25594-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="25594-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="25594-112">Description</span><span class="sxs-lookup"><span data-stu-id="25594-112">Description</span></span>  

 <span data-ttu-id="25594-113">구성 파일에 TrackingProfile이 없거나 ActivityDefinitionId가 프로필과 일치하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="25594-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="25594-114">메시지</span><span class="sxs-lookup"><span data-stu-id="25594-114">Message</span></span>  

 <span data-ttu-id="25594-115">ActivityDefinitionId '%2'에 대한 TrackingProfile '%1'을(를) 찾지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="25594-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="25594-116">구성 파일에 TrackingProfile이 없거나 ActivityDefinitionId가 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25594-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="25594-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="25594-117">Details</span></span>  
  
|<span data-ttu-id="25594-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="25594-118">Data Item Name</span></span>|<span data-ttu-id="25594-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="25594-119">Data Item Type</span></span>|<span data-ttu-id="25594-120">Description</span><span class="sxs-lookup"><span data-stu-id="25594-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="25594-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="25594-121">TrackingProfile</span></span>|<span data-ttu-id="25594-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="25594-122">xs:string</span></span>|<span data-ttu-id="25594-123">추적 프로필의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="25594-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="25594-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="25594-124">ActivityDefinitionId</span></span>|<span data-ttu-id="25594-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="25594-125">xs:string</span></span>|<span data-ttu-id="25594-126">작업 정의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="25594-126">The activity definition id.</span></span>|  
|<span data-ttu-id="25594-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="25594-127">AppDomain</span></span>|<span data-ttu-id="25594-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="25594-128">xs:string</span></span>|<span data-ttu-id="25594-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="25594-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
