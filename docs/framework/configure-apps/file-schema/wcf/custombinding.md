---
title: <customBinding>
ms.date: 03/30/2017
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
ms.openlocfilehash: 9ed5f25a9297edc5f921305edc009edf5076672b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159746"
---
# <a name="custombinding"></a><span data-ttu-id="f0526-101">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f0526-101">\<customBinding></span></span>

<span data-ttu-id="f0526-102">사용자에게 메시징 스택에 대한 모든 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-102">Provides full control over the messaging stack for the user.</span></span>

<span data-ttu-id="f0526-103">\<system.serviceModel>\\</span><span class="sxs-lookup"><span data-stu-id="f0526-103">\<system.serviceModel>\\</span></span>
<span data-ttu-id="f0526-104">\<bindings>\\</span><span class="sxs-lookup"><span data-stu-id="f0526-104">\<bindings>\\</span></span>
<span data-ttu-id="f0526-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f0526-105">\<customBinding></span></span>

## <a name="syntax"></a><span data-ttu-id="f0526-106">구문</span><span class="sxs-lookup"><span data-stu-id="f0526-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="f0526-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f0526-107">Attributes and Elements</span></span>

<span data-ttu-id="f0526-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-108">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="f0526-109">특성</span><span class="sxs-lookup"><span data-stu-id="f0526-109">Attributes</span></span>

