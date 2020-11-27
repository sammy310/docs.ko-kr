---
title: 216 - MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: b3e9e1a48951ad5a2e5e7820dc1828c20e310635
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278910"
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="3682e-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="3682e-102">216 - MessageSentByTransport</span></span>

## <a name="properties"></a><span data-ttu-id="3682e-103">속성</span><span class="sxs-lookup"><span data-stu-id="3682e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3682e-104">ID</span><span class="sxs-lookup"><span data-stu-id="3682e-104">ID</span></span>|<span data-ttu-id="3682e-105">216</span><span class="sxs-lookup"><span data-stu-id="3682e-105">216</span></span>|  
|<span data-ttu-id="3682e-106">키워드</span><span class="sxs-lookup"><span data-stu-id="3682e-106">Keywords</span></span>|<span data-ttu-id="3682e-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3682e-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="3682e-108">Level</span><span class="sxs-lookup"><span data-stu-id="3682e-108">Level</span></span>|<span data-ttu-id="3682e-109">정보</span><span class="sxs-lookup"><span data-stu-id="3682e-109">Information</span></span>|  
|<span data-ttu-id="3682e-110">채널</span><span class="sxs-lookup"><span data-stu-id="3682e-110">Channel</span></span>|<span data-ttu-id="3682e-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="3682e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3682e-112">Description</span><span class="sxs-lookup"><span data-stu-id="3682e-112">Description</span></span>  

 <span data-ttu-id="3682e-113">이 이벤트는 TCP 기반 전송이 메시지를 보낼 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3682e-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="3682e-114">전송 수준에서는 단일 작업에 대해 클라이언트와 서비스 간에 여러 메시지가 교환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3682e-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="3682e-115">이는 보안과 같은 인프라 동작 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3682e-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="3682e-116">따라서 내보내는 **MessageSentByTransport** 이벤트 수는 서비스의 바인딩 및 해당 구성에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="3682e-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3682e-117">메시지</span><span class="sxs-lookup"><span data-stu-id="3682e-117">Message</span></span>  

 <span data-ttu-id="3682e-118">전송이 '%1'에 메시지를 보냈습니다.</span><span class="sxs-lookup"><span data-stu-id="3682e-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3682e-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="3682e-119">Details</span></span>  
  
|<span data-ttu-id="3682e-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="3682e-120">Data Item Name</span></span>|<span data-ttu-id="3682e-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="3682e-121">Data Item Type</span></span>|<span data-ttu-id="3682e-122">Description</span><span class="sxs-lookup"><span data-stu-id="3682e-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3682e-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="3682e-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="3682e-124">요청 메시지가 전달된 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3682e-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="3682e-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="3682e-125">HostReference</span></span>|<span data-ttu-id="3682e-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="3682e-126">xs:string</span></span>|<span data-ttu-id="3682e-127">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="3682e-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="3682e-128">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3682e-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="3682e-129">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="3682e-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="3682e-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3682e-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="3682e-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3682e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
