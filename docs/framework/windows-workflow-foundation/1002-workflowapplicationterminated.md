---
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: e7c92dcc9ce472c50af6f0aa26c59f55d62fbb9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239941"
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="7c1e0-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="7c1e0-102">1002 - WorkflowApplicationTerminated</span></span>

## <a name="properties"></a><span data-ttu-id="7c1e0-103">속성</span><span class="sxs-lookup"><span data-stu-id="7c1e0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7c1e0-104">ID</span><span class="sxs-lookup"><span data-stu-id="7c1e0-104">ID</span></span>|<span data-ttu-id="7c1e0-105">1002</span><span class="sxs-lookup"><span data-stu-id="7c1e0-105">1002</span></span>|  
|<span data-ttu-id="7c1e0-106">키워드</span><span class="sxs-lookup"><span data-stu-id="7c1e0-106">Keywords</span></span>|<span data-ttu-id="7c1e0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7c1e0-107">WFRuntime</span></span>|  
|<span data-ttu-id="7c1e0-108">Level</span><span class="sxs-lookup"><span data-stu-id="7c1e0-108">Level</span></span>|<span data-ttu-id="7c1e0-109">정보</span><span class="sxs-lookup"><span data-stu-id="7c1e0-109">Information</span></span>|  
|<span data-ttu-id="7c1e0-110">채널</span><span class="sxs-lookup"><span data-stu-id="7c1e0-110">Channel</span></span>|<span data-ttu-id="7c1e0-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="7c1e0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7c1e0-112">Description</span><span class="sxs-lookup"><span data-stu-id="7c1e0-112">Description</span></span>  

 <span data-ttu-id="7c1e0-113">워크플로 애플리케이션에 예외가 발생하여 오류 상태로 종료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7c1e0-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7c1e0-114">메시지</span><span class="sxs-lookup"><span data-stu-id="7c1e0-114">Message</span></span>  

 <span data-ttu-id="7c1e0-115">WorkflowApplication Id: '%1'이(가) 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1e0-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="7c1e0-116">예외가 발생하여 오류 상태로 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1e0-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7c1e0-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="7c1e0-117">Details</span></span>  
  
|<span data-ttu-id="7c1e0-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="7c1e0-118">Data Item Name</span></span>|<span data-ttu-id="7c1e0-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="7c1e0-119">Data Item Type</span></span>|<span data-ttu-id="7c1e0-120">Description</span><span class="sxs-lookup"><span data-stu-id="7c1e0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7c1e0-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="7c1e0-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="7c1e0-122">워크플로 애플리케이션 ID</span><span class="sxs-lookup"><span data-stu-id="7c1e0-122">The workflow application id</span></span>|  
|<span data-ttu-id="7c1e0-123">예외</span><span class="sxs-lookup"><span data-stu-id="7c1e0-123">Exception</span></span>|`xs:string`|<span data-ttu-id="7c1e0-124">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="7c1e0-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="7c1e0-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7c1e0-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7c1e0-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7c1e0-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
