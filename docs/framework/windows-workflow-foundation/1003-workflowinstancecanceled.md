---
title: 1003 - WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: c76a2dab6a95bda7f3969af07f814aba30071c7f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008631"
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="f055d-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="f055d-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="f055d-103">속성</span><span class="sxs-lookup"><span data-stu-id="f055d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f055d-104">ID</span><span class="sxs-lookup"><span data-stu-id="f055d-104">ID</span></span>|<span data-ttu-id="f055d-105">1003</span><span class="sxs-lookup"><span data-stu-id="f055d-105">1003</span></span>|  
|<span data-ttu-id="f055d-106">키워드</span><span class="sxs-lookup"><span data-stu-id="f055d-106">Keywords</span></span>|<span data-ttu-id="f055d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f055d-107">WFRuntime</span></span>|  
|<span data-ttu-id="f055d-108">수준</span><span class="sxs-lookup"><span data-stu-id="f055d-108">Level</span></span>|<span data-ttu-id="f055d-109">정보</span><span class="sxs-lookup"><span data-stu-id="f055d-109">Information</span></span>|  
|<span data-ttu-id="f055d-110">채널</span><span class="sxs-lookup"><span data-stu-id="f055d-110">Channel</span></span>|<span data-ttu-id="f055d-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="f055d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f055d-112">설명</span><span class="sxs-lookup"><span data-stu-id="f055d-112">Description</span></span>  
 <span data-ttu-id="f055d-113">워크플로 인스턴스가 Closed 상태에서 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f055d-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f055d-114">메시지</span><span class="sxs-lookup"><span data-stu-id="f055d-114">Message</span></span>  
 <span data-ttu-id="f055d-115">WorkflowInstance Id: '%1'이(가) Canceled 상태에서 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f055d-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f055d-116">설명</span><span class="sxs-lookup"><span data-stu-id="f055d-116">Details</span></span>  
  
|<span data-ttu-id="f055d-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f055d-117">Data Item Name</span></span>|<span data-ttu-id="f055d-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f055d-118">Data Item Type</span></span>|<span data-ttu-id="f055d-119">설명</span><span class="sxs-lookup"><span data-stu-id="f055d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f055d-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="f055d-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="f055d-121">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="f055d-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="f055d-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f055d-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f055d-123">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f055d-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
