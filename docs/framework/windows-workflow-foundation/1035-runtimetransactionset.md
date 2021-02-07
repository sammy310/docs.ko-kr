---
description: '자세한 정보: 1035-RuntimeTransactionSet'
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 513ba49962a8f02ab47b8e5b762949cd09154a3c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667904"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="44c32-103">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="44c32-103">1035 - RuntimeTransactionSet</span></span>

## <a name="properties"></a><span data-ttu-id="44c32-104">속성</span><span class="sxs-lookup"><span data-stu-id="44c32-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44c32-105">ID</span><span class="sxs-lookup"><span data-stu-id="44c32-105">ID</span></span>|<span data-ttu-id="44c32-106">1035</span><span class="sxs-lookup"><span data-stu-id="44c32-106">1035</span></span>|  
|<span data-ttu-id="44c32-107">키워드</span><span class="sxs-lookup"><span data-stu-id="44c32-107">Keywords</span></span>|<span data-ttu-id="44c32-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="44c32-108">WFRuntime</span></span>|  
|<span data-ttu-id="44c32-109">Level</span><span class="sxs-lookup"><span data-stu-id="44c32-109">Level</span></span>|<span data-ttu-id="44c32-110">자세히</span><span class="sxs-lookup"><span data-stu-id="44c32-110">Verbose</span></span>|  
|<span data-ttu-id="44c32-111">채널</span><span class="sxs-lookup"><span data-stu-id="44c32-111">Channel</span></span>|<span data-ttu-id="44c32-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="44c32-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="44c32-113">설명</span><span class="sxs-lookup"><span data-stu-id="44c32-113">Description</span></span>  

 <span data-ttu-id="44c32-114">작업이 런타임 트랜잭션으로 설정되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44c32-114">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="44c32-115">메시지</span><span class="sxs-lookup"><span data-stu-id="44c32-115">Message</span></span>  

 <span data-ttu-id="44c32-116">작업 ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '이 (가) 런타임 트랜잭션을 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="44c32-116">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="44c32-117">작업 ' %4 ', DisplayName: ' %5 ', InstanceId: ' %6 ' (으)로의 실행이 격리 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="44c32-117">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="44c32-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="44c32-118">Details</span></span>  
  
|<span data-ttu-id="44c32-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="44c32-119">Data Item Name</span></span>|<span data-ttu-id="44c32-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="44c32-120">Data Item Type</span></span>|<span data-ttu-id="44c32-121">설명</span><span class="sxs-lookup"><span data-stu-id="44c32-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="44c32-122">활동</span><span class="sxs-lookup"><span data-stu-id="44c32-122">Activity</span></span>|<span data-ttu-id="44c32-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="44c32-123">xs:string</span></span>|<span data-ttu-id="44c32-124">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="44c32-124">The type name of the activity.</span></span>|  
|<span data-ttu-id="44c32-125">DisplayName</span><span class="sxs-lookup"><span data-stu-id="44c32-125">DisplayName</span></span>|<span data-ttu-id="44c32-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="44c32-126">xs:string</span></span>|<span data-ttu-id="44c32-127">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="44c32-127">The display name of the activity.</span></span>|  
|<span data-ttu-id="44c32-128">InstanceId</span><span class="sxs-lookup"><span data-stu-id="44c32-128">InstanceId</span></span>|<span data-ttu-id="44c32-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="44c32-129">xs:string</span></span>|<span data-ttu-id="44c32-130">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="44c32-130">The instance id of the activity.</span></span>|  
|<span data-ttu-id="44c32-131">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="44c32-131">IsolatedActivity</span></span>|<span data-ttu-id="44c32-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="44c32-132">xs:string</span></span>|<span data-ttu-id="44c32-133">트랜잭션이 격리된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="44c32-133">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="44c32-134">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="44c32-134">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="44c32-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="44c32-135">xs:string</span></span>|<span data-ttu-id="44c32-136">트랜잭션이 격리된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="44c32-136">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="44c32-137">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="44c32-137">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="44c32-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="44c32-138">xs:string</span></span>|<span data-ttu-id="44c32-139">트랜잭션이 격리된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="44c32-139">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="44c32-140">AppDomain</span><span class="sxs-lookup"><span data-stu-id="44c32-140">AppDomain</span></span>|<span data-ttu-id="44c32-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="44c32-141">xs:string</span></span>|<span data-ttu-id="44c32-142">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="44c32-142">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
