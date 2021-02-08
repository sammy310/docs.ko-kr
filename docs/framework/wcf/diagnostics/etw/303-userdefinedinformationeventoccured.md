---
description: '자세한 정보: 303-UserDefinedInformationEventOccured'
title: 303 - UserDefinedInformationEventOccured
ms.date: 03/30/2017
ms.assetid: 5ed5acaf-3755-4417-92c4-4ebc8e854ca1
ms.openlocfilehash: 51c4acd5d10a2d563dd7fbcebf90b75c64ff20ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794236"
---
# <a name="303---userdefinedinformationeventoccured"></a><span data-ttu-id="f17da-103">303 - UserDefinedInformationEventOccured</span><span class="sxs-lookup"><span data-stu-id="f17da-103">303 - UserDefinedInformationEventOccured</span></span>

## <a name="properties"></a><span data-ttu-id="f17da-104">속성</span><span class="sxs-lookup"><span data-stu-id="f17da-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f17da-105">ID</span><span class="sxs-lookup"><span data-stu-id="f17da-105">ID</span></span>|<span data-ttu-id="f17da-106">303</span><span class="sxs-lookup"><span data-stu-id="f17da-106">303</span></span>|  
|<span data-ttu-id="f17da-107">키워드</span><span class="sxs-lookup"><span data-stu-id="f17da-107">Keywords</span></span>|<span data-ttu-id="f17da-108">문제 해결, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="f17da-108">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="f17da-109">Level</span><span class="sxs-lookup"><span data-stu-id="f17da-109">Level</span></span>|<span data-ttu-id="f17da-110">정보</span><span class="sxs-lookup"><span data-stu-id="f17da-110">Information</span></span>|  
|<span data-ttu-id="f17da-111">채널</span><span class="sxs-lookup"><span data-stu-id="f17da-111">Channel</span></span>|<span data-ttu-id="f17da-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="f17da-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f17da-113">설명</span><span class="sxs-lookup"><span data-stu-id="f17da-113">Description</span></span>  

 <span data-ttu-id="f17da-114">이 이벤트는 사용자 코드에서 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="f17da-114">This event is emitted from user code.</span></span> <span data-ttu-id="f17da-115">개발자는 자신의 서비스에서 사용자 정의 정보 이벤트가 발생할 때 이 이벤트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17da-115">Developers can emit this event when a custom-defined informational event occurs in their service.</span></span> <span data-ttu-id="f17da-116">이 작업은 <xref:System.Diagnostics.Eventing> API를 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17da-116">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="f17da-117">이외에도 이 API를 래핑하고 이 이벤트를 적절히 내보내는 방법을 보여 주는 WCF 샘플을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17da-117">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f17da-118">메시지</span><span class="sxs-lookup"><span data-stu-id="f17da-118">Message</span></span>  

 <span data-ttu-id="f17da-119">이름:'%1', 참조:'%2', 페이로드:%3</span><span class="sxs-lookup"><span data-stu-id="f17da-119">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="f17da-120">세부 정보</span><span class="sxs-lookup"><span data-stu-id="f17da-120">Details</span></span>  
  
|<span data-ttu-id="f17da-121">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f17da-121">Data Item Name</span></span>|<span data-ttu-id="f17da-122">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f17da-122">Data Item Type</span></span>|<span data-ttu-id="f17da-123">설명</span><span class="sxs-lookup"><span data-stu-id="f17da-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f17da-124">Name</span><span class="sxs-lookup"><span data-stu-id="f17da-124">Name</span></span>|`xs:string`|<span data-ttu-id="f17da-125">이벤트의 사용자 정의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f17da-125">The user-defined name of the event</span></span>|  
|<span data-ttu-id="f17da-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="f17da-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="f17da-127">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f17da-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f17da-128">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f17da-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f17da-129">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="f17da-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f17da-130">Payload</span><span class="sxs-lookup"><span data-stu-id="f17da-130">Payload</span></span>|`xs:string`|<span data-ttu-id="f17da-131">이벤트의 사용자 정의 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="f17da-131">The user-defined payload of the event.</span></span>|
