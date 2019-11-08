---
title: <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
ms.openlocfilehash: 0a5090166efd90efa7537f87d5fa47b8c9d078cb
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735763"
---
# <a name="ws2007federationhttpbinding"></a><span data-ttu-id="fe0dd-101">\<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="fe0dd-101">\<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="fe0dd-102">[\<wsFederationHttpBinding >](wsfederationhttpbinding.md) 에서 파생 되 고 페더레이션된 보안을 지 원하는 안전 하 고 상호 운용 가능한 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-102">A secure and interoperable binding that derives from [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) and supports federated security.</span></span>

<span data-ttu-id="fe0dd-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fe0dd-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fe0dd-104">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="fe0dd-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fe0dd-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="fe0dd-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="fe0dd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ws2007FederationHttpBinding >**</span><span class="sxs-lookup"><span data-stu-id="fe0dd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ws2007FederationHttpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe0dd-107">구문</span><span class="sxs-lookup"><span data-stu-id="fe0dd-107">Syntax</span></span>

```xml
<ws2007FederationHttpBinding>
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
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
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
</ws2007FederationHttpBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fe0dd-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fe0dd-108">Attributes and Elements</span></span>

<span data-ttu-id="fe0dd-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="fe0dd-110">특성</span><span class="sxs-lookup"><span data-stu-id="fe0dd-110">Attributes</span></span>

|<span data-ttu-id="fe0dd-111">특성</span><span class="sxs-lookup"><span data-stu-id="fe0dd-111">Attribute</span></span>|<span data-ttu-id="fe0dd-112">설명</span><span class="sxs-lookup"><span data-stu-id="fe0dd-112">Description</span></span>|
|---------------|-----------------|
|`bypassProxyOnLocal`|<span data-ttu-id="fe0dd-113">로컬 주소에 대해 프록시 서버를 우회할지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-113">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="fe0dd-114">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-114">The default is `false`.</span></span>|
|`closeTimeout`|<span data-ttu-id="fe0dd-115">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="fe0dd-116">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="fe0dd-117">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-117">The default is 00:01:00.</span></span>|
|`hostNameComparisonMode`|<span data-ttu-id="fe0dd-118">URI 구문 분석에 사용되는 HTTP 호스트 이름 비교 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-118">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="fe0dd-119">이 특성은 <xref:System.ServiceModel.HostNameComparisonMode> 형식이며 URI에 대해 비교할 때 호스트 이름이 서비스에 연결하는 데 사용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-119">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="fe0dd-120">기본값은 <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>이며 이 값은 비교 시 호스트 이름을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-120">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|`maxBufferPoolSize`|<span data-ttu-id="fe0dd-121">이 바인딩에 대한 최대 버퍼 풀 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-121">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="fe0dd-122">기본값은 524288 바이트 (512 \* 1024)입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-122">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="fe0dd-123">WCF (Windows Communication Foundation)의 많은 부분에서 버퍼를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-123">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="fe0dd-124">사용 될 때마다 버퍼를 만들고 삭제 하는 것은 비용이 많이 들고 버퍼에 대 한 가비지 수집도 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-124">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="fe0dd-125">버퍼 풀을 사용 하면 풀에서 버퍼를 가져와서 사용 하 고 완료 되 면 풀로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-125">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="fe0dd-126">따라서 버퍼를 만들고 삭제 하는 오버 헤드는 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-126">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|`maxReceivedMessageSize`|<span data-ttu-id="fe0dd-127">이 바인딩으로 구성된 채널에서 받을 수 있는 헤더를 비롯한 최대 메시지 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-127">The maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="fe0dd-128">이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-128">The sender of a message that exceeds this limit receives a SOAP fault.</span></span> <span data-ttu-id="fe0dd-129">수신자는 메시지를 삭제 하 고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-129">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="fe0dd-130">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-130">The default is 65536.</span></span>|
|`messageEncoding`|<span data-ttu-id="fe0dd-131">메시지를 인코딩하는 데 사용되는 인코더를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-131">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="fe0dd-132">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-132">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="fe0dd-133">-Text: 텍스트 메시지 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-133">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="fe0dd-134">-Mtom: 메시지 전송 조직 메커니즘 1.0 (MTOM) 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-134">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="fe0dd-135">기본값은 Text입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-135">The default is Text.</span></span><br /><br /> <span data-ttu-id="fe0dd-136">이 특성은 <xref:System.ServiceModel.WSMessageEncoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-136">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|`name`|<span data-ttu-id="fe0dd-137">바인딩의 구성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-137">The configuration name of the binding.</span></span> <span data-ttu-id="fe0dd-138">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-138">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="fe0dd-139">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-139">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="fe0dd-140">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-140">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|`openTimeout`|<span data-ttu-id="fe0dd-141">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-141">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="fe0dd-142">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-142">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="fe0dd-143">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-143">The default is 00:01:00.</span></span>|
|`privacyNoticeAt`|<span data-ttu-id="fe0dd-144">개인 정보 알림이 있는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-144">A URI at which the privacy notice is located.</span></span>|
|`privacyNoticeVersion`|<span data-ttu-id="fe0dd-145">현재 개인 정보 알림의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-145">The version of the current privacy notice.</span></span>|
|`proxyAddress`|<span data-ttu-id="fe0dd-146">HTTP 프록시의 주소를 지정 하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-146">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="fe0dd-147">`useDefaultWebProxy`가 `true`일 경우 이 설정은 `null`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-147">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="fe0dd-148">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-148">The default is `null`.</span></span>|
|`receiveTimeout`|<span data-ttu-id="fe0dd-149">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="fe0dd-150">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="fe0dd-151">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-151">The default is 00:10:00.</span></span>|
|`sendTimeout`|<span data-ttu-id="fe0dd-152">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-152">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="fe0dd-153">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-153">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="fe0dd-154">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-154">The default is 00:01:00.</span></span>|
|`textEncoding`|<span data-ttu-id="fe0dd-155">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-155">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="fe0dd-156">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-156">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="fe0dd-157">-BigEndianUnicode: 유니코드 빅 Endian 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-157">-   BigEndianUnicode: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="fe0dd-158">-Unicode: 16 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-158">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="fe0dd-159">-UTF8:8 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-159">-   UTF8: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="fe0dd-160">기본값은 UTF8입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-160">The default is UTF8.</span></span> <span data-ttu-id="fe0dd-161">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-161">This attribute is of type <xref:System.Text.Encoding>.</span></span>|
|`transactionFlow`|<span data-ttu-id="fe0dd-162">바인딩에서 WS-트랜잭션 이동을 지원할지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-162">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="fe0dd-163">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-163">The default is `false`.</span></span>|
|`useDefaultWebProxy`|<span data-ttu-id="fe0dd-164">시스템의 자동 구성된 HTTP 프록시 사용 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-164">A value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="fe0dd-165">이 특성이 `null`이면 프록시 주소는 `true`이어야 합니다(설정되지 않음).</span><span class="sxs-lookup"><span data-stu-id="fe0dd-165">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="fe0dd-166">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-166">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="fe0dd-167">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fe0dd-167">Child Elements</span></span>

|<span data-ttu-id="fe0dd-168">요소</span><span class="sxs-lookup"><span data-stu-id="fe0dd-168">Element</span></span>|<span data-ttu-id="fe0dd-169">설명</span><span class="sxs-lookup"><span data-stu-id="fe0dd-169">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fe0dd-170">\<security ></span><span class="sxs-lookup"><span data-stu-id="fe0dd-170">\<security></span></span>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="fe0dd-171">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-171">Defines the security settings for the message.</span></span> <span data-ttu-id="fe0dd-172">이 요소는 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-172">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|<span data-ttu-id="fe0dd-173">[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fe0dd-173">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="fe0dd-174">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-174">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="fe0dd-175">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-175">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|<span data-ttu-id="fe0dd-176">[\<reliableSession >](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="fe0dd-176">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="fe0dd-177">채널 엔드포인트 간에 신뢰할 수 있는 세션이 설정되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-177">Specifies whether reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="fe0dd-178">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fe0dd-178">Parent Elements</span></span>

|<span data-ttu-id="fe0dd-179">요소</span><span class="sxs-lookup"><span data-stu-id="fe0dd-179">Element</span></span>|<span data-ttu-id="fe0dd-180">설명</span><span class="sxs-lookup"><span data-stu-id="fe0dd-180">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fe0dd-181">\<bindings ></span><span class="sxs-lookup"><span data-stu-id="fe0dd-181">\<bindings></span></span>](bindings.md)|<span data-ttu-id="fe0dd-182">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-182">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fe0dd-183">주의</span><span class="sxs-lookup"><span data-stu-id="fe0dd-183">Remarks</span></span>

<span data-ttu-id="fe0dd-184">페더레이션은 인증 및 권한 부여를 위해 여러 기업이 나 트러스트 도메인에서 id를 공유 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-184">Federation is the ability to share identities across multiple enterprises or trust domains for authentication and authorization.</span></span> <span data-ttu-id="fe0dd-185">WS-TRUST 프로토콜을 사용 하 여 트러스트 도메인 간에 id 표시를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-185">It uses the WS-Trust protocol to map the identity representation from one trust domain to another.</span></span> <span data-ttu-id="fe0dd-186">페더레이션된 HTTP 바인딩은 SOAP 보안과 혼합 모드 보안을 지원 하지만 전송 보안을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-186">Federated HTTP binding supports SOAP security as well as mixed-mode security, but it does not support transport security.</span></span> <span data-ttu-id="fe0dd-187">이 바인딩으로 구성 된 서비스는 HTTP 전송을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-187">Services configured with this binding must use the HTTP transport.</span></span> <span data-ttu-id="fe0dd-188">자세한 내용은 [\<wsFederationHttpBinding >](wsfederationhttpbinding.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe0dd-188">For more information, see [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="fe0dd-189">예제</span><span class="sxs-lookup"><span data-stu-id="fe0dd-189">Example</span></span>

```xml
<configuration>
  <system.ServiceModel>
    <bindings>
      <ws2007FederationHttpBinding>
        <binding bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://www.contoso.com"
                 textEncoding="Utf16TextEncoding"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="None">
            <message negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"
                     issuedKeyType="PublicKey">
              <issuer address="http://localhost/Sts" />
            </message>
          </security>
        </binding>
      </ws2007FederationBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="fe0dd-190">참조</span><span class="sxs-lookup"><span data-stu-id="fe0dd-190">See also</span></span>

- <xref:System.ServiceModel.WS2007FederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>
- [<span data-ttu-id="fe0dd-191">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="fe0dd-191">\<wsFederationHttpBinding></span></span>](wsfederationhttpbinding.md)
- [<span data-ttu-id="fe0dd-192">바인딩</span><span class="sxs-lookup"><span data-stu-id="fe0dd-192">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="fe0dd-193">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="fe0dd-193">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="fe0dd-194">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="fe0dd-194">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="fe0dd-195">\<binding ></span><span class="sxs-lookup"><span data-stu-id="fe0dd-195">\<binding></span></span>](bindings.md)
