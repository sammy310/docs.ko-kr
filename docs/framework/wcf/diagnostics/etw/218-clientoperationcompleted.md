---
title: 218 - ClientOperationCompleted
ms.date: 03/30/2017
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
ms.openlocfilehash: d74aa77aff7b45b50f6891c999889011d9e03381
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278858"
---
# <a name="218---clientoperationcompleted"></a><span data-ttu-id="cc41d-102">218 - ClientOperationCompleted</span><span class="sxs-lookup"><span data-stu-id="cc41d-102">218 - ClientOperationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="cc41d-103">속성</span><span class="sxs-lookup"><span data-stu-id="cc41d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cc41d-104">ID</span><span class="sxs-lookup"><span data-stu-id="cc41d-104">ID</span></span>|<span data-ttu-id="cc41d-105">218</span><span class="sxs-lookup"><span data-stu-id="cc41d-105">218</span></span>|  
|<span data-ttu-id="cc41d-106">키워드</span><span class="sxs-lookup"><span data-stu-id="cc41d-106">Keywords</span></span>|<span data-ttu-id="cc41d-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cc41d-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="cc41d-108">Level</span><span class="sxs-lookup"><span data-stu-id="cc41d-108">Level</span></span>|<span data-ttu-id="cc41d-109">정보</span><span class="sxs-lookup"><span data-stu-id="cc41d-109">Information</span></span>|  
|<span data-ttu-id="cc41d-110">채널</span><span class="sxs-lookup"><span data-stu-id="cc41d-110">Channel</span></span>|<span data-ttu-id="cc41d-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="cc41d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cc41d-112">Description</span><span class="sxs-lookup"><span data-stu-id="cc41d-112">Description</span></span>  

 <span data-ttu-id="cc41d-113">이 이벤트는 작업이 완료된 직후에 클라이언트에서 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="cc41d-113">This event is emitted by clients just after an operation completes.</span></span> <span data-ttu-id="cc41d-114">즉, 단방향 작업의 경우 메시지가 성공적으로 보내진 직후에 내보내지고</span><span class="sxs-lookup"><span data-stu-id="cc41d-114">For one-way operations, this is just after the message is sent successfully.</span></span> <span data-ttu-id="cc41d-115">요청-응답 작업의 경우 응답이 수신된 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="cc41d-115">For request-response operations this is after the response is received.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cc41d-116">메시지</span><span class="sxs-lookup"><span data-stu-id="cc41d-116">Message</span></span>  

 <span data-ttu-id="cc41d-117">클라이언트가 '%2' 계약과 연결된 '%1' 작업 실행을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="cc41d-117">The Client completed executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="cc41d-118">메시지가 '%3'(으)로 전송되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc41d-118">The message was sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cc41d-119">세부 정보</span><span class="sxs-lookup"><span data-stu-id="cc41d-119">Details</span></span>  
  
|<span data-ttu-id="cc41d-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="cc41d-120">Data Item Name</span></span>|<span data-ttu-id="cc41d-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="cc41d-121">Data Item Type</span></span>|<span data-ttu-id="cc41d-122">설명</span><span class="sxs-lookup"><span data-stu-id="cc41d-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cc41d-123">작업</span><span class="sxs-lookup"><span data-stu-id="cc41d-123">Action</span></span>|<span data-ttu-id="cc41d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="cc41d-124">xs:string</span></span>|<span data-ttu-id="cc41d-125">보내는 메시지의 SOAP 동작 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="cc41d-125">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="cc41d-126">Contract Name</span><span class="sxs-lookup"><span data-stu-id="cc41d-126">Contract Name</span></span>|`xs:string`|<span data-ttu-id="cc41d-127">계약 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cc41d-127">The name of the contract.</span></span> <span data-ttu-id="cc41d-128">예를 들면 ICalculator와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cc41d-128">Example: ICalculator.</span></span>|  
|<span data-ttu-id="cc41d-129">대상</span><span class="sxs-lookup"><span data-stu-id="cc41d-129">Destination</span></span>|`xs:string`|<span data-ttu-id="cc41d-130">메시지를 받은 서비스 엔드포인트의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="cc41d-130">The address of the service endpoint that the message was sent to.</span></span>|  
|<span data-ttu-id="cc41d-131">HostReference</span><span class="sxs-lookup"><span data-stu-id="cc41d-131">HostReference</span></span>|`xs:string`|<span data-ttu-id="cc41d-132">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="cc41d-132">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="cc41d-133">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc41d-133">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="cc41d-134">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="cc41d-134">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="cc41d-135">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cc41d-135">AppDomain</span></span>|`xs:string`|<span data-ttu-id="cc41d-136">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="cc41d-136">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
