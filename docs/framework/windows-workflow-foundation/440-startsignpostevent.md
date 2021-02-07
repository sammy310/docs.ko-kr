---
description: '자세한 정보: 440-StartSignpostEvent1'
title: 440 - StartSignpostEvent
ms.date: 03/30/2017
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
ms.openlocfilehash: 462ad54c9dd8230632d76d88f2b779eaea3b43ee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720373"
---
# <a name="440---startsignpostevent1"></a><span data-ttu-id="5d5cc-103">440 - StartSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="5d5cc-103">440 - StartSignpostEvent1</span></span>

## <a name="properties"></a><span data-ttu-id="5d5cc-104">속성</span><span class="sxs-lookup"><span data-stu-id="5d5cc-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d5cc-105">ID</span><span class="sxs-lookup"><span data-stu-id="5d5cc-105">ID</span></span>|<span data-ttu-id="5d5cc-106">440</span><span class="sxs-lookup"><span data-stu-id="5d5cc-106">440</span></span>|  
|<span data-ttu-id="5d5cc-107">키워드</span><span class="sxs-lookup"><span data-stu-id="5d5cc-107">Keywords</span></span>|<span data-ttu-id="5d5cc-108">문제 해결</span><span class="sxs-lookup"><span data-stu-id="5d5cc-108">Troubleshooting</span></span>|  
|<span data-ttu-id="5d5cc-109">Level</span><span class="sxs-lookup"><span data-stu-id="5d5cc-109">Level</span></span>|<span data-ttu-id="5d5cc-110">정보</span><span class="sxs-lookup"><span data-stu-id="5d5cc-110">Information</span></span>|  
|<span data-ttu-id="5d5cc-111">채널</span><span class="sxs-lookup"><span data-stu-id="5d5cc-111">Channel</span></span>|<span data-ttu-id="5d5cc-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="5d5cc-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5d5cc-113">설명</span><span class="sxs-lookup"><span data-stu-id="5d5cc-113">Description</span></span>  

 <span data-ttu-id="5d5cc-114">동작 추적에서 보내거나 받을 메시지가 동작 경계를 넘기 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5d5cc-114">In activity tracing, indicates a message has started crossing an activity boundary in send or receive.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5d5cc-115">메시지</span><span class="sxs-lookup"><span data-stu-id="5d5cc-115">Message</span></span>  

 <span data-ttu-id="5d5cc-116">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="5d5cc-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5d5cc-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="5d5cc-117">Details</span></span>  
  
|<span data-ttu-id="5d5cc-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="5d5cc-118">Data Item Name</span></span>|<span data-ttu-id="5d5cc-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="5d5cc-119">Data Item Type</span></span>|<span data-ttu-id="5d5cc-120">설명</span><span class="sxs-lookup"><span data-stu-id="5d5cc-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5d5cc-121">ExtendedData</span><span class="sxs-lookup"><span data-stu-id="5d5cc-121">ExtendedData</span></span>|`xs:string`|<span data-ttu-id="5d5cc-122">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5d5cc-122">The name of the activity.</span></span>|  
|<span data-ttu-id="5d5cc-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5d5cc-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5d5cc-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5d5cc-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
