---
title: <udpBinding>
ms.date: 03/30/2017
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
ms.openlocfilehash: 84a5bc763f898b3d323a6cee468c6e22d27d85a0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229604"
---
# <a name="udpbinding"></a><span data-ttu-id="c798c-101">\<udpBinding></span><span class="sxs-lookup"><span data-stu-id="c798c-101">\<udpBinding></span></span>
<span data-ttu-id="c798c-102"><xref:System.ServiceModel.UdpBinding> 바인딩을 구성하는 데 사용되는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-102">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
 <span data-ttu-id="c798c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c798c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c798c-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c798c-104">\<bindings></span></span>  
<span data-ttu-id="c798c-105">\<udpBinding></span><span class="sxs-lookup"><span data-stu-id="c798c-105">\<udpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c798c-106">구문</span><span class="sxs-lookup"><span data-stu-id="c798c-106">Syntax</span></span>  
  
```xml  
<udpBinding>
  <binding closeTimeout="TimeSpan"
           duplicateMessageHistoryLength="Integer"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxPendingMessagesTotalSize="Integer"
           maxReceivedMessageSize="Integer"
           maxRetransmitCount="Integer"
           multicastInterfaceId="Integer"
           name="String"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           timeToLive="TimeSpan">
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</basicHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c798c-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c798c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c798c-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c798c-109">특성</span><span class="sxs-lookup"><span data-stu-id="c798c-109">Attributes</span></span>  
  
|<span data-ttu-id="c798c-110">특성</span><span class="sxs-lookup"><span data-stu-id="c798c-110">Attribute</span></span>|<span data-ttu-id="c798c-111">설명</span><span class="sxs-lookup"><span data-stu-id="c798c-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="c798c-112">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="c798c-113">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c798c-114">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-114">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="c798c-115">중복 메시지 기록 길이를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-115">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="c798c-116">채널에서 메시지를 수신하는 메시지 버퍼 관리자가 사용하도록 할당된 최대 메모리를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-116">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="c798c-117">기본값은 524288(0x80000)바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-117">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="c798c-118">이 바인딩으로 구성된 엔드포인트에 대해 메시지가 처리되는 동안 해당 메시지를 저장하는 버퍼의 최대 크기(바이트)를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-118">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="c798c-119">기본값은 65,536바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-119">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="c798c-120">수신되었으나 개별 채널 인스턴스의 입력 큐에서 아직 제거되지 않은 최대 메시지 수를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-120">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="c798c-121">이 바인딩으로 구성된 채널에서 받을 수 있는 메시지(헤더 포함)의 최대 메시지 크기(바이트)를 정의하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-121">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="c798c-122">수신자에게 너무 큰 메시지를 보낸 발신자에게는 SOAP 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-122">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="c798c-123">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-123">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="c798c-124">기본값은 65,536바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-124">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="c798c-125">메시지를 재전송하는 최대 횟수를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-125">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="c798c-126">멀티캐스트 인터페이스 ID를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-126">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="c798c-127">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-127">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="c798c-128">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-128">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="c798c-129">각 바인딩에는 서비스의 메타데이터에서 함께 바인딩을 고유하게 식별하는 `name` 및 `namespace` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-129">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="c798c-130">또한 이 이름은 동일한 형식의 바인딩 간에 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-130">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="c798c-131">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-131">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="c798c-132">기본 구성 및 이름 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 하세요. [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) 하 고 [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-132">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="c798c-133">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-133">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="c798c-134">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-134">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c798c-135">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-135">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="c798c-136">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-136">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="c798c-137">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-137">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c798c-138">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-138">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="c798c-139">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-139">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="c798c-140">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-140">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c798c-141">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-141">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="c798c-142">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-142">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="c798c-143">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-143">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c798c-144">-   BigEndianUnicode: 유니코드 BigEndian 인코딩</span><span class="sxs-lookup"><span data-stu-id="c798c-144">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="c798c-145">유니코드를 지원 합니다. 16 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-145">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="c798c-146">-   UTF8: 8 비트 인코딩</span><span class="sxs-lookup"><span data-stu-id="c798c-146">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="c798c-147">기본값은 UTF8입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-147">The default is UTF8.</span></span> <span data-ttu-id="c798c-148">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-148">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="c798c-149">바인딩에 대한 TTL(Time To Live)을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-149">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c798c-150">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c798c-150">Child Elements</span></span>  
  
|<span data-ttu-id="c798c-151">요소</span><span class="sxs-lookup"><span data-stu-id="c798c-151">Element</span></span>|<span data-ttu-id="c798c-152">설명</span><span class="sxs-lookup"><span data-stu-id="c798c-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c798c-153">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="c798c-153">\<readerQuotas></span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="c798c-154">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-154">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="c798c-155">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-155">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c798c-156">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c798c-156">Parent Elements</span></span>  
  
|<span data-ttu-id="c798c-157">요소</span><span class="sxs-lookup"><span data-stu-id="c798c-157">Element</span></span>|<span data-ttu-id="c798c-158">설명</span><span class="sxs-lookup"><span data-stu-id="c798c-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c798c-159">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c798c-159">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="c798c-160">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-160">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c798c-161">설명</span><span class="sxs-lookup"><span data-stu-id="c798c-161">Remarks</span></span>  
 <span data-ttu-id="c798c-162">UdpBinding을 사용하면 WCF 서비스가 UDP 전송을 통해 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-162">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="c798c-163">여기서 클라이언트는 서비스에 메시지를 보냅니다 응답을 예상 하지 "fire and forget" 메시지 교환을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c798c-163">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c798c-164">예제</span><span class="sxs-lookup"><span data-stu-id="c798c-164">Example</span></span>  
 <span data-ttu-id="c798c-165">다음 예제에서는 구성 방법을 보여 줍니다.는 <xref:System.ServiceModel.UdpBinding> 를 사용 하는 <`udpBinding`> 요소.</span><span class="sxs-lookup"><span data-stu-id="c798c-165">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
```xml  
<udpBinding>
  <binding  closeTimeout="00:10:00"
            duplicateMessageHistoryLength="100"
            maxBufferPoolSize="100"
            maxPendingMessagesTotalSize="100000"
            maxReceivedMessageSize="65536"
            maxRetransmitCount="10"
            multicastInterfaceId="00000"
            name="myUdpBinding"
            openTimeout="00:10:00"
            receiveTimeout="00:10:00"
            sendTimeout="00:10:00"
            textEncoding="utf-8"
            timeToLive="00:10:00">
    <readerQuotas />
  </binding>
</udpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="c798c-166">참고자료</span><span class="sxs-lookup"><span data-stu-id="c798c-166">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="c798c-167">바인딩</span><span class="sxs-lookup"><span data-stu-id="c798c-167">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="c798c-168">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="c798c-168">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c798c-169">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="c798c-169">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="c798c-170">\<binding></span><span class="sxs-lookup"><span data-stu-id="c798c-170">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
