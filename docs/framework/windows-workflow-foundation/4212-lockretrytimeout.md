---
description: '자세한 정보: 4212-LockRetryTimeout'
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: a2299d0d9643fb60ff420519fb43199e3f747c69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667085"
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="41e73-103">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="41e73-103">4212 - LockRetryTimeout</span></span>

## <a name="properties"></a><span data-ttu-id="41e73-104">속성</span><span class="sxs-lookup"><span data-stu-id="41e73-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="41e73-105">ID</span><span class="sxs-lookup"><span data-stu-id="41e73-105">ID</span></span>|<span data-ttu-id="41e73-106">4212</span><span class="sxs-lookup"><span data-stu-id="41e73-106">4212</span></span>|  
|<span data-ttu-id="41e73-107">키워드</span><span class="sxs-lookup"><span data-stu-id="41e73-107">Keywords</span></span>|<span data-ttu-id="41e73-108">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="41e73-108">WFInstanceStore</span></span>|  
|<span data-ttu-id="41e73-109">Level</span><span class="sxs-lookup"><span data-stu-id="41e73-109">Level</span></span>|<span data-ttu-id="41e73-110">경고</span><span class="sxs-lookup"><span data-stu-id="41e73-110">Warning</span></span>|  
|<span data-ttu-id="41e73-111">채널</span><span class="sxs-lookup"><span data-stu-id="41e73-111">Channel</span></span>|<span data-ttu-id="41e73-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="41e73-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="41e73-113">설명</span><span class="sxs-lookup"><span data-stu-id="41e73-113">Description</span></span>  

 <span data-ttu-id="41e73-114">SQL 공급자에서 인스턴스 잠금을 얻으려는 중 시간 초과가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="41e73-114">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="41e73-115">메시지</span><span class="sxs-lookup"><span data-stu-id="41e73-115">Message</span></span>  

 <span data-ttu-id="41e73-116">인스턴스 잠금을 얻으려고 시도 하는 동안 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41e73-116">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="41e73-117">할당된 시간 제한인 %1 내에 작업을 완료하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="41e73-117">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="41e73-118">이 작업에 할당된 시간은 더 긴 시간 제한의 일부였을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41e73-118">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="41e73-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="41e73-119">Details</span></span>  
  
|<span data-ttu-id="41e73-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="41e73-120">Data Item Name</span></span>|<span data-ttu-id="41e73-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="41e73-121">Data Item Type</span></span>|<span data-ttu-id="41e73-122">설명</span><span class="sxs-lookup"><span data-stu-id="41e73-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="41e73-123">Delay</span><span class="sxs-lookup"><span data-stu-id="41e73-123">Delay</span></span>|<span data-ttu-id="41e73-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="41e73-124">xs:string</span></span>|<span data-ttu-id="41e73-125">재시도 사이의 지연입니다.</span><span class="sxs-lookup"><span data-stu-id="41e73-125">The delay between retries.</span></span>|  
|<span data-ttu-id="41e73-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="41e73-126">AppDomain</span></span>|<span data-ttu-id="41e73-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="41e73-127">xs:string</span></span>|<span data-ttu-id="41e73-128">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="41e73-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
