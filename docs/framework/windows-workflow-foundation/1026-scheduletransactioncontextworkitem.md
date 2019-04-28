---
title: 1026 - ScheduleTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
ms.openlocfilehash: 6d0b43208f86c52e8863d4415a64466b0531832c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924633"
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="5c304-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="5c304-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="5c304-103">속성</span><span class="sxs-lookup"><span data-stu-id="5c304-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5c304-104">ID</span><span class="sxs-lookup"><span data-stu-id="5c304-104">ID</span></span>|<span data-ttu-id="5c304-105">1026</span><span class="sxs-lookup"><span data-stu-id="5c304-105">1026</span></span>|  
|<span data-ttu-id="5c304-106">키워드</span><span class="sxs-lookup"><span data-stu-id="5c304-106">Keywords</span></span>|<span data-ttu-id="5c304-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5c304-107">WFRuntime</span></span>|  
|<span data-ttu-id="5c304-108">수준</span><span class="sxs-lookup"><span data-stu-id="5c304-108">Level</span></span>|<span data-ttu-id="5c304-109">자세히</span><span class="sxs-lookup"><span data-stu-id="5c304-109">Verbose</span></span>|  
|<span data-ttu-id="5c304-110">채널</span><span class="sxs-lookup"><span data-stu-id="5c304-110">Channel</span></span>|<span data-ttu-id="5c304-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="5c304-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5c304-112">설명</span><span class="sxs-lookup"><span data-stu-id="5c304-112">Description</span></span>  
 <span data-ttu-id="5c304-113">TransactionContextWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5c304-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5c304-114">메시지</span><span class="sxs-lookup"><span data-stu-id="5c304-114">Message</span></span>  
 <span data-ttu-id="5c304-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 TransactionContextWorkItem이 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5c304-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5c304-116">설명</span><span class="sxs-lookup"><span data-stu-id="5c304-116">Details</span></span>  
  
|<span data-ttu-id="5c304-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="5c304-117">Data Item Name</span></span>|<span data-ttu-id="5c304-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="5c304-118">Data Item Type</span></span>|<span data-ttu-id="5c304-119">설명</span><span class="sxs-lookup"><span data-stu-id="5c304-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5c304-120">활동</span><span class="sxs-lookup"><span data-stu-id="5c304-120">Activity</span></span>|<span data-ttu-id="5c304-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5c304-121">xs:string</span></span>|<span data-ttu-id="5c304-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5c304-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="5c304-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="5c304-123">DisplayName</span></span>|<span data-ttu-id="5c304-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5c304-124">xs:string</span></span>|<span data-ttu-id="5c304-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5c304-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="5c304-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="5c304-126">InstanceId</span></span>|<span data-ttu-id="5c304-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="5c304-127">xs:string</span></span>|<span data-ttu-id="5c304-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5c304-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="5c304-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5c304-129">AppDomain</span></span>|<span data-ttu-id="5c304-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="5c304-130">xs:string</span></span>|<span data-ttu-id="5c304-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5c304-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
