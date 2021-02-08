---
description: '자세한 정보: 4203-RenewLockSystemError'
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 0e62c501391fcaec56f2016631707832170775ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792780"
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="98175-103">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="98175-103">4203 - RenewLockSystemError</span></span>

## <a name="properties"></a><span data-ttu-id="98175-104">속성</span><span class="sxs-lookup"><span data-stu-id="98175-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98175-105">ID</span><span class="sxs-lookup"><span data-stu-id="98175-105">ID</span></span>|<span data-ttu-id="98175-106">4203</span><span class="sxs-lookup"><span data-stu-id="98175-106">4203</span></span>|  
|<span data-ttu-id="98175-107">키워드</span><span class="sxs-lookup"><span data-stu-id="98175-107">Keywords</span></span>|<span data-ttu-id="98175-108">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="98175-108">WFInstanceStore</span></span>|  
|<span data-ttu-id="98175-109">Level</span><span class="sxs-lookup"><span data-stu-id="98175-109">Level</span></span>|<span data-ttu-id="98175-110">Error</span><span class="sxs-lookup"><span data-stu-id="98175-110">Error</span></span>|  
|<span data-ttu-id="98175-111">채널</span><span class="sxs-lookup"><span data-stu-id="98175-111">Channel</span></span>|<span data-ttu-id="98175-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="98175-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="98175-113">설명</span><span class="sxs-lookup"><span data-stu-id="98175-113">Description</span></span>  

 <span data-ttu-id="98175-114">잠금 만료가 이미 지났거나 잠금 소유자가 삭제되었기 때문에 SQL 공급자가 잠금 만료를 연장하지 못했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="98175-114">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="98175-115">SqlWorkflowInstanceStore가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="98175-115">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="98175-116">메시지</span><span class="sxs-lookup"><span data-stu-id="98175-116">Message</span></span>  

 <span data-ttu-id="98175-117">잠금 만료를 연장하지 못했습니다. 잠금 만료가 이미 지났거나 잠금 소유자가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="98175-117">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="98175-118">SqlWorkflowInstanceStore를 중단하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="98175-118">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="98175-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="98175-119">Details</span></span>  
  
|<span data-ttu-id="98175-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="98175-120">Data Item Name</span></span>|<span data-ttu-id="98175-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="98175-121">Data Item Type</span></span>|<span data-ttu-id="98175-122">설명</span><span class="sxs-lookup"><span data-stu-id="98175-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="98175-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="98175-123">AppDomain</span></span>|<span data-ttu-id="98175-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="98175-124">xs:string</span></span>|<span data-ttu-id="98175-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="98175-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
