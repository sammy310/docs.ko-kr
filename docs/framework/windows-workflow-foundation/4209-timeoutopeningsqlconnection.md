---
description: '자세한 정보: 4209-TimeoutOpeningSqlConnection'
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: 9c7540e328530fdc01b9f065dfb75b92c467bd43
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787996"
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="7518e-103">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="7518e-103">4209 - TimeoutOpeningSqlConnection</span></span>

## <a name="properties"></a><span data-ttu-id="7518e-104">속성</span><span class="sxs-lookup"><span data-stu-id="7518e-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7518e-105">ID</span><span class="sxs-lookup"><span data-stu-id="7518e-105">ID</span></span>|<span data-ttu-id="7518e-106">4209</span><span class="sxs-lookup"><span data-stu-id="7518e-106">4209</span></span>|  
|<span data-ttu-id="7518e-107">키워드</span><span class="sxs-lookup"><span data-stu-id="7518e-107">Keywords</span></span>|<span data-ttu-id="7518e-108">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="7518e-108">WFInstanceStore</span></span>|  
|<span data-ttu-id="7518e-109">Level</span><span class="sxs-lookup"><span data-stu-id="7518e-109">Level</span></span>|<span data-ttu-id="7518e-110">Error</span><span class="sxs-lookup"><span data-stu-id="7518e-110">Error</span></span>|  
|<span data-ttu-id="7518e-111">채널</span><span class="sxs-lookup"><span data-stu-id="7518e-111">Channel</span></span>|<span data-ttu-id="7518e-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="7518e-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7518e-113">설명</span><span class="sxs-lookup"><span data-stu-id="7518e-113">Description</span></span>  

 <span data-ttu-id="7518e-114">SQL 연결을 여는 동안 시간 초과가 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7518e-114">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7518e-115">메시지</span><span class="sxs-lookup"><span data-stu-id="7518e-115">Message</span></span>  

 <span data-ttu-id="7518e-116">SQL 연결을 열려는 중 시간이 초과했습니다.</span><span class="sxs-lookup"><span data-stu-id="7518e-116">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="7518e-117">할당된 시간 제한인 %1 내에 작업을 완료하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="7518e-117">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="7518e-118">이 작업에 할당된 시간은 더 긴 시간 제한의 일부였을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7518e-118">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7518e-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="7518e-119">Details</span></span>  
  
|<span data-ttu-id="7518e-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="7518e-120">Data Item Name</span></span>|<span data-ttu-id="7518e-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="7518e-121">Data Item Type</span></span>|<span data-ttu-id="7518e-122">설명</span><span class="sxs-lookup"><span data-stu-id="7518e-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7518e-123">제한 시간</span><span class="sxs-lookup"><span data-stu-id="7518e-123">Timeout</span></span>|<span data-ttu-id="7518e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="7518e-124">xs:string</span></span>|<span data-ttu-id="7518e-125">SQL 연결을 열기 위한 시간 제한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7518e-125">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="7518e-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7518e-126">AppDomain</span></span>|<span data-ttu-id="7518e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="7518e-127">xs:string</span></span>|<span data-ttu-id="7518e-128">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7518e-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
