---
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: 37a689b30b0bcab9124472deb98627afbe30dfee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755599"
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="0e65e-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="0e65e-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="0e65e-103">속성</span><span class="sxs-lookup"><span data-stu-id="0e65e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0e65e-104">ID</span><span class="sxs-lookup"><span data-stu-id="0e65e-104">ID</span></span>|<span data-ttu-id="0e65e-105">3503</span><span class="sxs-lookup"><span data-stu-id="0e65e-105">3503</span></span>|  
|<span data-ttu-id="0e65e-106">키워드</span><span class="sxs-lookup"><span data-stu-id="0e65e-106">Keywords</span></span>|<span data-ttu-id="0e65e-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="0e65e-107">WFServices</span></span>|  
|<span data-ttu-id="0e65e-108">수준</span><span class="sxs-lookup"><span data-stu-id="0e65e-108">Level</span></span>|<span data-ttu-id="0e65e-109">경고</span><span class="sxs-lookup"><span data-stu-id="0e65e-109">Warning</span></span>|  
|<span data-ttu-id="0e65e-110">채널</span><span class="sxs-lookup"><span data-stu-id="0e65e-110">Channel</span></span>|<span data-ttu-id="0e65e-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="0e65e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0e65e-112">설명</span><span class="sxs-lookup"><span data-stu-id="0e65e-112">Description</span></span>  
 <span data-ttu-id="0e65e-113">중복 CorrelationQuery를 찾았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e65e-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="0e65e-114">중복 쿼리는 상관 관계를 계산할 때 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e65e-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0e65e-115">메시지</span><span class="sxs-lookup"><span data-stu-id="0e65e-115">Message</span></span>  
 <span data-ttu-id="0e65e-116">Where='%1'인 중복 CorrelationQuery가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e65e-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="0e65e-117">이 중복 쿼리는 상관 관계를 계산할 때 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e65e-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0e65e-118">설명</span><span class="sxs-lookup"><span data-stu-id="0e65e-118">Details</span></span>  
  
|<span data-ttu-id="0e65e-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="0e65e-119">Data Item Name</span></span>|<span data-ttu-id="0e65e-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="0e65e-120">Data Item Type</span></span>|<span data-ttu-id="0e65e-121">설명</span><span class="sxs-lookup"><span data-stu-id="0e65e-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0e65e-122">Where</span><span class="sxs-lookup"><span data-stu-id="0e65e-122">Where</span></span>|<span data-ttu-id="0e65e-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="0e65e-123">xs:string</span></span>|<span data-ttu-id="0e65e-124">상관 관계 쿼리의 Where 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="0e65e-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="0e65e-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0e65e-125">AppDomain</span></span>|<span data-ttu-id="0e65e-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="0e65e-126">xs:string</span></span>|<span data-ttu-id="0e65e-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0e65e-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
