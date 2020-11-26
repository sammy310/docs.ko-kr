---
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 05278067e3f86612ee4aafbe7d5eb66dc934cb85
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242112"
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="f3e27-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="f3e27-102">3502 - InferredOperationDescription</span></span>

## <a name="properties"></a><span data-ttu-id="f3e27-103">속성</span><span class="sxs-lookup"><span data-stu-id="f3e27-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f3e27-104">ID</span><span class="sxs-lookup"><span data-stu-id="f3e27-104">ID</span></span>|<span data-ttu-id="f3e27-105">3502</span><span class="sxs-lookup"><span data-stu-id="f3e27-105">3502</span></span>|  
|<span data-ttu-id="f3e27-106">키워드</span><span class="sxs-lookup"><span data-stu-id="f3e27-106">Keywords</span></span>|<span data-ttu-id="f3e27-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="f3e27-107">WFServices</span></span>|  
|<span data-ttu-id="f3e27-108">Level</span><span class="sxs-lookup"><span data-stu-id="f3e27-108">Level</span></span>|<span data-ttu-id="f3e27-109">정보</span><span class="sxs-lookup"><span data-stu-id="f3e27-109">Information</span></span>|  
|<span data-ttu-id="f3e27-110">채널</span><span class="sxs-lookup"><span data-stu-id="f3e27-110">Channel</span></span>|<span data-ttu-id="f3e27-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="f3e27-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f3e27-112">Description</span><span class="sxs-lookup"><span data-stu-id="f3e27-112">Description</span></span>  

 <span data-ttu-id="f3e27-113">OperationDescription이 WorkflowService에서 유추되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f3e27-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f3e27-114">메시지</span><span class="sxs-lookup"><span data-stu-id="f3e27-114">Message</span></span>  

 <span data-ttu-id="f3e27-115">계약 '%2'에서 Name='%1'인 OperationDescription이 WorkflowService에서 유추되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e27-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="f3e27-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="f3e27-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f3e27-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="f3e27-117">Details</span></span>  
  
|<span data-ttu-id="f3e27-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f3e27-118">Data Item Name</span></span>|<span data-ttu-id="f3e27-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f3e27-119">Data Item Type</span></span>|<span data-ttu-id="f3e27-120">Description</span><span class="sxs-lookup"><span data-stu-id="f3e27-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f3e27-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="f3e27-121">OperationName</span></span>|<span data-ttu-id="f3e27-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3e27-122">xs:string</span></span>|<span data-ttu-id="f3e27-123">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f3e27-123">The name of the operation.</span></span>|  
|<span data-ttu-id="f3e27-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="f3e27-124">ContractName</span></span>|<span data-ttu-id="f3e27-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3e27-125">xs:string</span></span>|<span data-ttu-id="f3e27-126">계약 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f3e27-126">The name of the contract.</span></span>|  
|<span data-ttu-id="f3e27-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="f3e27-127">IsOneWay</span></span>|<span data-ttu-id="f3e27-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3e27-128">xs:string</span></span>|<span data-ttu-id="f3e27-129">계약이 단방향인지 여부를 나타내는 True 또는 False입니다.</span><span class="sxs-lookup"><span data-stu-id="f3e27-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="f3e27-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f3e27-130">AppDomain</span></span>|<span data-ttu-id="f3e27-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3e27-131">xs:string</span></span>|<span data-ttu-id="f3e27-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f3e27-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
