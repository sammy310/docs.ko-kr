---
title: 1010 - ActivityCompleted
ms.date: 03/30/2017
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
ms.openlocfilehash: d0ebf32ec1d5fe5b34ffe650d5547891be0eb665
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239915"
---
# <a name="1010---activitycompleted"></a><span data-ttu-id="62d89-102">1010 - ActivityCompleted</span><span class="sxs-lookup"><span data-stu-id="62d89-102">1010 - ActivityCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="62d89-103">속성</span><span class="sxs-lookup"><span data-stu-id="62d89-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="62d89-104">ID</span><span class="sxs-lookup"><span data-stu-id="62d89-104">ID</span></span>|<span data-ttu-id="62d89-105">1010</span><span class="sxs-lookup"><span data-stu-id="62d89-105">1010</span></span>|  
|<span data-ttu-id="62d89-106">키워드</span><span class="sxs-lookup"><span data-stu-id="62d89-106">Keywords</span></span>|<span data-ttu-id="62d89-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="62d89-107">WFRuntime</span></span>|  
|<span data-ttu-id="62d89-108">Level</span><span class="sxs-lookup"><span data-stu-id="62d89-108">Level</span></span>|<span data-ttu-id="62d89-109">정보</span><span class="sxs-lookup"><span data-stu-id="62d89-109">Information</span></span>|  
|<span data-ttu-id="62d89-110">채널</span><span class="sxs-lookup"><span data-stu-id="62d89-110">Channel</span></span>|<span data-ttu-id="62d89-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="62d89-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="62d89-112">Description</span><span class="sxs-lookup"><span data-stu-id="62d89-112">Description</span></span>  

 <span data-ttu-id="62d89-113">작업의 실행이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="62d89-113">Indicates an activity has completed execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="62d89-114">메시지</span><span class="sxs-lookup"><span data-stu-id="62d89-114">Message</span></span>  

 <span data-ttu-id="62d89-115">Activity '%1', DisplayName: '%2', InstanceId: '%3'이(가) '%4' 상태로 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62d89-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has completed in the '%4' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="62d89-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="62d89-116">Details</span></span>  
  
|<span data-ttu-id="62d89-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="62d89-117">Data Item Name</span></span>|<span data-ttu-id="62d89-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="62d89-118">Data Item Type</span></span>|<span data-ttu-id="62d89-119">Description</span><span class="sxs-lookup"><span data-stu-id="62d89-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="62d89-120">활동</span><span class="sxs-lookup"><span data-stu-id="62d89-120">Activity</span></span>|<span data-ttu-id="62d89-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="62d89-121">xs:string</span></span>|<span data-ttu-id="62d89-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="62d89-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="62d89-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="62d89-123">DisplayName</span></span>|<span data-ttu-id="62d89-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="62d89-124">xs:string</span></span>|<span data-ttu-id="62d89-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="62d89-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="62d89-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="62d89-126">InstanceId</span></span>|<span data-ttu-id="62d89-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="62d89-127">xs:string</span></span>|<span data-ttu-id="62d89-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="62d89-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="62d89-129">시스템 상태</span><span class="sxs-lookup"><span data-stu-id="62d89-129">State</span></span>|<span data-ttu-id="62d89-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="62d89-130">xs:string</span></span>|<span data-ttu-id="62d89-131">작업의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="62d89-131">The state of the activity.</span></span>|  
|<span data-ttu-id="62d89-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="62d89-132">AppDomain</span></span>|<span data-ttu-id="62d89-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="62d89-133">xs:string</span></span>|<span data-ttu-id="62d89-134">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="62d89-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
