---
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 96ea253fd61652a3719eaf8b1a4d31aa88337eeb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294263"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="e968d-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="e968d-102">1036 - RuntimeTransactionCompletionRequested</span></span>

## <a name="properties"></a><span data-ttu-id="e968d-103">속성</span><span class="sxs-lookup"><span data-stu-id="e968d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e968d-104">ID</span><span class="sxs-lookup"><span data-stu-id="e968d-104">ID</span></span>|<span data-ttu-id="e968d-105">1036</span><span class="sxs-lookup"><span data-stu-id="e968d-105">1036</span></span>|  
|<span data-ttu-id="e968d-106">키워드</span><span class="sxs-lookup"><span data-stu-id="e968d-106">Keywords</span></span>|<span data-ttu-id="e968d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e968d-107">WFRuntime</span></span>|  
|<span data-ttu-id="e968d-108">Level</span><span class="sxs-lookup"><span data-stu-id="e968d-108">Level</span></span>|<span data-ttu-id="e968d-109">자세히</span><span class="sxs-lookup"><span data-stu-id="e968d-109">Verbose</span></span>|  
|<span data-ttu-id="e968d-110">채널</span><span class="sxs-lookup"><span data-stu-id="e968d-110">Channel</span></span>|<span data-ttu-id="e968d-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="e968d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e968d-112">Description</span><span class="sxs-lookup"><span data-stu-id="e968d-112">Description</span></span>  

 <span data-ttu-id="e968d-113">작업이 런타임 트랜잭션의 완료를 예약했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e968d-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e968d-114">메시지</span><span class="sxs-lookup"><span data-stu-id="e968d-114">Message</span></span>  

 <span data-ttu-id="e968d-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'이(가) 런타임 트랜잭션 완료를 예약했습니다.</span><span class="sxs-lookup"><span data-stu-id="e968d-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e968d-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e968d-116">Details</span></span>  
  
|<span data-ttu-id="e968d-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="e968d-117">Data Item Name</span></span>|<span data-ttu-id="e968d-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="e968d-118">Data Item Type</span></span>|<span data-ttu-id="e968d-119">Description</span><span class="sxs-lookup"><span data-stu-id="e968d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e968d-120">활동</span><span class="sxs-lookup"><span data-stu-id="e968d-120">Activity</span></span>|<span data-ttu-id="e968d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e968d-121">xs:string</span></span>|<span data-ttu-id="e968d-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e968d-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="e968d-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e968d-123">DisplayName</span></span>|<span data-ttu-id="e968d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e968d-124">xs:string</span></span>|<span data-ttu-id="e968d-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e968d-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="e968d-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e968d-126">InstanceId</span></span>|<span data-ttu-id="e968d-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="e968d-127">xs:string</span></span>|<span data-ttu-id="e968d-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e968d-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="e968d-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e968d-129">AppDomain</span></span>|<span data-ttu-id="e968d-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="e968d-130">xs:string</span></span>|<span data-ttu-id="e968d-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e968d-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
