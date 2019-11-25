---
title: <customBinding>
ms.date: 03/30/2017
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
ms.openlocfilehash: cdaaacf0dfa75209d001f6e8d6ac7175816048aa
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140801"
---
# <a name="custombinding"></a>\<customBinding >

사용자에게 메시징 스택에 대한 모든 권한을 제공합니다.

[ **\<configuration>** ](../configuration-element.md)\
[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; \
&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) >
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<customBinding >**  

## <a name="syntax"></a>구문

```xml
<customBinding>
  <binding name="String"
           closeTimeout="TimeSpan"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
    <compositeDuplex clientBaseAddress="Uri" />
    <reliableSession acknowledgementInterval="TimeSpan"
                     advancedFlowControl="Boolean"
                     bufferedMessagesQuota="Integer"
                     inactivityTimeout="TimeSpan"
                     maxPendingChannels="Integer"
                     maxRetryCount="Integer"
                     ordered="Boolean" />
    <pnrpPeerResolver />
    <windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
    <sslStreamSecurity requireClientCertificate="Boolean" />
    <transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              contextMode="Cookie"
              defaultProtectionLevel="Sign"
              enableKeyDerivation="false"
              keyEntropyMode="ClientEntropy"
              messageProtectionOrder="SignBeforeEncryptAndEncryptSignature"
              securityVersion="WSSecurityXXX2005">
      <localClientSettings cacheCookies="false"
                           detectReplays="false"
                           maxCookieCachingTime="00:07:24" />
      <localServiceSettings replayCacheSize="9"
                            maxClockSkew="00:00:03"
                            replayWindow="00:07:22.2190000" />
    </security>
    <binaryMessageEncoding maxReadPoolSize="Integer"
                           maxWritePoolSize="Integer"
                           maxSessionSize="Integer" />
    <httpsTransport manualAddressing="Boolean"
                    maxMessageSize="Integer"
                    authenticationScheme="Negotiate"
                    bypassProxyOnLocal="Boolean"
                    hostNameComparisonMode="Exact"
                    mapAddressingHeadersToHttpHeaders="Boolean"
                    proxyaddress="Uri"
                    realm="String"
                    requireClientCertificate="Boolean" />
    <peerTransport manualAddressing="false"
                   maxMessageSize="20002"
                   listenIPAddress="202.10.1.9"
                   messageAuthentication="false"
                   peerNodeAuthenticationMode="None"
                   port="1000" />
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              bootstrapBindingConfiguration="String"
              bootstrapBindingSectionName="String"
              defaultProtectionLevel="None/Sign/EncryptAndSign"
              requireDerivedKeys="Boolean"
              securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
              includeTimestamp="Boolean"
              keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
              messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
              protectTokens="Boolean"
              requireSecurityContextCancellation="Boolean"
              securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"
              requireSignatureConfirmation="Boolean">
      <localClientSettings cacheCookies="Boolean"
                           detectReplays="Boolean"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           maxCookieCachingTime="TimeSpan"
                           replayWindow="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           timestampValidityDuration="TimeSpan"
                           cookieRenewalThresholdPercentage="Integer" />
      <localServiceSettings detectReplays="Boolean"
                            issuedCookieLifeTime="TimeSpan"
                            maxStatefulNegotiations="Integer"
                            replayCacheSize="Integer"
                            maxClockSkew="TimeSpan"
                            negotiationTimeout="TimeSpan"
                            replayWindow="TimeSpan"
                            inactivityTimeout="TimeSpan"
                            sessionKeyRenewalInterval="TimeSpan"
                            sessionKeyRolloverInterval="TimeSpan"
                            reconnectOnTransportFailure="Boolean"
                            maxConcurrentSessions="Integer"
                            timestampValidityDuration="TimeSpan" />
      <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />
    </security>
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              bootstrapBindingConfiguration="String"
              bootstrapBindingSectionName="String"
              defaultProtectionLevel="None/Sign/EncryptAndSign"
              requireDerivedKeys="Boolean"
              securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
              includeTimestamp="Boolean"
              keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
              messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
              protectTokens="Boolean"
              requireSecurityContextCancellation="Boolean"
              securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"
              requireSignatureConfirmation="Boolean" >
      <localClientSettings cacheCookies="Boolean"
                           detectReplays="Boolean"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           maxCookieCachingTime="TimeSpan"
                           replayWindow="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           timestampValidityDuration="TimeSpan"
                           cookieRenewalThresholdPercentage="Integer" />
      <localServiceSettings detectReplays="Boolean"
                           issuedCookieLifeTime="TimeSpan"
                           maxStatefulNegotiations="Integer"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           negotiationTimeout="TimeSpan"
                           replayWindow="TimeSpan"
                           inactivityTimeout="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           maxConcurrentSessions="Integer"
                           timestampValidityDuration="TimeSpan" />
      <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />
      <genericIssuedTokenParameters>
        <localIssuerIssuedTokenParameters keyType="SymmetricKey/PublicKey"
                                          keySize="Integer"
                                          tokenType="String" />
        <issuedTokenParametersEndpointAddress address="URI"
                                              bindingConfiguration="String"
                                              binding="String" />
        <issuedTokenClient localIssuerChannelBehaviors="String"
                           cacheIssuedTokens="Boolean"
                           maxIssuedTokenCachingTime="TimeSpan"
                           keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy" />
        <issuedTokenClientBehavior issuerAddress="String"
                                   behaviorConfiguration="String" />
        <issuedTokenClientBehavior address="URI"
                                   bindingConfiguration="String"
                                   binding="String" />
      </genericIssuedTokenParameters>
    </security>
  </binding>
</customBinding>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|특성|설명|
|---------------|-----------------|
|closeTimeout|닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다. 이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다. 기본값은 00:01:00입니다.|
|name|바인딩의 구성 이름을 포함하는 문자열입니다. 이 값은 사용자 지정 바인딩의 식별 문자열 역할을 하는 사용자 정의 문자열입니다. .NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다. 기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.|
|openTimeout|열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다. 이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다. 기본값은 00:01:00입니다.|
|receiveTimeout|받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다. 이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다. 기본값은 00:01:00입니다.|
|sendTimeout|보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다. 이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다. 기본값은 00:01:00입니다.|

### <a name="child-elements"></a>자식 요소

|요소|설명|
|-------------|-----------------|
|[\<compositeDuplex >](compositeduplex.md)|사용자 지정 바인딩에 대한 양방향 메시징을 정의합니다. HTTP와 같이 기본적으로 이중 통신을 허용 하지 않는 전송에 사용 됩니다. 이와 대조적으로 TCP는 기본적으로 이중 통신을 허용 하며, 서비스에 대해이 바인딩 요소를 사용 하 여 메시지를 클라이언트로 다시 보낼 필요가 없습니다.<br /><br /> 클라이언트는 연락처를 만들고 연결을 설정 하기 위해 서비스에 대 한 주소를 노출 해야 합니다. 이 클라이언트 주소는 `ClientBaseAddress` 특성을 사용하여 제공합니다.<br /><br /> 이 요소는 <xref:System.ServiceModel.Configuration.CompositeDuplexElement> 형식입니다.|
|[\<pnrpPeerResolver >](pnrppeerresolver.md)|PNRP(피어 이름 확인 프로토콜) 피어 이름 확인자를 지정합니다. 이 요소는 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement> 형식입니다.|
|[\<reliableSession >](reliablesession.md)|WS-Reliable Messaging 설정을 지정합니다. 이 요소를 사용자 지정 바인딩에 추가 하면 결과 채널에서 정확히 한 번의 배달 보증을 지원할 수 있습니다. 이 요소는 <xref:System.ServiceModel.Configuration.ReliableSessionElement> 형식입니다.|
|[\<보안 >](security-of-custombinding.md)|사용자 지정 바인딩에 대한 보안 옵션을 지정합니다. 이 요소는 <xref:System.ServiceModel.Configuration.SecurityElement> 형식입니다.|
|[\<sslStreamSecurity >](sslstreamsecurity.md)|SSL 스트림 바인딩에 대한 보안 설정을 지정합니다. 이 요소는 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement> 형식입니다.|
|[\<transactionFlow >](transactionflow.md)|바인딩이 트랜잭션 흐름 및 `transactionProtocol` 특성에 사용될 프로토콜을 지원하도록 지정합니다. 이 요소는 <xref:System.ServiceModel.Configuration.TransactionFlowElement> 형식입니다.|
|[\<windowsStreamSecurity >](windowsstreamsecurity.md)|사용자 지정 바인딩에 대한 스트리밍 보안 옵션을 지정합니다. 이 요소는 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement> 형식입니다.|

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|바인딩|Windows Communication Foundation 애플리케이션에 대한 모든 바인딩을 포함합니다.|

## <a name="remarks"></a>주의

사용자 지정 바인딩은 WCF 메시징 스택에 대한 모든 권한을 제공합니다. 특정 엔터티의 구성 요소를 추가하여 특수하게 조정된 바인딩을 만들 수 있습니다. 예를 들어, 사용자는 `httpsTransport` 섹션, `reliableSession` 섹션 및 `security` 섹션을 결합하여 믿을 수 있으며 안전한 https 기반 바인딩을 만들 수 있습니다.

개별 바인딩은 스택에 표시 되는 순서 대로 스택 요소에 대 한 구성 요소를 지정 하 여 메시지 스택을 정의 합니다. 각 요소는 스택의 한 요소를 정의 하 고 구성 합니다. 각 사용자 지정 바인딩에는 하나의 전송 요소만 있어야 합니다. 이 요소가 없으면 메시징 스택이 완전 하지 않습니다.

스택에서 요소가 표시 되는 순서는 작업이 메시지에 적용 되는 순서 이기 때문에 중요 합니다. 권장 되는 스택 요소 순서는 다음과 같습니다.

1. 트랜잭션 (옵션)

2. 안정적인 메시징 (옵션)

3. 보안 (선택 사항)

4. 전송

5. 인코더 (선택 사항)

시스템에서 제공 하는 바인딩 중 하나가 사용자의 서비스 요구 사항을 충족 하지 않는 경우 사용자 지정 바인딩을 사용 합니다. 예를 들어 서비스 끝점에서 새 전송 또는 새 인코더를 사용할 수 있도록 사용자 지정 바인딩을 사용할 수 있습니다.

사용자 지정 바인딩은 특정 순서로 "누적" 되는 바인딩 요소 컬렉션의 <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> 중 하나를 사용 하 여 생성 됩니다.

- 위쪽은 트랜잭션 이동을 허용 하는 선택적 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>입니다.

- 다음은 WS-RELIABLEMESSAGING 사양에 정의 된 대로 세션 및 순서 지정 메커니즘을 제공 하는 선택적 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>입니다. 이 세션의 개념은 SOAP 및 전송 중개자를 통과할 수 있습니다.

- 다음은 권한 부여, 인증, 보호 및 기밀성과 같은 보안 기능을 제공 하는 선택적 보안 바인딩 요소입니다. WCF (Windows Communication Foundation)에서 제공 하는 보안 바인딩 요소는 다음과 같습니다.

  - <xref:System.ServiceModel.Channels.SecurityBindingElement>

  - <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>

- 다음은 바인딩 요소에 지정 된 선택적 메시지 패턴입니다.

- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>

- 다음은 선택적 전송 업그레이드/도우미 바인딩 요소입니다.

  - <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- 다음은 필수 메시지 인코딩 바인딩 요소입니다. 사용자 고유의 전송을 사용 하거나 다음 메시지 인코딩 바인딩 중 하나를 사용할 수 있습니다.

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

- 맨 아래에는 필수 전송 요소가 있습니다. 사용자 고유의 전송을 사용 하거나 WCF (Windows Communication Foundation)에서 제공 하는 전송 바인딩 요소 중 하나를 사용할 수 있습니다.

  - <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

  - <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

  - <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

  - <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

다음 표에서는 각 계층에 대 한 옵션을 요약 합니다.

|레이어도|옵션|필요한 공간|
|-----------|-------------|--------------|
|트랜잭션 흐름|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|아니요|
|안정성|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|아니요|
|보안|대칭, 비대칭, 전송 수준|아니요|
|모양 변경|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|아니요|
|전송 업그레이드|SSL 스트림, Windows 스트림, 피어 확인자|아니요|
|인코딩|텍스트, 이진, MTOM, 사용자 지정|예|
|전송|TCP, 명명 된 파이프, HTTP, HTTPS, MSMQ의 특성, 사용자 지정|예|

또한 사용자 고유의 바인딩 요소를 정의 하 고 앞에서 정의한 계층 사이에 삽입할 수 있습니다.

사용자 지정 바인딩을 사용 하 여 시스템 제공 바인딩을 수정 하는 방법에 대 한 설명은 [방법: 시스템 제공 바인딩 사용자 지정](../../../wcf/extending/how-to-customize-a-system-provided-binding.md)을 참조 하세요.

## <a name="see-also"></a>참조

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<바인딩 >](bindings.md)
- [바인딩](../../../wcf/bindings.md)
- [바인딩 확장](../../../wcf/extending/extending-bindings.md)
- [사용자 지정 바인딩](../../../wcf/extending/custom-bindings.md)
- [customBinding 요소](custombinding.md)
- [바인딩](../../../wcf/bindings.md)
- [시스템 제공 바인딩 구성](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../wcf/using-bindings-to-configure-services-and-clients.md)
