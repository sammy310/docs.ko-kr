---
description: '자세한 정보: 1008-WorkflowApplicationUnloaded'
title: 1008 - WorkflowApplicationUnloaded
ms.date: 03/30/2017
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
ms.openlocfilehash: 5e906c0daae525accc3b8b13c907479d18f2fc8c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755566"
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="ae06f-103">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="ae06f-103">1008 - WorkflowApplicationUnloaded</span></span>

## <a name="properties"></a><span data-ttu-id="ae06f-104">속성</span><span class="sxs-lookup"><span data-stu-id="ae06f-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ae06f-105">ID</span><span class="sxs-lookup"><span data-stu-id="ae06f-105">ID</span></span>|<span data-ttu-id="ae06f-106">1008</span><span class="sxs-lookup"><span data-stu-id="ae06f-106">1008</span></span>|  
|<span data-ttu-id="ae06f-107">키워드</span><span class="sxs-lookup"><span data-stu-id="ae06f-107">Keywords</span></span>|<span data-ttu-id="ae06f-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ae06f-108">WFRuntime</span></span>|  
|<span data-ttu-id="ae06f-109">Level</span><span class="sxs-lookup"><span data-stu-id="ae06f-109">Level</span></span>|<span data-ttu-id="ae06f-110">정보</span><span class="sxs-lookup"><span data-stu-id="ae06f-110">Information</span></span>|  
|<span data-ttu-id="ae06f-111">채널</span><span class="sxs-lookup"><span data-stu-id="ae06f-111">Channel</span></span>|<span data-ttu-id="ae06f-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="ae06f-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ae06f-113">설명</span><span class="sxs-lookup"><span data-stu-id="ae06f-113">Description</span></span>  

 <span data-ttu-id="ae06f-114">워크플로 애플리케이션이 언로드되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae06f-114">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ae06f-115">메시지</span><span class="sxs-lookup"><span data-stu-id="ae06f-115">Message</span></span>  

 <span data-ttu-id="ae06f-116">WorkflowInstance Id: '%1'이(가) 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ae06f-116">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ae06f-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="ae06f-117">Details</span></span>  
  
|<span data-ttu-id="ae06f-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="ae06f-118">Data Item Name</span></span>|<span data-ttu-id="ae06f-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="ae06f-119">Data Item Type</span></span>|<span data-ttu-id="ae06f-120">설명</span><span class="sxs-lookup"><span data-stu-id="ae06f-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ae06f-121">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="ae06f-121">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="ae06f-122">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="ae06f-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="ae06f-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ae06f-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ae06f-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ae06f-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
