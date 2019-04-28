---
title: 213 - ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 819efa2e13c94e2c7a16c24f6ba9c7ef2b87ef8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781825"
---
# <a name="213---servicehoststarted"></a><span data-ttu-id="31a29-102">213 - ServiceHostStarted</span><span class="sxs-lookup"><span data-stu-id="31a29-102">213 - ServiceHostStarted</span></span>
## <a name="properties"></a><span data-ttu-id="31a29-103">속성</span><span class="sxs-lookup"><span data-stu-id="31a29-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="31a29-104">ID</span><span class="sxs-lookup"><span data-stu-id="31a29-104">ID</span></span>|<span data-ttu-id="31a29-105">213</span><span class="sxs-lookup"><span data-stu-id="31a29-105">213</span></span>|  
|<span data-ttu-id="31a29-106">키워드</span><span class="sxs-lookup"><span data-stu-id="31a29-106">Keywords</span></span>|<span data-ttu-id="31a29-107">EndToEndMonitoring, HealthMonitoring, 문제 해결, ServiceHost</span><span class="sxs-lookup"><span data-stu-id="31a29-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span></span>|  
|<span data-ttu-id="31a29-108">수준</span><span class="sxs-lookup"><span data-stu-id="31a29-108">Level</span></span>|<span data-ttu-id="31a29-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="31a29-109">LogAlways</span></span>|  
|<span data-ttu-id="31a29-110">채널</span><span class="sxs-lookup"><span data-stu-id="31a29-110">Channel</span></span>|<span data-ttu-id="31a29-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="31a29-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="31a29-112">설명</span><span class="sxs-lookup"><span data-stu-id="31a29-112">Description</span></span>  
 <span data-ttu-id="31a29-113">이 이벤트는 웹 호스팅 호스트가 시작될 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="31a29-113">This event is emitted when a Web-hosted service host is started.</span></span> <span data-ttu-id="31a29-114">일반적으로 이러한 경우는 서비스가 메시지에 의해 활성화될 때 발생하며,</span><span class="sxs-lookup"><span data-stu-id="31a29-114">This typically happens when the service is activated by a message.</span></span> <span data-ttu-id="31a29-115">서비스가 자동으로 시작되도록 구성된 경우에도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31a29-115">It may also happen if the service is configured to be automatically started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="31a29-116">메시지</span><span class="sxs-lookup"><span data-stu-id="31a29-116">Message</span></span>  
 <span data-ttu-id="31a29-117">ServiceHost 시작: '%1'.</span><span class="sxs-lookup"><span data-stu-id="31a29-117">ServiceHost started: '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="31a29-118">설명</span><span class="sxs-lookup"><span data-stu-id="31a29-118">Details</span></span>  
  
|<span data-ttu-id="31a29-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="31a29-119">Data Item Name</span></span>|<span data-ttu-id="31a29-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="31a29-120">Data Item Type</span></span>|<span data-ttu-id="31a29-121">설명</span><span class="sxs-lookup"><span data-stu-id="31a29-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="31a29-122">Service Type Name</span><span class="sxs-lookup"><span data-stu-id="31a29-122">Service Type Name</span></span>|`xs:string`|<span data-ttu-id="31a29-123">서비스 구현 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="31a29-123">The CLR FullName of the type of the service implementation.</span></span>|  
|<span data-ttu-id="31a29-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="31a29-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="31a29-125">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="31a29-125">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="31a29-126">해당 형식으로 정의 됩니다 ' Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="31a29-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="31a29-127">예제: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="31a29-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="31a29-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="31a29-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="31a29-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="31a29-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
