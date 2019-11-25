---
title: <wsFederationHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
ms.openlocfilehash: 0a77c791d55c6009cf59d5a4b15f3b2a63b7ccf9
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140466"
---
# <a name="wsfederationhttpbinding"></a><span data-ttu-id="bbc96-101">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="bbc96-101">\<wsFederationHttpBinding></span></span>

<span data-ttu-id="bbc96-102">WS-Federation을 지원하는 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-102">Defines a binding that supports WS-Federation.</span></span>

<span data-ttu-id="bbc96-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bbc96-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bbc96-104">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="bbc96-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bbc96-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="bbc96-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="bbc96-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<wsFederationHttpBinding >**</span><span class="sxs-lookup"><span data-stu-id="bbc96-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsFederationHttpBinding>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="bbc96-107">구문</span><span class="sxs-lookup"><span data-stu-id="bbc96-107">Syntax</span></span>

```xml
<wsFederationHttpBinding>
  <binding bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           privacyNoticeAt="Uri"
           privacyNoticeVersion="Integer"
           proxyAddress="Uri"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/ Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <security mode="None/Message/TransportWithMessageCredential">
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri" >
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuer>
        <issuerMetadata address="String">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuerMetadata>
        <tokenRequestParameters>
          <xmlElement>
          </xmlElement>
        </tokenRequestParameters>
      </message>
    </security>
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsFederationBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bbc96-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bbc96-108">Attributes and Elements</span></span>

<span data-ttu-id="bbc96-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="bbc96-110">특성</span><span class="sxs-lookup"><span data-stu-id="bbc96-110">Attributes</span></span>

|<span data-ttu-id="bbc96-111">특성</span><span class="sxs-lookup"><span data-stu-id="bbc96-111">Attribute</span></span>|<span data-ttu-id="bbc96-112">설명</span><span class="sxs-lookup"><span data-stu-id="bbc96-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="bbc96-113">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="bbc96-113">bypassProxyOnLocal</span></span>|<span data-ttu-id="bbc96-114">로컬 주소에 대해 프록시 서버를 사용 하지 않을 것인지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-114">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="bbc96-115">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-115">The default is `false`.</span></span>|
|<span data-ttu-id="bbc96-116">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="bbc96-116">closeTimeout</span></span>|<span data-ttu-id="bbc96-117">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-117">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="bbc96-118">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-118">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="bbc96-119">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-119">The default is 00:01:00.</span></span>|
|<span data-ttu-id="bbc96-120">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="bbc96-120">hostnameComparisonMode</span></span>|<span data-ttu-id="bbc96-121">URI 구문 분석에 사용되는 HTTP 호스트 이름 비교 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-121">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="bbc96-122">이 특성은 <xref:System.ServiceModel.HostNameComparisonMode> 형식이며 URI에 대해 비교할 때 호스트 이름이 서비스에 연결하는 데 사용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-122">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="bbc96-123">기본값은 <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>이며 이 값은 비교 시 호스트 이름을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-123">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|<span data-ttu-id="bbc96-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="bbc96-124">maxBufferPoolSize</span></span>|<span data-ttu-id="bbc96-125">이 바인딩의 최대 버퍼 풀 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-125">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="bbc96-126">기본값은 524288 바이트 (512 \* 1024)입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-126">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="bbc96-127">WCF (Windows Communication Foundation)의 많은 부분에서 버퍼를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-127">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="bbc96-128">사용 될 때마다 버퍼를 만들고 삭제 하는 것은 비용이 많이 들고 버퍼에 대 한 가비지 수집도 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-128">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="bbc96-129">버퍼 풀을 사용 하면 풀에서 버퍼를 가져와서 사용 하 고 완료 되 면 풀로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-129">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="bbc96-130">따라서 버퍼를 만들고 삭제 하는 오버 헤드는 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-130">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|<span data-ttu-id="bbc96-131">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="bbc96-131">maxReceivedMessageSize</span></span>|<span data-ttu-id="bbc96-132">헤더를 비롯하여 이 바인딩으로 구성된 채널에서 받을 수 있는 최대 메시지 크기(바이트)를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-132">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="bbc96-133">이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-133">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="bbc96-134">수신자는 메시지를 삭제 하 고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-134">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="bbc96-135">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-135">The default is 65536.</span></span>|
|<span data-ttu-id="bbc96-136">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="bbc96-136">messageEncoding</span></span>|<span data-ttu-id="bbc96-137">메시지를 인코딩하는 데 사용되는 인코더를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-137">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="bbc96-138">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="bbc96-139">-Text: 텍스트 메시지 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-139">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="bbc96-140">-Mtom: 메시지 전송 조직 메커니즘 1.0 (MTOM) 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-140">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="bbc96-141">기본값은 Text입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-141">The default is Text.</span></span><br /><br /> <span data-ttu-id="bbc96-142">이 특성은 <xref:System.ServiceModel.WSMessageEncoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-142">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|<span data-ttu-id="bbc96-143">name</span><span class="sxs-lookup"><span data-stu-id="bbc96-143">name</span></span>|<span data-ttu-id="bbc96-144">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-144">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="bbc96-145">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-145">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="bbc96-146">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-146">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="bbc96-147">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bbc96-147">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="bbc96-148">openTimeout</span><span class="sxs-lookup"><span data-stu-id="bbc96-148">openTimeout</span></span>|<span data-ttu-id="bbc96-149">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="bbc96-150">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="bbc96-151">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-151">The default is 00:01:00.</span></span>|
|<span data-ttu-id="bbc96-152">privacyNoticeAt</span><span class="sxs-lookup"><span data-stu-id="bbc96-152">privacyNoticeAt</span></span>|<span data-ttu-id="bbc96-153">개인 정보 알림이 있는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-153">A String that specifies a URI at which the privacy notice is located.</span></span>|
|<span data-ttu-id="bbc96-154">privacyNoticeVersion</span><span class="sxs-lookup"><span data-stu-id="bbc96-154">privacyNoticeVersion</span></span>|<span data-ttu-id="bbc96-155">현재 개인 정보 알림의 버전을 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-155">An integer that specifies the version of the current privacy notice.</span></span>|
|<span data-ttu-id="bbc96-156">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="bbc96-156">proxyAddress</span></span>|<span data-ttu-id="bbc96-157">HTTP 프록시의 주소를 지정 하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-157">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="bbc96-158">`useDefaultWebProxy`가 `true`일 경우 이 설정은 `null`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-158">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="bbc96-159">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-159">The default is `null`.</span></span>|
|<span data-ttu-id="bbc96-160">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="bbc96-160">receiveTimeout</span></span>|<span data-ttu-id="bbc96-161">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-161">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="bbc96-162">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-162">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="bbc96-163">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-163">The default is 00:10:00.</span></span>|
|<span data-ttu-id="bbc96-164">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="bbc96-164">sendTimeout</span></span>|<span data-ttu-id="bbc96-165">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-165">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="bbc96-166">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-166">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="bbc96-167">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-167">The default is 00:01:00.</span></span>|
|<span data-ttu-id="bbc96-168">textEncoding</span><span class="sxs-lookup"><span data-stu-id="bbc96-168">textEncoding</span></span>|<span data-ttu-id="bbc96-169">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-169">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="bbc96-170">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-170">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="bbc96-171">-BigEndianUnicode: Unicode가 나 Endian 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-171">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="bbc96-172">-Unicode: 16 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-172">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="bbc96-173">-UTF8:8 비트 인코딩</span><span class="sxs-lookup"><span data-stu-id="bbc96-173">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="bbc96-174">기본값은 UTF8입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-174">The default is UTF8.</span></span> <span data-ttu-id="bbc96-175">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-175">This attribute is of type <xref:System.Text.Encoding>..</span></span>|
|<span data-ttu-id="bbc96-176">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="bbc96-176">transactionFlow</span></span>|<span data-ttu-id="bbc96-177">바인딩에서 WS-Transactions 이동을 지원할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-177">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="bbc96-178">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-178">The default is `false`.</span></span>|
|<span data-ttu-id="bbc96-179">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="bbc96-179">useDefaultWebProxy</span></span>|<span data-ttu-id="bbc96-180">시스템의 자동 구성된 HTTP 프록시 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-180">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="bbc96-181">이 특성이 `null`이면 프록시 주소는 `true`이어야 합니다(설정되지 않음).</span><span class="sxs-lookup"><span data-stu-id="bbc96-181">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="bbc96-182">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-182">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="bbc96-183">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bbc96-183">Child Elements</span></span>

|<span data-ttu-id="bbc96-184">요소</span><span class="sxs-lookup"><span data-stu-id="bbc96-184">Element</span></span>|<span data-ttu-id="bbc96-185">설명</span><span class="sxs-lookup"><span data-stu-id="bbc96-185">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bbc96-186">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="bbc96-186">\<security></span></span>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="bbc96-187">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-187">Defines the security settings for the message.</span></span> <span data-ttu-id="bbc96-188">이 요소는 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-188">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|<span data-ttu-id="bbc96-189">[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bbc96-189">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="bbc96-190">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-190">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="bbc96-191">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-191">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|<span data-ttu-id="bbc96-192">[\<reliableSession >](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="bbc96-192">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="bbc96-193">채널 엔드포인트 간에 신뢰할 수 있는 세션이 설정되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-193">Specifies if reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bbc96-194">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bbc96-194">Parent Elements</span></span>

|<span data-ttu-id="bbc96-195">요소</span><span class="sxs-lookup"><span data-stu-id="bbc96-195">Element</span></span>|<span data-ttu-id="bbc96-196">설명</span><span class="sxs-lookup"><span data-stu-id="bbc96-196">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bbc96-197">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="bbc96-197">\<bindings></span></span>](bindings.md)|<span data-ttu-id="bbc96-198">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-198">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bbc96-199">주의</span><span class="sxs-lookup"><span data-stu-id="bbc96-199">Remarks</span></span>

<span data-ttu-id="bbc96-200">페더레이션은 인증 및 권한 부여를 위해 여러 시스템에서 id를 공유 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-200">Federation is the ability to share identities across multiple systems for authentication and authorization.</span></span> <span data-ttu-id="bbc96-201">이러한 id는 사용자 또는 컴퓨터를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-201">These identities can refer to users or to machines.</span></span> <span data-ttu-id="bbc96-202">페더레이션된 HTTP는 SOAP 보안과 혼합 모드 보안을 지원 하지만 전송 보안을 사용 하 여 독점적으로 지원 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-202">Federated HTTP supports SOAP security as well as mixed-mode security, but it does not support exclusively using transport security.</span></span> <span data-ttu-id="bbc96-203">이 바인딩은 WS-FEDERATION 프로토콜에 대 한 WCF (Windows Communication Foundation) 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-203">This binding provides Windows Communication Foundation (WCF) support for the WS-Federation protocol.</span></span> <span data-ttu-id="bbc96-204">이 바인딩으로 구성 된 서비스는 HTTP 전송을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-204">Services configured with this binding must use the HTTP transport.</span></span>

<span data-ttu-id="bbc96-205">바인딩은 바인딩 요소의 스택으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-205">Bindings consist of a stack of binding elements.</span></span> <span data-ttu-id="bbc96-206">가 기본값인 로 설정된 경우</span><span class="sxs-lookup"><span data-stu-id="bbc96-206">The stack of binding elements in</span></span>

<span data-ttu-id="bbc96-207">`wsFederationHttpBinding`에 있는 바인딩 요소의 스택은`wsHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="bbc96-207">`wsFederationHttpBinding` is the same as that contained in `wsHttpBinding`</span></span>

