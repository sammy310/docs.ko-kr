---
description: '자세한 정보: 4211-QueuingSqlRetry'
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: 674914ee105bb0a48f8c32efbd573c685d22d9f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742708"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="bc53e-103">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="bc53e-103">4211 - QueuingSqlRetry</span></span>

## <a name="properties"></a><span data-ttu-id="bc53e-104">속성</span><span class="sxs-lookup"><span data-stu-id="bc53e-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bc53e-105">ID</span><span class="sxs-lookup"><span data-stu-id="bc53e-105">ID</span></span>|<span data-ttu-id="bc53e-106">4211</span><span class="sxs-lookup"><span data-stu-id="bc53e-106">4211</span></span>|  
|<span data-ttu-id="bc53e-107">키워드</span><span class="sxs-lookup"><span data-stu-id="bc53e-107">Keywords</span></span>|<span data-ttu-id="bc53e-108">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="bc53e-108">WFInstanceStore</span></span>|  
|<span data-ttu-id="bc53e-109">Level</span><span class="sxs-lookup"><span data-stu-id="bc53e-109">Level</span></span>|<span data-ttu-id="bc53e-110">경고</span><span class="sxs-lookup"><span data-stu-id="bc53e-110">Warning</span></span>|  
|<span data-ttu-id="bc53e-111">채널</span><span class="sxs-lookup"><span data-stu-id="bc53e-111">Channel</span></span>|<span data-ttu-id="bc53e-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="bc53e-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bc53e-113">설명</span><span class="sxs-lookup"><span data-stu-id="bc53e-113">Description</span></span>  

 <span data-ttu-id="bc53e-114">SQL 재시도를 큐에 넣고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-114">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bc53e-115">메시지</span><span class="sxs-lookup"><span data-stu-id="bc53e-115">Message</span></span>  

 <span data-ttu-id="bc53e-116">%1밀리초의 지연으로 SQL 재시도를 큐에 넣고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-116">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bc53e-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="bc53e-117">Details</span></span>  
  
|<span data-ttu-id="bc53e-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="bc53e-118">Data Item Name</span></span>|<span data-ttu-id="bc53e-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="bc53e-119">Data Item Type</span></span>|<span data-ttu-id="bc53e-120">설명</span><span class="sxs-lookup"><span data-stu-id="bc53e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bc53e-121">Delay</span><span class="sxs-lookup"><span data-stu-id="bc53e-121">Delay</span></span>|<span data-ttu-id="bc53e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="bc53e-122">xs:string</span></span>|<span data-ttu-id="bc53e-123">재시도 사이의 지연입니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-123">The delay between retries.</span></span>|  
|<span data-ttu-id="bc53e-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bc53e-124">AppDomain</span></span>|<span data-ttu-id="bc53e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="bc53e-125">xs:string</span></span>|<span data-ttu-id="bc53e-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
