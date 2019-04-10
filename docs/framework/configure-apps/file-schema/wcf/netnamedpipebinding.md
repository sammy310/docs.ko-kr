---
title: <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 00a8580b-face-47a4-838d-b9fed48e72df
ms.openlocfilehash: dc1af462222920c7b3c6b66c3822e7b2b326b244
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169827"
---
# <a name="netnamedpipebinding"></a><span data-ttu-id="8d1d6-101">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="8d1d6-101">\<netNamedPipeBinding></span></span>
<span data-ttu-id="8d1d6-102">프로세스 간 시스템 통신에 적합한, 안전하고 신뢰할 수 있는 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-102">Defines a binding that is secure, reliable, optimized for on-machine cross process communication.</span></span> <span data-ttu-id="8d1d6-103">기본적으로 이 바인딩에서는 안정성을 위한 WS-ReliableMessaging, 전송 보안을 위한 전송 보안, 메시지 배달을 위한 명명된 파이프 및 이진 메시지 인코딩을 지원하는 런타임 통신 스택을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-103">By default, it generates a runtime communication stack with WS-ReliableMessaging for reliability, transport security for transfer security, named pipes for message delivery, and binary message encoding.</span></span>  
  
 <span data-ttu-id="8d1d6-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8d1d6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8d1d6-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8d1d6-105">\<bindings></span></span>  
<span data-ttu-id="8d1d6-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="8d1d6-106">\<netNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d1d6-107">구문</span><span class="sxs-lookup"><span data-stu-id="8d1d6-107">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxConnections="Integer"
           maxReceivedMessageSize="Integer"
           name="String"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transactionFlow="Boolean"
           transactionProtocol="OleTransactions/WS-AtomicTransactionOctober2004"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d1d6-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8d1d6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8d1d6-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d1d6-110">특성</span><span class="sxs-lookup"><span data-stu-id="8d1d6-110">Attributes</span></span>  
  
