---
description: '자세한 정보: 3503-DuplicateCorrelationQuery'
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: a8e1e41aad3aa1b273d8f8a5d7b0768fabe4e658
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778076"
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="17eda-103">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="17eda-103">3503 - DuplicateCorrelationQuery</span></span>

## <a name="properties"></a><span data-ttu-id="17eda-104">속성</span><span class="sxs-lookup"><span data-stu-id="17eda-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="17eda-105">ID</span><span class="sxs-lookup"><span data-stu-id="17eda-105">ID</span></span>|<span data-ttu-id="17eda-106">3503</span><span class="sxs-lookup"><span data-stu-id="17eda-106">3503</span></span>|  
|<span data-ttu-id="17eda-107">키워드</span><span class="sxs-lookup"><span data-stu-id="17eda-107">Keywords</span></span>|<span data-ttu-id="17eda-108">WFServices</span><span class="sxs-lookup"><span data-stu-id="17eda-108">WFServices</span></span>|  
|<span data-ttu-id="17eda-109">Level</span><span class="sxs-lookup"><span data-stu-id="17eda-109">Level</span></span>|<span data-ttu-id="17eda-110">경고</span><span class="sxs-lookup"><span data-stu-id="17eda-110">Warning</span></span>|  
|<span data-ttu-id="17eda-111">채널</span><span class="sxs-lookup"><span data-stu-id="17eda-111">Channel</span></span>|<span data-ttu-id="17eda-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="17eda-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="17eda-113">설명</span><span class="sxs-lookup"><span data-stu-id="17eda-113">Description</span></span>  

 <span data-ttu-id="17eda-114">중복 CorrelationQuery를 찾았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="17eda-114">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="17eda-115">중복 쿼리는 상관 관계를 계산할 때 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17eda-115">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="17eda-116">메시지</span><span class="sxs-lookup"><span data-stu-id="17eda-116">Message</span></span>  

 <span data-ttu-id="17eda-117">Where='%1'인 중복 CorrelationQuery가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17eda-117">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="17eda-118">이 중복 쿼리는 상관 관계를 계산할 때 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17eda-118">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="17eda-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="17eda-119">Details</span></span>  
  
|<span data-ttu-id="17eda-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="17eda-120">Data Item Name</span></span>|<span data-ttu-id="17eda-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="17eda-121">Data Item Type</span></span>|<span data-ttu-id="17eda-122">설명</span><span class="sxs-lookup"><span data-stu-id="17eda-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="17eda-123">Where</span><span class="sxs-lookup"><span data-stu-id="17eda-123">Where</span></span>|<span data-ttu-id="17eda-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="17eda-124">xs:string</span></span>|<span data-ttu-id="17eda-125">상관 관계 쿼리의 Where 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="17eda-125">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="17eda-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="17eda-126">AppDomain</span></span>|<span data-ttu-id="17eda-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="17eda-127">xs:string</span></span>|<span data-ttu-id="17eda-128">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="17eda-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
