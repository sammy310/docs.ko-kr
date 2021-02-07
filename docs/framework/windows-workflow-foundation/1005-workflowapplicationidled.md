---
description: '자세한 정보: 1005-WorkflowApplicationIdled'
title: 1005 - WorkflowApplicationIdled
ms.date: 03/30/2017
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
ms.openlocfilehash: ee8d0b7ff2155333213a718a04c3966024fda89d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755605"
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="c6de8-103">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="c6de8-103">1005 - WorkflowApplicationIdled</span></span>

## <a name="properties"></a><span data-ttu-id="c6de8-104">속성</span><span class="sxs-lookup"><span data-stu-id="c6de8-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c6de8-105">ID</span><span class="sxs-lookup"><span data-stu-id="c6de8-105">ID</span></span>|<span data-ttu-id="c6de8-106">1005</span><span class="sxs-lookup"><span data-stu-id="c6de8-106">1005</span></span>|  
|<span data-ttu-id="c6de8-107">키워드</span><span class="sxs-lookup"><span data-stu-id="c6de8-107">Keywords</span></span>|<span data-ttu-id="c6de8-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c6de8-108">WFRuntime</span></span>|  
|<span data-ttu-id="c6de8-109">Level</span><span class="sxs-lookup"><span data-stu-id="c6de8-109">Level</span></span>|<span data-ttu-id="c6de8-110">정보</span><span class="sxs-lookup"><span data-stu-id="c6de8-110">Information</span></span>|  
|<span data-ttu-id="c6de8-111">채널</span><span class="sxs-lookup"><span data-stu-id="c6de8-111">Channel</span></span>|<span data-ttu-id="c6de8-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="c6de8-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c6de8-113">설명</span><span class="sxs-lookup"><span data-stu-id="c6de8-113">Description</span></span>  

 <span data-ttu-id="c6de8-114">워크플로 애플리케이션은 유휴 상태임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c6de8-114">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c6de8-115">메시지</span><span class="sxs-lookup"><span data-stu-id="c6de8-115">Message</span></span>  

 <span data-ttu-id="c6de8-116">WorkflowApplication Id: '%1'이(가) 유휴 상태가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c6de8-116">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c6de8-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="c6de8-117">Details</span></span>  
  
|<span data-ttu-id="c6de8-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="c6de8-118">Data Item Name</span></span>|<span data-ttu-id="c6de8-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="c6de8-119">Data Item Type</span></span>|<span data-ttu-id="c6de8-120">설명</span><span class="sxs-lookup"><span data-stu-id="c6de8-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c6de8-121">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="c6de8-121">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="c6de8-122">워크플로 애플리케이션 ID</span><span class="sxs-lookup"><span data-stu-id="c6de8-122">The workflow application id</span></span>|  
|<span data-ttu-id="c6de8-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c6de8-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="c6de8-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c6de8-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
