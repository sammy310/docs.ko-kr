---
description: '자세한 정보: 403-SuspendSignpostEvent'
title: 403 - SuspendSignpostEvent
ms.date: 03/30/2017
ms.assetid: fb2e6f29-e556-47b4-b4c1-acd6b8879702
ms.openlocfilehash: 4e601920c94ed99c25a1c969508798f65f5348bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99656425"
---
# <a name="403---suspendsignpostevent"></a><span data-ttu-id="04d80-103">403 - SuspendSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="04d80-103">403 - SuspendSignpostEvent</span></span>

## <a name="properties"></a><span data-ttu-id="04d80-104">속성</span><span class="sxs-lookup"><span data-stu-id="04d80-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="04d80-105">ID</span><span class="sxs-lookup"><span data-stu-id="04d80-105">ID</span></span>|<span data-ttu-id="04d80-106">403</span><span class="sxs-lookup"><span data-stu-id="04d80-106">403</span></span>|  
|<span data-ttu-id="04d80-107">키워드</span><span class="sxs-lookup"><span data-stu-id="04d80-107">Keywords</span></span>|<span data-ttu-id="04d80-108">문제 해결</span><span class="sxs-lookup"><span data-stu-id="04d80-108">Troubleshooting</span></span>|  
|<span data-ttu-id="04d80-109">Level</span><span class="sxs-lookup"><span data-stu-id="04d80-109">Level</span></span>|<span data-ttu-id="04d80-110">정보</span><span class="sxs-lookup"><span data-stu-id="04d80-110">Information</span></span>|  
|<span data-ttu-id="04d80-111">채널</span><span class="sxs-lookup"><span data-stu-id="04d80-111">Channel</span></span>|<span data-ttu-id="04d80-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="04d80-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="04d80-113">설명</span><span class="sxs-lookup"><span data-stu-id="04d80-113">Description</span></span>  

 <span data-ttu-id="04d80-114">이 이벤트는 엔드투엔드 동작의 일시 중단을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-114">This event marks the suspension of an end-to-end activity.</span></span> <span data-ttu-id="04d80-115">여기에는 동작의 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-115">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="04d80-116">메시지</span><span class="sxs-lookup"><span data-stu-id="04d80-116">Message</span></span>  

 <span data-ttu-id="04d80-117">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-117">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="04d80-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="04d80-118">Details</span></span>  
  
|<span data-ttu-id="04d80-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="04d80-119">Data Item Name</span></span>|<span data-ttu-id="04d80-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="04d80-120">Data Item Type</span></span>|<span data-ttu-id="04d80-121">설명</span><span class="sxs-lookup"><span data-stu-id="04d80-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="04d80-122">Extended Data</span><span class="sxs-lookup"><span data-stu-id="04d80-122">Extended Data</span></span>|`xs:string`|<span data-ttu-id="04d80-123">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-123">The name of the activity.</span></span>|  
|<span data-ttu-id="04d80-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="04d80-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="04d80-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
