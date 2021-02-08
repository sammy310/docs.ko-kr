---
description: '자세한 정보: 221-MessageReceivedFromTransport'
title: 221 - MessageReceivedFromTransport
ms.date: 03/30/2017
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
ms.openlocfilehash: 0cc15fa95ae321083afa2792810807971e909e6b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803505"
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="9f8dd-103">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="9f8dd-103">221 - MessageReceivedFromTransport</span></span>

## <a name="properties"></a><span data-ttu-id="9f8dd-104">속성</span><span class="sxs-lookup"><span data-stu-id="9f8dd-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9f8dd-105">ID</span><span class="sxs-lookup"><span data-stu-id="9f8dd-105">ID</span></span>|<span data-ttu-id="9f8dd-106">221</span><span class="sxs-lookup"><span data-stu-id="9f8dd-106">221</span></span>|  
|<span data-ttu-id="9f8dd-107">키워드</span><span class="sxs-lookup"><span data-stu-id="9f8dd-107">Keywords</span></span>|<span data-ttu-id="9f8dd-108">EndToEndMonitoring, 문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9f8dd-108">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="9f8dd-109">Level</span><span class="sxs-lookup"><span data-stu-id="9f8dd-109">Level</span></span>|<span data-ttu-id="9f8dd-110">정보</span><span class="sxs-lookup"><span data-stu-id="9f8dd-110">Information</span></span>|  
|<span data-ttu-id="9f8dd-111">채널</span><span class="sxs-lookup"><span data-stu-id="9f8dd-111">Channel</span></span>|<span data-ttu-id="9f8dd-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="9f8dd-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9f8dd-113">설명</span><span class="sxs-lookup"><span data-stu-id="9f8dd-113">Description</span></span>  

 <span data-ttu-id="9f8dd-114">이 이벤트는 서비스 모델이 전송에서 메시지를 받을 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-114">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9f8dd-115">메시지</span><span class="sxs-lookup"><span data-stu-id="9f8dd-115">Message</span></span>  

 <span data-ttu-id="9f8dd-116">디스패처가 전송에서 메시지를 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-116">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="9f8dd-117">Correlation ID == '%1'.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-117">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9f8dd-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="9f8dd-118">Details</span></span>  
  
|<span data-ttu-id="9f8dd-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="9f8dd-119">Data Item Name</span></span>|<span data-ttu-id="9f8dd-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="9f8dd-120">Data Item Type</span></span>|<span data-ttu-id="9f8dd-121">설명</span><span class="sxs-lookup"><span data-stu-id="9f8dd-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9f8dd-122">상관관계 ID</span><span class="sxs-lookup"><span data-stu-id="9f8dd-122">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="9f8dd-123">서비스 또는 클라이언트의 `MessageSentToTransport` 이벤트를 다른 끝에 있는 해당 `MessageReceivedFromTransport`에 상호 연결하는 데 사용되는 동작 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-123">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="9f8dd-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="9f8dd-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="9f8dd-125">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9f8dd-126">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9f8dd-127">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9f8dd-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9f8dd-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9f8dd-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
