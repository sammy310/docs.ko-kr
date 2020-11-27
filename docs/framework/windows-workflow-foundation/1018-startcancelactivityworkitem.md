---
title: 1018 - StartCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
ms.openlocfilehash: c1558e19b0de2dc5d22d4356b0f80c35e5b4fbc1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275507"
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="372f8-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="372f8-102">1018 - StartCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="372f8-103">속성</span><span class="sxs-lookup"><span data-stu-id="372f8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="372f8-104">ID</span><span class="sxs-lookup"><span data-stu-id="372f8-104">ID</span></span>|<span data-ttu-id="372f8-105">1018</span><span class="sxs-lookup"><span data-stu-id="372f8-105">1018</span></span>|  
|<span data-ttu-id="372f8-106">키워드</span><span class="sxs-lookup"><span data-stu-id="372f8-106">Keywords</span></span>|<span data-ttu-id="372f8-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="372f8-107">WFRuntime</span></span>|  
|<span data-ttu-id="372f8-108">Level</span><span class="sxs-lookup"><span data-stu-id="372f8-108">Level</span></span>|<span data-ttu-id="372f8-109">자세히</span><span class="sxs-lookup"><span data-stu-id="372f8-109">Verbose</span></span>|  
|<span data-ttu-id="372f8-110">채널</span><span class="sxs-lookup"><span data-stu-id="372f8-110">Channel</span></span>|<span data-ttu-id="372f8-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="372f8-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="372f8-112">Description</span><span class="sxs-lookup"><span data-stu-id="372f8-112">Description</span></span>  

 <span data-ttu-id="372f8-113">CancelActivityWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="372f8-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="372f8-114">메시지</span><span class="sxs-lookup"><span data-stu-id="372f8-114">Message</span></span>  

 <span data-ttu-id="372f8-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CancelActivityWorkItem의 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="372f8-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="372f8-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="372f8-116">Details</span></span>  
  
|<span data-ttu-id="372f8-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="372f8-117">Data Item Name</span></span>|<span data-ttu-id="372f8-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="372f8-118">Data Item Type</span></span>|<span data-ttu-id="372f8-119">Description</span><span class="sxs-lookup"><span data-stu-id="372f8-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="372f8-120">활동</span><span class="sxs-lookup"><span data-stu-id="372f8-120">Activity</span></span>|<span data-ttu-id="372f8-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="372f8-121">xs:string</span></span>|<span data-ttu-id="372f8-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="372f8-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="372f8-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="372f8-123">DisplayName</span></span>|<span data-ttu-id="372f8-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="372f8-124">xs:string</span></span>|<span data-ttu-id="372f8-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="372f8-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="372f8-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="372f8-126">InstanceId</span></span>|<span data-ttu-id="372f8-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="372f8-127">xs:string</span></span>|<span data-ttu-id="372f8-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="372f8-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="372f8-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="372f8-129">AppDomain</span></span>|<span data-ttu-id="372f8-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="372f8-130">xs:string</span></span>|<span data-ttu-id="372f8-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="372f8-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
