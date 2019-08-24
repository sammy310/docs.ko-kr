---
title: 1032 - ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: 505b852d54e256b2c2bfff8d90944dd4e993e0c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924867"
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="3abe0-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="3abe0-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="3abe0-103">속성</span><span class="sxs-lookup"><span data-stu-id="3abe0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3abe0-104">ID</span><span class="sxs-lookup"><span data-stu-id="3abe0-104">ID</span></span>|<span data-ttu-id="3abe0-105">1032</span><span class="sxs-lookup"><span data-stu-id="3abe0-105">1032</span></span>|  
|<span data-ttu-id="3abe0-106">키워드</span><span class="sxs-lookup"><span data-stu-id="3abe0-106">Keywords</span></span>|<span data-ttu-id="3abe0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3abe0-107">WFRuntime</span></span>|  
|<span data-ttu-id="3abe0-108">수준</span><span class="sxs-lookup"><span data-stu-id="3abe0-108">Level</span></span>|<span data-ttu-id="3abe0-109">자세히</span><span class="sxs-lookup"><span data-stu-id="3abe0-109">Verbose</span></span>|  
|<span data-ttu-id="3abe0-110">채널</span><span class="sxs-lookup"><span data-stu-id="3abe0-110">Channel</span></span>|<span data-ttu-id="3abe0-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="3abe0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3abe0-112">설명</span><span class="sxs-lookup"><span data-stu-id="3abe0-112">Description</span></span>  
 <span data-ttu-id="3abe0-113">RuntimeWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3abe0-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3abe0-114">메시지</span><span class="sxs-lookup"><span data-stu-id="3abe0-114">Message</span></span>  
 <span data-ttu-id="3abe0-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목이 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3abe0-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3abe0-116">설명</span><span class="sxs-lookup"><span data-stu-id="3abe0-116">Details</span></span>  
  
|<span data-ttu-id="3abe0-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="3abe0-117">Data Item Name</span></span>|<span data-ttu-id="3abe0-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="3abe0-118">Data Item Type</span></span>|<span data-ttu-id="3abe0-119">설명</span><span class="sxs-lookup"><span data-stu-id="3abe0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3abe0-120">활동</span><span class="sxs-lookup"><span data-stu-id="3abe0-120">Activity</span></span>|<span data-ttu-id="3abe0-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3abe0-121">xs:string</span></span>|<span data-ttu-id="3abe0-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3abe0-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="3abe0-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3abe0-123">DisplayName</span></span>|<span data-ttu-id="3abe0-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3abe0-124">xs:string</span></span>|<span data-ttu-id="3abe0-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3abe0-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="3abe0-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3abe0-126">InstanceId</span></span>|<span data-ttu-id="3abe0-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3abe0-127">xs:string</span></span>|<span data-ttu-id="3abe0-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3abe0-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3abe0-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3abe0-129">AppDomain</span></span>|<span data-ttu-id="3abe0-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3abe0-130">xs:string</span></span>|<span data-ttu-id="3abe0-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3abe0-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
