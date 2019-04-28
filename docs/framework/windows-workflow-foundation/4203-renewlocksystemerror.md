---
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 984f7ddae8797cba17753a618d0820d21bde5eef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774350"
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="57fd4-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="57fd4-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="57fd4-103">속성</span><span class="sxs-lookup"><span data-stu-id="57fd4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="57fd4-104">ID</span><span class="sxs-lookup"><span data-stu-id="57fd4-104">ID</span></span>|<span data-ttu-id="57fd4-105">4203</span><span class="sxs-lookup"><span data-stu-id="57fd4-105">4203</span></span>|  
|<span data-ttu-id="57fd4-106">키워드</span><span class="sxs-lookup"><span data-stu-id="57fd4-106">Keywords</span></span>|<span data-ttu-id="57fd4-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="57fd4-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="57fd4-108">수준</span><span class="sxs-lookup"><span data-stu-id="57fd4-108">Level</span></span>|<span data-ttu-id="57fd4-109">Error</span><span class="sxs-lookup"><span data-stu-id="57fd4-109">Error</span></span>|  
|<span data-ttu-id="57fd4-110">채널</span><span class="sxs-lookup"><span data-stu-id="57fd4-110">Channel</span></span>|<span data-ttu-id="57fd4-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="57fd4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="57fd4-112">설명</span><span class="sxs-lookup"><span data-stu-id="57fd4-112">Description</span></span>  
 <span data-ttu-id="57fd4-113">잠금 만료가 이미 지났거나 잠금 소유자가 삭제되었기 때문에 SQL 공급자가 잠금 만료를 연장하지 못했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="57fd4-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="57fd4-114">SqlWorkflowInstanceStore가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="57fd4-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="57fd4-115">메시지</span><span class="sxs-lookup"><span data-stu-id="57fd4-115">Message</span></span>  
 <span data-ttu-id="57fd4-116">잠금 만료를 연장하지 못했습니다. 잠금 만료가 이미 지났거나 잠금 소유자가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="57fd4-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="57fd4-117">SqlWorkflowInstanceStore를 중단하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="57fd4-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="57fd4-118">설명</span><span class="sxs-lookup"><span data-stu-id="57fd4-118">Details</span></span>  
  
|<span data-ttu-id="57fd4-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="57fd4-119">Data Item Name</span></span>|<span data-ttu-id="57fd4-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="57fd4-120">Data Item Type</span></span>|<span data-ttu-id="57fd4-121">설명</span><span class="sxs-lookup"><span data-stu-id="57fd4-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="57fd4-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="57fd4-122">AppDomain</span></span>|<span data-ttu-id="57fd4-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="57fd4-123">xs:string</span></span>|<span data-ttu-id="57fd4-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="57fd4-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
