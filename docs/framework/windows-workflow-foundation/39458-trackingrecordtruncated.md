---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: f02a34673c51be6e0b127a64e4622131575d836f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275894"
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="7e993-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="7e993-102">39458 - TrackingRecordTruncated</span></span>

## <a name="properties"></a><span data-ttu-id="7e993-103">속성</span><span class="sxs-lookup"><span data-stu-id="7e993-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7e993-104">ID</span><span class="sxs-lookup"><span data-stu-id="7e993-104">ID</span></span>|<span data-ttu-id="7e993-105">39458</span><span class="sxs-lookup"><span data-stu-id="7e993-105">39458</span></span>|  
|<span data-ttu-id="7e993-106">키워드</span><span class="sxs-lookup"><span data-stu-id="7e993-106">Keywords</span></span>|<span data-ttu-id="7e993-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="7e993-107">WFTracking</span></span>|  
|<span data-ttu-id="7e993-108">Level</span><span class="sxs-lookup"><span data-stu-id="7e993-108">Level</span></span>|<span data-ttu-id="7e993-109">경고</span><span class="sxs-lookup"><span data-stu-id="7e993-109">Warning</span></span>|  
|<span data-ttu-id="7e993-110">채널</span><span class="sxs-lookup"><span data-stu-id="7e993-110">Channel</span></span>|<span data-ttu-id="7e993-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="7e993-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7e993-112">Description</span><span class="sxs-lookup"><span data-stu-id="7e993-112">Description</span></span>  

 <span data-ttu-id="7e993-113">추적 레코드가 잘렸음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7e993-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="7e993-114">변수/주석/사용자 데이터가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7e993-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7e993-115">메시지</span><span class="sxs-lookup"><span data-stu-id="7e993-115">Message</span></span>  

 <span data-ttu-id="7e993-116">잘린 추적 레코드 %1이(가) 공급자가 %2인 ETW 세션에 기록되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7e993-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="7e993-117">변수/주석/사용자 데이터가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7e993-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="7e993-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="7e993-118">Details</span></span>  
  
|<span data-ttu-id="7e993-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="7e993-119">Data Item Name</span></span>|<span data-ttu-id="7e993-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="7e993-120">Data Item Type</span></span>|<span data-ttu-id="7e993-121">Description</span><span class="sxs-lookup"><span data-stu-id="7e993-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7e993-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="7e993-122">RecordNumber</span></span>|<span data-ttu-id="7e993-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="7e993-123">xs:string</span></span>|<span data-ttu-id="7e993-124">추적 레코드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7e993-124">The tracking record number.</span></span>|  
|<span data-ttu-id="7e993-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="7e993-125">ProviderId</span></span>|<span data-ttu-id="7e993-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="7e993-126">xs:string</span></span>|<span data-ttu-id="7e993-127">ETW 공급자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7e993-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="7e993-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7e993-128">AppDomain</span></span>|<span data-ttu-id="7e993-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="7e993-129">xs:string</span></span>|<span data-ttu-id="7e993-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7e993-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
