---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 94c7ce231df241778f7c6ec5fe5998eae364750d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755573"
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="07582-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="07582-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="07582-103">속성</span><span class="sxs-lookup"><span data-stu-id="07582-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07582-104">ID</span><span class="sxs-lookup"><span data-stu-id="07582-104">ID</span></span>|<span data-ttu-id="07582-105">3508</span><span class="sxs-lookup"><span data-stu-id="07582-105">3508</span></span>|  
|<span data-ttu-id="07582-106">키워드</span><span class="sxs-lookup"><span data-stu-id="07582-106">Keywords</span></span>|<span data-ttu-id="07582-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="07582-107">WFServices</span></span>|  
|<span data-ttu-id="07582-108">수준</span><span class="sxs-lookup"><span data-stu-id="07582-108">Level</span></span>|<span data-ttu-id="07582-109">자세히</span><span class="sxs-lookup"><span data-stu-id="07582-109">Verbose</span></span>|  
|<span data-ttu-id="07582-110">채널</span><span class="sxs-lookup"><span data-stu-id="07582-110">Channel</span></span>|<span data-ttu-id="07582-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="07582-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="07582-112">설명</span><span class="sxs-lookup"><span data-stu-id="07582-112">Description</span></span>  
 <span data-ttu-id="07582-113">구성 파일에 TrackingProfile이 없거나 ActivityDefinitionId가 프로필과 일치하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="07582-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="07582-114">메시지</span><span class="sxs-lookup"><span data-stu-id="07582-114">Message</span></span>  
 <span data-ttu-id="07582-115">ActivityDefinitionId '%2'에 대한 TrackingProfile '%1'을(를) 찾지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="07582-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="07582-116">구성 파일에 TrackingProfile이 없거나 ActivityDefinitionId가 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07582-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="07582-117">설명</span><span class="sxs-lookup"><span data-stu-id="07582-117">Details</span></span>  
  
|<span data-ttu-id="07582-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="07582-118">Data Item Name</span></span>|<span data-ttu-id="07582-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="07582-119">Data Item Type</span></span>|<span data-ttu-id="07582-120">설명</span><span class="sxs-lookup"><span data-stu-id="07582-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="07582-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="07582-121">TrackingProfile</span></span>|<span data-ttu-id="07582-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="07582-122">xs:string</span></span>|<span data-ttu-id="07582-123">추적 프로필의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="07582-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="07582-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="07582-124">ActivityDefinitionId</span></span>|<span data-ttu-id="07582-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="07582-125">xs:string</span></span>|<span data-ttu-id="07582-126">작업 정의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="07582-126">The activity definition id.</span></span>|  
|<span data-ttu-id="07582-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="07582-127">AppDomain</span></span>|<span data-ttu-id="07582-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="07582-128">xs:string</span></span>|<span data-ttu-id="07582-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="07582-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
