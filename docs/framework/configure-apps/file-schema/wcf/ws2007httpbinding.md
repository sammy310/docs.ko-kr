---
title: <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 8586ecc9-bdaa-44d6-8d4d-7038e4ea1741
ms.openlocfilehash: 35e47d582a6b8534597945a626904d084fbeeade
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377003"
---
# <a name="ws2007httpbinding"></a><span data-ttu-id="006b0-101">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="006b0-101">\<ws2007HttpBinding></span></span>
<span data-ttu-id="006b0-102">올바른 버전의 <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession> 및 <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> 바인딩 요소를 지원하는 상호 운용 가능한 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-102">Defines an interoperable binding that provides support for the correct versions of the <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession>, and <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> binding elements.</span></span>  
  
 <span data-ttu-id="006b0-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="006b0-103">\<system.serviceModel></span></span>  
<span data-ttu-id="006b0-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="006b0-104">\<bindings></span></span>  
<span data-ttu-id="006b0-105">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="006b0-105">\<ws2007HttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="006b0-106">구문</span><span class="sxs-lookup"><span data-stu-id="006b0-106">Syntax</span></span>  
  
```xml  
<ws2007HttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           proxyAddress="URI"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="Message/None/Transport/TransportWithCredential">
      <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                 proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                 realm="string" />
        <message clientCredentialType ="Certificate/IssuedToken/None/UserName/Windows"
                 negotiateServiceCredential="Boolean"
                 algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
                 establishSecurityContext="Boolean"
                 negotiateServiceCredential="Boolean" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</ws2007HttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="006b0-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="006b0-107">Attributes and Elements</span></span>  
 <span data-ttu-id="006b0-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="006b0-109">특성</span><span class="sxs-lookup"><span data-stu-id="006b0-109">Attributes</span></span>  
  
|<span data-ttu-id="006b0-110">특성</span><span class="sxs-lookup"><span data-stu-id="006b0-110">Attribute</span></span>|<span data-ttu-id="006b0-111">설명</span><span class="sxs-lookup"><span data-stu-id="006b0-111">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="006b0-112">클라이언트가 쿠키를 수락하고 그러한 쿠키를 이후 요청에 전파할지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="006b0-113">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-113">The default is `false`.</span></span><br /><br /> <span data-ttu-id="006b0-114">쿠키를 사용하는 ASP.NET 웹 서비스(ASMX)와 상호 작용할 때 이 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-114">You can use this property when you interact with ASP.NET Web services (ASMX) that use cookies.</span></span> <span data-ttu-id="006b0-115">이 속성을 사용하면 서버에서 반환하는 쿠키가 해당 서비스에 대한 이후의 모든 클라이언트 요청에 자동으로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-115">This ensures that cookies that the server returns are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="006b0-116">로컬 주소에 대해 프록시 서버를 우회할지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-116">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="006b0-117">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-117">The default is `false`.</span></span>|  
|`closeTimeout`|<span data-ttu-id="006b0-118">닫기 작업을 완료하기 위한 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-118">A <xref:System.TimeSpan> value that specifies the time interval for a close operation to complete.</span></span> <span data-ttu-id="006b0-119">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="006b0-120">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-120">The default is 00:01:00.</span></span>|  
|`hostnameComparisonMode`|<span data-ttu-id="006b0-121">URI(Uniform Resource Identifier) 구문 분석에 사용되는 HTTP 호스트 이름 비교 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-121">Specifies the HTTP hostname comparison mode used to parse Uniform Resource Identifiers (URIs).</span></span> <span data-ttu-id="006b0-122">이 특성은 <xref:System.ServiceModel.HostNameComparisonMode> 형식이며 URI에 대해 비교할 때 호스트 이름이 서비스에 연결하는 데 사용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-122">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="006b0-123">기본값은 <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>이며 이 값은 비교 시 호스트 이름을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-123">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="006b0-124">이 바인딩에 대한 최대 버퍼 풀 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-124">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="006b0-125">기본값은 524,288바이트(512 x 1,024)입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-125">The default is 524,288 bytes (512 × 1,024).</span></span> <span data-ttu-id="006b0-126">WCF(Windows Communication Foundation)의 많은 부분에서 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-126">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="006b0-127">버퍼가 필요할 때마다 버퍼를 만들고 삭제하면 비용이 많이 들며, 버퍼에 대한 가비지 수집 비용도 무시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-127">Creating and destroying buffers each time they are used is expensive, as is garbage collection for buffers.</span></span> <span data-ttu-id="006b0-128">버퍼 풀이 있으면 이 풀에서 버퍼를 가져와 사용한 다음 다시 풀로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-128">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool when you are done.</span></span> <span data-ttu-id="006b0-129">따라서 버퍼를 만들고 삭제하는 오버헤드를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-129">This avoids the overhead in creating and destroying buffers.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="006b0-130">이 바인딩으로 구성된 채널에서 받을 수 있는 최대 메시지 크기(헤더 포함)로 단위는 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-130">The maximum message size, in bytes, including headers, which a channel configured with this binding, can receive.</span></span> <span data-ttu-id="006b0-131">이 한도를 초과하는 메시지를 보낸 발신자는 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-131">The sender of a message exceeding this limit receives a SOAP fault.</span></span> <span data-ttu-id="006b0-132">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-132">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="006b0-133">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-133">The default is 65536.</span></span>|  
|`messageEncoding`|<span data-ttu-id="006b0-134">메시지를 인코딩하는 데 사용되는 인코더를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-134">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="006b0-135">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-135">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="006b0-136">-   `Text`: 텍스트 메시지 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-136">-   `Text`: Use a text message encoder.</span></span><br /><span data-ttu-id="006b0-137">-   `Mtom`: 조직 메커니즘 1.0 MTOM (Message Transmission) 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-137">-   `Mtom`: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="006b0-138">기본값은 `Text`입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-138">The default is `Text`.</span></span><br /><br /> <span data-ttu-id="006b0-139">이 특성은 <xref:System.ServiceModel.WSMessageEncoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-139">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="006b0-140">바인딩의 구성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-140">The configuration name of the binding.</span></span> <span data-ttu-id="006b0-141">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-141">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="006b0-142">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-142">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="006b0-143">기본 구성 및 이름 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 하세요. [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) 하 고 [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-143">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="006b0-144">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-144">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="006b0-145">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-145">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="006b0-146">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-146">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="006b0-147">HTTP 프록시의 주소를 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-147">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="006b0-148">`useSystemWebProxy`가 `true`일 경우 이 설정은 `null`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-148">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="006b0-149">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-149">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="006b0-150">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-150">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="006b0-151">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-151">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="006b0-152">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-152">The default is 00:01:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="006b0-153">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-153">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="006b0-154">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-154">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="006b0-155">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-155">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="006b0-156">바인딩에서 메시지를 내보내는 데 사용할 문자 집합 인코딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-156">Specifies the character set encoding to use for emitting messages on the binding.</span></span> <span data-ttu-id="006b0-157">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-157">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="006b0-158">-   `UnicodeFffeTextEncoding`: 유니코드 Big Endian 인코딩</span><span class="sxs-lookup"><span data-stu-id="006b0-158">-   `UnicodeFffeTextEncoding`: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="006b0-159">-   `Utf16TextEncoding`: 16 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-159">-   `Utf16TextEncoding`: 16-bit encoding.</span></span><br /><span data-ttu-id="006b0-160">-   `Utf8TextEncoding`: 8 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-160">-   `Utf8TextEncoding`: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="006b0-161">기본값은 `Utf8TextEncoding`입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-161">The default is `Utf8TextEncoding`.</span></span><br /><br /> <span data-ttu-id="006b0-162">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-162">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transactionFlow`|<span data-ttu-id="006b0-163">바인딩에서 WS-트랜잭션 이동을 지원할지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-163">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="006b0-164">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-164">The default is `false`.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="006b0-165">시스템의 자동 구성된 HTTP 프록시 사용 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-165">A value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="006b0-166">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-166">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="006b0-167">자식 요소</span><span class="sxs-lookup"><span data-stu-id="006b0-167">Child Elements</span></span>  
  
