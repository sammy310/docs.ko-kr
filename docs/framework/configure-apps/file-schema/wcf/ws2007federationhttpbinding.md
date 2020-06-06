---
title: <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
ms.openlocfilehash: 20ba643fddbac8a488e5457f0195cc253d4d23f7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139319"
---
# \<ws2007FederationHttpBinding>

<span data-ttu-id="60e56-101">에서 파생 되 [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) 고 페더레이션된 보안을 지 원하는 안전 하 고 상호 운용 가능한 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-101">A secure and interoperable binding that derives from [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) and supports federated security.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ws2007FederationHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="60e56-102">구문</span><span class="sxs-lookup"><span data-stu-id="60e56-102">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="60e56-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="60e56-103">Attributes and Elements</span></span>

<span data-ttu-id="60e56-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="60e56-105">특성</span><span class="sxs-lookup"><span data-stu-id="60e56-105">Attributes</span></span>

|<span data-ttu-id="60e56-106">attribute</span><span class="sxs-lookup"><span data-stu-id="60e56-106">Attribute</span></span>|<span data-ttu-id="60e56-107">Description</span><span class="sxs-lookup"><span data-stu-id="60e56-107">Description</span></span>|
|---------------|-----------------|
|`bypassProxyOnLocal`|<span data-ttu-id="60e56-108">로컬 주소에 대해 프록시 서버를 우회할지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-108">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="60e56-109">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-109">The default is `false`.</span></span>|
|`closeTimeout`|<span data-ttu-id="60e56-110">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-110">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="60e56-111">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-111">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="60e56-112">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-112">The default is 00:01:00.</span></span>|
|`hostNameComparisonMode`|<span data-ttu-id="60e56-113">URI 구문 분석에 사용되는 HTTP 호스트 이름 비교 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-113">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="60e56-114">이 특성은 <xref:System.ServiceModel.HostNameComparisonMode> 형식이며 URI에 대해 비교할 때 호스트 이름이 서비스에 연결하는 데 사용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-114">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="60e56-115">기본값은 <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>이며 이 값은 비교 시 호스트 이름을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-115">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|`maxBufferPoolSize`|<span data-ttu-id="60e56-116">이 바인딩에 대한 최대 버퍼 풀 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-116">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="60e56-117">기본값은 524,288바이트(512 \* 1024)입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-117">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="60e56-118">WCF(Windows Communication Foundation)의 많은 부분에서 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-118">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="60e56-119">버퍼를 사용할 때마다 만들고 삭제하면 비용이 많이 들며, 버퍼에 대한 가비지 수집 역시 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-119">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="60e56-120">버퍼 풀이 있으면 이 풀로부터 버퍼를 가져와 사용한 다음 다시 풀로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-120">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="60e56-121">따라서 버퍼를 만들고 제거하는 데 오버헤드를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-121">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|`maxReceivedMessageSize`|<span data-ttu-id="60e56-122">이 바인딩으로 구성된 채널에서 받을 수 있는 헤더를 비롯한 최대 메시지 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-122">The maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="60e56-123">이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-123">The sender of a message that exceeds this limit receives a SOAP fault.</span></span> <span data-ttu-id="60e56-124">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-124">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="60e56-125">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-125">The default is 65536.</span></span>|
|`messageEncoding`|<span data-ttu-id="60e56-126">메시지를 인코딩하는 데 사용되는 인코더를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-126">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="60e56-127">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-127">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="60e56-128">-Text: 텍스트 메시지 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-128">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="60e56-129">-Mtom: 메시지 전송 조직 메커니즘 1.0 (MTOM) 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-129">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="60e56-130">기본값은 Text입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-130">The default is Text.</span></span><br /><br /> <span data-ttu-id="60e56-131">이 특성은 <xref:System.ServiceModel.WSMessageEncoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-131">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|`name`|<span data-ttu-id="60e56-132">바인딩의 구성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-132">The configuration name of the binding.</span></span> <span data-ttu-id="60e56-133">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-133">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="60e56-134">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-134">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="60e56-135">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="60e56-135">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|`openTimeout`|<span data-ttu-id="60e56-136">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-136">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="60e56-137">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-137">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="60e56-138">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-138">The default is 00:01:00.</span></span>|
|`privacyNoticeAt`|<span data-ttu-id="60e56-139">개인 정보 알림이 있는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-139">A URI at which the privacy notice is located.</span></span>|
|`privacyNoticeVersion`|<span data-ttu-id="60e56-140">현재 개인 정보 알림의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-140">The version of the current privacy notice.</span></span>|
|`proxyAddress`|<span data-ttu-id="60e56-141">HTTP 프록시의 주소를 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-141">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="60e56-142">`useDefaultWebProxy`가 `true`일 경우 이 설정은 `null`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-142">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="60e56-143">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-143">The default is `null`.</span></span>|
|`receiveTimeout`|<span data-ttu-id="60e56-144">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-144">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="60e56-145">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-145">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="60e56-146">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-146">The default is 00:10:00.</span></span>|
|`sendTimeout`|<span data-ttu-id="60e56-147">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-147">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="60e56-148">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-148">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="60e56-149">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-149">The default is 00:01:00.</span></span>|
|`textEncoding`|<span data-ttu-id="60e56-150">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-150">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="60e56-151">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-151">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="60e56-152">-BigEndianUnicode: 유니코드 빅 Endian 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-152">-   BigEndianUnicode: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="60e56-153">-Unicode: 16 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-153">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="60e56-154">-UTF8:8 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-154">-   UTF8: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="60e56-155">기본값은 UTF8입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-155">The default is UTF8.</span></span> <span data-ttu-id="60e56-156">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-156">This attribute is of type <xref:System.Text.Encoding>.</span></span>|
|`transactionFlow`|<span data-ttu-id="60e56-157">바인딩에서 WS-트랜잭션 이동을 지원할지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-157">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="60e56-158">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-158">The default is `false`.</span></span>|
|`useDefaultWebProxy`|<span data-ttu-id="60e56-159">시스템의 자동 구성된 HTTP 프록시 사용 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-159">A value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="60e56-160">이 특성이 `null`이면 프록시 주소는 `true`이어야 합니다(설정되지 않음).</span><span class="sxs-lookup"><span data-stu-id="60e56-160">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="60e56-161">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-161">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="60e56-162">자식 요소</span><span class="sxs-lookup"><span data-stu-id="60e56-162">Child Elements</span></span>

