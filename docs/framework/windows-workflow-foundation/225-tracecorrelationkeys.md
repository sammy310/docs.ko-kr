---
description: '자세한 정보: 225-TraceCorrelationKeys'
title: 225 - TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: c5fdb9305815cdc4df6bbae3e54209d2b5cffd9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778115"
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="0cef1-103">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="0cef1-103">225 - TraceCorrelationKeys</span></span>

## <a name="properties"></a><span data-ttu-id="0cef1-104">속성</span><span class="sxs-lookup"><span data-stu-id="0cef1-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0cef1-105">ID</span><span class="sxs-lookup"><span data-stu-id="0cef1-105">ID</span></span>|<span data-ttu-id="0cef1-106">225</span><span class="sxs-lookup"><span data-stu-id="0cef1-106">225</span></span>|  
|<span data-ttu-id="0cef1-107">키워드</span><span class="sxs-lookup"><span data-stu-id="0cef1-107">Keywords</span></span>|<span data-ttu-id="0cef1-108">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0cef1-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="0cef1-109">Level</span><span class="sxs-lookup"><span data-stu-id="0cef1-109">Level</span></span>|<span data-ttu-id="0cef1-110">정보</span><span class="sxs-lookup"><span data-stu-id="0cef1-110">Information</span></span>|  
|<span data-ttu-id="0cef1-111">채널</span><span class="sxs-lookup"><span data-stu-id="0cef1-111">Channel</span></span>|<span data-ttu-id="0cef1-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="0cef1-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0cef1-113">설명</span><span class="sxs-lookup"><span data-stu-id="0cef1-113">Description</span></span>  

 <span data-ttu-id="0cef1-114">이 이벤트는 워크플로 서비스에 내용 기반 상관 관계가 사용될 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="0cef1-114">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="0cef1-115">여기에는 메시지를 인스턴스에 연결하기 위해 적용되는 상관 관계 키가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cef1-115">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0cef1-116">메시지</span><span class="sxs-lookup"><span data-stu-id="0cef1-116">Message</span></span>  

 <span data-ttu-id="0cef1-117">'%3' 부모 범위에서 '%2' 값을 사용하여 '%1' 상관 관계 키를 계산했습니다.</span><span class="sxs-lookup"><span data-stu-id="0cef1-117">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0cef1-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="0cef1-118">Details</span></span>  
  
|<span data-ttu-id="0cef1-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="0cef1-119">Data Item Name</span></span>|<span data-ttu-id="0cef1-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="0cef1-120">Data Item Type</span></span>|<span data-ttu-id="0cef1-121">설명</span><span class="sxs-lookup"><span data-stu-id="0cef1-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0cef1-122">Instance Key</span><span class="sxs-lookup"><span data-stu-id="0cef1-122">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="0cef1-123">상관 관계 값에서 생성된 키입니다.</span><span class="sxs-lookup"><span data-stu-id="0cef1-123">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="0cef1-124">값</span><span class="sxs-lookup"><span data-stu-id="0cef1-124">Values</span></span>|`xs:string`|<span data-ttu-id="0cef1-125">상관 관계 인스턴스 키를 컴퓨팅하는 데 사용된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0cef1-125">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="0cef1-126">Parent Scope</span><span class="sxs-lookup"><span data-stu-id="0cef1-126">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="0cef1-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="0cef1-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="0cef1-128">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="0cef1-128">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="0cef1-129">해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cef1-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="0cef1-130">예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="0cef1-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="0cef1-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0cef1-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0cef1-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0cef1-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
