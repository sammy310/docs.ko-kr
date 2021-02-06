---
description: '다음에 대 한 자세한 정보: 39456-TrackingRecordDropped 됨'
title: 39456 - TrackingRecordDropped
ms.date: 03/30/2017
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
ms.openlocfilehash: 0f6920ef85327318f4ea8662ae36f26c7494bcb2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631296"
---
# <a name="39456---trackingrecorddropped"></a><span data-ttu-id="9e626-103">39456 - TrackingRecordDropped</span><span class="sxs-lookup"><span data-stu-id="9e626-103">39456 - TrackingRecordDropped</span></span>

## <a name="properties"></a><span data-ttu-id="9e626-104">속성</span><span class="sxs-lookup"><span data-stu-id="9e626-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9e626-105">ID</span><span class="sxs-lookup"><span data-stu-id="9e626-105">ID</span></span>|<span data-ttu-id="9e626-106">39456</span><span class="sxs-lookup"><span data-stu-id="9e626-106">39456</span></span>|  
|<span data-ttu-id="9e626-107">키워드</span><span class="sxs-lookup"><span data-stu-id="9e626-107">Keywords</span></span>|<span data-ttu-id="9e626-108">WFTracking</span><span class="sxs-lookup"><span data-stu-id="9e626-108">WFTracking</span></span>|  
|<span data-ttu-id="9e626-109">Level</span><span class="sxs-lookup"><span data-stu-id="9e626-109">Level</span></span>|<span data-ttu-id="9e626-110">경고</span><span class="sxs-lookup"><span data-stu-id="9e626-110">Warning</span></span>|  
|<span data-ttu-id="9e626-111">채널</span><span class="sxs-lookup"><span data-stu-id="9e626-111">Channel</span></span>|<span data-ttu-id="9e626-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="9e626-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9e626-113">설명</span><span class="sxs-lookup"><span data-stu-id="9e626-113">Description</span></span>  

 <span data-ttu-id="9e626-114">추적 레코드의 크기가 ETW 세션 공급자에서 허용하는 최대값을 초과하기 때문에 추적 레코드가 삭제되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e626-114">Indicates a tracking record has been dropped because its size exceeds maximum allowed by the ETW session provider.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9e626-115">메시지</span><span class="sxs-lookup"><span data-stu-id="9e626-115">Message</span></span>  

 <span data-ttu-id="9e626-116">추적 레코드 %1의 크기가 %2 공급자의 ETW 세션에서 허용된 최대값을 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="9e626-116">Size of tracking record %1 exceeds maximum allowed by the ETW session for provider %2</span></span>  
  
## <a name="details"></a><span data-ttu-id="9e626-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="9e626-117">Details</span></span>  
  
|<span data-ttu-id="9e626-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="9e626-118">Data Item Name</span></span>|<span data-ttu-id="9e626-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="9e626-119">Data Item Type</span></span>|<span data-ttu-id="9e626-120">설명</span><span class="sxs-lookup"><span data-stu-id="9e626-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9e626-121">예외</span><span class="sxs-lookup"><span data-stu-id="9e626-121">Exception</span></span>|<span data-ttu-id="9e626-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="9e626-122">xs:string</span></span>|<span data-ttu-id="9e626-123">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="9e626-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="9e626-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9e626-124">AppDomain</span></span>|<span data-ttu-id="9e626-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="9e626-125">xs:string</span></span>|<span data-ttu-id="9e626-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9e626-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
