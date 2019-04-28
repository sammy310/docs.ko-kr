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
# <a name="1104---workflowactivityresume"></a><span data-ttu-id="bb0dd-102">1104 - WorkflowActivityResume</span><span class="sxs-lookup"><span data-stu-id="bb0dd-102">1104 - WorkflowActivityResume</span></span>
## <a name="properties"></a><span data-ttu-id="bb0dd-103">속성</span><span class="sxs-lookup"><span data-stu-id="bb0dd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bb0dd-104">ID</span><span class="sxs-lookup"><span data-stu-id="bb0dd-104">ID</span></span>|<span data-ttu-id="bb0dd-105">1104</span><span class="sxs-lookup"><span data-stu-id="bb0dd-105">1104</span></span>|  
|<span data-ttu-id="bb0dd-106">키워드</span><span class="sxs-lookup"><span data-stu-id="bb0dd-106">Keywords</span></span>|<span data-ttu-id="bb0dd-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bb0dd-107">WFRuntime</span></span>|  
|<span data-ttu-id="bb0dd-108">수준</span><span class="sxs-lookup"><span data-stu-id="bb0dd-108">Level</span></span>|<span data-ttu-id="bb0dd-109">정보</span><span class="sxs-lookup"><span data-stu-id="bb0dd-109">Information</span></span>|  
|<span data-ttu-id="bb0dd-110">채널</span><span class="sxs-lookup"><span data-stu-id="bb0dd-110">Channel</span></span>|<span data-ttu-id="bb0dd-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="bb0dd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bb0dd-112">설명</span><span class="sxs-lookup"><span data-stu-id="bb0dd-112">Description</span></span>  
 <span data-ttu-id="bb0dd-113">워크플로 작업이 다시 시작되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bb0dd-113">Indicates a workflow activity has been resumed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bb0dd-114">메시지</span><span class="sxs-lookup"><span data-stu-id="bb0dd-114">Message</span></span>  
 <span data-ttu-id="bb0dd-115">WorkflowInstance Id: '%1' E2E 작업</span><span class="sxs-lookup"><span data-stu-id="bb0dd-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="bb0dd-116">설명</span><span class="sxs-lookup"><span data-stu-id="bb0dd-116">Details</span></span>  
  
|<span data-ttu-id="bb0dd-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="bb0dd-117">Data Item Name</span></span>|<span data-ttu-id="bb0dd-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="bb0dd-118">Data Item Type</span></span>|<span data-ttu-id="bb0dd-119">설명</span><span class="sxs-lookup"><span data-stu-id="bb0dd-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bb0dd-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="bb0dd-120">WorkflowInstanceId</span></span>|<span data-ttu-id="bb0dd-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="bb0dd-121">xs:string</span></span>|<span data-ttu-id="bb0dd-122">워크플로 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="bb0dd-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="bb0dd-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bb0dd-123">AppDomain</span></span>|<span data-ttu-id="bb0dd-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="bb0dd-124">xs:string</span></span>|<span data-ttu-id="bb0dd-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bb0dd-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
