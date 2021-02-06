---
description: '다음에 대 한 자세한 정보: 39458-TrackingRecordTruncated'
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: bb9a46dc5bd9bc4f4709a740dd0e7ec47ca826e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631283"
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="05700-103">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="05700-103">39458 - TrackingRecordTruncated</span></span>

## <a name="properties"></a><span data-ttu-id="05700-104">속성</span><span class="sxs-lookup"><span data-stu-id="05700-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05700-105">ID</span><span class="sxs-lookup"><span data-stu-id="05700-105">ID</span></span>|<span data-ttu-id="05700-106">39458</span><span class="sxs-lookup"><span data-stu-id="05700-106">39458</span></span>|  
|<span data-ttu-id="05700-107">키워드</span><span class="sxs-lookup"><span data-stu-id="05700-107">Keywords</span></span>|<span data-ttu-id="05700-108">WFTracking</span><span class="sxs-lookup"><span data-stu-id="05700-108">WFTracking</span></span>|  
|<span data-ttu-id="05700-109">Level</span><span class="sxs-lookup"><span data-stu-id="05700-109">Level</span></span>|<span data-ttu-id="05700-110">경고</span><span class="sxs-lookup"><span data-stu-id="05700-110">Warning</span></span>|  
|<span data-ttu-id="05700-111">채널</span><span class="sxs-lookup"><span data-stu-id="05700-111">Channel</span></span>|<span data-ttu-id="05700-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="05700-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="05700-113">설명</span><span class="sxs-lookup"><span data-stu-id="05700-113">Description</span></span>  

 <span data-ttu-id="05700-114">추적 레코드가 잘렸음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05700-114">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="05700-115">변수/주석/사용자 데이터가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="05700-115">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="05700-116">메시지</span><span class="sxs-lookup"><span data-stu-id="05700-116">Message</span></span>  

 <span data-ttu-id="05700-117">잘린 추적 레코드 %1이(가) 공급자가 %2인 ETW 세션에 기록되었습니다.</span><span class="sxs-lookup"><span data-stu-id="05700-117">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="05700-118">변수/주석/사용자 데이터가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="05700-118">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="05700-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="05700-119">Details</span></span>  
  
|<span data-ttu-id="05700-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="05700-120">Data Item Name</span></span>|<span data-ttu-id="05700-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="05700-121">Data Item Type</span></span>|<span data-ttu-id="05700-122">설명</span><span class="sxs-lookup"><span data-stu-id="05700-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="05700-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="05700-123">RecordNumber</span></span>|<span data-ttu-id="05700-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="05700-124">xs:string</span></span>|<span data-ttu-id="05700-125">추적 레코드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="05700-125">The tracking record number.</span></span>|  
|<span data-ttu-id="05700-126">ProviderId</span><span class="sxs-lookup"><span data-stu-id="05700-126">ProviderId</span></span>|<span data-ttu-id="05700-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="05700-127">xs:string</span></span>|<span data-ttu-id="05700-128">ETW 공급자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="05700-128">The ETW provider id.</span></span>|  
|<span data-ttu-id="05700-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="05700-129">AppDomain</span></span>|<span data-ttu-id="05700-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="05700-130">xs:string</span></span>|<span data-ttu-id="05700-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="05700-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