|<span data-ttu-id="60e56-163">요소</span><span class="sxs-lookup"><span data-stu-id="60e56-163">Element</span></span>|<span data-ttu-id="60e56-164">Description</span><span class="sxs-lookup"><span data-stu-id="60e56-164">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="60e56-165">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-165">Defines the security settings for the message.</span></span> <span data-ttu-id="60e56-166">이 요소는 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-166">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="60e56-167">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-167">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="60e56-168">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-168">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="60e56-169">채널 엔드포인트 간에 신뢰할 수 있는 세션이 설정되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-169">Specifies whether reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="60e56-170">부모 요소</span><span class="sxs-lookup"><span data-stu-id="60e56-170">Parent Elements</span></span>

|<span data-ttu-id="60e56-171">요소</span><span class="sxs-lookup"><span data-stu-id="60e56-171">Element</span></span>|<span data-ttu-id="60e56-172">Description</span><span class="sxs-lookup"><span data-stu-id="60e56-172">Description</span></span>|
|-------------|-----------------|
|[\<bindings>](bindings.md)|<span data-ttu-id="60e56-173">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-173">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="60e56-174">설명</span><span class="sxs-lookup"><span data-stu-id="60e56-174">Remarks</span></span>

<span data-ttu-id="60e56-175">페더레이션은 인증 및 권한 부여를 위해 여러 회사나 트러스트 도메인 간에 ID를 공유하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-175">Federation is the ability to share identities across multiple enterprises or trust domains for authentication and authorization.</span></span> <span data-ttu-id="60e56-176">WS-Trust 프로토콜을 사용하여 ID 표현을 트러스트 도메인 간에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-176">It uses the WS-Trust protocol to map the identity representation from one trust domain to another.</span></span> <span data-ttu-id="60e56-177">페더레이션 HTTP 바인딩은 SOAP 보안과 혼합 모드 보안을 지원하지만 전송 보안을 지원하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-177">Federated HTTP binding supports SOAP security as well as mixed-mode security, but it does not support transport security.</span></span> <span data-ttu-id="60e56-178">이 바인딩으로 구성된 서비스는 HTTP 전송을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60e56-178">Services configured with this binding must use the HTTP transport.</span></span> <span data-ttu-id="60e56-179">자세한 내용은 [\<wsFederationHttpBinding>](wsfederationhttpbinding.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60e56-179">For more information, see [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="60e56-180">예제</span><span class="sxs-lookup"><span data-stu-id="60e56-180">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="60e56-181">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60e56-181">See also</span></span>

- <xref:System.ServiceModel.WS2007FederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>
- [\<wsFederationHttpBinding>](wsfederationhttpbinding.md)
- [<span data-ttu-id="60e56-182">바인딩</span><span class="sxs-lookup"><span data-stu-id="60e56-182">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="60e56-183">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="60e56-183">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="60e56-184">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="60e56-184">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