|<span data-ttu-id="006b0-168">요소</span><span class="sxs-lookup"><span data-stu-id="006b0-168">Element</span></span>|<span data-ttu-id="006b0-169">설명</span><span class="sxs-lookup"><span data-stu-id="006b0-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="006b0-170">\<security></span><span class="sxs-lookup"><span data-stu-id="006b0-170">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="006b0-171">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-171">Defines the security settings for the binding.</span></span> <span data-ttu-id="006b0-172">이 요소는 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-172">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|<span data-ttu-id="006b0-173">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="006b0-173">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="006b0-174">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-174">Defines the constraints on the complexity of SOAP messages that endpoints configured with this binding can process.</span></span> <span data-ttu-id="006b0-175">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-175">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|<span data-ttu-id="006b0-176">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="006b0-176">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="006b0-177">채널 엔드포인트 간에 신뢰할 수 있는 세션이 설정되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-177">Specifies whether reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="006b0-178">부모 요소</span><span class="sxs-lookup"><span data-stu-id="006b0-178">Parent Elements</span></span>  
  
|<span data-ttu-id="006b0-179">요소</span><span class="sxs-lookup"><span data-stu-id="006b0-179">Element</span></span>|<span data-ttu-id="006b0-180">설명</span><span class="sxs-lookup"><span data-stu-id="006b0-180">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="006b0-181">\<bindings></span><span class="sxs-lookup"><span data-stu-id="006b0-181">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="006b0-182">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-182">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="006b0-183">설명</span><span class="sxs-lookup"><span data-stu-id="006b0-183">Remarks</span></span>  
 <span data-ttu-id="006b0-184">
  `WS2007HttpBinding`은 `WSHttpBinding\`과 비슷한 시스템 제공 바인딩을 추가하지만, OASIS(Organization for the Advancement of Structured Information Standards) 표준 버전의 ReliableSession, Security 및 TransactionFlow 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-184">The `WS2007HttpBinding` adds a system-provided binding similar to `WSHttpBinding` but uses the Organization for the Advancement of Structured Information Standards (OASIS) standard versions of the ReliableSession, Security, and TransactionFlow protocols.</span></span> <span data-ttu-id="006b0-185">이 바인딩을 사용할 때는 개체 모델이나 기본 설정을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="006b0-185">No changes to the object model or default settings are required when using this binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="006b0-186">예제</span><span class="sxs-lookup"><span data-stu-id="006b0-186">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <ws2007HttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://www.contoso.com"
                 textEncoding="utf-16"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="Transport">
            <transport clientCredentialType="Digest"
                       proxyCredentialType="None"
                       realm="someRealm" />
            <message clientCredentialType="Windows"
                     negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     defaultProtectionLevel="None" />
          </security>
        </binding>
      </ws2007HttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="006b0-187">참고자료</span><span class="sxs-lookup"><span data-stu-id="006b0-187">See also</span></span>
- <xref:System.ServiceModel.WS2007HttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007HttpBindingElement>
- [<span data-ttu-id="006b0-188">바인딩</span><span class="sxs-lookup"><span data-stu-id="006b0-188">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="006b0-189">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="006b0-189">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="006b0-190">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="006b0-190">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="006b0-191">\<binding></span><span class="sxs-lookup"><span data-stu-id="006b0-191">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