|<span data-ttu-id="f0526-110">특성</span><span class="sxs-lookup"><span data-stu-id="f0526-110">Attribute</span></span>|<span data-ttu-id="f0526-111">설명</span><span class="sxs-lookup"><span data-stu-id="f0526-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="f0526-112">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="f0526-112">closeTimeout</span></span>|<span data-ttu-id="f0526-113">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="f0526-114">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f0526-115">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-115">The default is 00:01:00.</span></span>|
|<span data-ttu-id="f0526-116">name</span><span class="sxs-lookup"><span data-stu-id="f0526-116">name</span></span>|<span data-ttu-id="f0526-117">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-117">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="f0526-118">이 값은 사용자 지정 바인딩의 식별 문자열 역할을 하는 사용자 정의 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-118">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="f0526-119">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="f0526-120">기본 구성 및 이름 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 하세요. [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) 하 고 [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="f0526-121">openTimeout</span><span class="sxs-lookup"><span data-stu-id="f0526-121">openTimeout</span></span>|<span data-ttu-id="f0526-122">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="f0526-123">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f0526-124">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-124">The default is 00:01:00.</span></span>|
|<span data-ttu-id="f0526-125">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="f0526-125">receiveTimeout</span></span>|<span data-ttu-id="f0526-126">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="f0526-127">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f0526-128">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-128">The default is 00:01:00.</span></span>|
|<span data-ttu-id="f0526-129">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="f0526-129">sendTimeout</span></span>|<span data-ttu-id="f0526-130">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-130">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="f0526-131">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-131">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f0526-132">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-132">The default is 00:01:00.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f0526-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f0526-133">Child Elements</span></span>

|<span data-ttu-id="f0526-134">요소</span><span class="sxs-lookup"><span data-stu-id="f0526-134">Element</span></span>|<span data-ttu-id="f0526-135">설명</span><span class="sxs-lookup"><span data-stu-id="f0526-135">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f0526-136">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="f0526-136">\<compositeDuplex></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)|<span data-ttu-id="f0526-137">사용자 지정 바인딩에 대한 양방향 메시징을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-137">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="f0526-138">예를 들어, HTTP와 같이 원래는 이중 통신을 허용하지 않는 전송에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-138">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="f0526-139">그에 반해 TCP는 기본적으로 이중 통신을 허용하므로, 이 바인딩 요소를 사용하지 않더라도 서비스에서 클라이언트로 회신 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-139">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="f0526-140">서비스에서 접속하여 연결을 설정하려면 클라이언트가 주소를 공개해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-140">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="f0526-141">이 클라이언트 주소는 `ClientBaseAddress` 특성을 사용하여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-141">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="f0526-142">이 요소는 <xref:System.ServiceModel.Configuration.CompositeDuplexElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-142">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|
|[<span data-ttu-id="f0526-143">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="f0526-143">\<pnrpPeerResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/pnrppeerresolver.md)|<span data-ttu-id="f0526-144">PNRP(피어 이름 확인 프로토콜) 피어 이름 확인자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-144">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="f0526-145">이 요소는 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-145">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|
|[<span data-ttu-id="f0526-146">\<reliableSession></span><span class="sxs-lookup"><span data-stu-id="f0526-146">\<reliableSession></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md)|<span data-ttu-id="f0526-147">WS-Reliable Messaging 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-147">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="f0526-148">이 요소가 사용자 지정 바인딩에 추가되면 그 결과로 만들어지는 채널에서 EOD(Exactly-Once Delivery) 보증을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-148">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="f0526-149">이 요소는 <xref:System.ServiceModel.Configuration.ReliableSessionElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-149">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|
|[<span data-ttu-id="f0526-150">\<security></span><span class="sxs-lookup"><span data-stu-id="f0526-150">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="f0526-151">사용자 지정 바인딩에 대한 보안 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-151">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="f0526-152">이 요소는 <xref:System.ServiceModel.Configuration.SecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-152">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|
|[<span data-ttu-id="f0526-153">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="f0526-153">\<sslStreamSecurity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)|<span data-ttu-id="f0526-154">SSL 스트림 바인딩에 대한 보안 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-154">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="f0526-155">이 요소는 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-155">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|
|[<span data-ttu-id="f0526-156">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="f0526-156">\<transactionFlow></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md)|<span data-ttu-id="f0526-157">바인딩이 트랜잭션 흐름 및 `transactionProtocol` 특성에 사용될 프로토콜을 지원하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-157">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="f0526-158">이 요소는 <xref:System.ServiceModel.Configuration.TransactionFlowElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-158">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|
|[<span data-ttu-id="f0526-159">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="f0526-159">\<windowsStreamSecurity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsstreamsecurity.md)|<span data-ttu-id="f0526-160">사용자 지정 바인딩에 대한 스트리밍 보안 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-160">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="f0526-161">이 요소는 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-161">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f0526-162">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f0526-162">Parent Elements</span></span>

|<span data-ttu-id="f0526-163">요소</span><span class="sxs-lookup"><span data-stu-id="f0526-163">Element</span></span>|<span data-ttu-id="f0526-164">설명</span><span class="sxs-lookup"><span data-stu-id="f0526-164">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="f0526-165">바인딩</span><span class="sxs-lookup"><span data-stu-id="f0526-165">bindings</span></span>|<span data-ttu-id="f0526-166">Windows Communication Foundation 응용 프로그램에 대한 모든 바인딩을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-166">Contains all bindings for Windows Communication Foundation applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f0526-167">설명</span><span class="sxs-lookup"><span data-stu-id="f0526-167">Remarks</span></span>

<span data-ttu-id="f0526-168">사용자 지정 바인딩은 WCF 메시징 스택에 대한 모든 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-168">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="f0526-169">특정 엔터티의 구성 요소를 추가하여 특수하게 조정된 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-169">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="f0526-170">예를 들어, 사용자는 `httpsTransport` 섹션, `reliableSession` 섹션 및 `security` 섹션을 결합하여 믿을 수 있으며 안전한 https 기반 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-170">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>

<span data-ttu-id="f0526-171">개별 바인딩에서는 스택에 나타나는 순서대로 스택 요소의 구성 요소를 지정함으로써 메시지 스택을 정의하며,</span><span class="sxs-lookup"><span data-stu-id="f0526-171">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="f0526-172">각 요소는 스택의 한 요소를 정의하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-172">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="f0526-173">각 사용자 지정 바인딩에는 단 한 개의 전송 요소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-173">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="f0526-174">이 요소가 없으면 메시징 스택이 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-174">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="f0526-175">스택에서 요소가 나타나는 순서는 작업이 메시지에 적용되는 순서이므로 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-175">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="f0526-176">다음과 같은 스택 요소 순서를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-176">The recommended order of stack elements is the following:</span></span>

1. <span data-ttu-id="f0526-177">Transactions(선택적)</span><span class="sxs-lookup"><span data-stu-id="f0526-177">Transactions (optional)</span></span>

2. <span data-ttu-id="f0526-178">Reliable Messaging(선택적)</span><span class="sxs-lookup"><span data-stu-id="f0526-178">Reliable Messaging (optional)</span></span>

3. <span data-ttu-id="f0526-179">Security(선택적)</span><span class="sxs-lookup"><span data-stu-id="f0526-179">Security (optional)</span></span>

4. <span data-ttu-id="f0526-180">전송</span><span class="sxs-lookup"><span data-stu-id="f0526-180">Transport</span></span>

5. <span data-ttu-id="f0526-181">인코더(선택적)</span><span class="sxs-lookup"><span data-stu-id="f0526-181">Encoder (optional)</span></span>

<span data-ttu-id="f0526-182">시스템에서 제공하는 바인딩 중 하나가 사용자의 서비스 요구 사항을 충족하지 않을 때 사용자 지정 바인딩을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f0526-182">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="f0526-183">사용자 지정 바인딩을 사용하면 예를 들어 서비스 끝점에서 새 전송 또는 새 인코더 사용을 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-183">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>

<span data-ttu-id="f0526-184">사용자 지정 바인딩은 특정 순서로 "스택"되는 바인딩 요소 컬렉션에서 <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> 중 하나를 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-184">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="f0526-185">맨 위에는 트랜잭션 이동을 허용하는 선택적 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-185">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>

- <span data-ttu-id="f0526-186">다음에는 WS-ReliableMessaging 사양에서 정의된 세션 및 순서 지정 메커니즘을 제공하는 선택적 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-186">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="f0526-187">이 세션 개념은 SOAP 매개자 및 전송 매개자에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-187">This notion of a session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="f0526-188">다음에는 권한 부여, 인증, 보호, 기밀성과 같은 보안 기능을 제공하는 선택적 보안 바인딩 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-188">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="f0526-189">다음 보안 바인딩 요소에는 Windows Communication Foundation (WCF)에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-189">The following security binding elements are provided by Windows Communication Foundation (WCF):</span></span>

    - <xref:System.ServiceModel.Channels.SecurityBindingElement>

    - <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

    - <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

    - <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>

- <span data-ttu-id="f0526-190">다음에는 바인딩 요소에서 지정되는 선택적 메시지 패턴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-190">Next are the optional message-patterns specified by binding elements:</span></span>

- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>

- <span data-ttu-id="f0526-191">다음에는 선택적 전송 업그레이드/도우미 바인딩 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-191">Next are the optional transport upgrades/helpers binding elements:</span></span>

    - <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>

    - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

    - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="f0526-192">다음에는 필수 메시지 인코딩 바인딩 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-192">Next is a required message encoding binding element.</span></span> <span data-ttu-id="f0526-193">직접 작성한 전송을 사용하거나 다음 메시지 인코딩 바인딩 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-193">You can use your own transport or use one of the following message encoding bindings:</span></span>

    - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

    - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

    - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

- <span data-ttu-id="f0526-194">맨 아래에는 필수 전송 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-194">At the bottom is a required transport element.</span></span> <span data-ttu-id="f0526-195">고유의 전송을 사용 하거나 전송 하 여 Windows Communication Foundation (WCF)를 제공 하는 요소를 바인딩 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-195">You can use your own transport or use one of transport binding elements provided by Windows Communication Foundation (WCF):</span></span>

    - <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

    - <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

    - <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

    - <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

    - <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

    - <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

    - <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

<span data-ttu-id="f0526-196">다음 표에서는 각 계층의 옵션을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-196">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="f0526-197">계층</span><span class="sxs-lookup"><span data-stu-id="f0526-197">Layer</span></span>|<span data-ttu-id="f0526-198">옵션</span><span class="sxs-lookup"><span data-stu-id="f0526-198">Options</span></span>|<span data-ttu-id="f0526-199">필수</span><span class="sxs-lookup"><span data-stu-id="f0526-199">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="f0526-200">트랜잭션 흐름</span><span class="sxs-lookup"><span data-stu-id="f0526-200">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="f0526-201">아니요</span><span class="sxs-lookup"><span data-stu-id="f0526-201">No</span></span>|
|<span data-ttu-id="f0526-202">안정성</span><span class="sxs-lookup"><span data-stu-id="f0526-202">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="f0526-203">아니요</span><span class="sxs-lookup"><span data-stu-id="f0526-203">No</span></span>|
|<span data-ttu-id="f0526-204">보안</span><span class="sxs-lookup"><span data-stu-id="f0526-204">Security</span></span>|<span data-ttu-id="f0526-205">대칭, 비대칭, 전송 수준</span><span class="sxs-lookup"><span data-stu-id="f0526-205">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="f0526-206">아니요</span><span class="sxs-lookup"><span data-stu-id="f0526-206">No</span></span>|
|<span data-ttu-id="f0526-207">Shape Change</span><span class="sxs-lookup"><span data-stu-id="f0526-207">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="f0526-208">아니요</span><span class="sxs-lookup"><span data-stu-id="f0526-208">No</span></span>|
|<span data-ttu-id="f0526-209">Transport Upgrades</span><span class="sxs-lookup"><span data-stu-id="f0526-209">Transport Upgrades</span></span>|<span data-ttu-id="f0526-210">SSL 스트림, Windows 스트림, 피어 확인자</span><span class="sxs-lookup"><span data-stu-id="f0526-210">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="f0526-211">아니요</span><span class="sxs-lookup"><span data-stu-id="f0526-211">No</span></span>|
|<span data-ttu-id="f0526-212">Encoding</span><span class="sxs-lookup"><span data-stu-id="f0526-212">Encoding</span></span>|<span data-ttu-id="f0526-213">텍스트, 이진, MTOM, 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="f0526-213">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="f0526-214">예</span><span class="sxs-lookup"><span data-stu-id="f0526-214">Yes</span></span>|
|<span data-ttu-id="f0526-215">전송</span><span class="sxs-lookup"><span data-stu-id="f0526-215">Transport</span></span>|<span data-ttu-id="f0526-216">TCP, 명명된 파이프, HTTP, HTTPS, MSMQ 버전, 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="f0526-216">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="f0526-217">예</span><span class="sxs-lookup"><span data-stu-id="f0526-217">Yes</span></span>|

<span data-ttu-id="f0526-218">또한 고유의 바인딩 요소를 정의하여 이전에 정의된 계층 사이에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-218">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

<span data-ttu-id="f0526-219">사용자 지정 시스템 제공 바인딩을 수정 하는 바인딩을 사용 하는 방법에 대 한 논의 참조 하세요. [방법: 시스템 제공 바인딩 사용자 지정](../../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f0526-219">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0526-220">참고자료</span><span class="sxs-lookup"><span data-stu-id="f0526-220">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f0526-221">\<binding></span><span class="sxs-lookup"><span data-stu-id="f0526-221">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="f0526-222">바인딩</span><span class="sxs-lookup"><span data-stu-id="f0526-222">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f0526-223">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="f0526-223">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f0526-224">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="f0526-224">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f0526-225">customBinding 요소</span><span class="sxs-lookup"><span data-stu-id="f0526-225">customBinding Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="f0526-226">바인딩</span><span class="sxs-lookup"><span data-stu-id="f0526-226">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f0526-227">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="f0526-227">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f0526-228">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="f0526-228">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
