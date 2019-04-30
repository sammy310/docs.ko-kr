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
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="4d289-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="4d289-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="4d289-103">속성</span><span class="sxs-lookup"><span data-stu-id="4d289-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4d289-104">ID</span><span class="sxs-lookup"><span data-stu-id="4d289-104">ID</span></span>|<span data-ttu-id="4d289-105">3552</span><span class="sxs-lookup"><span data-stu-id="4d289-105">3552</span></span>|  
|<span data-ttu-id="4d289-106">키워드</span><span class="sxs-lookup"><span data-stu-id="4d289-106">Keywords</span></span>|<span data-ttu-id="4d289-107">할당량, WFServices</span><span class="sxs-lookup"><span data-stu-id="4d289-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="4d289-108">수준</span><span class="sxs-lookup"><span data-stu-id="4d289-108">Level</span></span>|<span data-ttu-id="4d289-109">경고</span><span class="sxs-lookup"><span data-stu-id="4d289-109">Warning</span></span>|  
|<span data-ttu-id="4d289-110">채널</span><span class="sxs-lookup"><span data-stu-id="4d289-110">Channel</span></span>|<span data-ttu-id="4d289-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="4d289-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4d289-112">설명</span><span class="sxs-lookup"><span data-stu-id="4d289-112">Description</span></span>  
 <span data-ttu-id="4d289-113">스로틀 'MaxPendingMessagesPerChannel' 한도에 도달했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4d289-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4d289-114">메시지</span><span class="sxs-lookup"><span data-stu-id="4d289-114">Message</span></span>  
 <span data-ttu-id="4d289-115">스로틀 'MaxPendingMessagesPerChannel ' 한도 '%1'에 도달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4d289-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="4d289-116">이 한도를 늘리려면 BufferedReceiveServiceBehavior에서 MaxPendingMessagesPerChannel 속성을 조정하세요.</span><span class="sxs-lookup"><span data-stu-id="4d289-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4d289-117">설명</span><span class="sxs-lookup"><span data-stu-id="4d289-117">Details</span></span>  
  
|<span data-ttu-id="4d289-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="4d289-118">Data Item Name</span></span>|<span data-ttu-id="4d289-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="4d289-119">Data Item Type</span></span>|<span data-ttu-id="4d289-120">설명</span><span class="sxs-lookup"><span data-stu-id="4d289-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4d289-121">Limit</span><span class="sxs-lookup"><span data-stu-id="4d289-121">Limit</span></span>|<span data-ttu-id="4d289-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="4d289-122">xs:string</span></span>|<span data-ttu-id="4d289-123">MaxPendingMessagesPerChannel 스로틀의 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="4d289-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="4d289-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4d289-124">AppDomain</span></span>|<span data-ttu-id="4d289-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="4d289-125">xs:string</span></span>|<span data-ttu-id="4d289-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4d289-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
