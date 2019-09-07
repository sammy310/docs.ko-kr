---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: ad87a5876381a7224341babdb076c85edcd1dd87
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399569"
---
# <a name="servicethrottling"></a><span data-ttu-id="e3589-101">\<serviceThrottling></span><span class="sxs-lookup"><span data-stu-id="e3589-101">\<serviceThrottling></span></span>
<span data-ttu-id="e3589-102">WCF(Windows Communication Foundation) 서비스의 스로틀 메커니즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e3589-102">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
<span data-ttu-id="e3589-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e3589-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e3589-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e3589-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e3589-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e3589-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="e3589-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e3589-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="e3589-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e3589-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="e3589-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceThrottling >**</span><span class="sxs-lookup"><span data-stu-id="e3589-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceThrottling>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3589-109">구문</span><span class="sxs-lookup"><span data-stu-id="e3589-109">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3589-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e3589-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e3589-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3589-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3589-112">특성</span><span class="sxs-lookup"><span data-stu-id="e3589-112">Attributes</span></span>  
  
|<span data-ttu-id="e3589-113">특성</span><span class="sxs-lookup"><span data-stu-id="e3589-113">Attribute</span></span>|<span data-ttu-id="e3589-114">Description</span><span class="sxs-lookup"><span data-stu-id="e3589-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e3589-115">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="e3589-115">maxConcurrentCalls</span></span>|<span data-ttu-id="e3589-116"><xref:System.ServiceModel.ServiceHost>에서 현재 처리되는 메시지 수를 제한하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3589-116">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="e3589-117">한도를 초과하는 호출은 대기됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3589-117">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="e3589-118">이 값을 0으로 설정하는 것은 Int32.MaxValue로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3589-118">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="e3589-119">기본값은 16 \* 프로세서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3589-119">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="e3589-120">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="e3589-120">maxConcurrentInstances</span></span>|<span data-ttu-id="e3589-121"><xref:System.ServiceModel.InstanceContext>에서 한 번에 실행하는 <xref:System.ServiceModel.ServiceHost> 개체 수를 제한하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3589-121">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="e3589-122">추가 인스턴스 생성 요청은 큐에 대기했다가 인스턴스 수가 한도 아래로 내려가면 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3589-122">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="e3589-123">기본값은 maxConcurrentSessions와 MaxConcurrentCalls의 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="e3589-123">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="e3589-124">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="e3589-124">maxConcurrentSessions</span></span>|<span data-ttu-id="e3589-125"><xref:System.ServiceModel.ServiceHost> 개체에서 수락할 수 있는 세션 수를 제한하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3589-125">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="e3589-126">서비스는 제한을 초과하는 연결을 수락하지만 제한 아래의 채널만 활성화되며 해당 채널에서 메시지를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="e3589-126">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="e3589-127">이 값을 0으로 설정하는 것은 Int32.MaxValue로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3589-127">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="e3589-128">기본값은 100 \* 프로세서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3589-128">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3589-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e3589-129">Child Elements</span></span>  
 <span data-ttu-id="e3589-130">없음</span><span class="sxs-lookup"><span data-stu-id="e3589-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e3589-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e3589-131">Parent Elements</span></span>  
  
|<span data-ttu-id="e3589-132">요소</span><span class="sxs-lookup"><span data-stu-id="e3589-132">Element</span></span>|<span data-ttu-id="e3589-133">설명</span><span class="sxs-lookup"><span data-stu-id="e3589-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3589-134">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e3589-134">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="e3589-135">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e3589-135">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3589-136">설명</span><span class="sxs-lookup"><span data-stu-id="e3589-136">Remarks</span></span>  
 <span data-ttu-id="e3589-137">스로틀은 리소스가 과도하게 사용되는 것을 방지하기 위해 동시 호출, 인스턴스 또는 세션 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="e3589-137">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="e3589-138">특성 값에 도달할 때마다 추적이 기록되며</span><span class="sxs-lookup"><span data-stu-id="e3589-138">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="e3589-139">첫 번째 추적이 경고로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3589-139">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3589-140">예제</span><span class="sxs-lookup"><span data-stu-id="e3589-140">Example</span></span>  
 <span data-ttu-id="e3589-141">다음 구성 예제에서는 서비스가 최대 동시 호출 수를 2로 제한하고 최대 동시 인스턴스 수를 10으로 제한하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e3589-141">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="e3589-142">이 예제를 실행 하는 방법에 대 한 자세한 예제는 [제한](../../../wcf/samples/throttling.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3589-142">For a detailed example of running this example, see [Throttling](../../../wcf/samples/throttling.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e3589-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="e3589-143">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [<span data-ttu-id="e3589-144">ServiceThrottlingBehavior를 사용하여 WCF 서비스 성능 제어</span><span class="sxs-lookup"><span data-stu-id="e3589-144">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
