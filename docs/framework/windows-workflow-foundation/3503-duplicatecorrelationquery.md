---
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: e1e64824ee9a95757ed7c00aa17fa80898219401
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270330"
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="83adc-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="83adc-102">3503 - DuplicateCorrelationQuery</span></span>

## <a name="properties"></a><span data-ttu-id="83adc-103">속성</span><span class="sxs-lookup"><span data-stu-id="83adc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="83adc-104">ID</span><span class="sxs-lookup"><span data-stu-id="83adc-104">ID</span></span>|<span data-ttu-id="83adc-105">3503</span><span class="sxs-lookup"><span data-stu-id="83adc-105">3503</span></span>|  
|<span data-ttu-id="83adc-106">키워드</span><span class="sxs-lookup"><span data-stu-id="83adc-106">Keywords</span></span>|<span data-ttu-id="83adc-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="83adc-107">WFServices</span></span>|  
|<span data-ttu-id="83adc-108">Level</span><span class="sxs-lookup"><span data-stu-id="83adc-108">Level</span></span>|<span data-ttu-id="83adc-109">경고</span><span class="sxs-lookup"><span data-stu-id="83adc-109">Warning</span></span>|  
|<span data-ttu-id="83adc-110">채널</span><span class="sxs-lookup"><span data-stu-id="83adc-110">Channel</span></span>|<span data-ttu-id="83adc-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="83adc-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="83adc-112">Description</span><span class="sxs-lookup"><span data-stu-id="83adc-112">Description</span></span>  

 <span data-ttu-id="83adc-113">중복 CorrelationQuery를 찾았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="83adc-114">중복 쿼리는 상관 관계를 계산할 때 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="83adc-115">메시지</span><span class="sxs-lookup"><span data-stu-id="83adc-115">Message</span></span>  

 <span data-ttu-id="83adc-116">Where='%1'인 중복 CorrelationQuery가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="83adc-117">이 중복 쿼리는 상관 관계를 계산할 때 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="83adc-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="83adc-118">Details</span></span>  
  
|<span data-ttu-id="83adc-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="83adc-119">Data Item Name</span></span>|<span data-ttu-id="83adc-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="83adc-120">Data Item Type</span></span>|<span data-ttu-id="83adc-121">Description</span><span class="sxs-lookup"><span data-stu-id="83adc-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="83adc-122">Where</span><span class="sxs-lookup"><span data-stu-id="83adc-122">Where</span></span>|<span data-ttu-id="83adc-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="83adc-123">xs:string</span></span>|<span data-ttu-id="83adc-124">상관 관계 쿼리의 Where 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="83adc-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="83adc-125">AppDomain</span></span>|<span data-ttu-id="83adc-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="83adc-126">xs:string</span></span>|<span data-ttu-id="83adc-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
