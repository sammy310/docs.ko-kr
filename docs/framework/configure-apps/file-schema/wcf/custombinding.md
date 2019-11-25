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
# <a name="custombinding"></a><span data-ttu-id="7cbe2-101">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="7cbe2-101">\<customBinding></span></span>

<span data-ttu-id="7cbe2-102">사용자에게 메시징 스택에 대한 모든 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-102">Provides full control over the messaging stack for the user.</span></span>

<span data-ttu-id="7cbe2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7cbe2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7cbe2-104">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="7cbe2-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7cbe2-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="7cbe2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="7cbe2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<customBinding >**</span><span class="sxs-lookup"><span data-stu-id="7cbe2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customBinding>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="7cbe2-107">구문</span><span class="sxs-lookup"><span data-stu-id="7cbe2-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="7cbe2-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7cbe2-108">Attributes and Elements</span></span>

<span data-ttu-id="7cbe2-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-109">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="7cbe2-110">특성</span><span class="sxs-lookup"><span data-stu-id="7cbe2-110">Attributes</span></span>

|<span data-ttu-id="7cbe2-111">특성</span><span class="sxs-lookup"><span data-stu-id="7cbe2-111">Attribute</span></span>|<span data-ttu-id="7cbe2-112">설명</span><span class="sxs-lookup"><span data-stu-id="7cbe2-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="7cbe2-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="7cbe2-113">closeTimeout</span></span>|<span data-ttu-id="7cbe2-114">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="7cbe2-115">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7cbe2-116">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-116">The default is 00:01:00.</span></span>|
|<span data-ttu-id="7cbe2-117">name</span><span class="sxs-lookup"><span data-stu-id="7cbe2-117">name</span></span>|<span data-ttu-id="7cbe2-118">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-118">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="7cbe2-119">이 값은 사용자 지정 바인딩의 식별 문자열 역할을 하는 사용자 정의 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-119">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="7cbe2-120">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-120">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="7cbe2-121">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="7cbe2-122">openTimeout</span><span class="sxs-lookup"><span data-stu-id="7cbe2-122">openTimeout</span></span>|<span data-ttu-id="7cbe2-123">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="7cbe2-124">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7cbe2-125">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-125">The default is 00:01:00.</span></span>|
|<span data-ttu-id="7cbe2-126">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="7cbe2-126">receiveTimeout</span></span>|<span data-ttu-id="7cbe2-127">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="7cbe2-128">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7cbe2-129">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-129">The default is 00:01:00.</span></span>|
|<span data-ttu-id="7cbe2-130">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="7cbe2-130">sendTimeout</span></span>|<span data-ttu-id="7cbe2-131">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-131">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="7cbe2-132">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-132">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7cbe2-133">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-133">The default is 00:01:00.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7cbe2-134">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7cbe2-134">Child Elements</span></span>

