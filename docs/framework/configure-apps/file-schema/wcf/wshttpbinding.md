---
title: <wsHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsHttpBinding Element
ms.assetid: 0eee8ced-ad68-427d-b95a-97260e98deed
ms.openlocfilehash: 6059bc91588492afdd1f205398e6cdfdba0be7ef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670185"
---
# <a name="wshttpbinding"></a><span data-ttu-id="460fe-101">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="460fe-101">\<wsHttpBinding></span></span>
<span data-ttu-id="460fe-102">비이중 서비스 계약에 적합한 안전하고 신뢰할 수 있으며 상호 운용할 수 있는 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-102">Defines a secure, reliable, interoperable binding suitable for non-duplex service contracts.</span></span> <span data-ttu-id="460fe-103">바인딩에 다음 사양을 구현 합니다. Ws-reliable Messaging 안정성 및 메시지 보안 및 인증을 위해 Ws-security에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-103">The binding implements the following specifications: WS-Reliable Messaging for reliability, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="460fe-104">전송은 HTTP이며 메시지 인코딩은 Text/XML 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-104">The transport is HTTP, and message encoding is Text/XML encoding.</span></span>  
  
 <span data-ttu-id="460fe-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="460fe-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="460fe-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="460fe-106">\<bindings></span></span>  
<span data-ttu-id="460fe-107">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="460fe-107">\<wsHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="460fe-108">구문</span><span class="sxs-lookup"><span data-stu-id="460fe-108">Syntax</span></span>  
  
