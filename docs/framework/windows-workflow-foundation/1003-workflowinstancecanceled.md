---
description: '자세한 정보: 1003-WorkflowInstanceCanceled'
title: 1003 - WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: ef7b7c6849e96866204fe53deadce8302d18e0d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703369"
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="3b0ad-103">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="3b0ad-103">1003 - WorkflowInstanceCanceled</span></span>

## <a name="properties"></a><span data-ttu-id="3b0ad-104">속성</span><span class="sxs-lookup"><span data-stu-id="3b0ad-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3b0ad-105">ID</span><span class="sxs-lookup"><span data-stu-id="3b0ad-105">ID</span></span>|<span data-ttu-id="3b0ad-106">1003</span><span class="sxs-lookup"><span data-stu-id="3b0ad-106">1003</span></span>|  
|<span data-ttu-id="3b0ad-107">키워드</span><span class="sxs-lookup"><span data-stu-id="3b0ad-107">Keywords</span></span>|<span data-ttu-id="3b0ad-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3b0ad-108">WFRuntime</span></span>|  
|<span data-ttu-id="3b0ad-109">Level</span><span class="sxs-lookup"><span data-stu-id="3b0ad-109">Level</span></span>|<span data-ttu-id="3b0ad-110">정보</span><span class="sxs-lookup"><span data-stu-id="3b0ad-110">Information</span></span>|  
|<span data-ttu-id="3b0ad-111">채널</span><span class="sxs-lookup"><span data-stu-id="3b0ad-111">Channel</span></span>|<span data-ttu-id="3b0ad-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="3b0ad-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3b0ad-113">설명</span><span class="sxs-lookup"><span data-stu-id="3b0ad-113">Description</span></span>  

 <span data-ttu-id="3b0ad-114">워크플로 인스턴스가 Closed 상태에서 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-114">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3b0ad-115">메시지</span><span class="sxs-lookup"><span data-stu-id="3b0ad-115">Message</span></span>  

 <span data-ttu-id="3b0ad-116">WorkflowInstance Id: '%1'이(가) Canceled 상태에서 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-116">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3b0ad-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="3b0ad-117">Details</span></span>  
  
|<span data-ttu-id="3b0ad-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="3b0ad-118">Data Item Name</span></span>|<span data-ttu-id="3b0ad-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="3b0ad-119">Data Item Type</span></span>|<span data-ttu-id="3b0ad-120">설명</span><span class="sxs-lookup"><span data-stu-id="3b0ad-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3b0ad-121">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="3b0ad-121">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="3b0ad-122">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="3b0ad-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="3b0ad-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3b0ad-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="3b0ad-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
