---
description: '자세한 정보: 1041-WorkflowApplicationPersistableIdle'
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: eb004077a36ed3e78229df92a73972ed5feda665
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667761"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="ebd78-103">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="ebd78-103">1041 - WorkflowApplicationPersistableIdle</span></span>

## <a name="properties"></a><span data-ttu-id="ebd78-104">속성</span><span class="sxs-lookup"><span data-stu-id="ebd78-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ebd78-105">ID</span><span class="sxs-lookup"><span data-stu-id="ebd78-105">ID</span></span>|<span data-ttu-id="ebd78-106">1041</span><span class="sxs-lookup"><span data-stu-id="ebd78-106">1041</span></span>|  
|<span data-ttu-id="ebd78-107">키워드</span><span class="sxs-lookup"><span data-stu-id="ebd78-107">Keywords</span></span>|<span data-ttu-id="ebd78-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ebd78-108">WFRuntime</span></span>|  
|<span data-ttu-id="ebd78-109">Level</span><span class="sxs-lookup"><span data-stu-id="ebd78-109">Level</span></span>|<span data-ttu-id="ebd78-110">정보</span><span class="sxs-lookup"><span data-stu-id="ebd78-110">Information</span></span>|  
|<span data-ttu-id="ebd78-111">채널</span><span class="sxs-lookup"><span data-stu-id="ebd78-111">Channel</span></span>|<span data-ttu-id="ebd78-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="ebd78-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ebd78-113">설명</span><span class="sxs-lookup"><span data-stu-id="ebd78-113">Description</span></span>  

 <span data-ttu-id="ebd78-114">워크플로 애플리케이션이 유휴 상태이며 지속 가능함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ebd78-114">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="ebd78-115">워크플로 애플리케이션이 유휴 상태이거나 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebd78-115">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ebd78-116">메시지</span><span class="sxs-lookup"><span data-stu-id="ebd78-116">Message</span></span>  

 <span data-ttu-id="ebd78-117">WorkflowApplication Id: ' %1 '이 (가) 유휴 상태 이며 지속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebd78-117">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="ebd78-118">다음 작업이 수행 됩니다. %2.</span><span class="sxs-lookup"><span data-stu-id="ebd78-118">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ebd78-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="ebd78-119">Details</span></span>  
  
|<span data-ttu-id="ebd78-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="ebd78-120">Data Item Name</span></span>|<span data-ttu-id="ebd78-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="ebd78-121">Data Item Type</span></span>|<span data-ttu-id="ebd78-122">설명</span><span class="sxs-lookup"><span data-stu-id="ebd78-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ebd78-123">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="ebd78-123">WorkflowApplicationId</span></span>|<span data-ttu-id="ebd78-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ebd78-124">xs:string</span></span>|<span data-ttu-id="ebd78-125">워크플로 애플리케이션 ID</span><span class="sxs-lookup"><span data-stu-id="ebd78-125">The workflow application id</span></span>|  
|<span data-ttu-id="ebd78-126">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="ebd78-126">ActionTaken</span></span>|<span data-ttu-id="ebd78-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ebd78-127">xs:string</span></span>|<span data-ttu-id="ebd78-128">작업이 워크플로 애플리케이션에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebd78-128">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="ebd78-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ebd78-129">AppDomain</span></span>|<span data-ttu-id="ebd78-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ebd78-130">xs:string</span></span>|<span data-ttu-id="ebd78-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ebd78-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
