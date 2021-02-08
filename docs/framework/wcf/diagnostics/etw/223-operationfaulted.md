---
description: '자세한 정보: 223-OperationFaulted 발생 했습니다.'
title: 223 - OperationFaulted
ms.date: 03/30/2017
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
ms.openlocfilehash: e4155516e07568d4ee4ca76d63754ec4171e1064
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794288"
---
# <a name="223---operationfaulted"></a><span data-ttu-id="0fe9c-103">223 - OperationFaulted</span><span class="sxs-lookup"><span data-stu-id="0fe9c-103">223 - OperationFaulted</span></span>

## <a name="properties"></a><span data-ttu-id="0fe9c-104">속성</span><span class="sxs-lookup"><span data-stu-id="0fe9c-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0fe9c-105">ID</span><span class="sxs-lookup"><span data-stu-id="0fe9c-105">ID</span></span>|<span data-ttu-id="0fe9c-106">223</span><span class="sxs-lookup"><span data-stu-id="0fe9c-106">223</span></span>|  
|<span data-ttu-id="0fe9c-107">키워드</span><span class="sxs-lookup"><span data-stu-id="0fe9c-107">Keywords</span></span>|<span data-ttu-id="0fe9c-108">EndToEndMonitoring, HealthMonitoring, 문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0fe9c-108">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="0fe9c-109">Level</span><span class="sxs-lookup"><span data-stu-id="0fe9c-109">Level</span></span>|<span data-ttu-id="0fe9c-110">경고</span><span class="sxs-lookup"><span data-stu-id="0fe9c-110">Warning</span></span>|  
|<span data-ttu-id="0fe9c-111">채널</span><span class="sxs-lookup"><span data-stu-id="0fe9c-111">Channel</span></span>|<span data-ttu-id="0fe9c-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="0fe9c-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0fe9c-113">설명</span><span class="sxs-lookup"><span data-stu-id="0fe9c-113">Description</span></span>  

 <span data-ttu-id="0fe9c-114">이 이벤트는 서비스 모델의 기본 `OperationInvoker`에서 해당 메서드를 호출하는 동안 `FaultException`에서 파생되는 예외가 발생하면 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="0fe9c-114">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception deriving from `FaultException` while invoking its method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0fe9c-115">메시지</span><span class="sxs-lookup"><span data-stu-id="0fe9c-115">Message</span></span>  

 <span data-ttu-id="0fe9c-116">OperationInvoker의 호출을 받은 '%1' 메서드에서 FaultException이 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="0fe9c-116">The '%1' method threw a FaultException when invoked by the OperationInvoker.</span></span> <span data-ttu-id="0fe9c-117">메서드 호출 기간은 '%2'밀리초입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe9c-117">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0fe9c-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="0fe9c-118">Details</span></span>  
  
|<span data-ttu-id="0fe9c-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="0fe9c-119">Data Item Name</span></span>|<span data-ttu-id="0fe9c-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="0fe9c-120">Data Item Type</span></span>|<span data-ttu-id="0fe9c-121">설명</span><span class="sxs-lookup"><span data-stu-id="0fe9c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0fe9c-122">MethodName</span><span class="sxs-lookup"><span data-stu-id="0fe9c-122">MethodName</span></span>|`xs:string`|<span data-ttu-id="0fe9c-123">`OperationInvoker`의 호출을 받은 메서드의 CLR 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe9c-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="0fe9c-124">Duration</span><span class="sxs-lookup"><span data-stu-id="0fe9c-124">Duration</span></span>|`xs:long`|<span data-ttu-id="0fe9c-125">`OperationInvoker`가 메서드를 호출하는 데 걸린 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe9c-125">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="0fe9c-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="0fe9c-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="0fe9c-127">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe9c-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="0fe9c-128">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fe9c-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="0fe9c-129">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="0fe9c-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="0fe9c-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0fe9c-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0fe9c-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe9c-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
