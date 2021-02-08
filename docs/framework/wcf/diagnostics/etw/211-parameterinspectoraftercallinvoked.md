---
description: '자세한 정보: 211-ParameterInspectorAfterCallInvoked'
title: 211 - ParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
ms.openlocfilehash: 6168528fb001b5669e80595c8327dc57651e815e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794431"
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="34bd7-103">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="34bd7-103">211 - ParameterInspectorAfterCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="34bd7-104">속성</span><span class="sxs-lookup"><span data-stu-id="34bd7-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34bd7-105">ID</span><span class="sxs-lookup"><span data-stu-id="34bd7-105">ID</span></span>|<span data-ttu-id="34bd7-106">211</span><span class="sxs-lookup"><span data-stu-id="34bd7-106">211</span></span>|  
|<span data-ttu-id="34bd7-107">키워드</span><span class="sxs-lookup"><span data-stu-id="34bd7-107">Keywords</span></span>|<span data-ttu-id="34bd7-108">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="34bd7-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="34bd7-109">Level</span><span class="sxs-lookup"><span data-stu-id="34bd7-109">Level</span></span>|<span data-ttu-id="34bd7-110">정보</span><span class="sxs-lookup"><span data-stu-id="34bd7-110">Information</span></span>|  
|<span data-ttu-id="34bd7-111">채널</span><span class="sxs-lookup"><span data-stu-id="34bd7-111">Channel</span></span>|<span data-ttu-id="34bd7-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="34bd7-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="34bd7-113">설명</span><span class="sxs-lookup"><span data-stu-id="34bd7-113">Description</span></span>  

 <span data-ttu-id="34bd7-114">이 이벤트는 서비스 모델이 `AfterCall`에 대해 `ParameterInspector` 메서드를 호출한 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="34bd7-114">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="34bd7-115">메시지</span><span class="sxs-lookup"><span data-stu-id="34bd7-115">Message</span></span>  

 <span data-ttu-id="34bd7-116">디스패처가 '%1' 형식의 ParameterInspector에 대해 'AfterCall'을 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="34bd7-116">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="34bd7-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="34bd7-117">Details</span></span>  
  
|<span data-ttu-id="34bd7-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="34bd7-118">Data Item Name</span></span>|<span data-ttu-id="34bd7-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="34bd7-119">Data Item Type</span></span>|<span data-ttu-id="34bd7-120">설명</span><span class="sxs-lookup"><span data-stu-id="34bd7-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="34bd7-121">유형 이름</span><span class="sxs-lookup"><span data-stu-id="34bd7-121">Type Name</span></span>|`xs:string`|<span data-ttu-id="34bd7-122">호출된 `ParameterInspector` 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="34bd7-122">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="34bd7-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="34bd7-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="34bd7-124">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="34bd7-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="34bd7-125">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34bd7-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="34bd7-126">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="34bd7-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="34bd7-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="34bd7-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="34bd7-128">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="34bd7-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