|<span data-ttu-id="8d1d6-111">특성</span><span class="sxs-lookup"><span data-stu-id="8d1d6-111">Attribute</span></span>|<span data-ttu-id="8d1d6-112">설명</span><span class="sxs-lookup"><span data-stu-id="8d1d6-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8d1d6-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="8d1d6-113">closeTimeout</span></span>|<span data-ttu-id="8d1d6-114">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="8d1d6-115">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8d1d6-116">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-116">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="8d1d6-117">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="8d1d6-117">hostNameComparisonMode</span></span>|<span data-ttu-id="8d1d6-118">URI 구문 분석에 사용되는 HTTP 호스트 이름 비교 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-118">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="8d1d6-119">이 특성은 <xref:System.ServiceModel.HostNameComparisonMode> 형식이며 URI에 대해 비교할 때 호스트 이름이 서비스에 연결하는 데 사용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-119">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="8d1d6-120">기본값은 <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>이며 이 값은 비교 시 호스트 이름을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-120">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="8d1d6-121">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="8d1d6-121">maxBufferPoolSize</span></span>|<span data-ttu-id="8d1d6-122">이 바인딩의 최대 버퍼 풀 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-122">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="8d1d6-123">기본값은 524,288바이트(512 \* 1024)입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-123">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="8d1d6-124">WCF(Windows Communication Foundation)의 많은 부분에서 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-124">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="8d1d6-125">버퍼를 사용할 때마다 만들고 삭제하면 비용이 많이 들며, 버퍼에 대한 가비지 수집 역시 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-125">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="8d1d6-126">버퍼 풀이 있으면 이 풀로부터 버퍼를 가져와 사용한 다음 다시 풀로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-126">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="8d1d6-127">따라서 버퍼를 만들고 삭제하는 데 오버헤드를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-127">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="8d1d6-128">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="8d1d6-128">maxBufferSize</span></span>|<span data-ttu-id="8d1d6-129">메시지를 메모리에 저장하는 데 사용되는 버퍼의 최대 크기(바이트)를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-129">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span> <span data-ttu-id="8d1d6-130">버퍼가 꽉 차면 초과 데이터는 버퍼에 공간이 생길 때까지 내부 소켓에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-130">If the buffer is full, excess data remains in the underlying socket until the buffer has room again.</span></span> <span data-ttu-id="8d1d6-131">이 값은 `maxReceivedMessageSize` 특성보다 작을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-131">This value cannot be less than `maxReceivedMessageSize` attribute.</span></span> <span data-ttu-id="8d1d6-132">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-132">The default is 65536.</span></span> <span data-ttu-id="8d1d6-133">자세한 내용은 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-133">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|<span data-ttu-id="8d1d6-134">maxConnections</span><span class="sxs-lookup"><span data-stu-id="8d1d6-134">maxConnections</span></span>|<span data-ttu-id="8d1d6-135">서비스에서 생성하고 수락하는 최대 아웃바운드 및 인바운드 연결 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-135">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="8d1d6-136">들어오는 연결과 나가는 연결 수는 이 특성에서 지정한 별도의 제한에 따라 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-136">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="8d1d6-137">이 제한을 초과하는 인바운드 연결은 연결 수가 제한 아래로 내려갈 때까지 큐에 대기됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-137">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="8d1d6-138">이 한도를 초과하는 아웃바운드 연결은 연결 수가 한도 아래로 내려갈 때까지 큐에 대기됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-138">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="8d1d6-139">기본값은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-139">The default is 10.</span></span>|  
|<span data-ttu-id="8d1d6-140">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="8d1d6-140">maxReceivedMessageSize</span></span>|<span data-ttu-id="8d1d6-141">헤더를 비롯하여 이 바인딩으로 구성된 채널에서 받을 수 있는 최대 메시지 크기(바이트)를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-141">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="8d1d6-142">이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-142">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="8d1d6-143">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-143">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="8d1d6-144">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-144">The default is 65536.</span></span>|  
|<span data-ttu-id="8d1d6-145">name</span><span class="sxs-lookup"><span data-stu-id="8d1d6-145">name</span></span>|<span data-ttu-id="8d1d6-146">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-146">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="8d1d6-147">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-147">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="8d1d6-148">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-148">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="8d1d6-149">기본 구성 및 이름 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 하세요. [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) 하 고 [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-149">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="8d1d6-150">openTimeout</span><span class="sxs-lookup"><span data-stu-id="8d1d6-150">openTimeout</span></span>|<span data-ttu-id="8d1d6-151">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="8d1d6-152">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8d1d6-153">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-153">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="8d1d6-154">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="8d1d6-154">receiveTimeout</span></span>|<span data-ttu-id="8d1d6-155">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-155">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="8d1d6-156">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-156">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8d1d6-157">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-157">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="8d1d6-158">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="8d1d6-158">sendTimeout</span></span>|<span data-ttu-id="8d1d6-159">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="8d1d6-160">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8d1d6-161">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-161">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="8d1d6-162">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="8d1d6-162">transactionFlow</span></span>|<span data-ttu-id="8d1d6-163">바인딩에서 WS-Transactions 이동을 지원할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-163">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="8d1d6-164">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-164">The default is `false`.</span></span>|  
|<span data-ttu-id="8d1d6-165">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="8d1d6-165">transactionProtocol</span></span>|<span data-ttu-id="8d1d6-166">이 바인딩과 함께 사용되는 트랜잭션 프로토콜을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-166">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="8d1d6-167">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-167">Valid values are</span></span><br /><br /> <span data-ttu-id="8d1d6-168">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="8d1d6-168">-   OleTransactions</span></span><br /><span data-ttu-id="8d1d6-169">-   WS-AtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="8d1d6-169">-   WS-AtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="8d1d6-170">기본값은 OleTransactions입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-170">The default is OleTransactions.</span></span> <span data-ttu-id="8d1d6-171">이 특성은 <xref:System.ServiceModel.TransactionProtocol> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-171">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|<span data-ttu-id="8d1d6-172">transferMode</span><span class="sxs-lookup"><span data-stu-id="8d1d6-172">transferMode</span></span>|<span data-ttu-id="8d1d6-173">메시지가 버퍼링되거나 스트리밍되는지 또는 요청이나 응답인지 지정하는 <xref:System.ServiceModel.TransferMode> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-173">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8d1d6-174">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8d1d6-174">Child Elements</span></span>  
  
