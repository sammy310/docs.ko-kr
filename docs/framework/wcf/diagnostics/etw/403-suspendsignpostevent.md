---
title: 403 - SuspendSignpostEvent
ms.date: 03/30/2017
ms.assetid: fb2e6f29-e556-47b4-b4c1-acd6b8879702
ms.openlocfilehash: 66251141cdf66c18ad0c1334f6f3e6c0629b4b33
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241059"
---
# <a name="403---suspendsignpostevent"></a><span data-ttu-id="9bdba-102">403 - SuspendSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="9bdba-102">403 - SuspendSignpostEvent</span></span>

## <a name="properties"></a><span data-ttu-id="9bdba-103">속성</span><span class="sxs-lookup"><span data-stu-id="9bdba-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9bdba-104">ID</span><span class="sxs-lookup"><span data-stu-id="9bdba-104">ID</span></span>|<span data-ttu-id="9bdba-105">403</span><span class="sxs-lookup"><span data-stu-id="9bdba-105">403</span></span>|  
|<span data-ttu-id="9bdba-106">키워드</span><span class="sxs-lookup"><span data-stu-id="9bdba-106">Keywords</span></span>|<span data-ttu-id="9bdba-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="9bdba-107">Troubleshooting</span></span>|  
|<span data-ttu-id="9bdba-108">Level</span><span class="sxs-lookup"><span data-stu-id="9bdba-108">Level</span></span>|<span data-ttu-id="9bdba-109">정보</span><span class="sxs-lookup"><span data-stu-id="9bdba-109">Information</span></span>|  
|<span data-ttu-id="9bdba-110">채널</span><span class="sxs-lookup"><span data-stu-id="9bdba-110">Channel</span></span>|<span data-ttu-id="9bdba-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="9bdba-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9bdba-112">Description</span><span class="sxs-lookup"><span data-stu-id="9bdba-112">Description</span></span>  

 <span data-ttu-id="9bdba-113">이 이벤트는 엔드투엔드 동작의 일시 중단을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9bdba-113">This event marks the suspension of an end-to-end activity.</span></span> <span data-ttu-id="9bdba-114">여기에는 동작의 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bdba-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9bdba-115">메시지</span><span class="sxs-lookup"><span data-stu-id="9bdba-115">Message</span></span>  

 <span data-ttu-id="9bdba-116">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="9bdba-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9bdba-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="9bdba-117">Details</span></span>  
  
|<span data-ttu-id="9bdba-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="9bdba-118">Data Item Name</span></span>|<span data-ttu-id="9bdba-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="9bdba-119">Data Item Type</span></span>|<span data-ttu-id="9bdba-120">Description</span><span class="sxs-lookup"><span data-stu-id="9bdba-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9bdba-121">Extended Data</span><span class="sxs-lookup"><span data-stu-id="9bdba-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="9bdba-122">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9bdba-122">The name of the activity.</span></span>|  
|<span data-ttu-id="9bdba-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9bdba-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9bdba-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9bdba-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
