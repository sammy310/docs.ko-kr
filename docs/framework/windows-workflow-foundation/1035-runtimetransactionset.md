---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: b8bf8431c4e2b82c6aac95820eb45de2a404e976
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294276"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="9e8bd-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="9e8bd-102">1035 - RuntimeTransactionSet</span></span>

## <a name="properties"></a><span data-ttu-id="9e8bd-103">속성</span><span class="sxs-lookup"><span data-stu-id="9e8bd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9e8bd-104">ID</span><span class="sxs-lookup"><span data-stu-id="9e8bd-104">ID</span></span>|<span data-ttu-id="9e8bd-105">1035</span><span class="sxs-lookup"><span data-stu-id="9e8bd-105">1035</span></span>|  
|<span data-ttu-id="9e8bd-106">키워드</span><span class="sxs-lookup"><span data-stu-id="9e8bd-106">Keywords</span></span>|<span data-ttu-id="9e8bd-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9e8bd-107">WFRuntime</span></span>|  
|<span data-ttu-id="9e8bd-108">Level</span><span class="sxs-lookup"><span data-stu-id="9e8bd-108">Level</span></span>|<span data-ttu-id="9e8bd-109">자세히</span><span class="sxs-lookup"><span data-stu-id="9e8bd-109">Verbose</span></span>|  
|<span data-ttu-id="9e8bd-110">채널</span><span class="sxs-lookup"><span data-stu-id="9e8bd-110">Channel</span></span>|<span data-ttu-id="9e8bd-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="9e8bd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9e8bd-112">Description</span><span class="sxs-lookup"><span data-stu-id="9e8bd-112">Description</span></span>  

 <span data-ttu-id="9e8bd-113">작업이 런타임 트랜잭션으로 설정되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e8bd-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9e8bd-114">메시지</span><span class="sxs-lookup"><span data-stu-id="9e8bd-114">Message</span></span>  

 <span data-ttu-id="9e8bd-115">작업 ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '이 (가) 런타임 트랜잭션을 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9e8bd-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="9e8bd-116">작업 ' %4 ', DisplayName: ' %5 ', InstanceId: ' %6 ' (으)로의 실행이 격리 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9e8bd-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9e8bd-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="9e8bd-117">Details</span></span>  
  
|<span data-ttu-id="9e8bd-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="9e8bd-118">Data Item Name</span></span>|<span data-ttu-id="9e8bd-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="9e8bd-119">Data Item Type</span></span>|<span data-ttu-id="9e8bd-120">Description</span><span class="sxs-lookup"><span data-stu-id="9e8bd-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9e8bd-121">활동</span><span class="sxs-lookup"><span data-stu-id="9e8bd-121">Activity</span></span>|<span data-ttu-id="9e8bd-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="9e8bd-122">xs:string</span></span>|<span data-ttu-id="9e8bd-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8bd-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="9e8bd-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9e8bd-124">DisplayName</span></span>|<span data-ttu-id="9e8bd-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="9e8bd-125">xs:string</span></span>|<span data-ttu-id="9e8bd-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8bd-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="9e8bd-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="9e8bd-127">InstanceId</span></span>|<span data-ttu-id="9e8bd-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="9e8bd-128">xs:string</span></span>|<span data-ttu-id="9e8bd-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8bd-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="9e8bd-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="9e8bd-130">IsolatedActivity</span></span>|<span data-ttu-id="9e8bd-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="9e8bd-131">xs:string</span></span>|<span data-ttu-id="9e8bd-132">트랜잭션이 격리된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8bd-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="9e8bd-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="9e8bd-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="9e8bd-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="9e8bd-134">xs:string</span></span>|<span data-ttu-id="9e8bd-135">트랜잭션이 격리된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8bd-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="9e8bd-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="9e8bd-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="9e8bd-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="9e8bd-137">xs:string</span></span>|<span data-ttu-id="9e8bd-138">트랜잭션이 격리된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8bd-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="9e8bd-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9e8bd-139">AppDomain</span></span>|<span data-ttu-id="9e8bd-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="9e8bd-140">xs:string</span></span>|<span data-ttu-id="9e8bd-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8bd-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
