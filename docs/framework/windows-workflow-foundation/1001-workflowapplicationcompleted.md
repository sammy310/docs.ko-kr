---
description: '자세한 정보: 1001-WorkflowApplicationCompleted'
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: d32028bbe582f4a1e31796ed1f75e41c651e6c59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755644"
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="f5001-103">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="f5001-103">1001 - WorkflowApplicationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="f5001-104">속성</span><span class="sxs-lookup"><span data-stu-id="f5001-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f5001-105">ID</span><span class="sxs-lookup"><span data-stu-id="f5001-105">ID</span></span>|<span data-ttu-id="f5001-106">1001</span><span class="sxs-lookup"><span data-stu-id="f5001-106">1001</span></span>|  
|<span data-ttu-id="f5001-107">키워드</span><span class="sxs-lookup"><span data-stu-id="f5001-107">Keywords</span></span>|<span data-ttu-id="f5001-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f5001-108">WFRuntime</span></span>|  
|<span data-ttu-id="f5001-109">Level</span><span class="sxs-lookup"><span data-stu-id="f5001-109">Level</span></span>|<span data-ttu-id="f5001-110">정보</span><span class="sxs-lookup"><span data-stu-id="f5001-110">Information</span></span>|  
|<span data-ttu-id="f5001-111">채널</span><span class="sxs-lookup"><span data-stu-id="f5001-111">Channel</span></span>|<span data-ttu-id="f5001-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="f5001-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f5001-113">설명</span><span class="sxs-lookup"><span data-stu-id="f5001-113">Description</span></span>  

 <span data-ttu-id="f5001-114">워크플로 애플리케이션이 Closed 상태에서 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f5001-114">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f5001-115">메시지</span><span class="sxs-lookup"><span data-stu-id="f5001-115">Message</span></span>  

 <span data-ttu-id="f5001-116">WorkflowInstance Id: '%1'이(가) Closed 상태에서 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f5001-116">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f5001-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="f5001-117">Details</span></span>  
  
|<span data-ttu-id="f5001-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f5001-118">Data Item Name</span></span>|<span data-ttu-id="f5001-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f5001-119">Data Item Type</span></span>|<span data-ttu-id="f5001-120">설명</span><span class="sxs-lookup"><span data-stu-id="f5001-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f5001-121">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="f5001-121">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="f5001-122">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="f5001-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="f5001-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f5001-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f5001-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f5001-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
