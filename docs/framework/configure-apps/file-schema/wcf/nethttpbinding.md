---
title: <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: b0d81ca0-87c5-4090-8baa-e390fd3656d2
ms.openlocfilehash: 815ee3993a2f2b2819210b225c0cb0b3d3fd8b87
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201020"
---
# \<netHttpBinding>
<span data-ttu-id="98118-101">WCF (Windows Communication Foundation) 서비스가 HTTP를 통해 통신할 수 있는 끝점을 구성 및 노출 하는 데 사용할 수 있는 바인딩을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="98118-101">Represents a binding that a Windows Communication Foundation (WCF) service can use to configure and expose endpoints that are able to communicate over HTTP.</span></span> <span data-ttu-id="98118-102">이중 계약과 함께 사용하는 경우 WebSocket이 사용되고, 그렇지 않으면 HTTP가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-102">When used with a duplex contract, Web Sockets will be used, otherwise HTTP will be used.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="98118-103">구문</span><span class="sxs-lookup"><span data-stu-id="98118-103">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Binary/Text/Mtom"
           name="String"
           openTimeout="TimeSpan"
           proxyAddress="URI"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"
           useDefaultWebProxy="Boolean">
    <security mode="None/Transport/Message/TransportWithMessageCredential/TransportCredentialOnly">
      <transport clientCredentialType="None/Basic/Digest/Ntlm/Windows/Certificate"
                 proxyCredentialType="None/Basic/Digest/Ntlm/Windows"
                 realm="string" />
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="UserName/Certificate" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="98118-104">형식</span><span class="sxs-lookup"><span data-stu-id="98118-104">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98118-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="98118-105">Attributes and Elements</span></span>  
 <span data-ttu-id="98118-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98118-107">특성</span><span class="sxs-lookup"><span data-stu-id="98118-107">Attributes</span></span>  
  
