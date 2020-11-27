---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
ms.openlocfilehash: 9249bdd0fe996ee7c1b04783ac8fef2c48063cc0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294159"
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="d26f0-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="d26f0-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>

## <a name="properties"></a><span data-ttu-id="d26f0-103">속성</span><span class="sxs-lookup"><span data-stu-id="d26f0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d26f0-104">ID</span><span class="sxs-lookup"><span data-stu-id="d26f0-104">ID</span></span>|<span data-ttu-id="d26f0-105">1132</span><span class="sxs-lookup"><span data-stu-id="d26f0-105">1132</span></span>|  
|<span data-ttu-id="d26f0-106">키워드</span><span class="sxs-lookup"><span data-stu-id="d26f0-106">Keywords</span></span>|<span data-ttu-id="d26f0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d26f0-107">WFRuntime</span></span>|  
|<span data-ttu-id="d26f0-108">Level</span><span class="sxs-lookup"><span data-stu-id="d26f0-108">Level</span></span>|<span data-ttu-id="d26f0-109">정보</span><span class="sxs-lookup"><span data-stu-id="d26f0-109">Information</span></span>|  
|<span data-ttu-id="d26f0-110">채널</span><span class="sxs-lookup"><span data-stu-id="d26f0-110">Channel</span></span>|<span data-ttu-id="d26f0-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="d26f0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d26f0-112">Description</span><span class="sxs-lookup"><span data-stu-id="d26f0-112">Description</span></span>  

 <span data-ttu-id="d26f0-113">CacheMetadata 단계 중 InvokeMethod 작업에서 메서드를 호출할 때 비동기 패턴을 사용하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d26f0-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d26f0-114">메시지</span><span class="sxs-lookup"><span data-stu-id="d26f0-114">Message</span></span>  

 <span data-ttu-id="d26f0-115">InvokeMethod '%1' - 메서드에서 비동기 패턴을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d26f0-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d26f0-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d26f0-116">Details</span></span>  
  
|<span data-ttu-id="d26f0-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="d26f0-117">Data Item Name</span></span>|<span data-ttu-id="d26f0-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="d26f0-118">Data Item Type</span></span>|<span data-ttu-id="d26f0-119">Description</span><span class="sxs-lookup"><span data-stu-id="d26f0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d26f0-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="d26f0-120">InvokeMethod</span></span>|<span data-ttu-id="d26f0-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d26f0-121">xs:string</span></span>|<span data-ttu-id="d26f0-122">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d26f0-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="d26f0-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d26f0-123">AppDomain</span></span>|<span data-ttu-id="d26f0-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d26f0-124">xs:string</span></span>|<span data-ttu-id="d26f0-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d26f0-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
