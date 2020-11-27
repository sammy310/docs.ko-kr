---
title: 213 - ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 87a98d30f5ecde6f81580a95e337df22341c23d4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279027"
---
# <a name="213---servicehoststarted"></a><span data-ttu-id="4589d-102">213 - ServiceHostStarted</span><span class="sxs-lookup"><span data-stu-id="4589d-102">213 - ServiceHostStarted</span></span>

## <a name="properties"></a><span data-ttu-id="4589d-103">속성</span><span class="sxs-lookup"><span data-stu-id="4589d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4589d-104">ID</span><span class="sxs-lookup"><span data-stu-id="4589d-104">ID</span></span>|<span data-ttu-id="4589d-105">213</span><span class="sxs-lookup"><span data-stu-id="4589d-105">213</span></span>|  
|<span data-ttu-id="4589d-106">키워드</span><span class="sxs-lookup"><span data-stu-id="4589d-106">Keywords</span></span>|<span data-ttu-id="4589d-107">EndToEndMonitoring, HealthMonitoring, 문제 해결, ServiceHost</span><span class="sxs-lookup"><span data-stu-id="4589d-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span></span>|  
|<span data-ttu-id="4589d-108">Level</span><span class="sxs-lookup"><span data-stu-id="4589d-108">Level</span></span>|<span data-ttu-id="4589d-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="4589d-109">LogAlways</span></span>|  
|<span data-ttu-id="4589d-110">채널</span><span class="sxs-lookup"><span data-stu-id="4589d-110">Channel</span></span>|<span data-ttu-id="4589d-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="4589d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4589d-112">Description</span><span class="sxs-lookup"><span data-stu-id="4589d-112">Description</span></span>  

 <span data-ttu-id="4589d-113">이 이벤트는 웹 호스팅 호스트가 시작될 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="4589d-113">This event is emitted when a Web-hosted service host is started.</span></span> <span data-ttu-id="4589d-114">일반적으로 이러한 경우는 서비스가 메시지에 의해 활성화될 때 발생하며,</span><span class="sxs-lookup"><span data-stu-id="4589d-114">This typically happens when the service is activated by a message.</span></span> <span data-ttu-id="4589d-115">서비스가 자동으로 시작되도록 구성된 경우에도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4589d-115">It may also happen if the service is configured to be automatically started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4589d-116">메시지</span><span class="sxs-lookup"><span data-stu-id="4589d-116">Message</span></span>  

 <span data-ttu-id="4589d-117">ServiceHost 시작: '%1'.</span><span class="sxs-lookup"><span data-stu-id="4589d-117">ServiceHost started: '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4589d-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="4589d-118">Details</span></span>  
  
|<span data-ttu-id="4589d-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="4589d-119">Data Item Name</span></span>|<span data-ttu-id="4589d-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="4589d-120">Data Item Type</span></span>|<span data-ttu-id="4589d-121">Description</span><span class="sxs-lookup"><span data-stu-id="4589d-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4589d-122">Service Type Name</span><span class="sxs-lookup"><span data-stu-id="4589d-122">Service Type Name</span></span>|`xs:string`|<span data-ttu-id="4589d-123">서비스 구현 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="4589d-123">The CLR FullName of the type of the service implementation.</span></span>|  
|<span data-ttu-id="4589d-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="4589d-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="4589d-125">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4589d-125">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="4589d-126">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4589d-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="4589d-127">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="4589d-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="4589d-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4589d-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4589d-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4589d-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