|<span data-ttu-id="7cbe2-135">요소</span><span class="sxs-lookup"><span data-stu-id="7cbe2-135">Element</span></span>|<span data-ttu-id="7cbe2-136">설명</span><span class="sxs-lookup"><span data-stu-id="7cbe2-136">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7cbe2-137">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="7cbe2-137">\<compositeDuplex></span></span>](compositeduplex.md)|<span data-ttu-id="7cbe2-138">사용자 지정 바인딩에 대한 양방향 메시징을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-138">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="7cbe2-139">HTTP와 같이 기본적으로 이중 통신을 허용 하지 않는 전송에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-139">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="7cbe2-140">이와 대조적으로 TCP는 기본적으로 이중 통신을 허용 하며, 서비스에 대해이 바인딩 요소를 사용 하 여 메시지를 클라이언트로 다시 보낼 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-140">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="7cbe2-141">클라이언트는 연락처를 만들고 연결을 설정 하기 위해 서비스에 대 한 주소를 노출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-141">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="7cbe2-142">이 클라이언트 주소는 `ClientBaseAddress` 특성을 사용하여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-142">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="7cbe2-143">이 요소는 <xref:System.ServiceModel.Configuration.CompositeDuplexElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-143">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|
|[<span data-ttu-id="7cbe2-144">\<pnrpPeerResolver ></span><span class="sxs-lookup"><span data-stu-id="7cbe2-144">\<pnrpPeerResolver></span></span>](pnrppeerresolver.md)|<span data-ttu-id="7cbe2-145">PNRP(피어 이름 확인 프로토콜) 피어 이름 확인자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-145">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="7cbe2-146">이 요소는 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-146">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|
|[<span data-ttu-id="7cbe2-147">\<reliableSession ></span><span class="sxs-lookup"><span data-stu-id="7cbe2-147">\<reliableSession></span></span>](reliablesession.md)|<span data-ttu-id="7cbe2-148">WS-Reliable Messaging 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-148">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="7cbe2-149">이 요소를 사용자 지정 바인딩에 추가 하면 결과 채널에서 정확히 한 번의 배달 보증을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-149">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="7cbe2-150">이 요소는 <xref:System.ServiceModel.Configuration.ReliableSessionElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-150">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|
|[<span data-ttu-id="7cbe2-151">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="7cbe2-151">\<security></span></span>](security-of-custombinding.md)|<span data-ttu-id="7cbe2-152">사용자 지정 바인딩에 대한 보안 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-152">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="7cbe2-153">이 요소는 <xref:System.ServiceModel.Configuration.SecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-153">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|
|[<span data-ttu-id="7cbe2-154">\<sslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="7cbe2-154">\<sslStreamSecurity></span></span>](sslstreamsecurity.md)|<span data-ttu-id="7cbe2-155">SSL 스트림 바인딩에 대한 보안 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-155">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="7cbe2-156">이 요소는 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-156">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|
|[<span data-ttu-id="7cbe2-157">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="7cbe2-157">\<transactionFlow></span></span>](transactionflow.md)|<span data-ttu-id="7cbe2-158">바인딩이 트랜잭션 흐름 및 `transactionProtocol` 특성에 사용될 프로토콜을 지원하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-158">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="7cbe2-159">이 요소는 <xref:System.ServiceModel.Configuration.TransactionFlowElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-159">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|
|[<span data-ttu-id="7cbe2-160">\<windowsStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="7cbe2-160">\<windowsStreamSecurity></span></span>](windowsstreamsecurity.md)|<span data-ttu-id="7cbe2-161">사용자 지정 바인딩에 대한 스트리밍 보안 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-161">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="7cbe2-162">이 요소는 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-162">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7cbe2-163">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7cbe2-163">Parent Elements</span></span>

|<span data-ttu-id="7cbe2-164">요소</span><span class="sxs-lookup"><span data-stu-id="7cbe2-164">Element</span></span>|<span data-ttu-id="7cbe2-165">설명</span><span class="sxs-lookup"><span data-stu-id="7cbe2-165">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="7cbe2-166">바인딩</span><span class="sxs-lookup"><span data-stu-id="7cbe2-166">bindings</span></span>|<span data-ttu-id="7cbe2-167">Windows Communication Foundation 애플리케이션에 대한 모든 바인딩을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-167">Contains all bindings for Windows Communication Foundation applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7cbe2-168">주의</span><span class="sxs-lookup"><span data-stu-id="7cbe2-168">Remarks</span></span>

<span data-ttu-id="7cbe2-169">사용자 지정 바인딩은 WCF 메시징 스택에 대한 모든 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-169">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="7cbe2-170">특정 엔터티의 구성 요소를 추가하여 특수하게 조정된 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-170">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="7cbe2-171">예를 들어, 사용자는 `httpsTransport` 섹션, `reliableSession` 섹션 및 `security` 섹션을 결합하여 믿을 수 있으며 안전한 https 기반 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-171">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>

