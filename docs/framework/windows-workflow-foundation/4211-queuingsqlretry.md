---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ff8a1e099934f5bf71fef0afbb7e54c0d1851fae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267184"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="90bc3-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="90bc3-102">4211 - QueuingSqlRetry</span></span>

## <a name="properties"></a><span data-ttu-id="90bc3-103">속성</span><span class="sxs-lookup"><span data-stu-id="90bc3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="90bc3-104">ID</span><span class="sxs-lookup"><span data-stu-id="90bc3-104">ID</span></span>|<span data-ttu-id="90bc3-105">4211</span><span class="sxs-lookup"><span data-stu-id="90bc3-105">4211</span></span>|  
|<span data-ttu-id="90bc3-106">키워드</span><span class="sxs-lookup"><span data-stu-id="90bc3-106">Keywords</span></span>|<span data-ttu-id="90bc3-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="90bc3-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="90bc3-108">Level</span><span class="sxs-lookup"><span data-stu-id="90bc3-108">Level</span></span>|<span data-ttu-id="90bc3-109">경고</span><span class="sxs-lookup"><span data-stu-id="90bc3-109">Warning</span></span>|  
|<span data-ttu-id="90bc3-110">채널</span><span class="sxs-lookup"><span data-stu-id="90bc3-110">Channel</span></span>|<span data-ttu-id="90bc3-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="90bc3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="90bc3-112">Description</span><span class="sxs-lookup"><span data-stu-id="90bc3-112">Description</span></span>  

 <span data-ttu-id="90bc3-113">SQL 재시도를 큐에 넣고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="90bc3-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="90bc3-114">메시지</span><span class="sxs-lookup"><span data-stu-id="90bc3-114">Message</span></span>  

 <span data-ttu-id="90bc3-115">%1밀리초의 지연으로 SQL 재시도를 큐에 넣고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90bc3-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="90bc3-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="90bc3-116">Details</span></span>  
  
|<span data-ttu-id="90bc3-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="90bc3-117">Data Item Name</span></span>|<span data-ttu-id="90bc3-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="90bc3-118">Data Item Type</span></span>|<span data-ttu-id="90bc3-119">Description</span><span class="sxs-lookup"><span data-stu-id="90bc3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="90bc3-120">Delay</span><span class="sxs-lookup"><span data-stu-id="90bc3-120">Delay</span></span>|<span data-ttu-id="90bc3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="90bc3-121">xs:string</span></span>|<span data-ttu-id="90bc3-122">재시도 사이의 지연입니다.</span><span class="sxs-lookup"><span data-stu-id="90bc3-122">The delay between retries.</span></span>|  
|<span data-ttu-id="90bc3-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="90bc3-123">AppDomain</span></span>|<span data-ttu-id="90bc3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="90bc3-124">xs:string</span></span>|<span data-ttu-id="90bc3-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="90bc3-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
