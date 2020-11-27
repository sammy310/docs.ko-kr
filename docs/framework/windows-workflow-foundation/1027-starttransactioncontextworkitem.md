---
title: 1027 - StartTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
ms.openlocfilehash: cb5671ce7a30a7096104ba0ca6c4f36bed6b93f9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275234"
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="8f5bb-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="8f5bb-102">1027 - StartTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="8f5bb-103">속성</span><span class="sxs-lookup"><span data-stu-id="8f5bb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8f5bb-104">ID</span><span class="sxs-lookup"><span data-stu-id="8f5bb-104">ID</span></span>|<span data-ttu-id="8f5bb-105">1027</span><span class="sxs-lookup"><span data-stu-id="8f5bb-105">1027</span></span>|  
|<span data-ttu-id="8f5bb-106">키워드</span><span class="sxs-lookup"><span data-stu-id="8f5bb-106">Keywords</span></span>|<span data-ttu-id="8f5bb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8f5bb-107">WFRuntime</span></span>|  
|<span data-ttu-id="8f5bb-108">Level</span><span class="sxs-lookup"><span data-stu-id="8f5bb-108">Level</span></span>|<span data-ttu-id="8f5bb-109">자세히</span><span class="sxs-lookup"><span data-stu-id="8f5bb-109">Verbose</span></span>|  
|<span data-ttu-id="8f5bb-110">채널</span><span class="sxs-lookup"><span data-stu-id="8f5bb-110">Channel</span></span>|<span data-ttu-id="8f5bb-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="8f5bb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8f5bb-112">Description</span><span class="sxs-lookup"><span data-stu-id="8f5bb-112">Description</span></span>  

 <span data-ttu-id="8f5bb-113">TransactionContextWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8f5bb-114">메시지</span><span class="sxs-lookup"><span data-stu-id="8f5bb-114">Message</span></span>  

 <span data-ttu-id="8f5bb-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 TransactionContextWorkItem의 실행 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8f5bb-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="8f5bb-116">Details</span></span>  
  
|<span data-ttu-id="8f5bb-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="8f5bb-117">Data Item Name</span></span>|<span data-ttu-id="8f5bb-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="8f5bb-118">Data Item Type</span></span>|<span data-ttu-id="8f5bb-119">Description</span><span class="sxs-lookup"><span data-stu-id="8f5bb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8f5bb-120">활동</span><span class="sxs-lookup"><span data-stu-id="8f5bb-120">Activity</span></span>|<span data-ttu-id="8f5bb-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f5bb-121">xs:string</span></span>|<span data-ttu-id="8f5bb-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="8f5bb-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8f5bb-123">DisplayName</span></span>|<span data-ttu-id="8f5bb-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f5bb-124">xs:string</span></span>|<span data-ttu-id="8f5bb-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="8f5bb-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8f5bb-126">InstanceId</span></span>|<span data-ttu-id="8f5bb-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f5bb-127">xs:string</span></span>|<span data-ttu-id="8f5bb-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8f5bb-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8f5bb-129">AppDomain</span></span>|<span data-ttu-id="8f5bb-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f5bb-130">xs:string</span></span>|<span data-ttu-id="8f5bb-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8f5bb-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
