---
title: 215 - MessageReceivedByTransport
ms.date: 03/30/2017
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
ms.openlocfilehash: 2f247e751a0690f13d059eff29d633c6d047775d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279079"
---
# <a name="215---messagereceivedbytransport"></a><span data-ttu-id="c2afc-102">215 - MessageReceivedByTransport</span><span class="sxs-lookup"><span data-stu-id="c2afc-102">215 - MessageReceivedByTransport</span></span>

## <a name="properties"></a><span data-ttu-id="c2afc-103">속성</span><span class="sxs-lookup"><span data-stu-id="c2afc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c2afc-104">ID</span><span class="sxs-lookup"><span data-stu-id="c2afc-104">ID</span></span>|<span data-ttu-id="c2afc-105">215</span><span class="sxs-lookup"><span data-stu-id="c2afc-105">215</span></span>|  
|<span data-ttu-id="c2afc-106">키워드</span><span class="sxs-lookup"><span data-stu-id="c2afc-106">Keywords</span></span>|<span data-ttu-id="c2afc-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c2afc-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="c2afc-108">Level</span><span class="sxs-lookup"><span data-stu-id="c2afc-108">Level</span></span>|<span data-ttu-id="c2afc-109">정보</span><span class="sxs-lookup"><span data-stu-id="c2afc-109">Information</span></span>|  
|<span data-ttu-id="c2afc-110">채널</span><span class="sxs-lookup"><span data-stu-id="c2afc-110">Channel</span></span>|<span data-ttu-id="c2afc-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="c2afc-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c2afc-112">Description</span><span class="sxs-lookup"><span data-stu-id="c2afc-112">Description</span></span>  

 <span data-ttu-id="c2afc-113">이 이벤트는 TCP 기반 전송이 메시지를 받을 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c2afc-113">This event occurs when a TCP-based transport receives a message.</span></span> <span data-ttu-id="c2afc-114">전송 수준에서는 단일 작업에 대해 클라이언트와 서비스 간에 여러 메시지가 교환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2afc-114">Note that at the transport level, multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="c2afc-115">이는 보안과 같은 인프라 동작 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2afc-115">This can be due to infrastructure behavior, security is a good example.</span></span> <span data-ttu-id="c2afc-116">따라서 내보내지는 `MessageReceivedByTransport` 이벤트의 수는 서비스의 바인딩과 해당 구성에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="c2afc-116">Therefore, the number of `MessageReceivedByTransport` events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2afc-117">이 이벤트는 단방향 전송에 대해 내보내지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2afc-117">This event is not emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c2afc-118">메시지</span><span class="sxs-lookup"><span data-stu-id="c2afc-118">Message</span></span>  

 <span data-ttu-id="c2afc-119">전송이 '%1'에서 메시지를 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="c2afc-119">The transport received a message from '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c2afc-120">세부 정보</span><span class="sxs-lookup"><span data-stu-id="c2afc-120">Details</span></span>  
  
|<span data-ttu-id="c2afc-121">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="c2afc-121">Data Item Name</span></span>|<span data-ttu-id="c2afc-122">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="c2afc-122">Data Item Type</span></span>|<span data-ttu-id="c2afc-123">Description</span><span class="sxs-lookup"><span data-stu-id="c2afc-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c2afc-124">Listen Address</span><span class="sxs-lookup"><span data-stu-id="c2afc-124">Listen Address</span></span>|`xs:string`|<span data-ttu-id="c2afc-125">메시지를 받은 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c2afc-125">The address that received the message.</span></span>|  
|<span data-ttu-id="c2afc-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="c2afc-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="c2afc-127">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c2afc-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="c2afc-128">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2afc-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="c2afc-129">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="c2afc-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="c2afc-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c2afc-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="c2afc-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c2afc-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
