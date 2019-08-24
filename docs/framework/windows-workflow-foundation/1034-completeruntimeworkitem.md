---
title: 1034 - CompleteRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
ms.openlocfilehash: bd49c608a8f6a6caab6975850507a00a2c0edb03
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924555"
---
# <a name="1034---completeruntimeworkitem"></a><span data-ttu-id="356ed-102">1034 - CompleteRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="356ed-102">1034 - CompleteRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="356ed-103">속성</span><span class="sxs-lookup"><span data-stu-id="356ed-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="356ed-104">ID</span><span class="sxs-lookup"><span data-stu-id="356ed-104">ID</span></span>|<span data-ttu-id="356ed-105">1034</span><span class="sxs-lookup"><span data-stu-id="356ed-105">1034</span></span>|  
|<span data-ttu-id="356ed-106">키워드</span><span class="sxs-lookup"><span data-stu-id="356ed-106">Keywords</span></span>|<span data-ttu-id="356ed-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="356ed-107">WFRuntime</span></span>|  
|<span data-ttu-id="356ed-108">수준</span><span class="sxs-lookup"><span data-stu-id="356ed-108">Level</span></span>|<span data-ttu-id="356ed-109">자세히</span><span class="sxs-lookup"><span data-stu-id="356ed-109">Verbose</span></span>|  
|<span data-ttu-id="356ed-110">채널</span><span class="sxs-lookup"><span data-stu-id="356ed-110">Channel</span></span>|<span data-ttu-id="356ed-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="356ed-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="356ed-112">설명</span><span class="sxs-lookup"><span data-stu-id="356ed-112">Description</span></span>  
 <span data-ttu-id="356ed-113">RuntimeWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="356ed-113">Indicates a RuntimeWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="356ed-114">메시지</span><span class="sxs-lookup"><span data-stu-id="356ed-114">Message</span></span>  
 <span data-ttu-id="356ed-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="356ed-115">A runtime work item has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="356ed-116">설명</span><span class="sxs-lookup"><span data-stu-id="356ed-116">Details</span></span>  
  
|<span data-ttu-id="356ed-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="356ed-117">Data Item Name</span></span>|<span data-ttu-id="356ed-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="356ed-118">Data Item Type</span></span>|<span data-ttu-id="356ed-119">설명</span><span class="sxs-lookup"><span data-stu-id="356ed-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="356ed-120">활동</span><span class="sxs-lookup"><span data-stu-id="356ed-120">Activity</span></span>|<span data-ttu-id="356ed-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="356ed-121">xs:string</span></span>|<span data-ttu-id="356ed-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="356ed-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="356ed-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="356ed-123">DisplayName</span></span>|<span data-ttu-id="356ed-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="356ed-124">xs:string</span></span>|<span data-ttu-id="356ed-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="356ed-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="356ed-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="356ed-126">InstanceId</span></span>|<span data-ttu-id="356ed-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="356ed-127">xs:string</span></span>|<span data-ttu-id="356ed-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="356ed-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="356ed-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="356ed-129">AppDomain</span></span>|<span data-ttu-id="356ed-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="356ed-130">xs:string</span></span>|<span data-ttu-id="356ed-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="356ed-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
