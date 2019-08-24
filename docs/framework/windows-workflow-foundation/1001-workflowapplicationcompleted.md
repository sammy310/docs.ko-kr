---
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: 430174b96a499fff7e0156327bb15e066ce2ca36
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008644"
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="70c04-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="70c04-102">1001 - WorkflowApplicationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="70c04-103">속성</span><span class="sxs-lookup"><span data-stu-id="70c04-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="70c04-104">ID</span><span class="sxs-lookup"><span data-stu-id="70c04-104">ID</span></span>|<span data-ttu-id="70c04-105">1001</span><span class="sxs-lookup"><span data-stu-id="70c04-105">1001</span></span>|  
|<span data-ttu-id="70c04-106">키워드</span><span class="sxs-lookup"><span data-stu-id="70c04-106">Keywords</span></span>|<span data-ttu-id="70c04-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="70c04-107">WFRuntime</span></span>|  
|<span data-ttu-id="70c04-108">수준</span><span class="sxs-lookup"><span data-stu-id="70c04-108">Level</span></span>|<span data-ttu-id="70c04-109">정보</span><span class="sxs-lookup"><span data-stu-id="70c04-109">Information</span></span>|  
|<span data-ttu-id="70c04-110">채널</span><span class="sxs-lookup"><span data-stu-id="70c04-110">Channel</span></span>|<span data-ttu-id="70c04-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="70c04-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="70c04-112">설명</span><span class="sxs-lookup"><span data-stu-id="70c04-112">Description</span></span>  
 <span data-ttu-id="70c04-113">워크플로 애플리케이션이 Closed 상태에서 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="70c04-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="70c04-114">메시지</span><span class="sxs-lookup"><span data-stu-id="70c04-114">Message</span></span>  
 <span data-ttu-id="70c04-115">WorkflowInstance Id: '%1'이(가) Closed 상태에서 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70c04-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="70c04-116">설명</span><span class="sxs-lookup"><span data-stu-id="70c04-116">Details</span></span>  
  
|<span data-ttu-id="70c04-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="70c04-117">Data Item Name</span></span>|<span data-ttu-id="70c04-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="70c04-118">Data Item Type</span></span>|<span data-ttu-id="70c04-119">설명</span><span class="sxs-lookup"><span data-stu-id="70c04-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="70c04-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="70c04-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="70c04-121">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="70c04-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="70c04-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="70c04-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="70c04-123">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="70c04-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
