---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: a163ed216cbdfbf2b9d77d25979733d6bdb121d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945940"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="37c3b-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="37c3b-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="37c3b-103">속성</span><span class="sxs-lookup"><span data-stu-id="37c3b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="37c3b-104">ID</span><span class="sxs-lookup"><span data-stu-id="37c3b-104">ID</span></span>|<span data-ttu-id="37c3b-105">3552</span><span class="sxs-lookup"><span data-stu-id="37c3b-105">3552</span></span>|  
|<span data-ttu-id="37c3b-106">키워드</span><span class="sxs-lookup"><span data-stu-id="37c3b-106">Keywords</span></span>|<span data-ttu-id="37c3b-107">할당량, WFServices</span><span class="sxs-lookup"><span data-stu-id="37c3b-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="37c3b-108">수준</span><span class="sxs-lookup"><span data-stu-id="37c3b-108">Level</span></span>|<span data-ttu-id="37c3b-109">경고</span><span class="sxs-lookup"><span data-stu-id="37c3b-109">Warning</span></span>|  
|<span data-ttu-id="37c3b-110">채널</span><span class="sxs-lookup"><span data-stu-id="37c3b-110">Channel</span></span>|<span data-ttu-id="37c3b-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="37c3b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="37c3b-112">설명</span><span class="sxs-lookup"><span data-stu-id="37c3b-112">Description</span></span>  
 <span data-ttu-id="37c3b-113">스로틀 'MaxPendingMessagesPerChannel' 한도에 도달했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="37c3b-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="37c3b-114">메시지</span><span class="sxs-lookup"><span data-stu-id="37c3b-114">Message</span></span>  
 <span data-ttu-id="37c3b-115">스로틀 'MaxPendingMessagesPerChannel ' 한도 '%1'에 도달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="37c3b-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="37c3b-116">이 한도를 늘리려면 BufferedReceiveServiceBehavior에서 MaxPendingMessagesPerChannel 속성을 조정하세요.</span><span class="sxs-lookup"><span data-stu-id="37c3b-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="37c3b-117">설명</span><span class="sxs-lookup"><span data-stu-id="37c3b-117">Details</span></span>  
  
|<span data-ttu-id="37c3b-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="37c3b-118">Data Item Name</span></span>|<span data-ttu-id="37c3b-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="37c3b-119">Data Item Type</span></span>|<span data-ttu-id="37c3b-120">설명</span><span class="sxs-lookup"><span data-stu-id="37c3b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="37c3b-121">Limit</span><span class="sxs-lookup"><span data-stu-id="37c3b-121">Limit</span></span>|<span data-ttu-id="37c3b-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="37c3b-122">xs:string</span></span>|<span data-ttu-id="37c3b-123">MaxPendingMessagesPerChannel 스로틀의 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="37c3b-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="37c3b-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="37c3b-124">AppDomain</span></span>|<span data-ttu-id="37c3b-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="37c3b-125">xs:string</span></span>|<span data-ttu-id="37c3b-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="37c3b-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