|<span data-ttu-id="8d1d6-175">요소</span><span class="sxs-lookup"><span data-stu-id="8d1d6-175">Element</span></span>|<span data-ttu-id="8d1d6-176">설명</span><span class="sxs-lookup"><span data-stu-id="8d1d6-176">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d1d6-177">\<security></span><span class="sxs-lookup"><span data-stu-id="8d1d6-177">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="8d1d6-178">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-178">Defines the security settings for the binding.</span></span> <span data-ttu-id="8d1d6-179">이 요소는 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-179">This element is of type <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>.</span></span>|  
|[<span data-ttu-id="8d1d6-180">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="8d1d6-180">\<readerQuotas></span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="8d1d6-181">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-181">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="8d1d6-182">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-182">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8d1d6-183">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8d1d6-183">Parent Elements</span></span>  
  
|<span data-ttu-id="8d1d6-184">요소</span><span class="sxs-lookup"><span data-stu-id="8d1d6-184">Element</span></span>|<span data-ttu-id="8d1d6-185">설명</span><span class="sxs-lookup"><span data-stu-id="8d1d6-185">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d1d6-186">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8d1d6-186">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="8d1d6-187">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-187">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d1d6-188">설명</span><span class="sxs-lookup"><span data-stu-id="8d1d6-188">Remarks</span></span>  
 <span data-ttu-id="8d1d6-189">`NetNamedPipeBinding`에서는 기본적으로 런타임 통신 스택을 생성하며, 이 스택은 전송 보안, 메시지 배달을 위한 명명된 파이프 및 이진 메시지 인코딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-189">The `NetNamedPipeBinding` generates a run-time communication stack by default, which uses transport security, named pipes for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="8d1d6-190">이 바인딩은 시스템 통신을 위한 적절한 WCF(Windows Communication Foundation) 시스템 제공 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-190">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for on-machine communication.</span></span> <span data-ttu-id="8d1d6-191">트랜잭션도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-191">It also supports transactions.</span></span>  
  
 <span data-ttu-id="8d1d6-192">`NetNamedPipeBinding`의 기본 구성은 `NetTcpBinding`에서 제공하는 구성과 비슷하지만, WCF 구현이 시스템에서만 사용되므로 노출되는 기능이 더 적기 때문에 더 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-192">The default configuration for the `NetNamedPipeBinding` is similar to the configuration provided by the `NetTcpBinding`, but it is simpler because the WCF implementation is only meant for on-machine use and consequently there are fewer exposed features.</span></span> <span data-ttu-id="8d1d6-193">가장 두드러진 차이점은 `securityMode` 설정에서는 `None` 및 `Transport` 옵션만 제공한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-193">The most notable difference is that the `securityMode` setting only offers the `None` and `Transport` options.</span></span> <span data-ttu-id="8d1d6-194">SOAP 보안 지원은 포함된 옵션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-194">SOAP security support is not an included option.</span></span> <span data-ttu-id="8d1d6-195">보안 동작은 선택적 `securityMode` 특성을 사용하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-195">The security behavior is configurable using the optional `securityMode` attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d1d6-196">예제</span><span class="sxs-lookup"><span data-stu-id="8d1d6-196">Example</span></span>  
 <span data-ttu-id="8d1d6-197">다음은 netNamedPipeBinding 바인딩의 예로, 동일한 시스템에서 프로세스 간 통신을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-197">The following example demonstrates the netNamedPipeBinding binding, which provides cross-process communication on the same machine.</span></span> <span data-ttu-id="8d1d6-198">이름이 지정된 파이프는 시스템 간에 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-198">Named pipes do not work across machines.</span></span>  
  
 <span data-ttu-id="8d1d6-199">클라이언트 및 서비스 구성 파일에 바인딩이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-199">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="8d1d6-200">바인딩 형식은 `binding` 요소의 `<endpoint>` 특성에서 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-200">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="8d1d6-201">netNamedPipeBinding 바인딩을 구성하고 설정 중 일부를 변경하려면 바인딩 구성을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-201">If you want to configure the netNamedPipeBinding binding and change some of its settings, you must define a binding configuration.</span></span> <span data-ttu-id="8d1d6-202">엔드포인트는 `bindingConfiguration` 특성이 있는 이름으로 바인딩 구성을 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-202">The endpoint must reference the binding configuration by name with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="8d1d6-203">이 예제에서는 바인딩 구성 이름이 Binding1로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d1d6-203">In this example, the binding configuration is named Binding1.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <host>
          <baseAddresses>
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
          </baseAddresses>
        </host>
        <!-- this endpoint is exposed at the base address provided by host: net.pipe://localhost/ServiceModelSamples/service  -->
        <endpoint address="net.pipe://localhost/ServiceModelSamples/service"
                  binding="netNamedPipeBinding"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <bindings>
      <netNamedPipeBinding>
        <binding closeTimeout="00:01:00"
                 openTimeout="00:01:00"
                 receiveTimeout="00:10:00"
                 sendTimeout="00:01:00"
                 transactionFlow="false"
                 transferMode="Buffered"
                 transactionProtocol="OleTransactions"
                 hostNameComparisonMode="StrongWildcard"
                 maxBufferPoolSize="524288"
                 maxBufferSize="65536"
                 maxConnections="10"
                 maxReceivedMessageSize="65536">
          <security mode="Transport">
            <transport protectionLevel="EncryptAndSign" />
          </security>
        </binding>
      </netNamedPipeBinding>
    </bindings>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="8d1d6-204">참고자료</span><span class="sxs-lookup"><span data-stu-id="8d1d6-204">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>
- <xref:System.ServiceModel.NetNamedPipeBinding>
- [<span data-ttu-id="8d1d6-205">\<binding></span><span class="sxs-lookup"><span data-stu-id="8d1d6-205">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="8d1d6-206">바인딩</span><span class="sxs-lookup"><span data-stu-id="8d1d6-206">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="8d1d6-207">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="8d1d6-207">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8d1d6-208">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="8d1d6-208">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
