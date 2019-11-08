---
title: <wsDualHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsDualHttpBinding Element
ms.assetid: fd8ac4e2-5641-473b-9115-73f14ab1c065
ms.openlocfilehash: 8d5cfed3cddb9e85e3bfac900723e11a39af1ae7
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735673"
---
# <a name="wsdualhttpbinding"></a><span data-ttu-id="05cd6-101">\<wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="05cd6-101">\<wsDualHttpBinding></span></span>
<span data-ttu-id="05cd6-102">이중 서비스 계약 또는 SOAP 중간 매개자를 통한 통신에 사용할 수 있도록 보안이 유지되고 신뢰할 수 있으며 상호 운용할 수 있는 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-102">Defines a secure, reliable and interoperable binding that is suitable for duplex service contracts or communication through SOAP intermediaries.</span></span>  
  
<span data-ttu-id="05cd6-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="05cd6-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="05cd6-104">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="05cd6-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="05cd6-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="05cd6-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="05cd6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<wsDualHttpBinding >**</span><span class="sxs-lookup"><span data-stu-id="05cd6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsDualHttpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05cd6-107">구문</span><span class="sxs-lookup"><span data-stu-id="05cd6-107">Syntax</span></span>  
  
```xml  
<wsDualHttpBinding>
  <binding name="String"
          closeTimeout="TimeSpan"
          openTimeout="TimeSpan"
          receiveTimeout="TimeSpan"
          sendTimeout="TimeSpan"
          bypassProxyOnLocal="Boolean"
          clientBaseAddress="URI"
          transactionFlow="Boolean"
          hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
          maxBufferPoolSize="integer"
          maxReceivedMessageSize="Integer"
          messageEncoding="Text/Mtom"
          proxyAddress="URI"
          textEncoding="Unicode/BigEndianUnicode/UTF8"
          useDefaultWebProxy="Boolean">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan" />
    <security mode="None/Message">
      <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsDualHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05cd6-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="05cd6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="05cd6-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05cd6-110">특성</span><span class="sxs-lookup"><span data-stu-id="05cd6-110">Attributes</span></span>  
  
|<span data-ttu-id="05cd6-111">특성</span><span class="sxs-lookup"><span data-stu-id="05cd6-111">Attribute</span></span>|<span data-ttu-id="05cd6-112">설명</span><span class="sxs-lookup"><span data-stu-id="05cd6-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="05cd6-113">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="05cd6-113">bypassProxyOnLocal</span></span>|<span data-ttu-id="05cd6-114">로컬 주소에 대해 프록시 서버를 사용 하지 않을 것인지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-114">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="05cd6-115">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-115">The default is `false`.</span></span>|  
|<span data-ttu-id="05cd6-116">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="05cd6-116">clientBaseAddress</span></span>|<span data-ttu-id="05cd6-117">클라이언트가 서비스로부터의 응답 메시지를 수신할 기본 주소를 설정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-117">A URI that sets the base address that the client listens to for response messages from the service.</span></span> <span data-ttu-id="05cd6-118">이 특성을 지정하면 수신에 이 주소와 채널별 GUID가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-118">If specified, this address (plus a per-channelGUID) is used for listening.</span></span> <span data-ttu-id="05cd6-119">값을 지정하지 않으면 전송별로 클라이언트 기본 주소가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-119">If the value is not specified, the client base address is generated in a transport-specific manner.</span></span> <span data-ttu-id="05cd6-120">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-120">The default is `null`.</span></span>|  
|<span data-ttu-id="05cd6-121">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="05cd6-121">closeTimeout</span></span>|<span data-ttu-id="05cd6-122">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="05cd6-123">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="05cd6-124">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-124">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="05cd6-125">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="05cd6-125">hostnameComparisonMode</span></span>|<span data-ttu-id="05cd6-126">URI 구문 분석에 사용되는 HTTP 호스트 이름 비교 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-126">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="05cd6-127">이 특성은 <xref:System.ServiceModel.HostNameComparisonMode> 형식이며 URI에 대해 비교할 때 호스트 이름이 서비스에 연결하는 데 사용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-127">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="05cd6-128">기본값은 <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>이며 이 값은 비교 시 호스트 이름을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-128">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="05cd6-129">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="05cd6-129">maxBufferPoolSize</span></span>|<span data-ttu-id="05cd6-130">이 바인딩의 최대 버퍼 풀 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-130">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="05cd6-131">기본값은 524288 바이트 (512 \* 1024)입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-131">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="05cd6-132">WCF (Windows Communication Foundation)의 많은 부분에서 버퍼를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-132">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="05cd6-133">사용 될 때마다 버퍼를 만들고 삭제 하는 것은 비용이 많이 들고 버퍼에 대 한 가비지 수집도 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-133">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="05cd6-134">버퍼 풀을 사용 하면 풀에서 버퍼를 가져와서 사용 하 고 완료 되 면 풀로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-134">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="05cd6-135">따라서 버퍼를 만들고 삭제 하는 오버 헤드는 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-135">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="05cd6-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="05cd6-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="05cd6-137">헤더를 비롯하여 이 바인딩으로 구성된 채널에서 받을 수 있는 최대 메시지 크기(바이트)를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-137">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="05cd6-138">이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-138">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="05cd6-139">수신자는 메시지를 삭제 하 고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-139">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="05cd6-140">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-140">The default is 65536.</span></span>|  
|<span data-ttu-id="05cd6-141">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="05cd6-141">messageEncoding</span></span>|<span data-ttu-id="05cd6-142">메시지를 인코딩하는 데 사용되는 인코더를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-142">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="05cd6-143">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-143">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="05cd6-144">-Text: 텍스트 메시지 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-144">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="05cd6-145">-Mtom: 메시지 전송 조직 메커니즘 1.0 (MTOM) 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-145">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="05cd6-146">-기본값은 Text입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-146">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="05cd6-147">이 특성은 <xref:System.ServiceModel.WSMessageEncoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-147">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="05cd6-148">name</span><span class="sxs-lookup"><span data-stu-id="05cd6-148">name</span></span>|<span data-ttu-id="05cd6-149">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-149">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="05cd6-150">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-150">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="05cd6-151">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-151">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="05cd6-152">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05cd6-152">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="05cd6-153">openTimeout</span><span class="sxs-lookup"><span data-stu-id="05cd6-153">openTimeout</span></span>|<span data-ttu-id="05cd6-154">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-154">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="05cd6-155">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-155">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="05cd6-156">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-156">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="05cd6-157">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="05cd6-157">proxyAddress</span></span>|<span data-ttu-id="05cd6-158">HTTP 프록시의 주소를 지정 하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-158">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="05cd6-159">`useDefaultWebProxy`가 `true`일 경우 이 설정은 `null`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-159">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="05cd6-160">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-160">The default is `null`.</span></span>|  
|<span data-ttu-id="05cd6-161">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="05cd6-161">receiveTimeout</span></span>|<span data-ttu-id="05cd6-162">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-162">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="05cd6-163">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-163">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="05cd6-164">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-164">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="05cd6-165">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="05cd6-165">sendTimeout</span></span>|<span data-ttu-id="05cd6-166">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-166">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="05cd6-167">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-167">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="05cd6-168">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-168">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="05cd6-169">textEncoding</span><span class="sxs-lookup"><span data-stu-id="05cd6-169">textEncoding</span></span>|<span data-ttu-id="05cd6-170">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-170">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="05cd6-171">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-171">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="05cd6-172">-BigEndianUnicode: Unicode가 나 Endian 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-172">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="05cd6-173">-Unicode: 16 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-173">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="05cd6-174">-UTF8:8 비트 인코딩</span><span class="sxs-lookup"><span data-stu-id="05cd6-174">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="05cd6-175">기본값은 UTF8입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-175">The default is UTF8.</span></span> <span data-ttu-id="05cd6-176">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-176">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="05cd6-177">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="05cd6-177">transactionFlow</span></span>|<span data-ttu-id="05cd6-178">바인딩에서 WS-Transactions 이동을 지원할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-178">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="05cd6-179">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-179">The default is `false`.</span></span>|  
|<span data-ttu-id="05cd6-180">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="05cd6-180">useDefaultWebProxy</span></span>|<span data-ttu-id="05cd6-181">시스템의 자동 구성된 HTTP 프록시 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-181">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="05cd6-182">이 특성이 `null`이면 프록시 주소는 `true`이어야 합니다(설정되지 않음).</span><span class="sxs-lookup"><span data-stu-id="05cd6-182">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="05cd6-183">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-183">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05cd6-184">자식 요소</span><span class="sxs-lookup"><span data-stu-id="05cd6-184">Child Elements</span></span>  
  
|<span data-ttu-id="05cd6-185">요소</span><span class="sxs-lookup"><span data-stu-id="05cd6-185">Element</span></span>|<span data-ttu-id="05cd6-186">설명</span><span class="sxs-lookup"><span data-stu-id="05cd6-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05cd6-187">\<security ></span><span class="sxs-lookup"><span data-stu-id="05cd6-187">\<security></span></span>](security-of-wsdualhttpbinding.md)|<span data-ttu-id="05cd6-188">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-188">Defines the security settings for the binding.</span></span> <span data-ttu-id="05cd6-189">이 요소는 <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-189">This element is of type <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement>.</span></span>|  
|<span data-ttu-id="05cd6-190">[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="05cd6-190">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="05cd6-191">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-191">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="05cd6-192">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-192">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|<span data-ttu-id="05cd6-193">[\<reliableSession >](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="05cd6-193">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="05cd6-194">채널 엔드포인트 간에 신뢰할 수 있는 세션이 설정되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-194">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="05cd6-195">부모 요소</span><span class="sxs-lookup"><span data-stu-id="05cd6-195">Parent Elements</span></span>  
  
|<span data-ttu-id="05cd6-196">요소</span><span class="sxs-lookup"><span data-stu-id="05cd6-196">Element</span></span>|<span data-ttu-id="05cd6-197">설명</span><span class="sxs-lookup"><span data-stu-id="05cd6-197">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05cd6-198">\<bindings ></span><span class="sxs-lookup"><span data-stu-id="05cd6-198">\<bindings></span></span>](bindings.md)|<span data-ttu-id="05cd6-199">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-199">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05cd6-200">주의</span><span class="sxs-lookup"><span data-stu-id="05cd6-200">Remarks</span></span>  
 <span data-ttu-id="05cd6-201">`WSDualHttpBinding`는 `WSHttpBinding`와 동일한 웹 서비스 프로토콜에 대 한 지원을 제공 하지만 이중 계약과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-201">The `WSDualHttpBinding` provides the same support for Web Service protocols as the `WSHttpBinding`, but for use with duplex contracts.</span></span> <span data-ttu-id="05cd6-202">`WSDualHttpBinding`은 SOAP 보안만 지원 하며 신뢰할 수 있는 메시징이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-202">`WSDualHttpBinding` only supports SOAP security and requires reliable messaging.</span></span> <span data-ttu-id="05cd6-203">이 바인딩을 사용 하려면 클라이언트에 서비스에 대 한 콜백 끝점을 제공 하는 공용 URI가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-203">This binding requires that the client has a public URI that provides a callback endpoint for the service.</span></span> <span data-ttu-id="05cd6-204">이 공용 URI는 `clientBaseAddress` 특성에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-204">This is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="05cd6-205">이중 바인딩은 클라이언트의 IP 주소를 서비스에 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-205">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="05cd6-206">클라이언트는 보안을 사용 하 여 신뢰 하는 서비스에만 연결 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-206">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
 <span data-ttu-id="05cd6-207">이 바인딩을 사용하여 하나 이상의 SOAP 중간 매개자를 통해 안정적으로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-207">This binding can be used to communicate reliably through one or more SOAP intermediaries.</span></span>  
  
 <span data-ttu-id="05cd6-208">이 바인딩은 기본적으로 안정성을 위한 WS-ReliableMessaging, 메시지 보안 및 인증을 위한 WS-Security, 메시지 배달을 위한 HTTP 및 텍스트/XML 메시지 인코딩을 지원하는 런타임 스택을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd6-208">By default, this binding generates a runtime stack with WS-ReliableMessaging for reliability, WS-Security for message security and authentication, HTTP for message delivery, and a Text/XML message encoding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05cd6-209">예제</span><span class="sxs-lookup"><span data-stu-id="05cd6-209">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsDualHttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 clientBaseAddress="http://localhost:8001/client/"
                 transactionFlow="true"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="utf-16"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00" />
          <security mode="None">
            <message clientCredentialType="None"
                     negotiateServiceCredential="false"
                     algorithmSuite="Aes128" />
          </security>
        </binding>
      </wsDualHttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="05cd6-210">참조</span><span class="sxs-lookup"><span data-stu-id="05cd6-210">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>
- <xref:System.ServiceModel.Configuration.WSDualHttpBindingElement>
- [<span data-ttu-id="05cd6-211">바인딩</span><span class="sxs-lookup"><span data-stu-id="05cd6-211">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="05cd6-212">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="05cd6-212">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="05cd6-213">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="05cd6-213">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="05cd6-214">\<binding ></span><span class="sxs-lookup"><span data-stu-id="05cd6-214">\<binding></span></span>](bindings.md)
