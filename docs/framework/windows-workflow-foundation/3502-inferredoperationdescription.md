---
description: '자세한 정보: 3502-InferredOperationDescription'
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 5068a3553484b38242951ef985886190f8027035
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631491"
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="54ae4-103">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="54ae4-103">3502 - InferredOperationDescription</span></span>

## <a name="properties"></a><span data-ttu-id="54ae4-104">속성</span><span class="sxs-lookup"><span data-stu-id="54ae4-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="54ae4-105">ID</span><span class="sxs-lookup"><span data-stu-id="54ae4-105">ID</span></span>|<span data-ttu-id="54ae4-106">3502</span><span class="sxs-lookup"><span data-stu-id="54ae4-106">3502</span></span>|  
|<span data-ttu-id="54ae4-107">키워드</span><span class="sxs-lookup"><span data-stu-id="54ae4-107">Keywords</span></span>|<span data-ttu-id="54ae4-108">WFServices</span><span class="sxs-lookup"><span data-stu-id="54ae4-108">WFServices</span></span>|  
|<span data-ttu-id="54ae4-109">Level</span><span class="sxs-lookup"><span data-stu-id="54ae4-109">Level</span></span>|<span data-ttu-id="54ae4-110">정보</span><span class="sxs-lookup"><span data-stu-id="54ae4-110">Information</span></span>|  
|<span data-ttu-id="54ae4-111">채널</span><span class="sxs-lookup"><span data-stu-id="54ae4-111">Channel</span></span>|<span data-ttu-id="54ae4-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="54ae4-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="54ae4-113">설명</span><span class="sxs-lookup"><span data-stu-id="54ae4-113">Description</span></span>  

 <span data-ttu-id="54ae4-114">OperationDescription이 WorkflowService에서 유추되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54ae4-114">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="54ae4-115">메시지</span><span class="sxs-lookup"><span data-stu-id="54ae4-115">Message</span></span>  

 <span data-ttu-id="54ae4-116">계약 '%2'에서 Name='%1'인 OperationDescription이 WorkflowService에서 유추되었습니다.</span><span class="sxs-lookup"><span data-stu-id="54ae4-116">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="54ae4-117">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="54ae4-117">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="54ae4-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="54ae4-118">Details</span></span>  
  
|<span data-ttu-id="54ae4-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="54ae4-119">Data Item Name</span></span>|<span data-ttu-id="54ae4-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="54ae4-120">Data Item Type</span></span>|<span data-ttu-id="54ae4-121">설명</span><span class="sxs-lookup"><span data-stu-id="54ae4-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="54ae4-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="54ae4-122">OperationName</span></span>|<span data-ttu-id="54ae4-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="54ae4-123">xs:string</span></span>|<span data-ttu-id="54ae4-124">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54ae4-124">The name of the operation.</span></span>|  
|<span data-ttu-id="54ae4-125">ContractName</span><span class="sxs-lookup"><span data-stu-id="54ae4-125">ContractName</span></span>|<span data-ttu-id="54ae4-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="54ae4-126">xs:string</span></span>|<span data-ttu-id="54ae4-127">계약 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54ae4-127">The name of the contract.</span></span>|  
|<span data-ttu-id="54ae4-128">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="54ae4-128">IsOneWay</span></span>|<span data-ttu-id="54ae4-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="54ae4-129">xs:string</span></span>|<span data-ttu-id="54ae4-130">계약이 단방향인지 여부를 나타내는 True 또는 False입니다.</span><span class="sxs-lookup"><span data-stu-id="54ae4-130">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="54ae4-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="54ae4-131">AppDomain</span></span>|<span data-ttu-id="54ae4-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="54ae4-132">xs:string</span></span>|<span data-ttu-id="54ae4-133">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="54ae4-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
