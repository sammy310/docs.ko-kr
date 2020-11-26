---
title: 1005 - WorkflowApplicationIdled
ms.date: 03/30/2017
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
ms.openlocfilehash: 3b7210246b7fb754145c8aa6128da3183cea9f91
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239863"
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="bcc16-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="bcc16-102">1005 - WorkflowApplicationIdled</span></span>

## <a name="properties"></a><span data-ttu-id="bcc16-103">속성</span><span class="sxs-lookup"><span data-stu-id="bcc16-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bcc16-104">ID</span><span class="sxs-lookup"><span data-stu-id="bcc16-104">ID</span></span>|<span data-ttu-id="bcc16-105">1005</span><span class="sxs-lookup"><span data-stu-id="bcc16-105">1005</span></span>|  
|<span data-ttu-id="bcc16-106">키워드</span><span class="sxs-lookup"><span data-stu-id="bcc16-106">Keywords</span></span>|<span data-ttu-id="bcc16-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bcc16-107">WFRuntime</span></span>|  
|<span data-ttu-id="bcc16-108">Level</span><span class="sxs-lookup"><span data-stu-id="bcc16-108">Level</span></span>|<span data-ttu-id="bcc16-109">정보</span><span class="sxs-lookup"><span data-stu-id="bcc16-109">Information</span></span>|  
|<span data-ttu-id="bcc16-110">채널</span><span class="sxs-lookup"><span data-stu-id="bcc16-110">Channel</span></span>|<span data-ttu-id="bcc16-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="bcc16-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bcc16-112">Description</span><span class="sxs-lookup"><span data-stu-id="bcc16-112">Description</span></span>  

 <span data-ttu-id="bcc16-113">워크플로 애플리케이션은 유휴 상태임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bcc16-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bcc16-114">메시지</span><span class="sxs-lookup"><span data-stu-id="bcc16-114">Message</span></span>  

 <span data-ttu-id="bcc16-115">WorkflowApplication Id: '%1'이(가) 유휴 상태가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc16-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bcc16-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="bcc16-116">Details</span></span>  
  
|<span data-ttu-id="bcc16-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="bcc16-117">Data Item Name</span></span>|<span data-ttu-id="bcc16-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="bcc16-118">Data Item Type</span></span>|<span data-ttu-id="bcc16-119">Description</span><span class="sxs-lookup"><span data-stu-id="bcc16-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bcc16-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="bcc16-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="bcc16-121">워크플로 애플리케이션 ID</span><span class="sxs-lookup"><span data-stu-id="bcc16-121">The workflow application id</span></span>|  
|<span data-ttu-id="bcc16-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bcc16-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="bcc16-123">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc16-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
