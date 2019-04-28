---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: 416feb4073b31178b016ae72c9cd85e15c4a68c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774415"
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="f966e-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="f966e-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="f966e-103">속성</span><span class="sxs-lookup"><span data-stu-id="f966e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f966e-104">ID</span><span class="sxs-lookup"><span data-stu-id="f966e-104">ID</span></span>|<span data-ttu-id="f966e-105">39458</span><span class="sxs-lookup"><span data-stu-id="f966e-105">39458</span></span>|  
|<span data-ttu-id="f966e-106">키워드</span><span class="sxs-lookup"><span data-stu-id="f966e-106">Keywords</span></span>|<span data-ttu-id="f966e-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="f966e-107">WFTracking</span></span>|  
|<span data-ttu-id="f966e-108">수준</span><span class="sxs-lookup"><span data-stu-id="f966e-108">Level</span></span>|<span data-ttu-id="f966e-109">경고</span><span class="sxs-lookup"><span data-stu-id="f966e-109">Warning</span></span>|  
|<span data-ttu-id="f966e-110">채널</span><span class="sxs-lookup"><span data-stu-id="f966e-110">Channel</span></span>|<span data-ttu-id="f966e-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="f966e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f966e-112">설명</span><span class="sxs-lookup"><span data-stu-id="f966e-112">Description</span></span>  
 <span data-ttu-id="f966e-113">추적 레코드가 잘렸음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f966e-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="f966e-114">변수/주석/사용자 데이터가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f966e-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f966e-115">메시지</span><span class="sxs-lookup"><span data-stu-id="f966e-115">Message</span></span>  
 <span data-ttu-id="f966e-116">잘린 추적 레코드 %1이(가) 공급자가 %2인 ETW 세션에 기록되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f966e-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="f966e-117">변수/주석/사용자 데이터가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f966e-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="f966e-118">설명</span><span class="sxs-lookup"><span data-stu-id="f966e-118">Details</span></span>  
  
|<span data-ttu-id="f966e-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f966e-119">Data Item Name</span></span>|<span data-ttu-id="f966e-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f966e-120">Data Item Type</span></span>|<span data-ttu-id="f966e-121">설명</span><span class="sxs-lookup"><span data-stu-id="f966e-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f966e-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="f966e-122">RecordNumber</span></span>|<span data-ttu-id="f966e-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f966e-123">xs:string</span></span>|<span data-ttu-id="f966e-124">추적 레코드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="f966e-124">The tracking record number.</span></span>|  
|<span data-ttu-id="f966e-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="f966e-125">ProviderId</span></span>|<span data-ttu-id="f966e-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="f966e-126">xs:string</span></span>|<span data-ttu-id="f966e-127">ETW 공급자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f966e-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="f966e-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f966e-128">AppDomain</span></span>|<span data-ttu-id="f966e-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="f966e-129">xs:string</span></span>|<span data-ttu-id="f966e-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f966e-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
