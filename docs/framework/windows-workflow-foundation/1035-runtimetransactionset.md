---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 198e11dd94b0ad5cdc1e01c3611280754ca081d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924854"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="540ff-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="540ff-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="540ff-103">속성</span><span class="sxs-lookup"><span data-stu-id="540ff-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="540ff-104">ID</span><span class="sxs-lookup"><span data-stu-id="540ff-104">ID</span></span>|<span data-ttu-id="540ff-105">1035</span><span class="sxs-lookup"><span data-stu-id="540ff-105">1035</span></span>|  
|<span data-ttu-id="540ff-106">키워드</span><span class="sxs-lookup"><span data-stu-id="540ff-106">Keywords</span></span>|<span data-ttu-id="540ff-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="540ff-107">WFRuntime</span></span>|  
|<span data-ttu-id="540ff-108">수준</span><span class="sxs-lookup"><span data-stu-id="540ff-108">Level</span></span>|<span data-ttu-id="540ff-109">자세히</span><span class="sxs-lookup"><span data-stu-id="540ff-109">Verbose</span></span>|  
|<span data-ttu-id="540ff-110">채널</span><span class="sxs-lookup"><span data-stu-id="540ff-110">Channel</span></span>|<span data-ttu-id="540ff-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="540ff-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="540ff-112">설명</span><span class="sxs-lookup"><span data-stu-id="540ff-112">Description</span></span>  
 <span data-ttu-id="540ff-113">작업이 런타임 트랜잭션으로 설정되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="540ff-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="540ff-114">메시지</span><span class="sxs-lookup"><span data-stu-id="540ff-114">Message</span></span>  
 <span data-ttu-id="540ff-115">런타임 트랜잭션이 설정한 작업 '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="540ff-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="540ff-116">실행 격리 작업 '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="540ff-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="540ff-117">설명</span><span class="sxs-lookup"><span data-stu-id="540ff-117">Details</span></span>  
  
|<span data-ttu-id="540ff-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="540ff-118">Data Item Name</span></span>|<span data-ttu-id="540ff-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="540ff-119">Data Item Type</span></span>|<span data-ttu-id="540ff-120">설명</span><span class="sxs-lookup"><span data-stu-id="540ff-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="540ff-121">활동</span><span class="sxs-lookup"><span data-stu-id="540ff-121">Activity</span></span>|<span data-ttu-id="540ff-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="540ff-122">xs:string</span></span>|<span data-ttu-id="540ff-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="540ff-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="540ff-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="540ff-124">DisplayName</span></span>|<span data-ttu-id="540ff-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="540ff-125">xs:string</span></span>|<span data-ttu-id="540ff-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="540ff-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="540ff-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="540ff-127">InstanceId</span></span>|<span data-ttu-id="540ff-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="540ff-128">xs:string</span></span>|<span data-ttu-id="540ff-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="540ff-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="540ff-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="540ff-130">IsolatedActivity</span></span>|<span data-ttu-id="540ff-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="540ff-131">xs:string</span></span>|<span data-ttu-id="540ff-132">트랜잭션이 격리된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="540ff-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="540ff-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="540ff-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="540ff-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="540ff-134">xs:string</span></span>|<span data-ttu-id="540ff-135">트랜잭션이 격리된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="540ff-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="540ff-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="540ff-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="540ff-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="540ff-137">xs:string</span></span>|<span data-ttu-id="540ff-138">트랜잭션이 격리된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="540ff-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="540ff-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="540ff-139">AppDomain</span></span>|<span data-ttu-id="540ff-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="540ff-140">xs:string</span></span>|<span data-ttu-id="540ff-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="540ff-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
