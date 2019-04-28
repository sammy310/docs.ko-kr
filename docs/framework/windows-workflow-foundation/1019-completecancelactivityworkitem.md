---
title: 1019 - CompleteCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
ms.openlocfilehash: 28d19742055c51ca94c36ffddf15dced7dfc14cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924438"
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="bb41a-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="bb41a-102">1019 - CompleteCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="bb41a-103">속성</span><span class="sxs-lookup"><span data-stu-id="bb41a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bb41a-104">ID</span><span class="sxs-lookup"><span data-stu-id="bb41a-104">ID</span></span>|<span data-ttu-id="bb41a-105">1019</span><span class="sxs-lookup"><span data-stu-id="bb41a-105">1019</span></span>|  
|<span data-ttu-id="bb41a-106">키워드</span><span class="sxs-lookup"><span data-stu-id="bb41a-106">Keywords</span></span>|<span data-ttu-id="bb41a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bb41a-107">WFRuntime</span></span>|  
|<span data-ttu-id="bb41a-108">수준</span><span class="sxs-lookup"><span data-stu-id="bb41a-108">Level</span></span>|<span data-ttu-id="bb41a-109">자세히</span><span class="sxs-lookup"><span data-stu-id="bb41a-109">Verbose</span></span>|  
|<span data-ttu-id="bb41a-110">채널</span><span class="sxs-lookup"><span data-stu-id="bb41a-110">Channel</span></span>|<span data-ttu-id="bb41a-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="bb41a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bb41a-112">설명</span><span class="sxs-lookup"><span data-stu-id="bb41a-112">Description</span></span>  
 <span data-ttu-id="bb41a-113">CancelActivityWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bb41a-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bb41a-114">메시지</span><span class="sxs-lookup"><span data-stu-id="bb41a-114">Message</span></span>  
 <span data-ttu-id="bb41a-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CancelActivityWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bb41a-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bb41a-116">설명</span><span class="sxs-lookup"><span data-stu-id="bb41a-116">Details</span></span>  
  
|<span data-ttu-id="bb41a-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="bb41a-117">Data Item Name</span></span>|<span data-ttu-id="bb41a-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="bb41a-118">Data Item Type</span></span>|<span data-ttu-id="bb41a-119">설명</span><span class="sxs-lookup"><span data-stu-id="bb41a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bb41a-120">활동</span><span class="sxs-lookup"><span data-stu-id="bb41a-120">Activity</span></span>|<span data-ttu-id="bb41a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="bb41a-121">xs:string</span></span>|<span data-ttu-id="bb41a-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bb41a-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="bb41a-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="bb41a-123">DisplayName</span></span>|<span data-ttu-id="bb41a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="bb41a-124">xs:string</span></span>|<span data-ttu-id="bb41a-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bb41a-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="bb41a-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="bb41a-126">InstanceId</span></span>|<span data-ttu-id="bb41a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="bb41a-127">xs:string</span></span>|<span data-ttu-id="bb41a-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="bb41a-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="bb41a-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bb41a-129">AppDomain</span></span>|<span data-ttu-id="bb41a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="bb41a-130">xs:string</span></span>|<span data-ttu-id="bb41a-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bb41a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
