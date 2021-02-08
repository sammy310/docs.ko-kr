---
description: '자세한 정보: 220-MessageSentToTransport'
title: 220 - MessageSentToTransport
ms.date: 03/30/2017
ms.assetid: aef4e781-240b-45bc-bff8-400053037e71
ms.openlocfilehash: 8d76f147c8a31a5aa08c21073cd03e63436095ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794314"
---
# <a name="220---messagesenttotransport"></a><span data-ttu-id="1395f-103">220 - MessageSentToTransport</span><span class="sxs-lookup"><span data-stu-id="1395f-103">220 - MessageSentToTransport</span></span>

## <a name="properties"></a><span data-ttu-id="1395f-104">속성</span><span class="sxs-lookup"><span data-stu-id="1395f-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1395f-105">Id</span><span class="sxs-lookup"><span data-stu-id="1395f-105">Id</span></span>|<span data-ttu-id="1395f-106">220</span><span class="sxs-lookup"><span data-stu-id="1395f-106">220</span></span>|  
|<span data-ttu-id="1395f-107">키워드</span><span class="sxs-lookup"><span data-stu-id="1395f-107">Keywords</span></span>|<span data-ttu-id="1395f-108">EndToEndMonitoring, 문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1395f-108">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="1395f-109">Level</span><span class="sxs-lookup"><span data-stu-id="1395f-109">Level</span></span>|<span data-ttu-id="1395f-110">정보</span><span class="sxs-lookup"><span data-stu-id="1395f-110">Information</span></span>|  
|<span data-ttu-id="1395f-111">채널</span><span class="sxs-lookup"><span data-stu-id="1395f-111">Channel</span></span>|<span data-ttu-id="1395f-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="1395f-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1395f-113">설명</span><span class="sxs-lookup"><span data-stu-id="1395f-113">Description</span></span>  

 <span data-ttu-id="1395f-114">이 이벤트는 서비스 모델이 전송에 메시지를 보낼 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="1395f-114">This event is emitted when the Service Model sends a message to the transport.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1395f-115">단방향 전송의 경우에는 이 이벤트가 내보내지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1395f-115">This event will not be emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1395f-116">메시지</span><span class="sxs-lookup"><span data-stu-id="1395f-116">Message</span></span>  

 <span data-ttu-id="1395f-117">디스패처가 전송에 메시지를 보냈습니다.</span><span class="sxs-lookup"><span data-stu-id="1395f-117">The Dispatcher sent a message to the transport.</span></span> <span data-ttu-id="1395f-118">Correlation ID == '%1'.</span><span class="sxs-lookup"><span data-stu-id="1395f-118">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1395f-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="1395f-119">Details</span></span>  
  
|<span data-ttu-id="1395f-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="1395f-120">Data Item Name</span></span>|<span data-ttu-id="1395f-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="1395f-121">Data Item Type</span></span>|<span data-ttu-id="1395f-122">설명</span><span class="sxs-lookup"><span data-stu-id="1395f-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1395f-123">상관관계 ID</span><span class="sxs-lookup"><span data-stu-id="1395f-123">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="1395f-124">서비스 또는 클라이언트의 `MessageSentToTransport` 이벤트를 다른 끝에 있는 해당 `MessageReceivedFromTransport`에 상호 연결하는 데 사용되는 동작 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1395f-124">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="1395f-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="1395f-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="1395f-126">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1395f-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="1395f-127">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1395f-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="1395f-128">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="1395f-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="1395f-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1395f-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1395f-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1395f-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
