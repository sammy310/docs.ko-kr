---
title: 1027 - StartTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
ms.openlocfilehash: 231a7607f2ce9a38e8dd6c1486a68bc9eb459e5e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008826"
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="49013-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="49013-102">1027 - StartTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="49013-103">속성</span><span class="sxs-lookup"><span data-stu-id="49013-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49013-104">ID</span><span class="sxs-lookup"><span data-stu-id="49013-104">ID</span></span>|<span data-ttu-id="49013-105">1027</span><span class="sxs-lookup"><span data-stu-id="49013-105">1027</span></span>|  
|<span data-ttu-id="49013-106">키워드</span><span class="sxs-lookup"><span data-stu-id="49013-106">Keywords</span></span>|<span data-ttu-id="49013-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="49013-107">WFRuntime</span></span>|  
|<span data-ttu-id="49013-108">수준</span><span class="sxs-lookup"><span data-stu-id="49013-108">Level</span></span>|<span data-ttu-id="49013-109">자세히</span><span class="sxs-lookup"><span data-stu-id="49013-109">Verbose</span></span>|  
|<span data-ttu-id="49013-110">채널</span><span class="sxs-lookup"><span data-stu-id="49013-110">Channel</span></span>|<span data-ttu-id="49013-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="49013-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="49013-112">설명</span><span class="sxs-lookup"><span data-stu-id="49013-112">Description</span></span>  
 <span data-ttu-id="49013-113">TransactionContextWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="49013-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="49013-114">메시지</span><span class="sxs-lookup"><span data-stu-id="49013-114">Message</span></span>  
 <span data-ttu-id="49013-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 TransactionContextWorkItem의 실행 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="49013-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="49013-116">설명</span><span class="sxs-lookup"><span data-stu-id="49013-116">Details</span></span>  
  
|<span data-ttu-id="49013-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="49013-117">Data Item Name</span></span>|<span data-ttu-id="49013-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="49013-118">Data Item Type</span></span>|<span data-ttu-id="49013-119">설명</span><span class="sxs-lookup"><span data-stu-id="49013-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="49013-120">활동</span><span class="sxs-lookup"><span data-stu-id="49013-120">Activity</span></span>|<span data-ttu-id="49013-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="49013-121">xs:string</span></span>|<span data-ttu-id="49013-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="49013-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="49013-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="49013-123">DisplayName</span></span>|<span data-ttu-id="49013-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="49013-124">xs:string</span></span>|<span data-ttu-id="49013-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="49013-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="49013-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="49013-126">InstanceId</span></span>|<span data-ttu-id="49013-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="49013-127">xs:string</span></span>|<span data-ttu-id="49013-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="49013-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="49013-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="49013-129">AppDomain</span></span>|<span data-ttu-id="49013-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="49013-130">xs:string</span></span>|<span data-ttu-id="49013-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="49013-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
