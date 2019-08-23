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
# <a name="transactedbatching"></a>\<transactedBatching>

받기 작업에 트랜잭션 일괄 처리가 지원되는지 여부를 지정합니다.

\<system.ServiceModel>\
\<behaviors>\
\<endpointBehaviors>\
\<behavior>\
\<transactedBatching>

## <a name="syntax"></a>구문

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|특성|Description|
|---------------|-----------------|
|`maxBatchSize`|트랜잭션 한 번으로 일괄 처리할 수 있는 받기 작업의 최대 수를 지정하는 정수입니다. 기본값은 0입니다.|

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[\<behavior>](behavior-of-endpointbehaviors.md)|엔드포인트 동작을 지정합니다.|

## <a name="remarks"></a>설명

트랜잭션 일괄 처리로 구성된 전송에서 여러 개의 받기 작업을 한 번의 트랜잭션으로 일괄 처리하도록 시도합니다. 이렇게 하면 모든 받기 작업에서 트랜잭션을 만들고 이를 커밋하는 비용을 줄일 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 구성 파일에서 트랜잭션된 일괄 처리 동작을 서비스에 추가하는 방법을 보여 줍니다.

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

## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
