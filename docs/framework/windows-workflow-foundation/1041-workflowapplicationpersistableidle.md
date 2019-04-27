---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 07be0ae603443a1ef06cb539bba7b227d7b3e325
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924191"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="3c590-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="3c590-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="3c590-103">속성</span><span class="sxs-lookup"><span data-stu-id="3c590-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c590-104">ID</span><span class="sxs-lookup"><span data-stu-id="3c590-104">ID</span></span>|<span data-ttu-id="3c590-105">1041</span><span class="sxs-lookup"><span data-stu-id="3c590-105">1041</span></span>|  
|<span data-ttu-id="3c590-106">키워드</span><span class="sxs-lookup"><span data-stu-id="3c590-106">Keywords</span></span>|<span data-ttu-id="3c590-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3c590-107">WFRuntime</span></span>|  
|<span data-ttu-id="3c590-108">수준</span><span class="sxs-lookup"><span data-stu-id="3c590-108">Level</span></span>|<span data-ttu-id="3c590-109">정보</span><span class="sxs-lookup"><span data-stu-id="3c590-109">Information</span></span>|  
|<span data-ttu-id="3c590-110">채널</span><span class="sxs-lookup"><span data-stu-id="3c590-110">Channel</span></span>|<span data-ttu-id="3c590-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="3c590-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3c590-112">설명</span><span class="sxs-lookup"><span data-stu-id="3c590-112">Description</span></span>  
 <span data-ttu-id="3c590-113">워크플로 응용 프로그램이 유휴 상태이며 지속 가능함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c590-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="3c590-114">워크플로 응용 프로그램이 유휴 상태이거나 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c590-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3c590-115">메시지</span><span class="sxs-lookup"><span data-stu-id="3c590-115">Message</span></span>  
 <span data-ttu-id="3c590-116">WorkflowApplication Id: '%1'은 유휴 상태 이며 지속 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c590-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="3c590-117">다음 작업이 수행 됩니다. %2.</span><span class="sxs-lookup"><span data-stu-id="3c590-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3c590-118">설명</span><span class="sxs-lookup"><span data-stu-id="3c590-118">Details</span></span>  
  
|<span data-ttu-id="3c590-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="3c590-119">Data Item Name</span></span>|<span data-ttu-id="3c590-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="3c590-120">Data Item Type</span></span>|<span data-ttu-id="3c590-121">설명</span><span class="sxs-lookup"><span data-stu-id="3c590-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3c590-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="3c590-122">WorkflowApplicationId</span></span>|<span data-ttu-id="3c590-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c590-123">xs:string</span></span>|<span data-ttu-id="3c590-124">워크플로 응용 프로그램 ID</span><span class="sxs-lookup"><span data-stu-id="3c590-124">The workflow application id</span></span>|  
|<span data-ttu-id="3c590-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="3c590-125">ActionTaken</span></span>|<span data-ttu-id="3c590-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c590-126">xs:string</span></span>|<span data-ttu-id="3c590-127">작업이 워크플로 응용 프로그램에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c590-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="3c590-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3c590-128">AppDomain</span></span>|<span data-ttu-id="3c590-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c590-129">xs:string</span></span>|<span data-ttu-id="3c590-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3c590-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