<span data-ttu-id="7cbe2-172">개별 바인딩은 스택에 표시 되는 순서 대로 스택 요소에 대 한 구성 요소를 지정 하 여 메시지 스택을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-172">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="7cbe2-173">각 요소는 스택의 한 요소를 정의 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-173">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="7cbe2-174">각 사용자 지정 바인딩에는 하나의 전송 요소만 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-174">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="7cbe2-175">이 요소가 없으면 메시징 스택이 완전 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-175">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="7cbe2-176">스택에서 요소가 표시 되는 순서는 작업이 메시지에 적용 되는 순서 이기 때문에 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-176">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="7cbe2-177">권장 되는 스택 요소 순서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-177">The recommended order of stack elements is the following:</span></span>

1. <span data-ttu-id="7cbe2-178">트랜잭션 (옵션)</span><span class="sxs-lookup"><span data-stu-id="7cbe2-178">Transactions (optional)</span></span>

2. <span data-ttu-id="7cbe2-179">안정적인 메시징 (옵션)</span><span class="sxs-lookup"><span data-stu-id="7cbe2-179">Reliable Messaging (optional)</span></span>

3. <span data-ttu-id="7cbe2-180">보안 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="7cbe2-180">Security (optional)</span></span>

4. <span data-ttu-id="7cbe2-181">전송</span><span class="sxs-lookup"><span data-stu-id="7cbe2-181">Transport</span></span>

5. <span data-ttu-id="7cbe2-182">인코더 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="7cbe2-182">Encoder (optional)</span></span>

<span data-ttu-id="7cbe2-183">시스템에서 제공 하는 바인딩 중 하나가 사용자의 서비스 요구 사항을 충족 하지 않는 경우 사용자 지정 바인딩을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-183">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="7cbe2-184">예를 들어 서비스 끝점에서 새 전송 또는 새 인코더를 사용할 수 있도록 사용자 지정 바인딩을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-184">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>

<span data-ttu-id="7cbe2-185">사용자 지정 바인딩은 특정 순서로 "누적" 되는 바인딩 요소 컬렉션의 <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> 중 하나를 사용 하 여 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-185">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="7cbe2-186">위쪽은 트랜잭션 이동을 허용 하는 선택적 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-186">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>

- <span data-ttu-id="7cbe2-187">다음은 WS-RELIABLEMESSAGING 사양에 정의 된 대로 세션 및 순서 지정 메커니즘을 제공 하는 선택적 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-187">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="7cbe2-188">이 세션의 개념은 SOAP 및 전송 중개자를 통과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-188">This notion of a session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="7cbe2-189">다음은 권한 부여, 인증, 보호 및 기밀성과 같은 보안 기능을 제공 하는 선택적 보안 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-189">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="7cbe2-190">WCF (Windows Communication Foundation)에서 제공 하는 보안 바인딩 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-190">The following security binding elements are provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.SecurityBindingElement>

  - <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>

- <span data-ttu-id="7cbe2-191">다음은 바인딩 요소에 지정 된 선택적 메시지 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-191">Next are the optional message-patterns specified by binding elements:</span></span>

- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>

- <span data-ttu-id="7cbe2-192">다음은 선택적 전송 업그레이드/도우미 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-192">Next are the optional transport upgrades/helpers binding elements:</span></span>

  - <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="7cbe2-193">다음은 필수 메시지 인코딩 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-193">Next is a required message encoding binding element.</span></span> <span data-ttu-id="7cbe2-194">사용자 고유의 전송을 사용 하거나 다음 메시지 인코딩 바인딩 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-194">You can use your own transport or use one of the following message encoding bindings:</span></span>

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

- <span data-ttu-id="7cbe2-195">맨 아래에는 필수 전송 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-195">At the bottom is a required transport element.</span></span> <span data-ttu-id="7cbe2-196">사용자 고유의 전송을 사용 하거나 WCF (Windows Communication Foundation)에서 제공 하는 전송 바인딩 요소 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-196">You can use your own transport or use one of transport binding elements provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

  - <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

  - <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

  - <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

