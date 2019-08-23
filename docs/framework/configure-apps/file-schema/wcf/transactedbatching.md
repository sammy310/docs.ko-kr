---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 12369f1053638583a3864fab396869d0e7045732
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918673"
---
# <a name="transactedbatching"></a><span data-ttu-id="daddd-101">\<transactedBatching></span><span class="sxs-lookup"><span data-stu-id="daddd-101">\<transactedBatching></span></span>

<span data-ttu-id="daddd-102">받기 작업에 트랜잭션 일괄 처리가 지원되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="daddd-102">Specifies whether transaction batching is supported for receive operations.</span></span>

<span data-ttu-id="daddd-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="daddd-103">\<system.ServiceModel></span></span>\
<span data-ttu-id="daddd-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="daddd-104">\<behaviors></span></span>\
<span data-ttu-id="daddd-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="daddd-105">\<endpointBehaviors></span></span>\
<span data-ttu-id="daddd-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="daddd-106">\<behavior></span></span>\
<span data-ttu-id="daddd-107">\<transactedBatching></span><span class="sxs-lookup"><span data-stu-id="daddd-107">\<transactedBatching></span></span>

## <a name="syntax"></a><span data-ttu-id="daddd-108">구문</span><span class="sxs-lookup"><span data-stu-id="daddd-108">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="daddd-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="daddd-109">Attributes and Elements</span></span>

<span data-ttu-id="daddd-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="daddd-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="daddd-111">특성</span><span class="sxs-lookup"><span data-stu-id="daddd-111">Attributes</span></span>

|<span data-ttu-id="daddd-112">특성</span><span class="sxs-lookup"><span data-stu-id="daddd-112">Attribute</span></span>|<span data-ttu-id="daddd-113">Description</span><span class="sxs-lookup"><span data-stu-id="daddd-113">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="daddd-114">트랜잭션 한 번으로 일괄 처리할 수 있는 받기 작업의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="daddd-114">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="daddd-115">기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="daddd-115">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="daddd-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="daddd-116">Child Elements</span></span>

<span data-ttu-id="daddd-117">없음</span><span class="sxs-lookup"><span data-stu-id="daddd-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="daddd-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="daddd-118">Parent Elements</span></span>

|<span data-ttu-id="daddd-119">요소</span><span class="sxs-lookup"><span data-stu-id="daddd-119">Element</span></span>|<span data-ttu-id="daddd-120">설명</span><span class="sxs-lookup"><span data-stu-id="daddd-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="daddd-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="daddd-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="daddd-122">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="daddd-122">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="daddd-123">설명</span><span class="sxs-lookup"><span data-stu-id="daddd-123">Remarks</span></span>

<span data-ttu-id="daddd-124">트랜잭션 일괄 처리로 구성된 전송에서 여러 개의 받기 작업을 한 번의 트랜잭션으로 일괄 처리하도록 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="daddd-124">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="daddd-125">이렇게 하면 모든 받기 작업에서 트랜잭션을 만들고 이를 커밋하는 비용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daddd-125">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="daddd-126">예제</span><span class="sxs-lookup"><span data-stu-id="daddd-126">Example</span></span>

<span data-ttu-id="daddd-127">다음 예제에서는 구성 파일에서 트랜잭션된 일괄 처리 동작을 서비스에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="daddd-127">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="daddd-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="daddd-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
