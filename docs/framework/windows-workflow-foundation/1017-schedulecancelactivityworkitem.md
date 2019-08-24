---
title: 1017 - ScheduleCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
ms.openlocfilehash: 186b012cdd554ec7dd0d195b460619cca04eddcb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924490"
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="4c98f-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="4c98f-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="4c98f-103">속성</span><span class="sxs-lookup"><span data-stu-id="4c98f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4c98f-104">ID</span><span class="sxs-lookup"><span data-stu-id="4c98f-104">ID</span></span>|<span data-ttu-id="4c98f-105">1017</span><span class="sxs-lookup"><span data-stu-id="4c98f-105">1017</span></span>|  
|<span data-ttu-id="4c98f-106">키워드</span><span class="sxs-lookup"><span data-stu-id="4c98f-106">Keywords</span></span>|<span data-ttu-id="4c98f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4c98f-107">WFRuntime</span></span>|  
|<span data-ttu-id="4c98f-108">수준</span><span class="sxs-lookup"><span data-stu-id="4c98f-108">Level</span></span>|<span data-ttu-id="4c98f-109">자세히</span><span class="sxs-lookup"><span data-stu-id="4c98f-109">Verbose</span></span>|  
|<span data-ttu-id="4c98f-110">채널</span><span class="sxs-lookup"><span data-stu-id="4c98f-110">Channel</span></span>|<span data-ttu-id="4c98f-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="4c98f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4c98f-112">설명</span><span class="sxs-lookup"><span data-stu-id="4c98f-112">Description</span></span>  
 <span data-ttu-id="4c98f-113">CancelActivityWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4c98f-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4c98f-114">메시지</span><span class="sxs-lookup"><span data-stu-id="4c98f-114">Message</span></span>  
 <span data-ttu-id="4c98f-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CancelActivityWorkItem이 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4c98f-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4c98f-116">설명</span><span class="sxs-lookup"><span data-stu-id="4c98f-116">Details</span></span>  
  
|<span data-ttu-id="4c98f-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="4c98f-117">Data Item Name</span></span>|<span data-ttu-id="4c98f-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="4c98f-118">Data Item Type</span></span>|<span data-ttu-id="4c98f-119">설명</span><span class="sxs-lookup"><span data-stu-id="4c98f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4c98f-120">활동</span><span class="sxs-lookup"><span data-stu-id="4c98f-120">Activity</span></span>|<span data-ttu-id="4c98f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c98f-121">xs:string</span></span>|<span data-ttu-id="4c98f-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4c98f-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="4c98f-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="4c98f-123">DisplayName</span></span>|<span data-ttu-id="4c98f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c98f-124">xs:string</span></span>|<span data-ttu-id="4c98f-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4c98f-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="4c98f-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="4c98f-126">InstanceId</span></span>|<span data-ttu-id="4c98f-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c98f-127">xs:string</span></span>|<span data-ttu-id="4c98f-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4c98f-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="4c98f-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4c98f-129">AppDomain</span></span>|<span data-ttu-id="4c98f-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c98f-130">xs:string</span></span>|<span data-ttu-id="4c98f-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4c98f-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
