---
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: be97991be9b61908a23486da0ef255ebfbdc5485
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239954"
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="f6fb4-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="f6fb4-102">1001 - WorkflowApplicationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="f6fb4-103">속성</span><span class="sxs-lookup"><span data-stu-id="f6fb4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f6fb4-104">ID</span><span class="sxs-lookup"><span data-stu-id="f6fb4-104">ID</span></span>|<span data-ttu-id="f6fb4-105">1001</span><span class="sxs-lookup"><span data-stu-id="f6fb4-105">1001</span></span>|  
|<span data-ttu-id="f6fb4-106">키워드</span><span class="sxs-lookup"><span data-stu-id="f6fb4-106">Keywords</span></span>|<span data-ttu-id="f6fb4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f6fb4-107">WFRuntime</span></span>|  
|<span data-ttu-id="f6fb4-108">Level</span><span class="sxs-lookup"><span data-stu-id="f6fb4-108">Level</span></span>|<span data-ttu-id="f6fb4-109">정보</span><span class="sxs-lookup"><span data-stu-id="f6fb4-109">Information</span></span>|  
|<span data-ttu-id="f6fb4-110">채널</span><span class="sxs-lookup"><span data-stu-id="f6fb4-110">Channel</span></span>|<span data-ttu-id="f6fb4-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="f6fb4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f6fb4-112">Description</span><span class="sxs-lookup"><span data-stu-id="f6fb4-112">Description</span></span>  

 <span data-ttu-id="f6fb4-113">워크플로 애플리케이션이 Closed 상태에서 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f6fb4-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f6fb4-114">메시지</span><span class="sxs-lookup"><span data-stu-id="f6fb4-114">Message</span></span>  

 <span data-ttu-id="f6fb4-115">WorkflowInstance Id: '%1'이(가) Closed 상태에서 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f6fb4-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f6fb4-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="f6fb4-116">Details</span></span>  
  
|<span data-ttu-id="f6fb4-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f6fb4-117">Data Item Name</span></span>|<span data-ttu-id="f6fb4-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f6fb4-118">Data Item Type</span></span>|<span data-ttu-id="f6fb4-119">Description</span><span class="sxs-lookup"><span data-stu-id="f6fb4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f6fb4-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="f6fb4-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="f6fb4-121">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="f6fb4-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="f6fb4-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f6fb4-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f6fb4-123">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f6fb4-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
