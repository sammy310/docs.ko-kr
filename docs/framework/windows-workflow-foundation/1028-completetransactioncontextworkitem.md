---
description: '자세한 정보: 1028-CompleteTransactionContextWorkItem'
title: 1028 - CompleteTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
ms.openlocfilehash: ae66072769c24ce8d44f92a88cd4232d20bde5f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755462"
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="0efeb-103">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="0efeb-103">1028 - CompleteTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="0efeb-104">속성</span><span class="sxs-lookup"><span data-stu-id="0efeb-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0efeb-105">ID</span><span class="sxs-lookup"><span data-stu-id="0efeb-105">ID</span></span>|<span data-ttu-id="0efeb-106">1028</span><span class="sxs-lookup"><span data-stu-id="0efeb-106">1028</span></span>|  
|<span data-ttu-id="0efeb-107">키워드</span><span class="sxs-lookup"><span data-stu-id="0efeb-107">Keywords</span></span>|<span data-ttu-id="0efeb-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0efeb-108">WFRuntime</span></span>|  
|<span data-ttu-id="0efeb-109">Level</span><span class="sxs-lookup"><span data-stu-id="0efeb-109">Level</span></span>|<span data-ttu-id="0efeb-110">자세히</span><span class="sxs-lookup"><span data-stu-id="0efeb-110">Verbose</span></span>|  
|<span data-ttu-id="0efeb-111">채널</span><span class="sxs-lookup"><span data-stu-id="0efeb-111">Channel</span></span>|<span data-ttu-id="0efeb-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="0efeb-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0efeb-113">설명</span><span class="sxs-lookup"><span data-stu-id="0efeb-113">Description</span></span>  

 <span data-ttu-id="0efeb-114">TransactionContextWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0efeb-114">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0efeb-115">메시지</span><span class="sxs-lookup"><span data-stu-id="0efeb-115">Message</span></span>  

 <span data-ttu-id="0efeb-116">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 TransactionContextWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0efeb-116">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0efeb-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="0efeb-117">Details</span></span>  
  
|<span data-ttu-id="0efeb-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="0efeb-118">Data Item Name</span></span>|<span data-ttu-id="0efeb-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="0efeb-119">Data Item Type</span></span>|<span data-ttu-id="0efeb-120">설명</span><span class="sxs-lookup"><span data-stu-id="0efeb-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0efeb-121">활동</span><span class="sxs-lookup"><span data-stu-id="0efeb-121">Activity</span></span>|<span data-ttu-id="0efeb-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0efeb-122">xs:string</span></span>|<span data-ttu-id="0efeb-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0efeb-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="0efeb-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0efeb-124">DisplayName</span></span>|<span data-ttu-id="0efeb-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0efeb-125">xs:string</span></span>|<span data-ttu-id="0efeb-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0efeb-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="0efeb-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0efeb-127">InstanceId</span></span>|<span data-ttu-id="0efeb-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0efeb-128">xs:string</span></span>|<span data-ttu-id="0efeb-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0efeb-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0efeb-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0efeb-130">AppDomain</span></span>|<span data-ttu-id="0efeb-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="0efeb-131">xs:string</span></span>|<span data-ttu-id="0efeb-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0efeb-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
