---
description: '자세한 정보: 217-ClientOperationPrepared'
title: 217 - ClientOperationPrepared
ms.date: 03/30/2017
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
ms.openlocfilehash: eab6a9a654e6e48a8831f238cdf3a3bf7a9f62d2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794353"
---
# <a name="217---clientoperationprepared"></a><span data-ttu-id="edf48-103">217 - ClientOperationPrepared</span><span class="sxs-lookup"><span data-stu-id="edf48-103">217 - ClientOperationPrepared</span></span>

## <a name="properties"></a><span data-ttu-id="edf48-104">속성</span><span class="sxs-lookup"><span data-stu-id="edf48-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="edf48-105">ID</span><span class="sxs-lookup"><span data-stu-id="edf48-105">ID</span></span>|<span data-ttu-id="edf48-106">217</span><span class="sxs-lookup"><span data-stu-id="edf48-106">217</span></span>|  
|<span data-ttu-id="edf48-107">키워드</span><span class="sxs-lookup"><span data-stu-id="edf48-107">Keywords</span></span>|<span data-ttu-id="edf48-108">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="edf48-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="edf48-109">Level</span><span class="sxs-lookup"><span data-stu-id="edf48-109">Level</span></span>|<span data-ttu-id="edf48-110">정보</span><span class="sxs-lookup"><span data-stu-id="edf48-110">Information</span></span>|  
|<span data-ttu-id="edf48-111">채널</span><span class="sxs-lookup"><span data-stu-id="edf48-111">Channel</span></span>|<span data-ttu-id="edf48-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="edf48-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="edf48-113">설명</span><span class="sxs-lookup"><span data-stu-id="edf48-113">Description</span></span>  

 <span data-ttu-id="edf48-114">이 이벤트는 서비스에 작업을 보내기 바로 전에 클라이언트에서 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="edf48-114">This event is emitted by clients just before an operation is sent to the service.</span></span>  
  
## <a name="message"></a><span data-ttu-id="edf48-115">메시지</span><span class="sxs-lookup"><span data-stu-id="edf48-115">Message</span></span>  

 <span data-ttu-id="edf48-116">클라이언트가 '%2' 계약과 연결된 '%1' 작업을 실행하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="edf48-116">The Client is executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="edf48-117">메시지를 '%3'(으)로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="edf48-117">The message will be sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="edf48-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="edf48-118">Details</span></span>  
  
|<span data-ttu-id="edf48-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="edf48-119">Data Item Name</span></span>|<span data-ttu-id="edf48-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="edf48-120">Data Item Type</span></span>|<span data-ttu-id="edf48-121">설명</span><span class="sxs-lookup"><span data-stu-id="edf48-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="edf48-122">작업</span><span class="sxs-lookup"><span data-stu-id="edf48-122">Action</span></span>|`xs:string`|<span data-ttu-id="edf48-123">보내는 메시지의 SOAP 동작 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="edf48-123">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="edf48-124">Contract Name</span><span class="sxs-lookup"><span data-stu-id="edf48-124">Contract Name</span></span>|`xs:string`|<span data-ttu-id="edf48-125">계약 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="edf48-125">The name of the contract.</span></span> <span data-ttu-id="edf48-126">예를 들면 ICalculator와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="edf48-126">Example: ICalculator.</span></span>|  
|<span data-ttu-id="edf48-127">대상</span><span class="sxs-lookup"><span data-stu-id="edf48-127">Destination</span></span>|`xs:string`|<span data-ttu-id="edf48-128">메시지를 받는 서비스 엔드포인트의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="edf48-128">The address of the service endpoint that the message is sent to.</span></span>|  
|<span data-ttu-id="edf48-129">HostReference</span><span class="sxs-lookup"><span data-stu-id="edf48-129">HostReference</span></span>|`xs:string`|<span data-ttu-id="edf48-130">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="edf48-130">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="edf48-131">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="edf48-131">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="edf48-132">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="edf48-132">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="edf48-133">AppDomain</span><span class="sxs-lookup"><span data-stu-id="edf48-133">AppDomain</span></span>|`xs:string`|<span data-ttu-id="edf48-134">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="edf48-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