|<span data-ttu-id="98118-108">특성</span><span class="sxs-lookup"><span data-stu-id="98118-108">Attribute</span></span>|<span data-ttu-id="98118-109">설명</span><span class="sxs-lookup"><span data-stu-id="98118-109">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="98118-110">클라이언트가 쿠키를 수락하고 이를 앞으로의 요청에서 전파할지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-110">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="98118-111">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-111">The default is `false`.</span></span><br /><br /> <span data-ttu-id="98118-112">쿠키를 사용하는 ASMX 웹 서비스와 상호 작용할 때 이 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-112">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="98118-113">그러면 서버에서 반환된 쿠키가 해당 서비스에 대한 이후의 모든 클라이언트 요청에 자동으로 복사되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-113">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="98118-114">로컬 주소에 대해 프록시 서버를 사용하지 않을 것인지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-114">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="98118-115">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-115">The default is `false`.</span></span><br /><br /> <span data-ttu-id="98118-116">주소가 로컬인 인터넷 리소스는 로컬 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-116">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="98118-117">로컬 주소는 동일한 컴퓨터, 로컬 LAN 또는 인트라넷에 있는 주소 이며 구문적으로 Uri 및에서와 같이 마침표 (.)가 없는 것으로 식별 됩니다. `http://webserver/` `http://localhost/`</span><span class="sxs-lookup"><span data-stu-id="98118-117">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs `http://webserver/` and `http://localhost/`.</span></span><br /><br /> <span data-ttu-id="98118-118">이 특성은 BasicHttpBinding으로 구성된 엔드포인트가 로컬 리소스 액세스 시 프록시 서버를 사용할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-118">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="98118-119">이 특성이 `true`이면 로컬 인터넷 리소스에 대한 요청은 프록시 서버를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-119">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="98118-120">이 특성이 `true`로 설정된 경우 클라이언트가 동일한 시스템의 서비스와 통신할 때 프록시를 통하게 하려면 localhost 대신 호스트 이름을 사용해야 합니다</span><span class="sxs-lookup"><span data-stu-id="98118-120">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="98118-121">이 특성이 `false`이면 모든 인터넷 요청이 프록시 서버를 통해 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="98118-121">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="98118-122">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="98118-123">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="98118-124">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-124">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="98118-125">URI 구문 분석에 사용되는 HTTP 호스트 이름 비교 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-125">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="98118-126">이 특성은 <xref:System.ServiceModel.HostNameComparisonMode> 형식이며 URI에 대해 비교할 때 호스트 이름이 서비스에 연결하는 데 사용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="98118-126">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="98118-127">기본값은 <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>이며 이 값은 비교 시 호스트 이름을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-127">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="98118-128">채널에서 메시지를 수신하는 메시지 버퍼 관리자가 사용하도록 할당된 최대 메모리를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-128">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="98118-129">기본값은 524288(0x80000)바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-129">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="98118-130">버퍼 관리자는 버퍼 풀을 사용하여 버퍼 사용 비용을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-130">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="98118-131">버퍼는 메시지가 채널에서 나올 때 서비스를 이용하여 그 메시지를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-131">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="98118-132">버퍼 풀에 메시지 로드를 처리하기에 충분한 메모리가 없는 경우 버퍼 관리자는 CLR 힙으로부터 추가 메모리를 할당해야 하며, 이로 인해 가비지 컬렉션 오버헤드가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-132">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="98118-133">CLR 가비지 힙으로부터 다량의 할당이 이루어지는 경우 버퍼 풀 크기가 너무 작은 것이므로, 이 특성으로 지정된 제한을 늘려 더 크게 할당하면 성능이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-133">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="98118-134">이 바인딩으로 구성된 엔드포인트에 대해 메시지가 처리되는 동안 해당 메시지를 저장하는 버퍼의 최대 크기(바이트)를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-134">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="98118-135">기본값은 65,536바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-135">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="98118-136">이 바인딩으로 구성된 채널에서 받을 수 있는 메시지(헤더 포함)의 최대 메시지 크기(바이트)를 정의하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-136">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="98118-137">수신자에게 너무 큰 메시지를 보낸 발신자에게는 SOAP 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-137">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="98118-138">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98118-138">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="98118-139">기본값은 65,536바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-139">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="98118-140">SOAP 메시지를 인코딩하는 데 사용되는 인코더를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-140">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="98118-141">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-141">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="98118-142">-Text: 텍스트 메시지 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-142">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="98118-143">-Mtom: 메시지 전송 조직 메커니즘 1.0 (MTOM) 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-143">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="98118-144">기본값은 Text입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-144">The default is Text.</span></span> <span data-ttu-id="98118-145">이 특성은 <xref:System.ServiceModel.WSMessageEncoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-145">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="98118-146">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-146">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="98118-147">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-147">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="98118-148">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-148">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="98118-149">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98118-149">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="98118-150">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-150">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="98118-151">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-151">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="98118-152">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-152">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="98118-153">HTTP 프록시의 주소를 포함하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-153">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="98118-154">`useSystemWebProxy`를 `true`로 설정할 경우 이 설정은 `null`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-154">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="98118-155">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-155">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="98118-156">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-156">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="98118-157">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-157">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="98118-158">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-158">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="98118-159">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="98118-160">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="98118-161">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-161">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="98118-162">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-162">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="98118-163">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-163">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="98118-164">-BigEndianUnicode: Unicode가 나 Endian 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-164">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="98118-165">-Unicode: 16 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-165">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="98118-166">-UTF8:8 비트 인코딩</span><span class="sxs-lookup"><span data-stu-id="98118-166">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="98118-167">기본값은 UTF8입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-167">The default is UTF8.</span></span> <span data-ttu-id="98118-168">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-168">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="98118-169">메시지가 요청 또는 응답에서 버퍼링되는지 또는 스트리밍되는지를 지정하는 유효한 <xref:System.ServiceModel.TransferMode> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-169">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="98118-170">시스템의 자동 구성된 HTTP 프록시가 있는 경우 이를 사용할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-170">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="98118-171">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-171">The default is `true`.</span></span>|  
|||  
  
### <a name="child-elements"></a><span data-ttu-id="98118-172">자식 요소</span><span class="sxs-lookup"><span data-stu-id="98118-172">Child Elements</span></span>  
  
|<span data-ttu-id="98118-173">요소</span><span class="sxs-lookup"><span data-stu-id="98118-173">Element</span></span>|<span data-ttu-id="98118-174">설명</span><span class="sxs-lookup"><span data-stu-id="98118-174">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-basichttpbinding.md)|<span data-ttu-id="98118-175">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-175">Defines the security settings for the binding.</span></span> <span data-ttu-id="98118-176">이 요소는 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-176">This element is of type <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.</span></span>|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="98118-177">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-177">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="98118-178">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="98118-178">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="98118-179">부모 요소</span><span class="sxs-lookup"><span data-stu-id="98118-179">Parent Elements</span></span>  
  
