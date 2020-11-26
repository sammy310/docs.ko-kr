---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 9995823753fc78ca3f278cd635fcf6c7d2b84325
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238940"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="636cc-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="636cc-102">1041 - WorkflowApplicationPersistableIdle</span></span>

## <a name="properties"></a><span data-ttu-id="636cc-103">속성</span><span class="sxs-lookup"><span data-stu-id="636cc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="636cc-104">ID</span><span class="sxs-lookup"><span data-stu-id="636cc-104">ID</span></span>|<span data-ttu-id="636cc-105">1041</span><span class="sxs-lookup"><span data-stu-id="636cc-105">1041</span></span>|  
|<span data-ttu-id="636cc-106">키워드</span><span class="sxs-lookup"><span data-stu-id="636cc-106">Keywords</span></span>|<span data-ttu-id="636cc-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="636cc-107">WFRuntime</span></span>|  
|<span data-ttu-id="636cc-108">Level</span><span class="sxs-lookup"><span data-stu-id="636cc-108">Level</span></span>|<span data-ttu-id="636cc-109">정보</span><span class="sxs-lookup"><span data-stu-id="636cc-109">Information</span></span>|  
|<span data-ttu-id="636cc-110">채널</span><span class="sxs-lookup"><span data-stu-id="636cc-110">Channel</span></span>|<span data-ttu-id="636cc-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="636cc-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="636cc-112">Description</span><span class="sxs-lookup"><span data-stu-id="636cc-112">Description</span></span>  

 <span data-ttu-id="636cc-113">워크플로 애플리케이션이 유휴 상태이며 지속 가능함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="636cc-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="636cc-114">워크플로 애플리케이션이 유휴 상태이거나 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="636cc-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="636cc-115">메시지</span><span class="sxs-lookup"><span data-stu-id="636cc-115">Message</span></span>  

 <span data-ttu-id="636cc-116">WorkflowApplication Id: ' %1 '이 (가) 유휴 상태 이며 지속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="636cc-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="636cc-117">다음 작업이 수행 됩니다. %2.</span><span class="sxs-lookup"><span data-stu-id="636cc-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="636cc-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="636cc-118">Details</span></span>  
  
|<span data-ttu-id="636cc-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="636cc-119">Data Item Name</span></span>|<span data-ttu-id="636cc-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="636cc-120">Data Item Type</span></span>|<span data-ttu-id="636cc-121">Description</span><span class="sxs-lookup"><span data-stu-id="636cc-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="636cc-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="636cc-122">WorkflowApplicationId</span></span>|<span data-ttu-id="636cc-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="636cc-123">xs:string</span></span>|<span data-ttu-id="636cc-124">워크플로 애플리케이션 ID</span><span class="sxs-lookup"><span data-stu-id="636cc-124">The workflow application id</span></span>|  
|<span data-ttu-id="636cc-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="636cc-125">ActionTaken</span></span>|<span data-ttu-id="636cc-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="636cc-126">xs:string</span></span>|<span data-ttu-id="636cc-127">작업이 워크플로 애플리케이션에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="636cc-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="636cc-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="636cc-128">AppDomain</span></span>|<span data-ttu-id="636cc-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="636cc-129">xs:string</span></span>|<span data-ttu-id="636cc-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="636cc-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