<span data-ttu-id="7cbe2-197">다음 표에서는 각 계층에 대 한 옵션을 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-197">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="7cbe2-198">레이어도</span><span class="sxs-lookup"><span data-stu-id="7cbe2-198">Layer</span></span>|<span data-ttu-id="7cbe2-199">옵션</span><span class="sxs-lookup"><span data-stu-id="7cbe2-199">Options</span></span>|<span data-ttu-id="7cbe2-200">필요한 공간</span><span class="sxs-lookup"><span data-stu-id="7cbe2-200">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="7cbe2-201">트랜잭션 흐름</span><span class="sxs-lookup"><span data-stu-id="7cbe2-201">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="7cbe2-202">아니요</span><span class="sxs-lookup"><span data-stu-id="7cbe2-202">No</span></span>|
|<span data-ttu-id="7cbe2-203">안정성</span><span class="sxs-lookup"><span data-stu-id="7cbe2-203">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="7cbe2-204">아니요</span><span class="sxs-lookup"><span data-stu-id="7cbe2-204">No</span></span>|
|<span data-ttu-id="7cbe2-205">보안</span><span class="sxs-lookup"><span data-stu-id="7cbe2-205">Security</span></span>|<span data-ttu-id="7cbe2-206">대칭, 비대칭, 전송 수준</span><span class="sxs-lookup"><span data-stu-id="7cbe2-206">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="7cbe2-207">아니요</span><span class="sxs-lookup"><span data-stu-id="7cbe2-207">No</span></span>|
|<span data-ttu-id="7cbe2-208">모양 변경</span><span class="sxs-lookup"><span data-stu-id="7cbe2-208">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="7cbe2-209">아니요</span><span class="sxs-lookup"><span data-stu-id="7cbe2-209">No</span></span>|
|<span data-ttu-id="7cbe2-210">전송 업그레이드</span><span class="sxs-lookup"><span data-stu-id="7cbe2-210">Transport Upgrades</span></span>|<span data-ttu-id="7cbe2-211">SSL 스트림, Windows 스트림, 피어 확인자</span><span class="sxs-lookup"><span data-stu-id="7cbe2-211">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="7cbe2-212">아니요</span><span class="sxs-lookup"><span data-stu-id="7cbe2-212">No</span></span>|
|<span data-ttu-id="7cbe2-213">인코딩</span><span class="sxs-lookup"><span data-stu-id="7cbe2-213">Encoding</span></span>|<span data-ttu-id="7cbe2-214">텍스트, 이진, MTOM, 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="7cbe2-214">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="7cbe2-215">예</span><span class="sxs-lookup"><span data-stu-id="7cbe2-215">Yes</span></span>|
|<span data-ttu-id="7cbe2-216">전송</span><span class="sxs-lookup"><span data-stu-id="7cbe2-216">Transport</span></span>|<span data-ttu-id="7cbe2-217">TCP, 명명 된 파이프, HTTP, HTTPS, MSMQ의 특성, 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="7cbe2-217">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="7cbe2-218">예</span><span class="sxs-lookup"><span data-stu-id="7cbe2-218">Yes</span></span>|

<span data-ttu-id="7cbe2-219">또한 사용자 고유의 바인딩 요소를 정의 하 고 앞에서 정의한 계층 사이에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-219">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

<span data-ttu-id="7cbe2-220">사용자 지정 바인딩을 사용 하 여 시스템 제공 바인딩을 수정 하는 방법에 대 한 설명은 [방법: 시스템 제공 바인딩 사용자 지정](../../../wcf/extending/how-to-customize-a-system-provided-binding.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cbe2-220">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7cbe2-221">참조</span><span class="sxs-lookup"><span data-stu-id="7cbe2-221">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="7cbe2-222">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="7cbe2-222">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="7cbe2-223">바인딩</span><span class="sxs-lookup"><span data-stu-id="7cbe2-223">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7cbe2-224">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="7cbe2-224">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="7cbe2-225">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="7cbe2-225">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="7cbe2-226">customBinding 요소</span><span class="sxs-lookup"><span data-stu-id="7cbe2-226">customBinding Element</span></span>](custombinding.md)
- [<span data-ttu-id="7cbe2-227">바인딩</span><span class="sxs-lookup"><span data-stu-id="7cbe2-227">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7cbe2-228">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="7cbe2-228">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7cbe2-229">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="7cbe2-229">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
