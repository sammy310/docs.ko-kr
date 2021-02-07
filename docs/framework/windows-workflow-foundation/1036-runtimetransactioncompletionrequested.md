---
description: '자세한 정보: 1036-RuntimeTransactionCompletionRequested'
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: e07400902d5c3e08732385ab30e1be0d72d3e997
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667891"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="d8bea-103">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="d8bea-103">1036 - RuntimeTransactionCompletionRequested</span></span>

## <a name="properties"></a><span data-ttu-id="d8bea-104">속성</span><span class="sxs-lookup"><span data-stu-id="d8bea-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8bea-105">ID</span><span class="sxs-lookup"><span data-stu-id="d8bea-105">ID</span></span>|<span data-ttu-id="d8bea-106">1036</span><span class="sxs-lookup"><span data-stu-id="d8bea-106">1036</span></span>|  
|<span data-ttu-id="d8bea-107">키워드</span><span class="sxs-lookup"><span data-stu-id="d8bea-107">Keywords</span></span>|<span data-ttu-id="d8bea-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d8bea-108">WFRuntime</span></span>|  
|<span data-ttu-id="d8bea-109">Level</span><span class="sxs-lookup"><span data-stu-id="d8bea-109">Level</span></span>|<span data-ttu-id="d8bea-110">자세히</span><span class="sxs-lookup"><span data-stu-id="d8bea-110">Verbose</span></span>|  
|<span data-ttu-id="d8bea-111">채널</span><span class="sxs-lookup"><span data-stu-id="d8bea-111">Channel</span></span>|<span data-ttu-id="d8bea-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="d8bea-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d8bea-113">설명</span><span class="sxs-lookup"><span data-stu-id="d8bea-113">Description</span></span>  

 <span data-ttu-id="d8bea-114">작업이 런타임 트랜잭션의 완료를 예약했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d8bea-114">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d8bea-115">메시지</span><span class="sxs-lookup"><span data-stu-id="d8bea-115">Message</span></span>  

 <span data-ttu-id="d8bea-116">작업 '%1', DisplayName: '%2', InstanceId: '%3'이(가) 런타임 트랜잭션 완료를 예약했습니다.</span><span class="sxs-lookup"><span data-stu-id="d8bea-116">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d8bea-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d8bea-117">Details</span></span>  
  
|<span data-ttu-id="d8bea-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="d8bea-118">Data Item Name</span></span>|<span data-ttu-id="d8bea-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="d8bea-119">Data Item Type</span></span>|<span data-ttu-id="d8bea-120">설명</span><span class="sxs-lookup"><span data-stu-id="d8bea-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d8bea-121">활동</span><span class="sxs-lookup"><span data-stu-id="d8bea-121">Activity</span></span>|<span data-ttu-id="d8bea-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8bea-122">xs:string</span></span>|<span data-ttu-id="d8bea-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8bea-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="d8bea-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d8bea-124">DisplayName</span></span>|<span data-ttu-id="d8bea-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8bea-125">xs:string</span></span>|<span data-ttu-id="d8bea-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8bea-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="d8bea-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d8bea-127">InstanceId</span></span>|<span data-ttu-id="d8bea-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8bea-128">xs:string</span></span>|<span data-ttu-id="d8bea-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8bea-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="d8bea-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d8bea-130">AppDomain</span></span>|<span data-ttu-id="d8bea-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8bea-131">xs:string</span></span>|<span data-ttu-id="d8bea-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d8bea-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
