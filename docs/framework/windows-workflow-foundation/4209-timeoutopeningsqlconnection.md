---
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: 9aa8cdffebb0cdf8b1e8225a394edf78ecf032b9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238680"
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="f68c4-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="f68c4-102">4209 - TimeoutOpeningSqlConnection</span></span>

## <a name="properties"></a><span data-ttu-id="f68c4-103">속성</span><span class="sxs-lookup"><span data-stu-id="f68c4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f68c4-104">ID</span><span class="sxs-lookup"><span data-stu-id="f68c4-104">ID</span></span>|<span data-ttu-id="f68c4-105">4209</span><span class="sxs-lookup"><span data-stu-id="f68c4-105">4209</span></span>|  
|<span data-ttu-id="f68c4-106">키워드</span><span class="sxs-lookup"><span data-stu-id="f68c4-106">Keywords</span></span>|<span data-ttu-id="f68c4-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="f68c4-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="f68c4-108">Level</span><span class="sxs-lookup"><span data-stu-id="f68c4-108">Level</span></span>|<span data-ttu-id="f68c4-109">오류</span><span class="sxs-lookup"><span data-stu-id="f68c4-109">Error</span></span>|  
|<span data-ttu-id="f68c4-110">채널</span><span class="sxs-lookup"><span data-stu-id="f68c4-110">Channel</span></span>|<span data-ttu-id="f68c4-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="f68c4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f68c4-112">Description</span><span class="sxs-lookup"><span data-stu-id="f68c4-112">Description</span></span>  

 <span data-ttu-id="f68c4-113">SQL 연결을 여는 동안 시간 초과가 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f68c4-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f68c4-114">메시지</span><span class="sxs-lookup"><span data-stu-id="f68c4-114">Message</span></span>  

 <span data-ttu-id="f68c4-115">SQL 연결을 열려는 중 시간이 초과했습니다.</span><span class="sxs-lookup"><span data-stu-id="f68c4-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="f68c4-116">할당된 시간 제한인 %1 내에 작업을 완료하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="f68c4-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="f68c4-117">이 작업에 할당된 시간은 더 긴 시간 제한의 일부였을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f68c4-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f68c4-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="f68c4-118">Details</span></span>  
  
|<span data-ttu-id="f68c4-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f68c4-119">Data Item Name</span></span>|<span data-ttu-id="f68c4-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f68c4-120">Data Item Type</span></span>|<span data-ttu-id="f68c4-121">Description</span><span class="sxs-lookup"><span data-stu-id="f68c4-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f68c4-122">제한 시간</span><span class="sxs-lookup"><span data-stu-id="f68c4-122">Timeout</span></span>|<span data-ttu-id="f68c4-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f68c4-123">xs:string</span></span>|<span data-ttu-id="f68c4-124">SQL 연결을 열기 위한 시간 제한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f68c4-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="f68c4-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f68c4-125">AppDomain</span></span>|<span data-ttu-id="f68c4-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="f68c4-126">xs:string</span></span>|<span data-ttu-id="f68c4-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f68c4-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
