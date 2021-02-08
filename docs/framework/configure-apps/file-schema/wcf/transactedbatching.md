---
description: 다음에 대해 자세히 알아보세요. <transactedBatching>
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 9a57226c3a2f2b026c69324e37b00e87fd3dd693
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773695"
---
# \<transactedBatching>

<span data-ttu-id="87be1-102">받기 작업에 트랜잭션 일괄 처리가 지원되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="87be1-102">Specifies whether transaction batching is supported for receive operations.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactedBatching>**  

## <a name="syntax"></a><span data-ttu-id="87be1-103">구문</span><span class="sxs-lookup"><span data-stu-id="87be1-103">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="87be1-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="87be1-104">Attributes and Elements</span></span>

<span data-ttu-id="87be1-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="87be1-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="87be1-106">특성</span><span class="sxs-lookup"><span data-stu-id="87be1-106">Attributes</span></span>

|<span data-ttu-id="87be1-107">attribute</span><span class="sxs-lookup"><span data-stu-id="87be1-107">Attribute</span></span>|<span data-ttu-id="87be1-108">설명</span><span class="sxs-lookup"><span data-stu-id="87be1-108">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="87be1-109">트랜잭션 한 번으로 일괄 처리할 수 있는 받기 작업의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="87be1-109">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="87be1-110">기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="87be1-110">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="87be1-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="87be1-111">Child Elements</span></span>

<span data-ttu-id="87be1-112">없음</span><span class="sxs-lookup"><span data-stu-id="87be1-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="87be1-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="87be1-113">Parent Elements</span></span>

|<span data-ttu-id="87be1-114">요소</span><span class="sxs-lookup"><span data-stu-id="87be1-114">Element</span></span>|<span data-ttu-id="87be1-115">설명</span><span class="sxs-lookup"><span data-stu-id="87be1-115">Description</span></span>|
|-------------|-----------------|
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="87be1-116">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="87be1-116">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="87be1-117">설명</span><span class="sxs-lookup"><span data-stu-id="87be1-117">Remarks</span></span>

<span data-ttu-id="87be1-118">트랜잭션 일괄 처리로 구성된 전송에서 여러 개의 받기 작업을 한 번의 트랜잭션으로 일괄 처리하도록 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="87be1-118">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="87be1-119">이렇게 하면 모든 받기 작업에서 트랜잭션을 만들고 이를 커밋하는 비용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87be1-119">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="87be1-120">예제</span><span class="sxs-lookup"><span data-stu-id="87be1-120">Example</span></span>

<span data-ttu-id="87be1-121">다음 예제에서는 구성 파일에서 트랜잭션된 일괄 처리 동작을 서비스에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87be1-121">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="87be1-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87be1-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