```xml  
<wsHttpBinding>
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
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
               establishSecurityContext="Boolean"
               negotiateServiceCredential="Boolean" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="460fe-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="460fe-109">Attributes and Elements</span></span>  
 <span data-ttu-id="460fe-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="460fe-111">특성</span><span class="sxs-lookup"><span data-stu-id="460fe-111">Attributes</span></span>  
  
|<span data-ttu-id="460fe-112">특성</span><span class="sxs-lookup"><span data-stu-id="460fe-112">Attribute</span></span>|<span data-ttu-id="460fe-113">설명</span><span class="sxs-lookup"><span data-stu-id="460fe-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="460fe-114">allowCookies</span><span class="sxs-lookup"><span data-stu-id="460fe-114">allowCookies</span></span>|<span data-ttu-id="460fe-115">클라이언트가 쿠키를 수락하고 이를 앞으로의 요청에서 전파할지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-115">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="460fe-116">기본값은 false입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-116">The default is false.</span></span><br /><br /> <span data-ttu-id="460fe-117">쿠키를 사용하는 ASMX 웹 서비스와 상호 작용할 때 이 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-117">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="460fe-118">그러면 서버에서 반환된 쿠키가 해당 서비스에 대한 이후의 모든 클라이언트 요청에 자동으로 복사되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-118">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|<span data-ttu-id="460fe-119">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="460fe-119">bypassProxyOnLocal</span></span>|<span data-ttu-id="460fe-120">로컬 주소에 대해 프록시 서버를 사용하지 않을 것인지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-120">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="460fe-121">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-121">The default is `false`.</span></span>|  
|<span data-ttu-id="460fe-122">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="460fe-122">closeTimeout</span></span>|<span data-ttu-id="460fe-123">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="460fe-124">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="460fe-125">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-125">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="460fe-126">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="460fe-126">hostnameComparisonMode</span></span>|<span data-ttu-id="460fe-127">URI 구문 분석에 사용되는 HTTP 호스트 이름 비교 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-127">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="460fe-128">이 특성은 <xref:System.ServiceModel.HostNameComparisonMode> 형식이며 URI에 대해 비교할 때 호스트 이름이 서비스에 연결하는 데 사용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-128">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="460fe-129">기본값은 <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>이며 이 값은 비교 시 호스트 이름을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-129">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="460fe-130">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="460fe-130">maxBufferPoolSize</span></span>|<span data-ttu-id="460fe-131">이 바인딩의 최대 버퍼 풀 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-131">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="460fe-132">기본값은 524,288바이트(512 \* 1024)입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-132">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="460fe-133">WCF(Windows Communication Foundation)의 많은 부분에서 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-133">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="460fe-134">버퍼를 사용할 때마다 만들고 삭제하면 비용이 많이 들며, 버퍼에 대한 가비지 수집 역시 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-134">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="460fe-135">버퍼 풀이 있으면 이 풀로부터 버퍼를 가져와 사용한 다음 다시 풀로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-135">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="460fe-136">따라서 버퍼를 만들고 삭제하는 데 오버헤드를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-136">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="460fe-137">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="460fe-137">maxReceivedMessageSize</span></span>|<span data-ttu-id="460fe-138">헤더를 비롯하여 이 바인딩으로 구성된 채널에서 받을 수 있는 최대 메시지 크기(바이트)를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-138">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="460fe-139">이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-139">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="460fe-140">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-140">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="460fe-141">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-141">The default is 65536.</span></span>|  
|<span data-ttu-id="460fe-142">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="460fe-142">messageEncoding</span></span>|<span data-ttu-id="460fe-143">메시지를 인코딩하는 데 사용되는 인코더를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-143">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="460fe-144">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="460fe-145">텍스트: 텍스트 메시지 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-145">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="460fe-146">Mtom: 조직 메커니즘 1.0 MTOM (Message Transmission) 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-146">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="460fe-147">-기본값은 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-147">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="460fe-148">이 특성은 <xref:System.ServiceModel.WSMessageEncoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-148">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="460fe-149">name</span><span class="sxs-lookup"><span data-stu-id="460fe-149">name</span></span>|<span data-ttu-id="460fe-150">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-150">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="460fe-151">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-151">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="460fe-152">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-152">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="460fe-153">기본 구성 및 이름 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 하세요. [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) 하 고 [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-153">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="460fe-154">openTimeout</span><span class="sxs-lookup"><span data-stu-id="460fe-154">openTimeout</span></span>|<span data-ttu-id="460fe-155">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-155">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="460fe-156">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-156">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="460fe-157">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-157">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="460fe-158">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="460fe-158">proxyAddress</span></span>|<span data-ttu-id="460fe-159">HTTP 프록시의 주소를 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-159">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="460fe-160">`useSystemWebProxy`가 `true`일 경우 이 설정은 `null`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-160">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="460fe-161">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-161">The default is `null`.</span></span>|  
|<span data-ttu-id="460fe-162">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="460fe-162">receiveTimeout</span></span>|<span data-ttu-id="460fe-163">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-163">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="460fe-164">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-164">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="460fe-165">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-165">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="460fe-166">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="460fe-166">sendTimeout</span></span>|<span data-ttu-id="460fe-167">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-167">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="460fe-168">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-168">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="460fe-169">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-169">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="460fe-170">textEncoding</span><span class="sxs-lookup"><span data-stu-id="460fe-170">textEncoding</span></span>|<span data-ttu-id="460fe-171">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-171">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="460fe-172">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-172">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="460fe-173">-   UnicodeFffeTextEncoding: 유니코드 BigEndian 인코딩</span><span class="sxs-lookup"><span data-stu-id="460fe-173">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="460fe-174">-   Utf16TextEncoding: 16 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-174">-   Utf16TextEncoding: 16-bit encoding.</span></span><br /><span data-ttu-id="460fe-175">-   Utf8TextEncoding: 8 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-175">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="460fe-176">기본값은 Utf8TextEncoding입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-176">The default is Utf8TextEncoding.</span></span><br /><br /> <span data-ttu-id="460fe-177">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-177">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="460fe-178">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="460fe-178">transactionFlow</span></span>|<span data-ttu-id="460fe-179">바인딩에서 WS-Transactions 이동을 지원할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-179">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="460fe-180">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-180">The default is `false`.</span></span>|  
|<span data-ttu-id="460fe-181">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="460fe-181">useDefaultWebProxy</span></span>|<span data-ttu-id="460fe-182">시스템의 자동 구성된 HTTP 프록시 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-182">A Boolean value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="460fe-183">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-183">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="460fe-184">자식 요소</span><span class="sxs-lookup"><span data-stu-id="460fe-184">Child Elements</span></span>  
  
|<span data-ttu-id="460fe-185">요소</span><span class="sxs-lookup"><span data-stu-id="460fe-185">Element</span></span>|<span data-ttu-id="460fe-186">설명</span><span class="sxs-lookup"><span data-stu-id="460fe-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="460fe-187">\<security></span><span class="sxs-lookup"><span data-stu-id="460fe-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="460fe-188">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-188">Defines the security settings for the binding.</span></span> <span data-ttu-id="460fe-189">이 요소는 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-189">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|<span data-ttu-id="460fe-190">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="460fe-190">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="460fe-191">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-191">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="460fe-192">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-192">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|<span data-ttu-id="460fe-193">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="460fe-193">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="460fe-194">채널 엔드포인트 간에 신뢰할 수 있는 세션이 설정되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-194">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="460fe-195">부모 요소</span><span class="sxs-lookup"><span data-stu-id="460fe-195">Parent Elements</span></span>  
  
|<span data-ttu-id="460fe-196">요소</span><span class="sxs-lookup"><span data-stu-id="460fe-196">Element</span></span>|<span data-ttu-id="460fe-197">설명</span><span class="sxs-lookup"><span data-stu-id="460fe-197">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="460fe-198">\<bindings></span><span class="sxs-lookup"><span data-stu-id="460fe-198">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="460fe-199">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-199">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="460fe-200">설명</span><span class="sxs-lookup"><span data-stu-id="460fe-200">Remarks</span></span>  
 <span data-ttu-id="460fe-201">`WSHttpBinding`은 `BasicHttpBinding`과 비슷하지만 더 다양한 웹 서비스 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-201">The `WSHttpBinding` is similar to the `BasicHttpBinding` but provides more Web service features.</span></span> <span data-ttu-id="460fe-202">BasicHttpBinding과 마찬가지로 HTTP 전송을 사용하며 메시지 보안을 제공하지만 다른 점은 트랜잭션, 신뢰할 수 있는 메시징, WS-Addressing도 가능하다는 것입니다. 이러한 기능은 기본적으로 또는 단일 제어 설정을 통해 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="460fe-202">It uses the HTTP transport and provides message security, as does BasicHttpBinding, but it also provides transactions, reliable messaging, and WS-Addressing, either enabled by default or available through a single control setting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="460fe-203">예제</span><span class="sxs-lookup"><span data-stu-id="460fe-203">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsHttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
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
      </wsHttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="460fe-204">참고자료</span><span class="sxs-lookup"><span data-stu-id="460fe-204">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement>
- [<span data-ttu-id="460fe-205">바인딩</span><span class="sxs-lookup"><span data-stu-id="460fe-205">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="460fe-206">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="460fe-206">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="460fe-207">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="460fe-207">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="460fe-208">\<binding></span><span class="sxs-lookup"><span data-stu-id="460fe-208">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
