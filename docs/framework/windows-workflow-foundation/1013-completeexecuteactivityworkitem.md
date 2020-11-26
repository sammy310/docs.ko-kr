---
title: 1013 - CompleteExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
ms.openlocfilehash: 654f961088c371ab53e4a81f40e3c63335efb1a8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239590"
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="18270-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="18270-102">1013 - CompleteExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="18270-103">속성</span><span class="sxs-lookup"><span data-stu-id="18270-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="18270-104">ID</span><span class="sxs-lookup"><span data-stu-id="18270-104">ID</span></span>|<span data-ttu-id="18270-105">1013</span><span class="sxs-lookup"><span data-stu-id="18270-105">1013</span></span>|  
|<span data-ttu-id="18270-106">키워드</span><span class="sxs-lookup"><span data-stu-id="18270-106">Keywords</span></span>|<span data-ttu-id="18270-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="18270-107">WFRuntime</span></span>|  
|<span data-ttu-id="18270-108">Level</span><span class="sxs-lookup"><span data-stu-id="18270-108">Level</span></span>|<span data-ttu-id="18270-109">자세히</span><span class="sxs-lookup"><span data-stu-id="18270-109">Verbose</span></span>|  
|<span data-ttu-id="18270-110">채널</span><span class="sxs-lookup"><span data-stu-id="18270-110">Channel</span></span>|<span data-ttu-id="18270-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="18270-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="18270-112">Description</span><span class="sxs-lookup"><span data-stu-id="18270-112">Description</span></span>  

 <span data-ttu-id="18270-113">ExecuteActivityWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="18270-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="18270-114">메시지</span><span class="sxs-lookup"><span data-stu-id="18270-114">Message</span></span>  

 <span data-ttu-id="18270-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="18270-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="18270-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="18270-116">Details</span></span>  
  
|<span data-ttu-id="18270-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="18270-117">Data Item Name</span></span>|<span data-ttu-id="18270-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="18270-118">Data Item Type</span></span>|<span data-ttu-id="18270-119">Description</span><span class="sxs-lookup"><span data-stu-id="18270-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="18270-120">활동</span><span class="sxs-lookup"><span data-stu-id="18270-120">Activity</span></span>|<span data-ttu-id="18270-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="18270-121">xs:string</span></span>|<span data-ttu-id="18270-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="18270-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="18270-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="18270-123">DisplayName</span></span>|<span data-ttu-id="18270-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="18270-124">xs:string</span></span>|<span data-ttu-id="18270-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="18270-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="18270-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="18270-126">InstanceId</span></span>|<span data-ttu-id="18270-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="18270-127">xs:string</span></span>|<span data-ttu-id="18270-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="18270-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="18270-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="18270-129">AppDomain</span></span>|<span data-ttu-id="18270-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="18270-130">xs:string</span></span>|<span data-ttu-id="18270-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="18270-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
