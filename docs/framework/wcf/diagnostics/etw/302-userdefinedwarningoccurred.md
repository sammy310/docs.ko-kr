---
title: 302 - UserDefinedWarningOccurred
ms.date: 03/30/2017
ms.assetid: 8d1f0bf1-0151-45e6-be92-573d397b54de
ms.openlocfilehash: b942b2e9716713371b8679fc9df9b9634dfc7283
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243445"
---
# <a name="302---userdefinedwarningoccurred"></a><span data-ttu-id="83adc-102">302 - UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="83adc-102">302 - UserDefinedWarningOccurred</span></span>

## <a name="properties"></a><span data-ttu-id="83adc-103">속성</span><span class="sxs-lookup"><span data-stu-id="83adc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="83adc-104">ID</span><span class="sxs-lookup"><span data-stu-id="83adc-104">ID</span></span>|<span data-ttu-id="83adc-105">302</span><span class="sxs-lookup"><span data-stu-id="83adc-105">302</span></span>|  
|<span data-ttu-id="83adc-106">키워드</span><span class="sxs-lookup"><span data-stu-id="83adc-106">Keywords</span></span>|<span data-ttu-id="83adc-107">문제 해결, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="83adc-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="83adc-108">Level</span><span class="sxs-lookup"><span data-stu-id="83adc-108">Level</span></span>|<span data-ttu-id="83adc-109">경고</span><span class="sxs-lookup"><span data-stu-id="83adc-109">Warning</span></span>|  
|<span data-ttu-id="83adc-110">채널</span><span class="sxs-lookup"><span data-stu-id="83adc-110">Channel</span></span>|<span data-ttu-id="83adc-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="83adc-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="83adc-112">Description</span><span class="sxs-lookup"><span data-stu-id="83adc-112">Description</span></span>  

 <span data-ttu-id="83adc-113">이 이벤트는 사용자 코드에서 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-113">This event is emitted from user code.</span></span> <span data-ttu-id="83adc-114">개발자는 자신의 서비스에서 사용자 정의 경고 이벤트가 발생할 때 이 이벤트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-114">Developers can emit this event when a custom-defined warning event occurs in their service.</span></span> <span data-ttu-id="83adc-115">이 작업은 <xref:System.Diagnostics.Eventing> API를 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="83adc-116">이외에도 이 API를 래핑하고 이 이벤트를 적절히 내보내는 방법을 보여 주는 WCF 샘플을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="83adc-117">메시지</span><span class="sxs-lookup"><span data-stu-id="83adc-117">Message</span></span>  

 <span data-ttu-id="83adc-118">이름:'%1', 참조:'%2', 페이로드:%3</span><span class="sxs-lookup"><span data-stu-id="83adc-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="83adc-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="83adc-119">Details</span></span>  
  
|<span data-ttu-id="83adc-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="83adc-120">Data Item Name</span></span>|<span data-ttu-id="83adc-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="83adc-121">Data Item Type</span></span>|<span data-ttu-id="83adc-122">Description</span><span class="sxs-lookup"><span data-stu-id="83adc-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="83adc-123">이름</span><span class="sxs-lookup"><span data-stu-id="83adc-123">Name</span></span>|`xs:string`|<span data-ttu-id="83adc-124">이벤트의 사용자 정의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="83adc-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="83adc-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="83adc-126">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="83adc-127">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="83adc-128">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="83adc-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="83adc-129">Payload</span><span class="sxs-lookup"><span data-stu-id="83adc-129">Payload</span></span>|`xs:string`|<span data-ttu-id="83adc-130">이벤트의 사용자 정의 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-130">The user-defined payload of the event.</span></span>|
