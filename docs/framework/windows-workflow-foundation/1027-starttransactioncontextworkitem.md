---
description: '자세한 정보: 1027-StartTransactionContextWorkItem'
title: 1027 - StartTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
ms.openlocfilehash: e7f81a5998d948d3042b51dcdf20fbb1c88ad266
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755475"
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="fbd47-103">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="fbd47-103">1027 - StartTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="fbd47-104">속성</span><span class="sxs-lookup"><span data-stu-id="fbd47-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fbd47-105">ID</span><span class="sxs-lookup"><span data-stu-id="fbd47-105">ID</span></span>|<span data-ttu-id="fbd47-106">1027</span><span class="sxs-lookup"><span data-stu-id="fbd47-106">1027</span></span>|  
|<span data-ttu-id="fbd47-107">키워드</span><span class="sxs-lookup"><span data-stu-id="fbd47-107">Keywords</span></span>|<span data-ttu-id="fbd47-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fbd47-108">WFRuntime</span></span>|  
|<span data-ttu-id="fbd47-109">Level</span><span class="sxs-lookup"><span data-stu-id="fbd47-109">Level</span></span>|<span data-ttu-id="fbd47-110">자세히</span><span class="sxs-lookup"><span data-stu-id="fbd47-110">Verbose</span></span>|  
|<span data-ttu-id="fbd47-111">채널</span><span class="sxs-lookup"><span data-stu-id="fbd47-111">Channel</span></span>|<span data-ttu-id="fbd47-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="fbd47-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fbd47-113">설명</span><span class="sxs-lookup"><span data-stu-id="fbd47-113">Description</span></span>  

 <span data-ttu-id="fbd47-114">TransactionContextWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fbd47-114">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fbd47-115">메시지</span><span class="sxs-lookup"><span data-stu-id="fbd47-115">Message</span></span>  

 <span data-ttu-id="fbd47-116">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 TransactionContextWorkItem의 실행 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="fbd47-116">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fbd47-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="fbd47-117">Details</span></span>  
  
|<span data-ttu-id="fbd47-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="fbd47-118">Data Item Name</span></span>|<span data-ttu-id="fbd47-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="fbd47-119">Data Item Type</span></span>|<span data-ttu-id="fbd47-120">설명</span><span class="sxs-lookup"><span data-stu-id="fbd47-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fbd47-121">활동</span><span class="sxs-lookup"><span data-stu-id="fbd47-121">Activity</span></span>|<span data-ttu-id="fbd47-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbd47-122">xs:string</span></span>|<span data-ttu-id="fbd47-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fbd47-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="fbd47-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="fbd47-124">DisplayName</span></span>|<span data-ttu-id="fbd47-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbd47-125">xs:string</span></span>|<span data-ttu-id="fbd47-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fbd47-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="fbd47-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="fbd47-127">InstanceId</span></span>|<span data-ttu-id="fbd47-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbd47-128">xs:string</span></span>|<span data-ttu-id="fbd47-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fbd47-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="fbd47-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fbd47-130">AppDomain</span></span>|<span data-ttu-id="fbd47-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbd47-131">xs:string</span></span>|<span data-ttu-id="fbd47-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fbd47-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
