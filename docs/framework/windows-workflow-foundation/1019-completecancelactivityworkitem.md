---
title: 1019 - CompleteCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
ms.openlocfilehash: 903b497fb3f244fd40c6888829ef71dddd455251
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275481"
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="3e67e-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="3e67e-102">1019 - CompleteCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="3e67e-103">속성</span><span class="sxs-lookup"><span data-stu-id="3e67e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3e67e-104">ID</span><span class="sxs-lookup"><span data-stu-id="3e67e-104">ID</span></span>|<span data-ttu-id="3e67e-105">1019</span><span class="sxs-lookup"><span data-stu-id="3e67e-105">1019</span></span>|  
|<span data-ttu-id="3e67e-106">키워드</span><span class="sxs-lookup"><span data-stu-id="3e67e-106">Keywords</span></span>|<span data-ttu-id="3e67e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3e67e-107">WFRuntime</span></span>|  
|<span data-ttu-id="3e67e-108">Level</span><span class="sxs-lookup"><span data-stu-id="3e67e-108">Level</span></span>|<span data-ttu-id="3e67e-109">자세히</span><span class="sxs-lookup"><span data-stu-id="3e67e-109">Verbose</span></span>|  
|<span data-ttu-id="3e67e-110">채널</span><span class="sxs-lookup"><span data-stu-id="3e67e-110">Channel</span></span>|<span data-ttu-id="3e67e-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="3e67e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3e67e-112">Description</span><span class="sxs-lookup"><span data-stu-id="3e67e-112">Description</span></span>  

 <span data-ttu-id="3e67e-113">CancelActivityWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3e67e-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3e67e-114">메시지</span><span class="sxs-lookup"><span data-stu-id="3e67e-114">Message</span></span>  

 <span data-ttu-id="3e67e-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CancelActivityWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3e67e-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3e67e-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="3e67e-116">Details</span></span>  
  
|<span data-ttu-id="3e67e-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="3e67e-117">Data Item Name</span></span>|<span data-ttu-id="3e67e-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="3e67e-118">Data Item Type</span></span>|<span data-ttu-id="3e67e-119">Description</span><span class="sxs-lookup"><span data-stu-id="3e67e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3e67e-120">활동</span><span class="sxs-lookup"><span data-stu-id="3e67e-120">Activity</span></span>|<span data-ttu-id="3e67e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e67e-121">xs:string</span></span>|<span data-ttu-id="3e67e-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3e67e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="3e67e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3e67e-123">DisplayName</span></span>|<span data-ttu-id="3e67e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e67e-124">xs:string</span></span>|<span data-ttu-id="3e67e-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3e67e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="3e67e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3e67e-126">InstanceId</span></span>|<span data-ttu-id="3e67e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e67e-127">xs:string</span></span>|<span data-ttu-id="3e67e-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3e67e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3e67e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3e67e-129">AppDomain</span></span>|<span data-ttu-id="3e67e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e67e-130">xs:string</span></span>|<span data-ttu-id="3e67e-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3e67e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
