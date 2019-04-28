---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 471f3ecea66ebbd07a09686ab536a84b25d46e6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924711"
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="8996a-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="8996a-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="8996a-103">속성</span><span class="sxs-lookup"><span data-stu-id="8996a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8996a-104">ID</span><span class="sxs-lookup"><span data-stu-id="8996a-104">ID</span></span>|<span data-ttu-id="8996a-105">1006</span><span class="sxs-lookup"><span data-stu-id="8996a-105">1006</span></span>|  
|<span data-ttu-id="8996a-106">키워드</span><span class="sxs-lookup"><span data-stu-id="8996a-106">Keywords</span></span>|<span data-ttu-id="8996a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8996a-107">WFRuntime</span></span>|  
|<span data-ttu-id="8996a-108">수준</span><span class="sxs-lookup"><span data-stu-id="8996a-108">Level</span></span>|<span data-ttu-id="8996a-109">Error</span><span class="sxs-lookup"><span data-stu-id="8996a-109">Error</span></span>|  
|<span data-ttu-id="8996a-110">채널</span><span class="sxs-lookup"><span data-stu-id="8996a-110">Channel</span></span>|<span data-ttu-id="8996a-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="8996a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8996a-112">설명</span><span class="sxs-lookup"><span data-stu-id="8996a-112">Description</span></span>  
 <span data-ttu-id="8996a-113">워크플로 응용 프로그램에서 처리되지 않은 예외가 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8996a-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8996a-114">메시지</span><span class="sxs-lookup"><span data-stu-id="8996a-114">Message</span></span>  
 <span data-ttu-id="8996a-115">WorkflowInstance Id: '%1'에 처리 되지 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8996a-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="8996a-116">작업 '%2', DisplayName에서에서 발생 한 예외: '%3'.</span><span class="sxs-lookup"><span data-stu-id="8996a-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="8996a-117">다음 작업이 수행 됩니다. %4입니다.</span><span class="sxs-lookup"><span data-stu-id="8996a-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8996a-118">설명</span><span class="sxs-lookup"><span data-stu-id="8996a-118">Details</span></span>  
  
|<span data-ttu-id="8996a-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="8996a-119">Data Item Name</span></span>|<span data-ttu-id="8996a-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="8996a-120">Data Item Type</span></span>|<span data-ttu-id="8996a-121">설명</span><span class="sxs-lookup"><span data-stu-id="8996a-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8996a-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="8996a-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="8996a-123">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="8996a-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="8996a-124">예외</span><span class="sxs-lookup"><span data-stu-id="8996a-124">Exception</span></span>|`xs:string`|<span data-ttu-id="8996a-125">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="8996a-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="8996a-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8996a-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8996a-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8996a-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
