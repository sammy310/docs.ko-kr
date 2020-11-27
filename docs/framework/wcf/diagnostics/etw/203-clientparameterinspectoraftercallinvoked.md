---
title: 203 - ClientParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
ms.openlocfilehash: b964c26c9684cedef0fbe427bfd9ad232d199f12
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251531"
---
# <a name="203---clientparameterinspectoraftercallinvoked"></a><span data-ttu-id="6d4b4-102">203 - ClientParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="6d4b4-102">203 - ClientParameterInspectorAfterCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="6d4b4-103">속성</span><span class="sxs-lookup"><span data-stu-id="6d4b4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6d4b4-104">ID</span><span class="sxs-lookup"><span data-stu-id="6d4b4-104">ID</span></span>|<span data-ttu-id="6d4b4-105">203</span><span class="sxs-lookup"><span data-stu-id="6d4b4-105">203</span></span>|  
|<span data-ttu-id="6d4b4-106">키워드</span><span class="sxs-lookup"><span data-stu-id="6d4b4-106">Keywords</span></span>|<span data-ttu-id="6d4b4-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6d4b4-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="6d4b4-108">Level</span><span class="sxs-lookup"><span data-stu-id="6d4b4-108">Level</span></span>|<span data-ttu-id="6d4b4-109">정보</span><span class="sxs-lookup"><span data-stu-id="6d4b4-109">Information</span></span>|  
|<span data-ttu-id="6d4b4-110">채널</span><span class="sxs-lookup"><span data-stu-id="6d4b4-110">Channel</span></span>|<span data-ttu-id="6d4b4-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="6d4b4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6d4b4-112">Description</span><span class="sxs-lookup"><span data-stu-id="6d4b4-112">Description</span></span>  

 <span data-ttu-id="6d4b4-113">이 이벤트는 서비스 모델이 클라이언트 매개 변수 검사자에 대해 `AfterCall` 메서드를 호출한 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="6d4b4-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6d4b4-114">메시지</span><span class="sxs-lookup"><span data-stu-id="6d4b4-114">Message</span></span>  

 <span data-ttu-id="6d4b4-115">디스패처가 '%1' 형식의 ClientParameterInspector에 대해 'AfterCall'을 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4b4-115">The Dispatcher invoked 'AfterCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6d4b4-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="6d4b4-116">Details</span></span>  
  
|<span data-ttu-id="6d4b4-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="6d4b4-117">Data Item Name</span></span>|<span data-ttu-id="6d4b4-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="6d4b4-118">Data Item Type</span></span>|<span data-ttu-id="6d4b4-119">Description</span><span class="sxs-lookup"><span data-stu-id="6d4b4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6d4b4-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="6d4b4-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="6d4b4-121">호출된 검사자 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="6d4b4-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="6d4b4-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="6d4b4-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="6d4b4-123">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="6d4b4-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="6d4b4-124">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d4b4-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="6d4b4-125">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="6d4b4-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="6d4b4-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6d4b4-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="6d4b4-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6d4b4-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
