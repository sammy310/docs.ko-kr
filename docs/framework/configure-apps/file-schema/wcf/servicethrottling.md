---
description: 다음에 대해 자세히 알아보세요. <serviceThrottling>
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: eb65f6d60a266a367789d87e4e6ea10ebfd2c7a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786683"
---
# \<serviceThrottling>

<span data-ttu-id="504f8-102">WCF(Windows Communication Foundation) 서비스의 스로틀 메커니즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="504f8-102">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceThrottling>**  
  
## <a name="syntax"></a><span data-ttu-id="504f8-103">구문</span><span class="sxs-lookup"><span data-stu-id="504f8-103">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="504f8-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="504f8-104">Attributes and Elements</span></span>  

 <span data-ttu-id="504f8-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="504f8-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="504f8-106">특성</span><span class="sxs-lookup"><span data-stu-id="504f8-106">Attributes</span></span>  
  
|<span data-ttu-id="504f8-107">attribute</span><span class="sxs-lookup"><span data-stu-id="504f8-107">Attribute</span></span>|<span data-ttu-id="504f8-108">설명</span><span class="sxs-lookup"><span data-stu-id="504f8-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="504f8-109">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="504f8-109">maxConcurrentCalls</span></span>|<span data-ttu-id="504f8-110"><xref:System.ServiceModel.ServiceHost>에서 현재 처리되는 메시지 수를 제한하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="504f8-110">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="504f8-111">한도를 초과하는 호출은 대기됩니다.</span><span class="sxs-lookup"><span data-stu-id="504f8-111">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="504f8-112">이 값을 0으로 설정하는 것은 Int32.MaxValue로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="504f8-112">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="504f8-113">기본값은 16 \* 프로세서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="504f8-113">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="504f8-114">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="504f8-114">maxConcurrentInstances</span></span>|<span data-ttu-id="504f8-115"><xref:System.ServiceModel.InstanceContext>에서 한 번에 실행하는 <xref:System.ServiceModel.ServiceHost> 개체 수를 제한하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="504f8-115">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="504f8-116">추가 인스턴스 생성 요청은 큐에 대기했다가 인스턴스 수가 한도 아래로 내려가면 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="504f8-116">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="504f8-117">기본값은 maxConcurrentSessions와 MaxConcurrentCalls의 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="504f8-117">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="504f8-118">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="504f8-118">maxConcurrentSessions</span></span>|<span data-ttu-id="504f8-119"><xref:System.ServiceModel.ServiceHost> 개체에서 수락할 수 있는 세션 수를 제한하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="504f8-119">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="504f8-120">서비스는 제한을 초과하는 연결을 수락하지만 제한 아래의 채널만 활성화되며 해당 채널에서 메시지를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="504f8-120">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="504f8-121">이 값을 0으로 설정하는 것은 Int32.MaxValue로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="504f8-121">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="504f8-122">기본값은 100 \* 프로세서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="504f8-122">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="504f8-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="504f8-123">Child Elements</span></span>  

 <span data-ttu-id="504f8-124">없음</span><span class="sxs-lookup"><span data-stu-id="504f8-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="504f8-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="504f8-125">Parent Elements</span></span>  
  
|<span data-ttu-id="504f8-126">요소</span><span class="sxs-lookup"><span data-stu-id="504f8-126">Element</span></span>|<span data-ttu-id="504f8-127">설명</span><span class="sxs-lookup"><span data-stu-id="504f8-127">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="504f8-128">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="504f8-128">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="504f8-129">설명</span><span class="sxs-lookup"><span data-stu-id="504f8-129">Remarks</span></span>  

 <span data-ttu-id="504f8-130">스로틀은 리소스가 과도하게 사용되는 것을 방지하기 위해 동시 호출, 인스턴스 또는 세션 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="504f8-130">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="504f8-131">특성 값에 도달할 때마다 추적이 기록되며</span><span class="sxs-lookup"><span data-stu-id="504f8-131">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="504f8-132">첫 번째 추적이 경고로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="504f8-132">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="504f8-133">예제</span><span class="sxs-lookup"><span data-stu-id="504f8-133">Example</span></span>  

 <span data-ttu-id="504f8-134">다음 구성 예제에서는 서비스가 최대 동시 호출 수를 2로 제한하고 최대 동시 인스턴스 수를 10으로 제한하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="504f8-134">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="504f8-135">이 예제를 실행 하는 방법에 대 한 자세한 예제는 [제한](../../../wcf/samples/throttling.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="504f8-135">For a detailed example of running this example, see [Throttling](../../../wcf/samples/throttling.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="504f8-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="504f8-136">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [<span data-ttu-id="504f8-137">ServiceThrottlingBehavior를 사용하여 WCF 서비스 성능 제어</span><span class="sxs-lookup"><span data-stu-id="504f8-137">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
