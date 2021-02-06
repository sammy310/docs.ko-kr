---
description: '자세한 정보: 203-ClientParameterInspectorAfterCallInvoked'
title: 203 - ClientParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
ms.openlocfilehash: bacdc2a74fc2cef6d7e473fa58c0cbbcffffcf16
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99645024"
---
# <a name="203---clientparameterinspectoraftercallinvoked"></a><span data-ttu-id="043cc-103">203 - ClientParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="043cc-103">203 - ClientParameterInspectorAfterCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="043cc-104">속성</span><span class="sxs-lookup"><span data-stu-id="043cc-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="043cc-105">ID</span><span class="sxs-lookup"><span data-stu-id="043cc-105">ID</span></span>|<span data-ttu-id="043cc-106">203</span><span class="sxs-lookup"><span data-stu-id="043cc-106">203</span></span>|  
|<span data-ttu-id="043cc-107">키워드</span><span class="sxs-lookup"><span data-stu-id="043cc-107">Keywords</span></span>|<span data-ttu-id="043cc-108">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="043cc-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="043cc-109">Level</span><span class="sxs-lookup"><span data-stu-id="043cc-109">Level</span></span>|<span data-ttu-id="043cc-110">정보</span><span class="sxs-lookup"><span data-stu-id="043cc-110">Information</span></span>|  
|<span data-ttu-id="043cc-111">채널</span><span class="sxs-lookup"><span data-stu-id="043cc-111">Channel</span></span>|<span data-ttu-id="043cc-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="043cc-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="043cc-113">설명</span><span class="sxs-lookup"><span data-stu-id="043cc-113">Description</span></span>  

 <span data-ttu-id="043cc-114">이 이벤트는 서비스 모델이 클라이언트 매개 변수 검사자에 대해 `AfterCall` 메서드를 호출한 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="043cc-114">This event is emitted after the Service Model has invoked the `AfterCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="043cc-115">메시지</span><span class="sxs-lookup"><span data-stu-id="043cc-115">Message</span></span>  

 <span data-ttu-id="043cc-116">디스패처가 '%1' 형식의 ClientParameterInspector에 대해 'AfterCall'을 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="043cc-116">The Dispatcher invoked 'AfterCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="043cc-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="043cc-117">Details</span></span>  
  
|<span data-ttu-id="043cc-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="043cc-118">Data Item Name</span></span>|<span data-ttu-id="043cc-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="043cc-119">Data Item Type</span></span>|<span data-ttu-id="043cc-120">설명</span><span class="sxs-lookup"><span data-stu-id="043cc-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="043cc-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="043cc-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="043cc-122">호출된 검사자 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="043cc-122">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="043cc-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="043cc-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="043cc-124">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="043cc-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="043cc-125">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="043cc-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="043cc-126">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="043cc-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="043cc-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="043cc-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="043cc-128">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="043cc-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
