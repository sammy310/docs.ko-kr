---
title: 1104 - WorkflowActivityResume
ms.date: 03/30/2017
ms.assetid: 7fe95d1e-34bd-43ca-b92e-587d2d248fff
ms.openlocfilehash: 4c9ae5fd386fc93ea19578097aa4e0afdda527e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924126"
---
# <a name="1104---workflowactivityresume"></a><span data-ttu-id="e6465-102">1104 - WorkflowActivityResume</span><span class="sxs-lookup"><span data-stu-id="e6465-102">1104 - WorkflowActivityResume</span></span>
## <a name="properties"></a><span data-ttu-id="e6465-103">속성</span><span class="sxs-lookup"><span data-stu-id="e6465-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e6465-104">ID</span><span class="sxs-lookup"><span data-stu-id="e6465-104">ID</span></span>|<span data-ttu-id="e6465-105">1104</span><span class="sxs-lookup"><span data-stu-id="e6465-105">1104</span></span>|  
|<span data-ttu-id="e6465-106">키워드</span><span class="sxs-lookup"><span data-stu-id="e6465-106">Keywords</span></span>|<span data-ttu-id="e6465-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e6465-107">WFRuntime</span></span>|  
|<span data-ttu-id="e6465-108">수준</span><span class="sxs-lookup"><span data-stu-id="e6465-108">Level</span></span>|<span data-ttu-id="e6465-109">정보</span><span class="sxs-lookup"><span data-stu-id="e6465-109">Information</span></span>|  
|<span data-ttu-id="e6465-110">채널</span><span class="sxs-lookup"><span data-stu-id="e6465-110">Channel</span></span>|<span data-ttu-id="e6465-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="e6465-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e6465-112">설명</span><span class="sxs-lookup"><span data-stu-id="e6465-112">Description</span></span>  
 <span data-ttu-id="e6465-113">워크플로 작업이 다시 시작되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e6465-113">Indicates a workflow activity has been resumed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e6465-114">메시지</span><span class="sxs-lookup"><span data-stu-id="e6465-114">Message</span></span>  
 <span data-ttu-id="e6465-115">WorkflowInstance Id: '%1' E2E 작업</span><span class="sxs-lookup"><span data-stu-id="e6465-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="e6465-116">설명</span><span class="sxs-lookup"><span data-stu-id="e6465-116">Details</span></span>  
  
|<span data-ttu-id="e6465-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="e6465-117">Data Item Name</span></span>|<span data-ttu-id="e6465-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="e6465-118">Data Item Type</span></span>|<span data-ttu-id="e6465-119">설명</span><span class="sxs-lookup"><span data-stu-id="e6465-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e6465-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="e6465-120">WorkflowInstanceId</span></span>|<span data-ttu-id="e6465-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e6465-121">xs:string</span></span>|<span data-ttu-id="e6465-122">워크플로 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e6465-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="e6465-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e6465-123">AppDomain</span></span>|<span data-ttu-id="e6465-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e6465-124">xs:string</span></span>|<span data-ttu-id="e6465-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e6465-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
