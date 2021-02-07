---
description: '자세한 정보: 1131-InvokeMethodUseAsyncPattern'
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 59d8e5e1fe7c5b038df6fce3211fd01977abc4f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667319"
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="730ac-103">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="730ac-103">1131 - InvokeMethodUseAsyncPattern</span></span>

## <a name="properties"></a><span data-ttu-id="730ac-104">속성</span><span class="sxs-lookup"><span data-stu-id="730ac-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="730ac-105">ID</span><span class="sxs-lookup"><span data-stu-id="730ac-105">ID</span></span>|<span data-ttu-id="730ac-106">1131</span><span class="sxs-lookup"><span data-stu-id="730ac-106">1131</span></span>|  
|<span data-ttu-id="730ac-107">키워드</span><span class="sxs-lookup"><span data-stu-id="730ac-107">Keywords</span></span>|<span data-ttu-id="730ac-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="730ac-108">WFRuntime</span></span>|  
|<span data-ttu-id="730ac-109">Level</span><span class="sxs-lookup"><span data-stu-id="730ac-109">Level</span></span>|<span data-ttu-id="730ac-110">정보</span><span class="sxs-lookup"><span data-stu-id="730ac-110">Information</span></span>|  
|<span data-ttu-id="730ac-111">채널</span><span class="sxs-lookup"><span data-stu-id="730ac-111">Channel</span></span>|<span data-ttu-id="730ac-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="730ac-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="730ac-113">설명</span><span class="sxs-lookup"><span data-stu-id="730ac-113">Description</span></span>  

 <span data-ttu-id="730ac-114">CacheMetadata 단계 중 InvokeMethod 작업에서 메서드를 호출할 때 비동기 패턴을 사용함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="730ac-114">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="730ac-115">메시지</span><span class="sxs-lookup"><span data-stu-id="730ac-115">Message</span></span>  

 <span data-ttu-id="730ac-116">InvokeMethod '%1'' - 메서드에서 ''%2' 및 '%3'의 비동기 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="730ac-116">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="730ac-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="730ac-117">Details</span></span>  
  
|<span data-ttu-id="730ac-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="730ac-118">Data Item Name</span></span>|<span data-ttu-id="730ac-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="730ac-119">Data Item Type</span></span>|<span data-ttu-id="730ac-120">설명</span><span class="sxs-lookup"><span data-stu-id="730ac-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="730ac-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="730ac-121">InvokeMethod</span></span>|<span data-ttu-id="730ac-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="730ac-122">xs:string</span></span>|<span data-ttu-id="730ac-123">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="730ac-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="730ac-124">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="730ac-124">BeginMethod</span></span>|<span data-ttu-id="730ac-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="730ac-125">xs:string</span></span>|<span data-ttu-id="730ac-126">Begin 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="730ac-126">The name of the begin method.</span></span>|  
|<span data-ttu-id="730ac-127">EndMethod</span><span class="sxs-lookup"><span data-stu-id="730ac-127">EndMethod</span></span>|<span data-ttu-id="730ac-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="730ac-128">xs:string</span></span>|<span data-ttu-id="730ac-129">End 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="730ac-129">The name of the end method.</span></span>|  
|<span data-ttu-id="730ac-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="730ac-130">AppDomain</span></span>|<span data-ttu-id="730ac-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="730ac-131">xs:string</span></span>|<span data-ttu-id="730ac-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="730ac-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
