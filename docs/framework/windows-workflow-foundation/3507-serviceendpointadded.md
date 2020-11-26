---
title: 3507 - ServiceEndpointAdded
ms.date: 03/30/2017
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
ms.openlocfilehash: 903071e7b1f89dc3489b8d3ac05427d699a33a7e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240760"
---
# <a name="3507---serviceendpointadded"></a><span data-ttu-id="de92f-102">3507 - ServiceEndpointAdded</span><span class="sxs-lookup"><span data-stu-id="de92f-102">3507 - ServiceEndpointAdded</span></span>

## <a name="properties"></a><span data-ttu-id="de92f-103">속성</span><span class="sxs-lookup"><span data-stu-id="de92f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="de92f-104">ID</span><span class="sxs-lookup"><span data-stu-id="de92f-104">ID</span></span>|<span data-ttu-id="de92f-105">3507</span><span class="sxs-lookup"><span data-stu-id="de92f-105">3507</span></span>|  
|<span data-ttu-id="de92f-106">키워드</span><span class="sxs-lookup"><span data-stu-id="de92f-106">Keywords</span></span>|<span data-ttu-id="de92f-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="de92f-107">WFServices</span></span>|  
|<span data-ttu-id="de92f-108">Level</span><span class="sxs-lookup"><span data-stu-id="de92f-108">Level</span></span>|<span data-ttu-id="de92f-109">정보</span><span class="sxs-lookup"><span data-stu-id="de92f-109">Information</span></span>|  
|<span data-ttu-id="de92f-110">채널</span><span class="sxs-lookup"><span data-stu-id="de92f-110">Channel</span></span>|<span data-ttu-id="de92f-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="de92f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="de92f-112">Description</span><span class="sxs-lookup"><span data-stu-id="de92f-112">Description</span></span>  

 <span data-ttu-id="de92f-113">서비스 엔드포인트가 추가되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="de92f-113">Indicates a service endpoint has been added.</span></span>  
  
## <a name="message"></a><span data-ttu-id="de92f-114">메시지</span><span class="sxs-lookup"><span data-stu-id="de92f-114">Message</span></span>  

 <span data-ttu-id="de92f-115">주소 '%1', 바인딩 '%2' 및 계약 '%3'에 대해 서비스 엔드포인트가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="de92f-115">A service endpoint has been added for address '%1', binding '%2', and contract '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="de92f-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="de92f-116">Details</span></span>  
  
|<span data-ttu-id="de92f-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="de92f-117">Data Item Name</span></span>|<span data-ttu-id="de92f-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="de92f-118">Data Item Type</span></span>|<span data-ttu-id="de92f-119">Description</span><span class="sxs-lookup"><span data-stu-id="de92f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="de92f-120">주소</span><span class="sxs-lookup"><span data-stu-id="de92f-120">Address</span></span>|<span data-ttu-id="de92f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="de92f-121">xs:string</span></span>|<span data-ttu-id="de92f-122">엔드포인트의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="de92f-122">The address of the endpoint.</span></span>|  
|<span data-ttu-id="de92f-123">바인딩</span><span class="sxs-lookup"><span data-stu-id="de92f-123">Binding</span></span>|<span data-ttu-id="de92f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="de92f-124">xs:string</span></span>|<span data-ttu-id="de92f-125">엔드포인트의 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="de92f-125">The binding of the endpoint.</span></span>|  
|<span data-ttu-id="de92f-126">계약</span><span class="sxs-lookup"><span data-stu-id="de92f-126">Contract</span></span>|<span data-ttu-id="de92f-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="de92f-127">xs:string</span></span>|<span data-ttu-id="de92f-128">엔드포인트의 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="de92f-128">The contract of the endpoint.</span></span>|  
|<span data-ttu-id="de92f-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="de92f-129">AppDomain</span></span>|<span data-ttu-id="de92f-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="de92f-130">xs:string</span></span>|<span data-ttu-id="de92f-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="de92f-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
