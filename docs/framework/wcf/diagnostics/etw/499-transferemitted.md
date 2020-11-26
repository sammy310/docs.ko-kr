---
title: 499 - TransferEmitted
ms.date: 03/30/2017
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
ms.openlocfilehash: dc47aa36b5a409c89aaf7963ce51f11cdf84b0fc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247579"
---
# <a name="499---transferemitted"></a><span data-ttu-id="8d3f0-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="8d3f0-102">499 - TransferEmitted</span></span>

## <a name="properties"></a><span data-ttu-id="8d3f0-103">속성</span><span class="sxs-lookup"><span data-stu-id="8d3f0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8d3f0-104">ID</span><span class="sxs-lookup"><span data-stu-id="8d3f0-104">ID</span></span>|<span data-ttu-id="8d3f0-105">499</span><span class="sxs-lookup"><span data-stu-id="8d3f0-105">499</span></span>|  
|<span data-ttu-id="8d3f0-106">키워드</span><span class="sxs-lookup"><span data-stu-id="8d3f0-106">Keywords</span></span>|<span data-ttu-id="8d3f0-107">문제 해결, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="8d3f0-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="8d3f0-108">Level</span><span class="sxs-lookup"><span data-stu-id="8d3f0-108">Level</span></span>|<span data-ttu-id="8d3f0-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="8d3f0-109">LogAlways</span></span>|  
|<span data-ttu-id="8d3f0-110">채널</span><span class="sxs-lookup"><span data-stu-id="8d3f0-110">Channel</span></span>|<span data-ttu-id="8d3f0-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="8d3f0-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8d3f0-112">Description</span><span class="sxs-lookup"><span data-stu-id="8d3f0-112">Description</span></span>  

 <span data-ttu-id="8d3f0-113">전송 이벤트가 발생하는 경우 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8d3f0-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8d3f0-114">메시지</span><span class="sxs-lookup"><span data-stu-id="8d3f0-114">Message</span></span>  

 <span data-ttu-id="8d3f0-115">전송 이벤트를 내보냈습니다.</span><span class="sxs-lookup"><span data-stu-id="8d3f0-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8d3f0-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="8d3f0-116">Details</span></span>  
  
|<span data-ttu-id="8d3f0-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="8d3f0-117">Data Item Name</span></span>|<span data-ttu-id="8d3f0-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="8d3f0-118">Data Item Type</span></span>|<span data-ttu-id="8d3f0-119">Description</span><span class="sxs-lookup"><span data-stu-id="8d3f0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8d3f0-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="8d3f0-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="8d3f0-121">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="8d3f0-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="8d3f0-122">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d3f0-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="8d3f0-123">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="8d3f0-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="8d3f0-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8d3f0-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8d3f0-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8d3f0-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
