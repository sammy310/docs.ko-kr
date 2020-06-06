---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 6167a4ad56a9481a9f695b770605991a0a88d2d9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399408"
---
# \<transactedBatching>

<span data-ttu-id="e30b2-101">받기 작업에 트랜잭션 일괄 처리가 지원되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e30b2-101">Specifies whether transaction batching is supported for receive operations.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactedBatching>**  

## <a name="syntax"></a><span data-ttu-id="e30b2-102">구문</span><span class="sxs-lookup"><span data-stu-id="e30b2-102">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e30b2-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e30b2-103">Attributes and Elements</span></span>

<span data-ttu-id="e30b2-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e30b2-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e30b2-105">특성</span><span class="sxs-lookup"><span data-stu-id="e30b2-105">Attributes</span></span>

|<span data-ttu-id="e30b2-106">attribute</span><span class="sxs-lookup"><span data-stu-id="e30b2-106">Attribute</span></span>|<span data-ttu-id="e30b2-107">Description</span><span class="sxs-lookup"><span data-stu-id="e30b2-107">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="e30b2-108">트랜잭션 한 번으로 일괄 처리할 수 있는 받기 작업의 최대 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="e30b2-108">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="e30b2-109">기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="e30b2-109">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e30b2-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e30b2-110">Child Elements</span></span>

<span data-ttu-id="e30b2-111">없음</span><span class="sxs-lookup"><span data-stu-id="e30b2-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e30b2-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e30b2-112">Parent Elements</span></span>

|<span data-ttu-id="e30b2-113">요소</span><span class="sxs-lookup"><span data-stu-id="e30b2-113">Element</span></span>|<span data-ttu-id="e30b2-114">Description</span><span class="sxs-lookup"><span data-stu-id="e30b2-114">Description</span></span>|
|-------------|-----------------|
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="e30b2-115">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e30b2-115">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e30b2-116">설명</span><span class="sxs-lookup"><span data-stu-id="e30b2-116">Remarks</span></span>

<span data-ttu-id="e30b2-117">트랜잭션 일괄 처리로 구성된 전송에서 여러 개의 받기 작업을 한 번의 트랜잭션으로 일괄 처리하도록 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="e30b2-117">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="e30b2-118">이렇게 하면 모든 받기 작업에서 트랜잭션을 만들고 이를 커밋하는 비용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e30b2-118">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="e30b2-119">예제</span><span class="sxs-lookup"><span data-stu-id="e30b2-119">Example</span></span>

<span data-ttu-id="e30b2-120">다음 예제에서는 구성 파일에서 트랜잭션된 일괄 처리 동작을 서비스에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e30b2-120">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e30b2-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e30b2-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
