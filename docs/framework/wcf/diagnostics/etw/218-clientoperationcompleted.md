---
description: '자세한 정보: 218-ClientOperationCompleted'
title: 218 - ClientOperationCompleted
ms.date: 03/30/2017
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
ms.openlocfilehash: 3719b77ce653c5177cf7b92901ecd51982504b83
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794340"
---
# <a name="218---clientoperationcompleted"></a><span data-ttu-id="83ce8-103">218 - ClientOperationCompleted</span><span class="sxs-lookup"><span data-stu-id="83ce8-103">218 - ClientOperationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="83ce8-104">속성</span><span class="sxs-lookup"><span data-stu-id="83ce8-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="83ce8-105">ID</span><span class="sxs-lookup"><span data-stu-id="83ce8-105">ID</span></span>|<span data-ttu-id="83ce8-106">218</span><span class="sxs-lookup"><span data-stu-id="83ce8-106">218</span></span>|  
|<span data-ttu-id="83ce8-107">키워드</span><span class="sxs-lookup"><span data-stu-id="83ce8-107">Keywords</span></span>|<span data-ttu-id="83ce8-108">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="83ce8-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="83ce8-109">Level</span><span class="sxs-lookup"><span data-stu-id="83ce8-109">Level</span></span>|<span data-ttu-id="83ce8-110">정보</span><span class="sxs-lookup"><span data-stu-id="83ce8-110">Information</span></span>|  
|<span data-ttu-id="83ce8-111">채널</span><span class="sxs-lookup"><span data-stu-id="83ce8-111">Channel</span></span>|<span data-ttu-id="83ce8-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="83ce8-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="83ce8-113">설명</span><span class="sxs-lookup"><span data-stu-id="83ce8-113">Description</span></span>  

 <span data-ttu-id="83ce8-114">이 이벤트는 작업이 완료된 직후에 클라이언트에서 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="83ce8-114">This event is emitted by clients just after an operation completes.</span></span> <span data-ttu-id="83ce8-115">즉, 단방향 작업의 경우 메시지가 성공적으로 보내진 직후에 내보내지고</span><span class="sxs-lookup"><span data-stu-id="83ce8-115">For one-way operations, this is just after the message is sent successfully.</span></span> <span data-ttu-id="83ce8-116">요청-응답 작업의 경우 응답이 수신된 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="83ce8-116">For request-response operations this is after the response is received.</span></span>  
  
## <a name="message"></a><span data-ttu-id="83ce8-117">메시지</span><span class="sxs-lookup"><span data-stu-id="83ce8-117">Message</span></span>  

 <span data-ttu-id="83ce8-118">클라이언트가 '%2' 계약과 연결된 '%1' 작업 실행을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="83ce8-118">The Client completed executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="83ce8-119">메시지가 '%3'(으)로 전송되었습니다.</span><span class="sxs-lookup"><span data-stu-id="83ce8-119">The message was sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="83ce8-120">세부 정보</span><span class="sxs-lookup"><span data-stu-id="83ce8-120">Details</span></span>  
  
|<span data-ttu-id="83ce8-121">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="83ce8-121">Data Item Name</span></span>|<span data-ttu-id="83ce8-122">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="83ce8-122">Data Item Type</span></span>|<span data-ttu-id="83ce8-123">설명</span><span class="sxs-lookup"><span data-stu-id="83ce8-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="83ce8-124">작업</span><span class="sxs-lookup"><span data-stu-id="83ce8-124">Action</span></span>|<span data-ttu-id="83ce8-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="83ce8-125">xs:string</span></span>|<span data-ttu-id="83ce8-126">보내는 메시지의 SOAP 동작 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="83ce8-126">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="83ce8-127">Contract Name</span><span class="sxs-lookup"><span data-stu-id="83ce8-127">Contract Name</span></span>|`xs:string`|<span data-ttu-id="83ce8-128">계약 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="83ce8-128">The name of the contract.</span></span> <span data-ttu-id="83ce8-129">예를 들면 ICalculator와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="83ce8-129">Example: ICalculator.</span></span>|  
|<span data-ttu-id="83ce8-130">대상</span><span class="sxs-lookup"><span data-stu-id="83ce8-130">Destination</span></span>|`xs:string`|<span data-ttu-id="83ce8-131">메시지를 받은 서비스 엔드포인트의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="83ce8-131">The address of the service endpoint that the message was sent to.</span></span>|  
|<span data-ttu-id="83ce8-132">HostReference</span><span class="sxs-lookup"><span data-stu-id="83ce8-132">HostReference</span></span>|`xs:string`|<span data-ttu-id="83ce8-133">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="83ce8-133">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="83ce8-134">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83ce8-134">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="83ce8-135">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="83ce8-135">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="83ce8-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="83ce8-136">AppDomain</span></span>|`xs:string`|<span data-ttu-id="83ce8-137">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="83ce8-137">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