<span data-ttu-id="bbc96-208">[\<보안 >](security-of-wsfederationhttpbinding.md) <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>기본값인로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-208">when [\<security>](security-of-wsfederationhttpbinding.md) is set to the default value of <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span></span>

<span data-ttu-id="bbc96-209">`wsFederationHttpBinding` [\<메시지 >](message-element-of-wsfederationhttpbinding.md)에서 메시지 보안 설정의 세부 정보를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-209">The `wsFederationHttpBinding` controls the details of the message security settings in [\<message>](message-element-of-wsfederationhttpbinding.md).</span></span> <span data-ttu-id="bbc96-210">[\<security >](security-of-wsfederationhttpbinding.md) 요소는 바인딩이 생성 된 후 바인딩에서 사용 하는 보안을 변경할 수 없기 때문에 get 액세스만 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-210">Note that the [\<security>](security-of-wsfederationhttpbinding.md) element provides get access only as the security used by the binding cannot be changed once the binding is created.</span></span>

<span data-ttu-id="bbc96-211">또한 `wsFederationHttpBinding`은 개인 정보 알림이 있는 URI를 설정 하 고 검색 하는 privacyNoticeAt 특성도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-211">The `wsFederationHttpBinding` also provides a privacyNoticeAt attribute to set and retrieve the URI at which the privacy notice is located.</span></span>

