---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 6167a4ad56a9481a9f695b770605991a0a88d2d9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399408"
---
# <a name="transactedbatching"></a><span data-ttu-id="ac12d-101">\<transactedBatching></span><span class="sxs-lookup"><span data-stu-id="ac12d-101">\<transactedBatching></span></span>

<span data-ttu-id="ac12d-102">받기 작업에 트랜잭션 일괄 처리가 지원되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac12d-102">Specifies whether transaction batching is supported for receive operations.</span></span>

<span data-ttu-id="ac12d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ac12d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ac12d-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ac12d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ac12d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ac12d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="ac12d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ac12d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="ac12d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ac12d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="ac12d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<transactedBatching >**</span><span class="sxs-lookup"><span data-stu-id="ac12d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactedBatching>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="ac12d-109">구문</span><span class="sxs-lookup"><span data-stu-id="ac12d-109">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ac12d-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ac12d-110">Attributes and Elements</span></span>

<span data-ttu-id="ac12d-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ac12d-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ac12d-112">특성</span><span class="sxs-lookup"><span data-stu-id="ac12d-112">Attributes</span></span>

|<span data-ttu-id="ac12d-113">특성</span><span class="sxs-lookup"><span data-stu-id="ac12d-113">Attribute</span></span>|<span data-ttu-id="ac12d-114">Description</span><span class="sxs-lookup"><span data-stu-id="ac12d-114">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="ac12d-115">트랜잭션 한 번으로 일괄 처리할 수 있는 받기 작업의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="ac12d-115">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="ac12d-116">기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="ac12d-116">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ac12d-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ac12d-117">Child Elements</span></span>

<span data-ttu-id="ac12d-118">없음</span><span class="sxs-lookup"><span data-stu-id="ac12d-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ac12d-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ac12d-119">Parent Elements</span></span>

|<span data-ttu-id="ac12d-120">요소</span><span class="sxs-lookup"><span data-stu-id="ac12d-120">Element</span></span>|<span data-ttu-id="ac12d-121">설명</span><span class="sxs-lookup"><span data-stu-id="ac12d-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ac12d-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ac12d-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="ac12d-123">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac12d-123">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ac12d-124">설명</span><span class="sxs-lookup"><span data-stu-id="ac12d-124">Remarks</span></span>

<span data-ttu-id="ac12d-125">트랜잭션 일괄 처리로 구성된 전송에서 여러 개의 받기 작업을 한 번의 트랜잭션으로 일괄 처리하도록 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="ac12d-125">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="ac12d-126">이렇게 하면 모든 받기 작업에서 트랜잭션을 만들고 이를 커밋하는 비용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac12d-126">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="ac12d-127">예제</span><span class="sxs-lookup"><span data-stu-id="ac12d-127">Example</span></span>

<span data-ttu-id="ac12d-128">다음 예제에서는 구성 파일에서 트랜잭션된 일괄 처리 동작을 서비스에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac12d-128">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamples"
                binding="netMsmqBinding"
                contract="Microsoft.ServiceModel.Samples.IQueueCalculator" />
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>
  <behaviors>
    <endpointBehaviors>
      <behavior name="endpointBehavior">
        <transactedBatching maxBatchSize="10" />
      </behavior>
    </endpointBehaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="true" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```

## <a name="see-also"></a><span data-ttu-id="ac12d-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="ac12d-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
