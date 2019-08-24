---
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 649ba542a9ed2f330ac71e447602d637530dc601
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924841"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="42a16-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="42a16-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="42a16-103">속성</span><span class="sxs-lookup"><span data-stu-id="42a16-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42a16-104">ID</span><span class="sxs-lookup"><span data-stu-id="42a16-104">ID</span></span>|<span data-ttu-id="42a16-105">1036</span><span class="sxs-lookup"><span data-stu-id="42a16-105">1036</span></span>|  
|<span data-ttu-id="42a16-106">키워드</span><span class="sxs-lookup"><span data-stu-id="42a16-106">Keywords</span></span>|<span data-ttu-id="42a16-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="42a16-107">WFRuntime</span></span>|  
|<span data-ttu-id="42a16-108">수준</span><span class="sxs-lookup"><span data-stu-id="42a16-108">Level</span></span>|<span data-ttu-id="42a16-109">자세히</span><span class="sxs-lookup"><span data-stu-id="42a16-109">Verbose</span></span>|  
|<span data-ttu-id="42a16-110">채널</span><span class="sxs-lookup"><span data-stu-id="42a16-110">Channel</span></span>|<span data-ttu-id="42a16-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="42a16-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="42a16-112">설명</span><span class="sxs-lookup"><span data-stu-id="42a16-112">Description</span></span>  
 <span data-ttu-id="42a16-113">작업이 런타임 트랜잭션의 완료를 예약했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="42a16-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="42a16-114">메시지</span><span class="sxs-lookup"><span data-stu-id="42a16-114">Message</span></span>  
 <span data-ttu-id="42a16-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'이(가) 런타임 트랜잭션 완료를 예약했습니다.</span><span class="sxs-lookup"><span data-stu-id="42a16-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="42a16-116">설명</span><span class="sxs-lookup"><span data-stu-id="42a16-116">Details</span></span>  
  
|<span data-ttu-id="42a16-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="42a16-117">Data Item Name</span></span>|<span data-ttu-id="42a16-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="42a16-118">Data Item Type</span></span>|<span data-ttu-id="42a16-119">설명</span><span class="sxs-lookup"><span data-stu-id="42a16-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="42a16-120">활동</span><span class="sxs-lookup"><span data-stu-id="42a16-120">Activity</span></span>|<span data-ttu-id="42a16-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="42a16-121">xs:string</span></span>|<span data-ttu-id="42a16-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="42a16-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="42a16-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="42a16-123">DisplayName</span></span>|<span data-ttu-id="42a16-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="42a16-124">xs:string</span></span>|<span data-ttu-id="42a16-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="42a16-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="42a16-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="42a16-126">InstanceId</span></span>|<span data-ttu-id="42a16-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="42a16-127">xs:string</span></span>|<span data-ttu-id="42a16-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="42a16-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="42a16-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="42a16-129">AppDomain</span></span>|<span data-ttu-id="42a16-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="42a16-130">xs:string</span></span>|<span data-ttu-id="42a16-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="42a16-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
