---
description: '자세한 정보: 1006-WorkflowApplicationUnhandledException'
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: bfccd0d12c5dac4caad1e84e95f1cd096a551aa0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755592"
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="419ef-103">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="419ef-103">1006 - WorkflowApplicationUnhandledException</span></span>

## <a name="properties"></a><span data-ttu-id="419ef-104">속성</span><span class="sxs-lookup"><span data-stu-id="419ef-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="419ef-105">ID</span><span class="sxs-lookup"><span data-stu-id="419ef-105">ID</span></span>|<span data-ttu-id="419ef-106">1006</span><span class="sxs-lookup"><span data-stu-id="419ef-106">1006</span></span>|  
|<span data-ttu-id="419ef-107">키워드</span><span class="sxs-lookup"><span data-stu-id="419ef-107">Keywords</span></span>|<span data-ttu-id="419ef-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="419ef-108">WFRuntime</span></span>|  
|<span data-ttu-id="419ef-109">Level</span><span class="sxs-lookup"><span data-stu-id="419ef-109">Level</span></span>|<span data-ttu-id="419ef-110">Error</span><span class="sxs-lookup"><span data-stu-id="419ef-110">Error</span></span>|  
|<span data-ttu-id="419ef-111">채널</span><span class="sxs-lookup"><span data-stu-id="419ef-111">Channel</span></span>|<span data-ttu-id="419ef-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="419ef-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="419ef-113">설명</span><span class="sxs-lookup"><span data-stu-id="419ef-113">Description</span></span>  

 <span data-ttu-id="419ef-114">워크플로 애플리케이션에서 처리되지 않은 예외가 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="419ef-114">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="419ef-115">메시지</span><span class="sxs-lookup"><span data-stu-id="419ef-115">Message</span></span>  

 <span data-ttu-id="419ef-116">WorkflowInstance Id: ' %1 '에서 처리 되지 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="419ef-116">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="419ef-117">작업 ' %2 ', DisplayName: ' %3 '에서 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="419ef-117">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="419ef-118">다음 작업이 수행 됩니다. %4.</span><span class="sxs-lookup"><span data-stu-id="419ef-118">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="419ef-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="419ef-119">Details</span></span>  
  
|<span data-ttu-id="419ef-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="419ef-120">Data Item Name</span></span>|<span data-ttu-id="419ef-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="419ef-121">Data Item Type</span></span>|<span data-ttu-id="419ef-122">설명</span><span class="sxs-lookup"><span data-stu-id="419ef-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="419ef-123">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="419ef-123">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="419ef-124">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="419ef-124">The instance id for the workflow</span></span>|  
|<span data-ttu-id="419ef-125">예외</span><span class="sxs-lookup"><span data-stu-id="419ef-125">Exception</span></span>|`xs:string`|<span data-ttu-id="419ef-126">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="419ef-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="419ef-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="419ef-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="419ef-128">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="419ef-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
