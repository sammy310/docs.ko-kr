---
title: <udpBinding>
ms.date: 03/30/2017
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
ms.openlocfilehash: b2ff39e1292cfaad1165e14e693acda2518477a6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559046"
---
# \<udpBinding>
<span data-ttu-id="5052c-101"><xref:System.ServiceModel.UdpBinding> 바인딩을 구성하는 데 사용되는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-101">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<udpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="5052c-102">구문</span><span class="sxs-lookup"><span data-stu-id="5052c-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5052c-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5052c-103">Attributes and Elements</span></span>  
 <span data-ttu-id="5052c-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5052c-105">특성</span><span class="sxs-lookup"><span data-stu-id="5052c-105">Attributes</span></span>  
  
|<span data-ttu-id="5052c-106">attribute</span><span class="sxs-lookup"><span data-stu-id="5052c-106">Attribute</span></span>|<span data-ttu-id="5052c-107">Description</span><span class="sxs-lookup"><span data-stu-id="5052c-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="5052c-108">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="5052c-109">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5052c-110">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-110">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="5052c-111">중복 메시지 기록 길이를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-111">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="5052c-112">채널에서 메시지를 수신하는 메시지 버퍼 관리자가 사용하도록 할당된 최대 메모리를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-112">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="5052c-113">기본값은 524288(0x80000)바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-113">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="5052c-114">이 바인딩으로 구성된 엔드포인트에 대해 메시지가 처리되는 동안 해당 메시지를 저장하는 버퍼의 최대 크기(바이트)를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-114">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="5052c-115">기본값은 65,536바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-115">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="5052c-116">수신되었으나 개별 채널 인스턴스의 입력 큐에서 아직 제거되지 않은 최대 메시지 수를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-116">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="5052c-117">이 바인딩으로 구성된 채널에서 받을 수 있는 메시지(헤더 포함)의 최대 메시지 크기(바이트)를 정의하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-117">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="5052c-118">수신자에게 너무 큰 메시지를 보낸 발신자에게는 SOAP 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-118">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="5052c-119">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-119">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="5052c-120">기본값은 65,536바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-120">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="5052c-121">메시지를 재전송하는 최대 횟수를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-121">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="5052c-122">멀티캐스트 인터페이스 ID를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-122">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="5052c-123">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-123">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="5052c-124">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-124">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="5052c-125">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-125">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="5052c-126">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5052c-126">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="5052c-127">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="5052c-128">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5052c-129">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-129">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="5052c-130">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-130">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="5052c-131">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-131">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5052c-132">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-132">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="5052c-133">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-133">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="5052c-134">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-134">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5052c-135">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-135">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="5052c-136">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-136">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="5052c-137">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5052c-138">-BigEndianUnicode: Unicode가 나 Endian 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-138">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="5052c-139">-Unicode: 16 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-139">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="5052c-140">-UTF8:8 비트 인코딩</span><span class="sxs-lookup"><span data-stu-id="5052c-140">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="5052c-141">기본값은 UTF8입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-141">The default is UTF8.</span></span> <span data-ttu-id="5052c-142">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-142">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="5052c-143">바인딩에 대한 TTL(Time To Live)을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-143">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5052c-144">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5052c-144">Child Elements</span></span>  
  
|<span data-ttu-id="5052c-145">요소</span><span class="sxs-lookup"><span data-stu-id="5052c-145">Element</span></span>|<span data-ttu-id="5052c-146">Description</span><span class="sxs-lookup"><span data-stu-id="5052c-146">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="5052c-147">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-147">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="5052c-148">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-148">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5052c-149">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5052c-149">Parent Elements</span></span>  
  
|<span data-ttu-id="5052c-150">요소</span><span class="sxs-lookup"><span data-stu-id="5052c-150">Element</span></span>|<span data-ttu-id="5052c-151">Description</span><span class="sxs-lookup"><span data-stu-id="5052c-151">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="5052c-152">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-152">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5052c-153">설명</span><span class="sxs-lookup"><span data-stu-id="5052c-153">Remarks</span></span>  
 <span data-ttu-id="5052c-154">UdpBinding을 사용하면 WCF 서비스가 UDP 전송을 통해 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-154">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="5052c-155">클라이언트는 서비스에 메시지를 보내고 응답을 받지 않을 것으로 예상 하는 "화재 및 잊은" 메시지 교환을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5052c-155">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5052c-156">예제</span><span class="sxs-lookup"><span data-stu-id="5052c-156">Example</span></span>  
 <span data-ttu-id="5052c-157">다음 예제에서는 <xref:System.ServiceModel.UdpBinding> <> 요소를 사용 하 여를 구성 하는 방법을 보여 줍니다 `udpBinding` .</span><span class="sxs-lookup"><span data-stu-id="5052c-157">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5052c-158">참조</span><span class="sxs-lookup"><span data-stu-id="5052c-158">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="5052c-159">바인딩</span><span class="sxs-lookup"><span data-stu-id="5052c-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5052c-160">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="5052c-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5052c-161">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="5052c-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
