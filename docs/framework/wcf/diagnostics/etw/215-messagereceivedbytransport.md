---
description: '자세한 정보: 215-MessageReceivedByTransport'
title: 215 - MessageReceivedByTransport
ms.date: 03/30/2017
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
ms.openlocfilehash: e9645cfc8c4013f8891cb645db7df35477a57412
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794366"
---
# <a name="215---messagereceivedbytransport"></a><span data-ttu-id="fbde3-103">215 - MessageReceivedByTransport</span><span class="sxs-lookup"><span data-stu-id="fbde3-103">215 - MessageReceivedByTransport</span></span>

## <a name="properties"></a><span data-ttu-id="fbde3-104">속성</span><span class="sxs-lookup"><span data-stu-id="fbde3-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fbde3-105">ID</span><span class="sxs-lookup"><span data-stu-id="fbde3-105">ID</span></span>|<span data-ttu-id="fbde3-106">215</span><span class="sxs-lookup"><span data-stu-id="fbde3-106">215</span></span>|  
|<span data-ttu-id="fbde3-107">키워드</span><span class="sxs-lookup"><span data-stu-id="fbde3-107">Keywords</span></span>|<span data-ttu-id="fbde3-108">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fbde3-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="fbde3-109">Level</span><span class="sxs-lookup"><span data-stu-id="fbde3-109">Level</span></span>|<span data-ttu-id="fbde3-110">정보</span><span class="sxs-lookup"><span data-stu-id="fbde3-110">Information</span></span>|  
|<span data-ttu-id="fbde3-111">채널</span><span class="sxs-lookup"><span data-stu-id="fbde3-111">Channel</span></span>|<span data-ttu-id="fbde3-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="fbde3-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fbde3-113">설명</span><span class="sxs-lookup"><span data-stu-id="fbde3-113">Description</span></span>  

 <span data-ttu-id="fbde3-114">이 이벤트는 TCP 기반 전송이 메시지를 받을 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fbde3-114">This event occurs when a TCP-based transport receives a message.</span></span> <span data-ttu-id="fbde3-115">전송 수준에서는 단일 작업에 대해 클라이언트와 서비스 간에 여러 메시지가 교환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbde3-115">Note that at the transport level, multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="fbde3-116">이는 보안과 같은 인프라 동작 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbde3-116">This can be due to infrastructure behavior, security is a good example.</span></span> <span data-ttu-id="fbde3-117">따라서 내보내지는 `MessageReceivedByTransport` 이벤트의 수는 서비스의 바인딩과 해당 구성에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="fbde3-117">Therefore, the number of `MessageReceivedByTransport` events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fbde3-118">이 이벤트는 단방향 전송에 대해 내보내지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fbde3-118">This event is not emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fbde3-119">메시지</span><span class="sxs-lookup"><span data-stu-id="fbde3-119">Message</span></span>  

 <span data-ttu-id="fbde3-120">전송이 '%1'에서 메시지를 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="fbde3-120">The transport received a message from '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fbde3-121">세부 정보</span><span class="sxs-lookup"><span data-stu-id="fbde3-121">Details</span></span>  
  
|<span data-ttu-id="fbde3-122">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="fbde3-122">Data Item Name</span></span>|<span data-ttu-id="fbde3-123">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="fbde3-123">Data Item Type</span></span>|<span data-ttu-id="fbde3-124">설명</span><span class="sxs-lookup"><span data-stu-id="fbde3-124">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fbde3-125">Listen Address</span><span class="sxs-lookup"><span data-stu-id="fbde3-125">Listen Address</span></span>|`xs:string`|<span data-ttu-id="fbde3-126">메시지를 받은 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fbde3-126">The address that received the message.</span></span>|  
|<span data-ttu-id="fbde3-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="fbde3-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="fbde3-128">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="fbde3-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="fbde3-129">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbde3-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="fbde3-130">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="fbde3-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="fbde3-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fbde3-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="fbde3-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fbde3-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
