---
title: 1005 - WorkflowApplicationIdled
ms.date: 03/30/2017
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
ms.openlocfilehash: 6bbd12e8025b6a127dbfec8e5d3690825c188c4d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008605"
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="34efb-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="34efb-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="34efb-103">속성</span><span class="sxs-lookup"><span data-stu-id="34efb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34efb-104">ID</span><span class="sxs-lookup"><span data-stu-id="34efb-104">ID</span></span>|<span data-ttu-id="34efb-105">1005</span><span class="sxs-lookup"><span data-stu-id="34efb-105">1005</span></span>|  
|<span data-ttu-id="34efb-106">키워드</span><span class="sxs-lookup"><span data-stu-id="34efb-106">Keywords</span></span>|<span data-ttu-id="34efb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="34efb-107">WFRuntime</span></span>|  
|<span data-ttu-id="34efb-108">수준</span><span class="sxs-lookup"><span data-stu-id="34efb-108">Level</span></span>|<span data-ttu-id="34efb-109">정보</span><span class="sxs-lookup"><span data-stu-id="34efb-109">Information</span></span>|  
|<span data-ttu-id="34efb-110">채널</span><span class="sxs-lookup"><span data-stu-id="34efb-110">Channel</span></span>|<span data-ttu-id="34efb-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="34efb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="34efb-112">설명</span><span class="sxs-lookup"><span data-stu-id="34efb-112">Description</span></span>  
 <span data-ttu-id="34efb-113">워크플로 애플리케이션은 유휴 상태임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="34efb-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="34efb-114">메시지</span><span class="sxs-lookup"><span data-stu-id="34efb-114">Message</span></span>  
 <span data-ttu-id="34efb-115">WorkflowApplication Id: '%1'이(가) 유휴 상태가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="34efb-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="34efb-116">설명</span><span class="sxs-lookup"><span data-stu-id="34efb-116">Details</span></span>  
  
|<span data-ttu-id="34efb-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="34efb-117">Data Item Name</span></span>|<span data-ttu-id="34efb-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="34efb-118">Data Item Type</span></span>|<span data-ttu-id="34efb-119">설명</span><span class="sxs-lookup"><span data-stu-id="34efb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="34efb-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="34efb-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="34efb-121">워크플로 애플리케이션 ID</span><span class="sxs-lookup"><span data-stu-id="34efb-121">The workflow application id</span></span>|  
|<span data-ttu-id="34efb-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="34efb-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="34efb-123">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="34efb-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
