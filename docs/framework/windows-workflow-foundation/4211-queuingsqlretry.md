---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ede74eb642c5c2c79b90cf1458db424d9f83b087
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774246"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="90768-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="90768-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="90768-103">속성</span><span class="sxs-lookup"><span data-stu-id="90768-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="90768-104">ID</span><span class="sxs-lookup"><span data-stu-id="90768-104">ID</span></span>|<span data-ttu-id="90768-105">4211</span><span class="sxs-lookup"><span data-stu-id="90768-105">4211</span></span>|  
|<span data-ttu-id="90768-106">키워드</span><span class="sxs-lookup"><span data-stu-id="90768-106">Keywords</span></span>|<span data-ttu-id="90768-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="90768-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="90768-108">수준</span><span class="sxs-lookup"><span data-stu-id="90768-108">Level</span></span>|<span data-ttu-id="90768-109">경고</span><span class="sxs-lookup"><span data-stu-id="90768-109">Warning</span></span>|  
|<span data-ttu-id="90768-110">채널</span><span class="sxs-lookup"><span data-stu-id="90768-110">Channel</span></span>|<span data-ttu-id="90768-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="90768-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="90768-112">설명</span><span class="sxs-lookup"><span data-stu-id="90768-112">Description</span></span>  
 <span data-ttu-id="90768-113">SQL 재시도를 큐에 넣고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="90768-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="90768-114">메시지</span><span class="sxs-lookup"><span data-stu-id="90768-114">Message</span></span>  
 <span data-ttu-id="90768-115">%1밀리초의 지연으로 SQL 재시도를 큐에 넣고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90768-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="90768-116">설명</span><span class="sxs-lookup"><span data-stu-id="90768-116">Details</span></span>  
  
|<span data-ttu-id="90768-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="90768-117">Data Item Name</span></span>|<span data-ttu-id="90768-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="90768-118">Data Item Type</span></span>|<span data-ttu-id="90768-119">설명</span><span class="sxs-lookup"><span data-stu-id="90768-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="90768-120">지연</span><span class="sxs-lookup"><span data-stu-id="90768-120">Delay</span></span>|<span data-ttu-id="90768-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="90768-121">xs:string</span></span>|<span data-ttu-id="90768-122">재시도 사이의 지연입니다.</span><span class="sxs-lookup"><span data-stu-id="90768-122">The delay between retries.</span></span>|  
|<span data-ttu-id="90768-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="90768-123">AppDomain</span></span>|<span data-ttu-id="90768-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="90768-124">xs:string</span></span>|<span data-ttu-id="90768-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="90768-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
