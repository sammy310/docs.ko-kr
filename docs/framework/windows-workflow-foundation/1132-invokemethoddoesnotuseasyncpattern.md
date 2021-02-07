---
description: '자세한 정보: 1132-InvokeMethodDoesNotUseAsyncPattern'
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
ms.openlocfilehash: 05bbd1f6047ab4c6451d71a4f6007f3112f9630f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667280"
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="48188-103">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="48188-103">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>

## <a name="properties"></a><span data-ttu-id="48188-104">속성</span><span class="sxs-lookup"><span data-stu-id="48188-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48188-105">ID</span><span class="sxs-lookup"><span data-stu-id="48188-105">ID</span></span>|<span data-ttu-id="48188-106">1132</span><span class="sxs-lookup"><span data-stu-id="48188-106">1132</span></span>|  
|<span data-ttu-id="48188-107">키워드</span><span class="sxs-lookup"><span data-stu-id="48188-107">Keywords</span></span>|<span data-ttu-id="48188-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="48188-108">WFRuntime</span></span>|  
|<span data-ttu-id="48188-109">Level</span><span class="sxs-lookup"><span data-stu-id="48188-109">Level</span></span>|<span data-ttu-id="48188-110">정보</span><span class="sxs-lookup"><span data-stu-id="48188-110">Information</span></span>|  
|<span data-ttu-id="48188-111">채널</span><span class="sxs-lookup"><span data-stu-id="48188-111">Channel</span></span>|<span data-ttu-id="48188-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="48188-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="48188-113">설명</span><span class="sxs-lookup"><span data-stu-id="48188-113">Description</span></span>  

 <span data-ttu-id="48188-114">CacheMetadata 단계 중 InvokeMethod 작업에서 메서드를 호출할 때 비동기 패턴을 사용하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="48188-114">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="48188-115">메시지</span><span class="sxs-lookup"><span data-stu-id="48188-115">Message</span></span>  

 <span data-ttu-id="48188-116">InvokeMethod '%1' - 메서드에서 비동기 패턴을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48188-116">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="48188-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="48188-117">Details</span></span>  
  
|<span data-ttu-id="48188-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="48188-118">Data Item Name</span></span>|<span data-ttu-id="48188-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="48188-119">Data Item Type</span></span>|<span data-ttu-id="48188-120">설명</span><span class="sxs-lookup"><span data-stu-id="48188-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="48188-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="48188-121">InvokeMethod</span></span>|<span data-ttu-id="48188-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="48188-122">xs:string</span></span>|<span data-ttu-id="48188-123">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="48188-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="48188-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="48188-124">AppDomain</span></span>|<span data-ttu-id="48188-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="48188-125">xs:string</span></span>|<span data-ttu-id="48188-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="48188-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
