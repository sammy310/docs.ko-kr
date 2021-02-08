---
description: '자세한 정보: 499-전송 중'
title: 499 - TransferEmitted
ms.date: 03/30/2017
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
ms.openlocfilehash: d9802ef718ce6091abe1d1092ad6bb7e7fff108a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783575"
---
# <a name="499---transferemitted"></a><span data-ttu-id="1d0e0-103">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="1d0e0-103">499 - TransferEmitted</span></span>

## <a name="properties"></a><span data-ttu-id="1d0e0-104">속성</span><span class="sxs-lookup"><span data-stu-id="1d0e0-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1d0e0-105">ID</span><span class="sxs-lookup"><span data-stu-id="1d0e0-105">ID</span></span>|<span data-ttu-id="1d0e0-106">499</span><span class="sxs-lookup"><span data-stu-id="1d0e0-106">499</span></span>|  
|<span data-ttu-id="1d0e0-107">키워드</span><span class="sxs-lookup"><span data-stu-id="1d0e0-107">Keywords</span></span>|<span data-ttu-id="1d0e0-108">문제 해결, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="1d0e0-108">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="1d0e0-109">Level</span><span class="sxs-lookup"><span data-stu-id="1d0e0-109">Level</span></span>|<span data-ttu-id="1d0e0-110">LogAlways</span><span class="sxs-lookup"><span data-stu-id="1d0e0-110">LogAlways</span></span>|  
|<span data-ttu-id="1d0e0-111">채널</span><span class="sxs-lookup"><span data-stu-id="1d0e0-111">Channel</span></span>|<span data-ttu-id="1d0e0-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="1d0e0-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1d0e0-113">설명</span><span class="sxs-lookup"><span data-stu-id="1d0e0-113">Description</span></span>  

 <span data-ttu-id="1d0e0-114">전송 이벤트가 발생하는 경우 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d0e0-114">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1d0e0-115">메시지</span><span class="sxs-lookup"><span data-stu-id="1d0e0-115">Message</span></span>  

 <span data-ttu-id="1d0e0-116">전송 이벤트를 내보냈습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0e0-116">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1d0e0-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="1d0e0-117">Details</span></span>  
  
|<span data-ttu-id="1d0e0-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="1d0e0-118">Data Item Name</span></span>|<span data-ttu-id="1d0e0-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="1d0e0-119">Data Item Type</span></span>|<span data-ttu-id="1d0e0-120">설명</span><span class="sxs-lookup"><span data-stu-id="1d0e0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1d0e0-121">HostReference</span><span class="sxs-lookup"><span data-stu-id="1d0e0-121">HostReference</span></span>|`xs:string`|<span data-ttu-id="1d0e0-122">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0e0-122">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="1d0e0-123">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0e0-123">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="1d0e0-124">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="1d0e0-124">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="1d0e0-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1d0e0-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1d0e0-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0e0-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
