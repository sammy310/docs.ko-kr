---
description: '자세한 정보: 222-OperationFailed'
title: 222 - OperationFailed
ms.date: 03/30/2017
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
ms.openlocfilehash: ea07dbabb651413f213db6789f2af8059d2595c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794301"
---
# <a name="222---operationfailed"></a><span data-ttu-id="112de-103">222 - OperationFailed</span><span class="sxs-lookup"><span data-stu-id="112de-103">222 - OperationFailed</span></span>

## <a name="properties"></a><span data-ttu-id="112de-104">속성</span><span class="sxs-lookup"><span data-stu-id="112de-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="112de-105">ID</span><span class="sxs-lookup"><span data-stu-id="112de-105">ID</span></span>|<span data-ttu-id="112de-106">222</span><span class="sxs-lookup"><span data-stu-id="112de-106">222</span></span>|  
|<span data-ttu-id="112de-107">키워드</span><span class="sxs-lookup"><span data-stu-id="112de-107">Keywords</span></span>|<span data-ttu-id="112de-108">EndToEndMonitoring, HealthMonitoring, 문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="112de-108">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="112de-109">Level</span><span class="sxs-lookup"><span data-stu-id="112de-109">Level</span></span>|<span data-ttu-id="112de-110">경고</span><span class="sxs-lookup"><span data-stu-id="112de-110">Warning</span></span>|  
|<span data-ttu-id="112de-111">채널</span><span class="sxs-lookup"><span data-stu-id="112de-111">Channel</span></span>|<span data-ttu-id="112de-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="112de-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="112de-113">설명</span><span class="sxs-lookup"><span data-stu-id="112de-113">Description</span></span>  

 <span data-ttu-id="112de-114">이 이벤트는 서비스 모델의 기본 `OperationInvoker`에서 해당 메서드를 호출하는 동안 예외가 발생하면 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="112de-114">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception while invoking its method.</span></span> <span data-ttu-id="112de-115">`FaultException`에서 파생되는 예외가 발생할 경우에는 이 이벤트가 내보내지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="112de-115">Note that exceptions that derive from `FaultException` cause this event to not be emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="112de-116">메시지</span><span class="sxs-lookup"><span data-stu-id="112de-116">Message</span></span>  

 <span data-ttu-id="112de-117">OperationInvoker의 호출을 받은 '%1' 메서드에서 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="112de-117">The '%1' method threw an unhandled exception when invoked by the OperationInvoker.</span></span> <span data-ttu-id="112de-118">메서드 호출 기간은 '%2'밀리초입니다.</span><span class="sxs-lookup"><span data-stu-id="112de-118">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="112de-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="112de-119">Details</span></span>  
  
|<span data-ttu-id="112de-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="112de-120">Data Item Name</span></span>|<span data-ttu-id="112de-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="112de-121">Data Item Type</span></span>|<span data-ttu-id="112de-122">설명</span><span class="sxs-lookup"><span data-stu-id="112de-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="112de-123">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="112de-123">Method Name</span></span>|`xs:string`|<span data-ttu-id="112de-124">`OperationInvoker`의 호출을 받은 메서드의 CLR 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="112de-124">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="112de-125">Duration</span><span class="sxs-lookup"><span data-stu-id="112de-125">Duration</span></span>|`xs:long`|<span data-ttu-id="112de-126">`OperationInvoker`가 메서드를 호출하는 데 걸린 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="112de-126">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="112de-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="112de-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="112de-128">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="112de-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="112de-129">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="112de-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="112de-130">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="112de-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="112de-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="112de-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="112de-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="112de-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
