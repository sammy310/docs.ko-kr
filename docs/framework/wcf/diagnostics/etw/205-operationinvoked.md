---
description: '자세한 정보: 205-OperationInvoked'
title: 205 - OperationInvoked
ms.date: 03/30/2017
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
ms.openlocfilehash: 09afe4c29c5f56b06bbf524dd13d88ddf2319063
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99644972"
---
# <a name="205---operationinvoked"></a><span data-ttu-id="56211-103">205 - OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="56211-103">205 - OperationInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="56211-104">속성</span><span class="sxs-lookup"><span data-stu-id="56211-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="56211-105">ID</span><span class="sxs-lookup"><span data-stu-id="56211-105">ID</span></span>|<span data-ttu-id="56211-106">205</span><span class="sxs-lookup"><span data-stu-id="56211-106">205</span></span>|  
|<span data-ttu-id="56211-107">키워드</span><span class="sxs-lookup"><span data-stu-id="56211-107">Keywords</span></span>|<span data-ttu-id="56211-108">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="56211-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="56211-109">Level</span><span class="sxs-lookup"><span data-stu-id="56211-109">Level</span></span>|<span data-ttu-id="56211-110">정보</span><span class="sxs-lookup"><span data-stu-id="56211-110">Information</span></span>|  
|<span data-ttu-id="56211-111">채널</span><span class="sxs-lookup"><span data-stu-id="56211-111">Channel</span></span>|<span data-ttu-id="56211-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="56211-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="56211-113">설명</span><span class="sxs-lookup"><span data-stu-id="56211-113">Description</span></span>  

 <span data-ttu-id="56211-114">이 이벤트는 서비스 모델의 기본 `OperationInvoker`가 메서드에 대한 호출을 시작하기 바로 전에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="56211-114">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="56211-115">메시지</span><span class="sxs-lookup"><span data-stu-id="56211-115">Message</span></span>  

 <span data-ttu-id="56211-116">OperationInvoker가 '%1' 메서드를 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="56211-116">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="56211-117">호출자 정보: '%2'.</span><span class="sxs-lookup"><span data-stu-id="56211-117">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="56211-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="56211-118">Details</span></span>  
  
|<span data-ttu-id="56211-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="56211-119">Data Item Name</span></span>|<span data-ttu-id="56211-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="56211-120">Data Item Type</span></span>|<span data-ttu-id="56211-121">설명</span><span class="sxs-lookup"><span data-stu-id="56211-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="56211-122">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="56211-122">Method Name</span></span>|`xs:string`|<span data-ttu-id="56211-123">`OperationInvoker`의 호출을 받은 메서드의 CLR 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="56211-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="56211-124">호출자 정보</span><span class="sxs-lookup"><span data-stu-id="56211-124">Caller Information</span></span>|`xs:string`|<span data-ttu-id="56211-125">'IPAddress:PortNumber' 형식으로 된 클라이언트의 IP 주소와 포트 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="56211-125">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="56211-126">이 두 값은 작업 컨텍스트 내의 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' 메시지 속성에서 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="56211-126">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="56211-127">비 TCP 바인딩의 경우 이 값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="56211-127">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="56211-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="56211-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="56211-129">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="56211-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="56211-130">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56211-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="56211-131">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="56211-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="56211-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="56211-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="56211-133">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="56211-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
