---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: 77ed5e91f09d9e658deeb7996baaca445b4e0c90
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937104"
---
# <a name="servicethrottling"></a><span data-ttu-id="413cd-101">\<serviceThrottling></span><span class="sxs-lookup"><span data-stu-id="413cd-101">\<serviceThrottling></span></span>
<span data-ttu-id="413cd-102">WCF(Windows Communication Foundation) 서비스의 스로틀 메커니즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="413cd-102">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="413cd-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="413cd-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="413cd-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="413cd-104">\<behaviors></span></span>  
<span data-ttu-id="413cd-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="413cd-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="413cd-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="413cd-106">\<behavior></span></span>  
<span data-ttu-id="413cd-107">\<serviceThrottling></span><span class="sxs-lookup"><span data-stu-id="413cd-107">\<serviceThrottling></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="413cd-108">구문</span><span class="sxs-lookup"><span data-stu-id="413cd-108">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="413cd-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="413cd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="413cd-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="413cd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="413cd-111">특성</span><span class="sxs-lookup"><span data-stu-id="413cd-111">Attributes</span></span>  
  
|<span data-ttu-id="413cd-112">특성</span><span class="sxs-lookup"><span data-stu-id="413cd-112">Attribute</span></span>|<span data-ttu-id="413cd-113">설명</span><span class="sxs-lookup"><span data-stu-id="413cd-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="413cd-114">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="413cd-114">maxConcurrentCalls</span></span>|<span data-ttu-id="413cd-115"><xref:System.ServiceModel.ServiceHost>에서 현재 처리되는 메시지 수를 제한하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="413cd-115">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="413cd-116">한도를 초과하는 호출은 대기됩니다.</span><span class="sxs-lookup"><span data-stu-id="413cd-116">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="413cd-117">이 값을 0으로 설정하는 것은 Int32.MaxValue로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="413cd-117">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="413cd-118">기본값은 16 \* 프로세서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="413cd-118">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="413cd-119">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="413cd-119">maxConcurrentInstances</span></span>|<span data-ttu-id="413cd-120"><xref:System.ServiceModel.InstanceContext>에서 한 번에 실행하는 <xref:System.ServiceModel.ServiceHost> 개체 수를 제한하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="413cd-120">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="413cd-121">추가 인스턴스 생성 요청은 큐에 대기했다가 인스턴스 수가 한도 아래로 내려가면 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="413cd-121">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="413cd-122">기본값은 maxConcurrentSessions와 MaxConcurrentCalls의 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="413cd-122">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="413cd-123">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="413cd-123">maxConcurrentSessions</span></span>|<span data-ttu-id="413cd-124"><xref:System.ServiceModel.ServiceHost> 개체에서 수락할 수 있는 세션 수를 제한하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="413cd-124">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="413cd-125">서비스는 제한을 초과하는 연결을 수락하지만 제한 아래의 채널만 활성화되며 해당 채널에서 메시지를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="413cd-125">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="413cd-126">이 값을 0으로 설정하는 것은 Int32.MaxValue로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="413cd-126">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="413cd-127">기본값은 100 \* 프로세서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="413cd-127">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="413cd-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="413cd-128">Child Elements</span></span>  
 <span data-ttu-id="413cd-129">없음</span><span class="sxs-lookup"><span data-stu-id="413cd-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="413cd-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="413cd-130">Parent Elements</span></span>  
  
|<span data-ttu-id="413cd-131">요소</span><span class="sxs-lookup"><span data-stu-id="413cd-131">Element</span></span>|<span data-ttu-id="413cd-132">설명</span><span class="sxs-lookup"><span data-stu-id="413cd-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="413cd-133">\<behavior></span><span class="sxs-lookup"><span data-stu-id="413cd-133">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="413cd-134">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="413cd-134">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="413cd-135">설명</span><span class="sxs-lookup"><span data-stu-id="413cd-135">Remarks</span></span>  
 <span data-ttu-id="413cd-136">스로틀은 리소스가 과도하게 사용되는 것을 방지하기 위해 동시 호출, 인스턴스 또는 세션 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="413cd-136">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="413cd-137">특성 값에 도달할 때마다 추적이 기록되며</span><span class="sxs-lookup"><span data-stu-id="413cd-137">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="413cd-138">첫 번째 추적이 경고로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="413cd-138">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="413cd-139">예제</span><span class="sxs-lookup"><span data-stu-id="413cd-139">Example</span></span>  
 <span data-ttu-id="413cd-140">다음 구성 예제에서는 서비스가 최대 동시 호출 수를 2로 제한하고 최대 동시 인스턴스 수를 10으로 제한하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="413cd-140">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="413cd-141">이 예제를 실행 하는 방법에 대 한 자세한 예제는 [제한](../../../wcf/samples/throttling.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="413cd-141">For a detailed example of running this example, see [Throttling](../../../wcf/samples/throttling.md).</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDebug includeExceptionDetailInFaults="False" />
      <serviceMetadata httpGetEnabled="True" />
      <!-- Specify throttling behavior -->
      <serviceThrottling maxConcurrentCalls="2"
                         maxConcurrentInstances="10" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="413cd-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="413cd-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [<span data-ttu-id="413cd-143">ServiceThrottlingBehavior를 사용하여 WCF 서비스 성능 제어</span><span class="sxs-lookup"><span data-stu-id="413cd-143">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
