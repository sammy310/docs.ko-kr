---
title: 212 - ParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
ms.openlocfilehash: 28c2aca4555d2e4ff498e450deae55ad6a87743c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279040"
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="bad4a-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="bad4a-102">212 - ParameterInspectorBeforeCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="bad4a-103">속성</span><span class="sxs-lookup"><span data-stu-id="bad4a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bad4a-104">ID</span><span class="sxs-lookup"><span data-stu-id="bad4a-104">ID</span></span>|<span data-ttu-id="bad4a-105">212</span><span class="sxs-lookup"><span data-stu-id="bad4a-105">212</span></span>|  
|<span data-ttu-id="bad4a-106">키워드</span><span class="sxs-lookup"><span data-stu-id="bad4a-106">Keywords</span></span>|<span data-ttu-id="bad4a-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bad4a-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="bad4a-108">Level</span><span class="sxs-lookup"><span data-stu-id="bad4a-108">Level</span></span>|<span data-ttu-id="bad4a-109">정보</span><span class="sxs-lookup"><span data-stu-id="bad4a-109">Information</span></span>|  
|<span data-ttu-id="bad4a-110">채널</span><span class="sxs-lookup"><span data-stu-id="bad4a-110">Channel</span></span>|<span data-ttu-id="bad4a-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="bad4a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bad4a-112">Description</span><span class="sxs-lookup"><span data-stu-id="bad4a-112">Description</span></span>  

 <span data-ttu-id="bad4a-113">이 이벤트는 서비스 모델이 `BeforeCall`에 대해 `ParameterInspector` 메서드를 호출한 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="bad4a-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bad4a-114">메시지</span><span class="sxs-lookup"><span data-stu-id="bad4a-114">Message</span></span>  

 <span data-ttu-id="bad4a-115">디스패처가 '%1' 형식의 ParameterInspector에 대해 'BeforeCall'을 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="bad4a-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bad4a-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="bad4a-116">Details</span></span>  
  
|<span data-ttu-id="bad4a-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="bad4a-117">Data Item Name</span></span>|<span data-ttu-id="bad4a-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="bad4a-118">Data Item Type</span></span>|<span data-ttu-id="bad4a-119">Description</span><span class="sxs-lookup"><span data-stu-id="bad4a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bad4a-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="bad4a-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="bad4a-121">호출된 검사자 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="bad4a-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="bad4a-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="bad4a-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="bad4a-123">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="bad4a-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="bad4a-124">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bad4a-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="bad4a-125">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="bad4a-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="bad4a-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bad4a-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="bad4a-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bad4a-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
