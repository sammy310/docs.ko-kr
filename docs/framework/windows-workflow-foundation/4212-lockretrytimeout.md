---
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 43ec434064f768fc976232c6d3013f17c80fe053
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267171"
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="125d6-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="125d6-102">4212 - LockRetryTimeout</span></span>

## <a name="properties"></a><span data-ttu-id="125d6-103">속성</span><span class="sxs-lookup"><span data-stu-id="125d6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="125d6-104">ID</span><span class="sxs-lookup"><span data-stu-id="125d6-104">ID</span></span>|<span data-ttu-id="125d6-105">4212</span><span class="sxs-lookup"><span data-stu-id="125d6-105">4212</span></span>|  
|<span data-ttu-id="125d6-106">키워드</span><span class="sxs-lookup"><span data-stu-id="125d6-106">Keywords</span></span>|<span data-ttu-id="125d6-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="125d6-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="125d6-108">Level</span><span class="sxs-lookup"><span data-stu-id="125d6-108">Level</span></span>|<span data-ttu-id="125d6-109">경고</span><span class="sxs-lookup"><span data-stu-id="125d6-109">Warning</span></span>|  
|<span data-ttu-id="125d6-110">채널</span><span class="sxs-lookup"><span data-stu-id="125d6-110">Channel</span></span>|<span data-ttu-id="125d6-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="125d6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="125d6-112">Description</span><span class="sxs-lookup"><span data-stu-id="125d6-112">Description</span></span>  

 <span data-ttu-id="125d6-113">SQL 공급자에서 인스턴스 잠금을 얻으려는 중 시간 초과가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="125d6-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="125d6-114">메시지</span><span class="sxs-lookup"><span data-stu-id="125d6-114">Message</span></span>  

 <span data-ttu-id="125d6-115">인스턴스 잠금을 얻으려고 시도 하는 동안 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="125d6-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="125d6-116">할당된 시간 제한인 %1 내에 작업을 완료하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="125d6-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="125d6-117">이 작업에 할당된 시간은 더 긴 시간 제한의 일부였을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125d6-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="125d6-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="125d6-118">Details</span></span>  
  
|<span data-ttu-id="125d6-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="125d6-119">Data Item Name</span></span>|<span data-ttu-id="125d6-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="125d6-120">Data Item Type</span></span>|<span data-ttu-id="125d6-121">Description</span><span class="sxs-lookup"><span data-stu-id="125d6-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="125d6-122">Delay</span><span class="sxs-lookup"><span data-stu-id="125d6-122">Delay</span></span>|<span data-ttu-id="125d6-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="125d6-123">xs:string</span></span>|<span data-ttu-id="125d6-124">재시도 사이의 지연입니다.</span><span class="sxs-lookup"><span data-stu-id="125d6-124">The delay between retries.</span></span>|  
|<span data-ttu-id="125d6-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="125d6-125">AppDomain</span></span>|<span data-ttu-id="125d6-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="125d6-126">xs:string</span></span>|<span data-ttu-id="125d6-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="125d6-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
