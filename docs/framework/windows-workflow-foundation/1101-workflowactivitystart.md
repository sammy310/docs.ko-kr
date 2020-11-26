---
title: 1101 - WorkflowActivityStart
ms.date: 03/30/2017
ms.assetid: 831cd386-b9b5-47a9-9690-aff6292ff348
ms.openlocfilehash: 6e43b0ab1e2d35657bae43e7239a677643154fa9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238732"
---
# <a name="1101---workflowactivitystart"></a><span data-ttu-id="4ce45-102">1101 - WorkflowActivityStart</span><span class="sxs-lookup"><span data-stu-id="4ce45-102">1101 - WorkflowActivityStart</span></span>

## <a name="properties"></a><span data-ttu-id="4ce45-103">속성</span><span class="sxs-lookup"><span data-stu-id="4ce45-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4ce45-104">ID</span><span class="sxs-lookup"><span data-stu-id="4ce45-104">ID</span></span>|<span data-ttu-id="4ce45-105">1101</span><span class="sxs-lookup"><span data-stu-id="4ce45-105">1101</span></span>|  
|<span data-ttu-id="4ce45-106">키워드</span><span class="sxs-lookup"><span data-stu-id="4ce45-106">Keywords</span></span>|<span data-ttu-id="4ce45-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4ce45-107">WFRuntime</span></span>|  
|<span data-ttu-id="4ce45-108">Level</span><span class="sxs-lookup"><span data-stu-id="4ce45-108">Level</span></span>|<span data-ttu-id="4ce45-109">정보</span><span class="sxs-lookup"><span data-stu-id="4ce45-109">Information</span></span>|  
|<span data-ttu-id="4ce45-110">채널</span><span class="sxs-lookup"><span data-stu-id="4ce45-110">Channel</span></span>|<span data-ttu-id="4ce45-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="4ce45-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4ce45-112">Description</span><span class="sxs-lookup"><span data-stu-id="4ce45-112">Description</span></span>  

 <span data-ttu-id="4ce45-113">워크플로 작업이 시작되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4ce45-113">Indicates a workflow activity has started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4ce45-114">메시지</span><span class="sxs-lookup"><span data-stu-id="4ce45-114">Message</span></span>  

 <span data-ttu-id="4ce45-115">WorkflowInstance Id: '%1' E2E 작업</span><span class="sxs-lookup"><span data-stu-id="4ce45-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="4ce45-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="4ce45-116">Details</span></span>  
  
|<span data-ttu-id="4ce45-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="4ce45-117">Data Item Name</span></span>|<span data-ttu-id="4ce45-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="4ce45-118">Data Item Type</span></span>|<span data-ttu-id="4ce45-119">Description</span><span class="sxs-lookup"><span data-stu-id="4ce45-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4ce45-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="4ce45-120">WorkflowInstanceId</span></span>|<span data-ttu-id="4ce45-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ce45-121">xs:string</span></span>|<span data-ttu-id="4ce45-122">워크플로 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4ce45-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="4ce45-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4ce45-123">AppDomain</span></span>|<span data-ttu-id="4ce45-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ce45-124">xs:string</span></span>|<span data-ttu-id="4ce45-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4ce45-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