<span data-ttu-id="bbc96-212">정책 보안을 유지하는 것은 페더레이션 시나리오에서 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-212">Keeping policy secure is especially important in federation scenarios.</span></span> <span data-ttu-id="bbc96-213">HTTPS와 같은 특정 형식의 보안을 사용하여 악의적인 사용자로부터 정책을 보호할 것을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-213">The recommendation is to use some form of security, such as HTTPS, to protect the policy from malicious users.</span></span>

<span data-ttu-id="bbc96-214">이러한 바인딩을 사용하는 페더레이션 시나리오에서 서비스 정책은 발급된(SAML) 토큰을 암호화하기 위한 키, 토큰에 추가할 클레임 형식 등의 중요한 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-214">In federation scenarios using this binding, the service policy potentially has important information such as the key to use to encrypt the issued (SAML) token, the type of claims to put in the token, and so forth.</span></span> <span data-ttu-id="bbc96-215">이 정책이 훼손되면 공격자는 발급된 토큰의 키를 확인할 수 있게 되므로 추가적인 정보 변조, 정보 노출 및 기타 악의적인 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-215">If this policy is tampered with, an attacker could discover the key of the issued token leading to further tampering, info disclosure and other malicious behavior.</span></span> <span data-ttu-id="bbc96-216">이를 방지하려면 정책을 서비스에서 안전하게(예: HTTPS 사용) 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc96-216">To help prevent this, the policy must be obtained securely (for example using HTTPS) from the service.</span></span>

<span data-ttu-id="bbc96-217">이 바인딩에 대 한 자세한 내용은 [방법: WSFederationHttpBinding 만들기](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bbc96-217">For more information on this binding, see [How to: Create a WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="bbc96-218">예제</span><span class="sxs-lookup"><span data-stu-id="bbc96-218">Example</span></span>

```xml
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsFederationHttpBinding>
        <binding bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="Utf16TextEncoding"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="None">
            <message negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     issuedTokenType="saml"
                     issuedKeyType="PublicKey">
              <issuer address="http://localhost/Sts" />
            </message>
          </security>
        </binding>
      </wsFederationBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="bbc96-219">참조</span><span class="sxs-lookup"><span data-stu-id="bbc96-219">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>
- [<span data-ttu-id="bbc96-220">방법: WSFederationHttpBinding 만들기</span><span class="sxs-lookup"><span data-stu-id="bbc96-220">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="bbc96-221">바인딩</span><span class="sxs-lookup"><span data-stu-id="bbc96-221">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="bbc96-222">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="bbc96-222">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="bbc96-223">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="bbc96-223">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="bbc96-224">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="bbc96-224">\<binding></span></span>](bindings.md)
