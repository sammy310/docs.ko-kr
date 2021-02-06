---
description: '자세한 정보: 3552-MaxPendingMessagesPerChannelExceeded'
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: 5fb2d27f7d68716cebf2cfaafd21851226a456e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631439"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="2d3f3-103">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="2d3f3-103">3552 - MaxPendingMessagesPerChannelExceeded</span></span>

## <a name="properties"></a><span data-ttu-id="2d3f3-104">속성</span><span class="sxs-lookup"><span data-stu-id="2d3f3-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2d3f3-105">ID</span><span class="sxs-lookup"><span data-stu-id="2d3f3-105">ID</span></span>|<span data-ttu-id="2d3f3-106">3552</span><span class="sxs-lookup"><span data-stu-id="2d3f3-106">3552</span></span>|  
|<span data-ttu-id="2d3f3-107">키워드</span><span class="sxs-lookup"><span data-stu-id="2d3f3-107">Keywords</span></span>|<span data-ttu-id="2d3f3-108">할당량, WFServices</span><span class="sxs-lookup"><span data-stu-id="2d3f3-108">Quota, WFServices</span></span>|  
|<span data-ttu-id="2d3f3-109">Level</span><span class="sxs-lookup"><span data-stu-id="2d3f3-109">Level</span></span>|<span data-ttu-id="2d3f3-110">경고</span><span class="sxs-lookup"><span data-stu-id="2d3f3-110">Warning</span></span>|  
|<span data-ttu-id="2d3f3-111">채널</span><span class="sxs-lookup"><span data-stu-id="2d3f3-111">Channel</span></span>|<span data-ttu-id="2d3f3-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="2d3f3-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2d3f3-113">설명</span><span class="sxs-lookup"><span data-stu-id="2d3f3-113">Description</span></span>  

 <span data-ttu-id="2d3f3-114">스로틀 'MaxPendingMessagesPerChannel' 한도에 도달했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d3f3-114">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2d3f3-115">메시지</span><span class="sxs-lookup"><span data-stu-id="2d3f3-115">Message</span></span>  

 <span data-ttu-id="2d3f3-116">'%1'의 스로틀 'MaxPendingMessagesPerChannel' 한도에 도달했습니다.</span><span class="sxs-lookup"><span data-stu-id="2d3f3-116">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="2d3f3-117">이 한도를 늘리려면 BufferedReceiveServiceBehavior에서 MaxPendingMessagesPerChannel 속성을 조정하세요.</span><span class="sxs-lookup"><span data-stu-id="2d3f3-117">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2d3f3-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="2d3f3-118">Details</span></span>  
  
|<span data-ttu-id="2d3f3-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="2d3f3-119">Data Item Name</span></span>|<span data-ttu-id="2d3f3-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="2d3f3-120">Data Item Type</span></span>|<span data-ttu-id="2d3f3-121">설명</span><span class="sxs-lookup"><span data-stu-id="2d3f3-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2d3f3-122">제한</span><span class="sxs-lookup"><span data-stu-id="2d3f3-122">Limit</span></span>|<span data-ttu-id="2d3f3-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="2d3f3-123">xs:string</span></span>|<span data-ttu-id="2d3f3-124">MaxPendingMessagesPerChannel 스로틀의 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="2d3f3-124">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="2d3f3-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2d3f3-125">AppDomain</span></span>|<span data-ttu-id="2d3f3-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="2d3f3-126">xs:string</span></span>|<span data-ttu-id="2d3f3-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2d3f3-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
