---
description: '자세한 정보: 1002-WorkflowApplicationTerminated'
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: 8ceef41515231833767fc7e2095ab3850bf80e41
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755630"
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="e544d-103">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="e544d-103">1002 - WorkflowApplicationTerminated</span></span>

## <a name="properties"></a><span data-ttu-id="e544d-104">속성</span><span class="sxs-lookup"><span data-stu-id="e544d-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e544d-105">ID</span><span class="sxs-lookup"><span data-stu-id="e544d-105">ID</span></span>|<span data-ttu-id="e544d-106">1002</span><span class="sxs-lookup"><span data-stu-id="e544d-106">1002</span></span>|  
|<span data-ttu-id="e544d-107">키워드</span><span class="sxs-lookup"><span data-stu-id="e544d-107">Keywords</span></span>|<span data-ttu-id="e544d-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e544d-108">WFRuntime</span></span>|  
|<span data-ttu-id="e544d-109">Level</span><span class="sxs-lookup"><span data-stu-id="e544d-109">Level</span></span>|<span data-ttu-id="e544d-110">정보</span><span class="sxs-lookup"><span data-stu-id="e544d-110">Information</span></span>|  
|<span data-ttu-id="e544d-111">채널</span><span class="sxs-lookup"><span data-stu-id="e544d-111">Channel</span></span>|<span data-ttu-id="e544d-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="e544d-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e544d-113">설명</span><span class="sxs-lookup"><span data-stu-id="e544d-113">Description</span></span>  

 <span data-ttu-id="e544d-114">워크플로 애플리케이션에 예외가 발생하여 오류 상태로 종료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e544d-114">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e544d-115">메시지</span><span class="sxs-lookup"><span data-stu-id="e544d-115">Message</span></span>  

 <span data-ttu-id="e544d-116">WorkflowApplication Id: '%1'이(가) 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e544d-116">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="e544d-117">예외가 발생하여 오류 상태로 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e544d-117">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e544d-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e544d-118">Details</span></span>  
  
|<span data-ttu-id="e544d-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="e544d-119">Data Item Name</span></span>|<span data-ttu-id="e544d-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="e544d-120">Data Item Type</span></span>|<span data-ttu-id="e544d-121">설명</span><span class="sxs-lookup"><span data-stu-id="e544d-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e544d-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="e544d-122">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="e544d-123">워크플로 애플리케이션 ID</span><span class="sxs-lookup"><span data-stu-id="e544d-123">The workflow application id</span></span>|  
|<span data-ttu-id="e544d-124">예외</span><span class="sxs-lookup"><span data-stu-id="e544d-124">Exception</span></span>|`xs:string`|<span data-ttu-id="e544d-125">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="e544d-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="e544d-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e544d-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e544d-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e544d-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
