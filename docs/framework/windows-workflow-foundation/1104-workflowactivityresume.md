---
description: '자세한 정보: 1104-WorkflowActivityResume'
title: 1104 - WorkflowActivityResume
ms.date: 03/30/2017
ms.assetid: 7fe95d1e-34bd-43ca-b92e-587d2d248fff
ms.openlocfilehash: 875bbae9bdfd772cc9156cf544b7069d8d0b791f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667501"
---
# <a name="1104---workflowactivityresume"></a><span data-ttu-id="4c564-103">1104 - WorkflowActivityResume</span><span class="sxs-lookup"><span data-stu-id="4c564-103">1104 - WorkflowActivityResume</span></span>

## <a name="properties"></a><span data-ttu-id="4c564-104">속성</span><span class="sxs-lookup"><span data-stu-id="4c564-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4c564-105">ID</span><span class="sxs-lookup"><span data-stu-id="4c564-105">ID</span></span>|<span data-ttu-id="4c564-106">1104</span><span class="sxs-lookup"><span data-stu-id="4c564-106">1104</span></span>|  
|<span data-ttu-id="4c564-107">키워드</span><span class="sxs-lookup"><span data-stu-id="4c564-107">Keywords</span></span>|<span data-ttu-id="4c564-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4c564-108">WFRuntime</span></span>|  
|<span data-ttu-id="4c564-109">Level</span><span class="sxs-lookup"><span data-stu-id="4c564-109">Level</span></span>|<span data-ttu-id="4c564-110">정보</span><span class="sxs-lookup"><span data-stu-id="4c564-110">Information</span></span>|  
|<span data-ttu-id="4c564-111">채널</span><span class="sxs-lookup"><span data-stu-id="4c564-111">Channel</span></span>|<span data-ttu-id="4c564-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="4c564-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4c564-113">설명</span><span class="sxs-lookup"><span data-stu-id="4c564-113">Description</span></span>  

 <span data-ttu-id="4c564-114">워크플로 작업이 다시 시작되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4c564-114">Indicates a workflow activity has been resumed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4c564-115">메시지</span><span class="sxs-lookup"><span data-stu-id="4c564-115">Message</span></span>  

 <span data-ttu-id="4c564-116">WorkflowInstance Id: '%1' E2E 작업</span><span class="sxs-lookup"><span data-stu-id="4c564-116">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="4c564-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="4c564-117">Details</span></span>  
  
|<span data-ttu-id="4c564-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="4c564-118">Data Item Name</span></span>|<span data-ttu-id="4c564-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="4c564-119">Data Item Type</span></span>|<span data-ttu-id="4c564-120">설명</span><span class="sxs-lookup"><span data-stu-id="4c564-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4c564-121">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="4c564-121">WorkflowInstanceId</span></span>|<span data-ttu-id="4c564-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c564-122">xs:string</span></span>|<span data-ttu-id="4c564-123">워크플로 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4c564-123">The workflow instance id.</span></span>|  
|<span data-ttu-id="4c564-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4c564-124">AppDomain</span></span>|<span data-ttu-id="4c564-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c564-125">xs:string</span></span>|<span data-ttu-id="4c564-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4c564-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
