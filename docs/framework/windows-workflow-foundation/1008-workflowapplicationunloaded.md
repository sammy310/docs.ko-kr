---
title: 1008 - WorkflowApplicationUnloaded
ms.date: 03/30/2017
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
ms.openlocfilehash: 6ea121e7901d877d4f0d8f9f5bfd259c2f93696d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239823"
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="1774e-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="1774e-102">1008 - WorkflowApplicationUnloaded</span></span>

## <a name="properties"></a><span data-ttu-id="1774e-103">속성</span><span class="sxs-lookup"><span data-stu-id="1774e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1774e-104">ID</span><span class="sxs-lookup"><span data-stu-id="1774e-104">ID</span></span>|<span data-ttu-id="1774e-105">1008</span><span class="sxs-lookup"><span data-stu-id="1774e-105">1008</span></span>|  
|<span data-ttu-id="1774e-106">키워드</span><span class="sxs-lookup"><span data-stu-id="1774e-106">Keywords</span></span>|<span data-ttu-id="1774e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1774e-107">WFRuntime</span></span>|  
|<span data-ttu-id="1774e-108">Level</span><span class="sxs-lookup"><span data-stu-id="1774e-108">Level</span></span>|<span data-ttu-id="1774e-109">정보</span><span class="sxs-lookup"><span data-stu-id="1774e-109">Information</span></span>|  
|<span data-ttu-id="1774e-110">채널</span><span class="sxs-lookup"><span data-stu-id="1774e-110">Channel</span></span>|<span data-ttu-id="1774e-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="1774e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1774e-112">Description</span><span class="sxs-lookup"><span data-stu-id="1774e-112">Description</span></span>  

 <span data-ttu-id="1774e-113">워크플로 애플리케이션이 언로드되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1774e-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1774e-114">메시지</span><span class="sxs-lookup"><span data-stu-id="1774e-114">Message</span></span>  

 <span data-ttu-id="1774e-115">WorkflowInstance Id: '%1'이(가) 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1774e-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1774e-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="1774e-116">Details</span></span>  
  
|<span data-ttu-id="1774e-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="1774e-117">Data Item Name</span></span>|<span data-ttu-id="1774e-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="1774e-118">Data Item Type</span></span>|<span data-ttu-id="1774e-119">Description</span><span class="sxs-lookup"><span data-stu-id="1774e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1774e-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="1774e-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="1774e-121">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="1774e-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="1774e-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1774e-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1774e-123">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1774e-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
