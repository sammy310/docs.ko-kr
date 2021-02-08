---
description: '자세한 정보: 214-OperationCompleted'
title: 214 - OperationCompleted
ms.date: 03/30/2017
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
ms.openlocfilehash: aad1ac49667a2ebbf172b5132507584e05d0f03e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794392"
---
# <a name="214---operationcompleted"></a><span data-ttu-id="73614-103">214 - OperationCompleted</span><span class="sxs-lookup"><span data-stu-id="73614-103">214 - OperationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="73614-104">속성</span><span class="sxs-lookup"><span data-stu-id="73614-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="73614-105">ID</span><span class="sxs-lookup"><span data-stu-id="73614-105">ID</span></span>|<span data-ttu-id="73614-106">214</span><span class="sxs-lookup"><span data-stu-id="73614-106">214</span></span>|  
|<span data-ttu-id="73614-107">키워드</span><span class="sxs-lookup"><span data-stu-id="73614-107">Keywords</span></span>|<span data-ttu-id="73614-108">HealthMonitoring, EndToEndMonitoring, 문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="73614-108">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="73614-109">Level</span><span class="sxs-lookup"><span data-stu-id="73614-109">Level</span></span>|<span data-ttu-id="73614-110">정보</span><span class="sxs-lookup"><span data-stu-id="73614-110">Information</span></span>|  
|<span data-ttu-id="73614-111">채널</span><span class="sxs-lookup"><span data-stu-id="73614-111">Channel</span></span>|<span data-ttu-id="73614-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="73614-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="73614-113">설명</span><span class="sxs-lookup"><span data-stu-id="73614-113">Description</span></span>  

 <span data-ttu-id="73614-114">이 이벤트는 서비스 모델의 기본 `OperationInvoker`가 메서드에서 예외를 throw하지 않고 메서드에 대한 호출을 완료하면 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="73614-114">This event is emitted when the Service Model's default `OperationInvoker` has completed a call to a method without that method throwing an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="73614-115">메시지</span><span class="sxs-lookup"><span data-stu-id="73614-115">Message</span></span>  

 <span data-ttu-id="73614-116">OperationInvoker가 '%1' 메서드에 대한 호출을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="73614-116">An OperationInvoker completed the call to the '%1' method.</span></span> <span data-ttu-id="73614-117">메서드 호출 기간은 '%2'밀리초입니다.</span><span class="sxs-lookup"><span data-stu-id="73614-117">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="73614-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="73614-118">Details</span></span>  
  
|<span data-ttu-id="73614-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="73614-119">Data Item Name</span></span>|<span data-ttu-id="73614-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="73614-120">Data Item Type</span></span>|<span data-ttu-id="73614-121">설명</span><span class="sxs-lookup"><span data-stu-id="73614-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="73614-122">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="73614-122">Method Name</span></span>|`xs:string`|<span data-ttu-id="73614-123">`OperationInvoker`의 호출을 받은 메서드의 CLR 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="73614-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="73614-124">Duration</span><span class="sxs-lookup"><span data-stu-id="73614-124">Duration</span></span>|`xs:long`|<span data-ttu-id="73614-125">`OperationInvoker`가 메서드를 호출하는 데 걸린 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="73614-125">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="73614-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="73614-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="73614-127">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="73614-127">For web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="73614-128">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73614-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="73614-129">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="73614-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="73614-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="73614-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="73614-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="73614-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
