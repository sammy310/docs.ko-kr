---
title: 401- StopSignPostEvent
ms.date: 03/30/2017
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
ms.openlocfilehash: e549a8aabd0a54022000515050cde19dc4f20dd3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294068"
---
# <a name="401--stopsignpostevent"></a><span data-ttu-id="ce60a-102">401- StopSignPostEvent</span><span class="sxs-lookup"><span data-stu-id="ce60a-102">401- StopSignPostEvent</span></span>

## <a name="properties"></a><span data-ttu-id="ce60a-103">속성</span><span class="sxs-lookup"><span data-stu-id="ce60a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ce60a-104">ID</span><span class="sxs-lookup"><span data-stu-id="ce60a-104">ID</span></span>|<span data-ttu-id="ce60a-105">401</span><span class="sxs-lookup"><span data-stu-id="ce60a-105">401</span></span>|  
|<span data-ttu-id="ce60a-106">키워드</span><span class="sxs-lookup"><span data-stu-id="ce60a-106">Keywords</span></span>|<span data-ttu-id="ce60a-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="ce60a-107">Troubleshooting</span></span>|  
|<span data-ttu-id="ce60a-108">Level</span><span class="sxs-lookup"><span data-stu-id="ce60a-108">Level</span></span>|<span data-ttu-id="ce60a-109">정보</span><span class="sxs-lookup"><span data-stu-id="ce60a-109">Information</span></span>|  
|<span data-ttu-id="ce60a-110">채널</span><span class="sxs-lookup"><span data-stu-id="ce60a-110">Channel</span></span>|<span data-ttu-id="ce60a-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="ce60a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ce60a-112">Description</span><span class="sxs-lookup"><span data-stu-id="ce60a-112">Description</span></span>  

 <span data-ttu-id="ce60a-113">이 이벤트는 엔드투엔드 동작의 끝을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ce60a-113">This event marks the end of an end-to-end activity.</span></span> <span data-ttu-id="ce60a-114">여기에는 동작의 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce60a-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ce60a-115">메시지</span><span class="sxs-lookup"><span data-stu-id="ce60a-115">Message</span></span>  

 <span data-ttu-id="ce60a-116">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="ce60a-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ce60a-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="ce60a-117">Details</span></span>  
  
|<span data-ttu-id="ce60a-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="ce60a-118">Data Item Name</span></span>|<span data-ttu-id="ce60a-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="ce60a-119">Data Item Type</span></span>|<span data-ttu-id="ce60a-120">Description</span><span class="sxs-lookup"><span data-stu-id="ce60a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ce60a-121">Extended Data</span><span class="sxs-lookup"><span data-stu-id="ce60a-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="ce60a-122">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ce60a-122">The name of the activity.</span></span>|  
|<span data-ttu-id="ce60a-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ce60a-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ce60a-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ce60a-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
