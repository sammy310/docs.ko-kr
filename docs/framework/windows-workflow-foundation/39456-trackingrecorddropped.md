---
title: 39456 - TrackingRecordDropped
ms.date: 03/30/2017
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
ms.openlocfilehash: d958b506e057bc0d59f954debdc9da6015bf5f1f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273102"
---
# <a name="39456---trackingrecorddropped"></a><span data-ttu-id="46c65-102">39456 - TrackingRecordDropped</span><span class="sxs-lookup"><span data-stu-id="46c65-102">39456 - TrackingRecordDropped</span></span>

## <a name="properties"></a><span data-ttu-id="46c65-103">속성</span><span class="sxs-lookup"><span data-stu-id="46c65-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46c65-104">ID</span><span class="sxs-lookup"><span data-stu-id="46c65-104">ID</span></span>|<span data-ttu-id="46c65-105">39456</span><span class="sxs-lookup"><span data-stu-id="46c65-105">39456</span></span>|  
|<span data-ttu-id="46c65-106">키워드</span><span class="sxs-lookup"><span data-stu-id="46c65-106">Keywords</span></span>|<span data-ttu-id="46c65-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="46c65-107">WFTracking</span></span>|  
|<span data-ttu-id="46c65-108">Level</span><span class="sxs-lookup"><span data-stu-id="46c65-108">Level</span></span>|<span data-ttu-id="46c65-109">경고</span><span class="sxs-lookup"><span data-stu-id="46c65-109">Warning</span></span>|  
|<span data-ttu-id="46c65-110">채널</span><span class="sxs-lookup"><span data-stu-id="46c65-110">Channel</span></span>|<span data-ttu-id="46c65-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="46c65-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="46c65-112">Description</span><span class="sxs-lookup"><span data-stu-id="46c65-112">Description</span></span>  

 <span data-ttu-id="46c65-113">추적 레코드의 크기가 ETW 세션 공급자에서 허용하는 최대값을 초과하기 때문에 추적 레코드가 삭제되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="46c65-113">Indicates a tracking record has been dropped because its size exceeds maximum allowed by the ETW session provider.</span></span>  
  
## <a name="message"></a><span data-ttu-id="46c65-114">메시지</span><span class="sxs-lookup"><span data-stu-id="46c65-114">Message</span></span>  

 <span data-ttu-id="46c65-115">추적 레코드 %1의 크기가 %2 공급자의 ETW 세션에서 허용된 최대값을 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="46c65-115">Size of tracking record %1 exceeds maximum allowed by the ETW session for provider %2</span></span>  
  
## <a name="details"></a><span data-ttu-id="46c65-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="46c65-116">Details</span></span>  
  
|<span data-ttu-id="46c65-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="46c65-117">Data Item Name</span></span>|<span data-ttu-id="46c65-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="46c65-118">Data Item Type</span></span>|<span data-ttu-id="46c65-119">Description</span><span class="sxs-lookup"><span data-stu-id="46c65-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="46c65-120">예외</span><span class="sxs-lookup"><span data-stu-id="46c65-120">Exception</span></span>|<span data-ttu-id="46c65-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="46c65-121">xs:string</span></span>|<span data-ttu-id="46c65-122">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="46c65-122">The exception details for the exception</span></span>|  
|<span data-ttu-id="46c65-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="46c65-123">AppDomain</span></span>|<span data-ttu-id="46c65-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="46c65-124">xs:string</span></span>|<span data-ttu-id="46c65-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="46c65-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