|<span data-ttu-id="98118-180">요소</span><span class="sxs-lookup"><span data-stu-id="98118-180">Element</span></span>|<span data-ttu-id="98118-181">설명</span><span class="sxs-lookup"><span data-stu-id="98118-181">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="98118-182">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-182">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98118-183">설명</span><span class="sxs-lookup"><span data-stu-id="98118-183">Remarks</span></span>  
 <span data-ttu-id="98118-184">NetHttpBinding은 메시지를 보내기 위한 전송으로 HTTP를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-184">The NetHttpBinding uses HTTP as the transport for sending messages.</span></span> <span data-ttu-id="98118-185">이중 계약과 함께 사용하는 경우 WebSocket이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-185">When used with a duplex contract, Web Sockets will be used.</span></span>  <span data-ttu-id="98118-186">요청-회신 계약과 함께 사용하는 경우 NetHttpBinding은 이진 인코더를 사용하는 BasicHttpBinding처럼 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-186">When used with a request-reply contract NetHttpBinding will behave like a BasicHttpBinding with a binary encoder.</span></span>  
  
 <span data-ttu-id="98118-187">보안은 기본적으로 해제 되어 있지만 자식 요소의 mode 특성을 이외의 값으로 설정 하 여 추가할 수 있습니다 [\<security>](security-of-basichttpbinding.md) `None` .</span><span class="sxs-lookup"><span data-stu-id="98118-187">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="98118-188">기본적으로 "텍스트" 메시지 인코딩과 UTF-8 텍스트 인코딩을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-188">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98118-189">예제</span><span class="sxs-lookup"><span data-stu-id="98118-189">Example</span></span>  
 <span data-ttu-id="98118-190">다음 예제에서는 첫 번째 및 두 번째 세대 웹 서비스와의 HTTP 통신 및 최대 상호 운용성을 제공하는 <xref:System.ServiceModel.NetHttpBinding>의 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98118-190">The following example demonstrates the use of <xref:System.ServiceModel.NetHttpBinding> that provides HTTP communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="98118-191">클라이언트 및 서비스 구성 파일에 바인딩이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="98118-191">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="98118-192">바인딩 형식은 `binding` 요소의 `<endpoint>` 특성을 사용하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-192">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="98118-193">기본 바인딩을 구성하고 일부 설정을 변경하려면 바인딩 구성을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-193">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="98118-194">엔드포인트는 서비스에 대한 다음 구성 코드에 표시된 것처럼 `bindingConfiguration` 요소의 `<endpoint>` 특성을 사용하여 이름으로 바인딩 구성을 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98118-194">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
      <binding name="Binding1"
               hostNameComparisonMode="StrongWildcard"
               receiveTimeout="00:10:00"
               sendTimeout="00:10:00"
               openTimeout="00:10:00"
               closeTimeout="00:10:00"
               maxReceivedMessageSize="65536"
               maxBufferSize="65536"
               maxBufferPoolSize="524288"
               transferMode="Buffered"
               messageEncoding="Binary"
               textEncoding="utf-8"
               bypassProxyOnLocal="false"
               useDefaultWebProxy="true">
        <security mode="None" />
      </binding>
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="example"></a><span data-ttu-id="98118-195">예제</span><span class="sxs-lookup"><span data-stu-id="98118-195">Example</span></span>  
 <span data-ttu-id="98118-196">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-196">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="98118-197">이전 예제의 기능은 끝점 주소에서 bindingConfiguration을 제거 하 고 바인딩에서 이름을 제거 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98118-197">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name from the binding.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
      <binding hostNameComparisonMode="StrongWildcard"
               receiveTimeout="00:10:00"
               sendTimeout="00:10:00"
               openTimeout="00:10:00"
               closeTimeout="00:10:00"
               maxReceivedMessageSize="65536"
               maxBufferSize="65536"
               maxBufferPoolSize="524288"
               transferMode="Buffered"
               messageEncoding="Binary"
               textEncoding="utf-8"
               bypassProxyOnLocal="false"
               useDefaultWebProxy="true">
        <security mode="None" />
      </binding>
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
 <span data-ttu-id="98118-198">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98118-198">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98118-199">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98118-199">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="98118-200">바인딩</span><span class="sxs-lookup"><span data-stu-id="98118-200">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="98118-201">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="98118-201">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="98118-202">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="98118-202">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
