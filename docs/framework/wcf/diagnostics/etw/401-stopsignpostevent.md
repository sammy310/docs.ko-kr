---
description: '자세한 정보: 401-StopSignPostEvent'
title: 401- StopSignPostEvent
ms.date: 03/30/2017
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
ms.openlocfilehash: 99b6151d902f3f8059b0aa01e6cda290debafda6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793950"
---
# <a name="401--stopsignpostevent"></a><span data-ttu-id="da1a8-103">401- StopSignPostEvent</span><span class="sxs-lookup"><span data-stu-id="da1a8-103">401- StopSignPostEvent</span></span>

## <a name="properties"></a><span data-ttu-id="da1a8-104">속성</span><span class="sxs-lookup"><span data-stu-id="da1a8-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="da1a8-105">ID</span><span class="sxs-lookup"><span data-stu-id="da1a8-105">ID</span></span>|<span data-ttu-id="da1a8-106">401</span><span class="sxs-lookup"><span data-stu-id="da1a8-106">401</span></span>|  
|<span data-ttu-id="da1a8-107">키워드</span><span class="sxs-lookup"><span data-stu-id="da1a8-107">Keywords</span></span>|<span data-ttu-id="da1a8-108">문제 해결</span><span class="sxs-lookup"><span data-stu-id="da1a8-108">Troubleshooting</span></span>|  
|<span data-ttu-id="da1a8-109">Level</span><span class="sxs-lookup"><span data-stu-id="da1a8-109">Level</span></span>|<span data-ttu-id="da1a8-110">정보</span><span class="sxs-lookup"><span data-stu-id="da1a8-110">Information</span></span>|  
|<span data-ttu-id="da1a8-111">채널</span><span class="sxs-lookup"><span data-stu-id="da1a8-111">Channel</span></span>|<span data-ttu-id="da1a8-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="da1a8-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="da1a8-113">설명</span><span class="sxs-lookup"><span data-stu-id="da1a8-113">Description</span></span>  

 <span data-ttu-id="da1a8-114">이 이벤트는 엔드투엔드 동작의 끝을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="da1a8-114">This event marks the end of an end-to-end activity.</span></span> <span data-ttu-id="da1a8-115">여기에는 동작의 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="da1a8-115">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="da1a8-116">메시지</span><span class="sxs-lookup"><span data-stu-id="da1a8-116">Message</span></span>  

 <span data-ttu-id="da1a8-117">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="da1a8-117">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="da1a8-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="da1a8-118">Details</span></span>  
  
|<span data-ttu-id="da1a8-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="da1a8-119">Data Item Name</span></span>|<span data-ttu-id="da1a8-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="da1a8-120">Data Item Type</span></span>|<span data-ttu-id="da1a8-121">설명</span><span class="sxs-lookup"><span data-stu-id="da1a8-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="da1a8-122">Extended Data</span><span class="sxs-lookup"><span data-stu-id="da1a8-122">Extended Data</span></span>|`xs:string`|<span data-ttu-id="da1a8-123">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="da1a8-123">The name of the activity.</span></span>|  
|<span data-ttu-id="da1a8-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="da1a8-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="da1a8-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="da1a8-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
