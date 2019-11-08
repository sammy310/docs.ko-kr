---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: afe0479d9cbf6d754b309c18e23d3a479870177c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739077"
---
# <a name="binarymessageencoding"></a><span data-ttu-id="d5b55-101">binaryMessageEncoding \<</span><span class="sxs-lookup"><span data-stu-id="d5b55-101">\<binaryMessageEncoding></span></span>
<span data-ttu-id="d5b55-102">통신 중에 WCF(Windows Communication Foundation) 메시지를 이진 형식으로 인코딩하는 이진 메시지 인코더를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-102">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
<span data-ttu-id="d5b55-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d5b55-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d5b55-104">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="d5b55-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d5b55-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="d5b55-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="d5b55-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="d5b55-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="d5b55-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="d5b55-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="d5b55-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<binaryMessageEncoding >**</span><span class="sxs-lookup"><span data-stu-id="d5b55-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binaryMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5b55-109">구문</span><span class="sxs-lookup"><span data-stu-id="d5b55-109">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5b55-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d5b55-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d5b55-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5b55-112">특성</span><span class="sxs-lookup"><span data-stu-id="d5b55-112">Attributes</span></span>  
  
|<span data-ttu-id="d5b55-113">특성</span><span class="sxs-lookup"><span data-stu-id="d5b55-113">Attribute</span></span>|<span data-ttu-id="d5b55-114">설명</span><span class="sxs-lookup"><span data-stu-id="d5b55-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d5b55-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="d5b55-115">maxReadPoolSize</span></span>|<span data-ttu-id="d5b55-116">새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="d5b55-117">더 큰 풀 크기를 사용 하면 더 큰 작업 집합의 비용으로 더 큰 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="d5b55-118">기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-118">The default is 64.</span></span>|  
|<span data-ttu-id="d5b55-119">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="d5b55-119">maxSessionSize</span></span>|<span data-ttu-id="d5b55-120">인코딩에 사용되는 버퍼의 크기(바이트)를 설정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-120">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="d5b55-121">버퍼가 클수록 작업 집합의 크기에 따라 인코딩 속도가 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-121">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="d5b55-122">기본값은 2048입니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-122">The default is 2048.</span></span>|  
|<span data-ttu-id="d5b55-123">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="d5b55-123">maxWritePoolSize</span></span>|<span data-ttu-id="d5b55-124">새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-124">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="d5b55-125">더 큰 풀 크기를 사용 하면 더 큰 작업 집합의 비용으로 더 큰 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-125">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="d5b55-126">기본값은 16입니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-126">The default is 16.</span></span>|  
|<span data-ttu-id="d5b55-127">messageVersion</span><span class="sxs-lookup"><span data-stu-id="d5b55-127">messageVersion</span></span>|<span data-ttu-id="d5b55-128">사용되거나 필요한 SOAP 메시지 및 WS-Addressing 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-128">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5b55-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d5b55-129">Child Elements</span></span>  
  
|<span data-ttu-id="d5b55-130">요소</span><span class="sxs-lookup"><span data-stu-id="d5b55-130">Element</span></span>|<span data-ttu-id="d5b55-131">설명</span><span class="sxs-lookup"><span data-stu-id="d5b55-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d5b55-132">[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d5b55-132">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="d5b55-133">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d5b55-134">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d5b55-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d5b55-135">Parent Elements</span></span>  
  
|<span data-ttu-id="d5b55-136">요소</span><span class="sxs-lookup"><span data-stu-id="d5b55-136">Element</span></span>|<span data-ttu-id="d5b55-137">설명</span><span class="sxs-lookup"><span data-stu-id="d5b55-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5b55-138">\<binding ></span><span class="sxs-lookup"><span data-stu-id="d5b55-138">\<binding></span></span>](bindings.md)|<span data-ttu-id="d5b55-139">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5b55-140">주의</span><span class="sxs-lookup"><span data-stu-id="d5b55-140">Remarks</span></span>  
 <span data-ttu-id="d5b55-141">인코딩은 메시지를 바이트 시퀀스로 변형하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="d5b55-142">디코딩은 역프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-142">Decoding is the reverse process.</span></span> <span data-ttu-id="d5b55-143">WCF (Windows Communication Foundation)는 SOAP 메시지에 대해 텍스트, 이진 및 MTOM (메시지 전송 최적화 메커니즘)의 세 가지 인코딩 유형을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-143">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="d5b55-144">`binaryMessageEncoding` 요소는 XML에 대한 .NET 이진 형식을 지정하며, 사용할 SOAP 및 WS-Addressing 버전과 문자 인코딩을 지정하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-144">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="d5b55-145">이진 메시지 인코더는 통신 중에 WCF(Windows Communication Foundation) 메시지를 이진 형식으로 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-145">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="d5b55-146">이 인코딩은 메시지를 매우 빠르게 전송 하지만 WS-\* 표준을 기반으로 하는 상호 운용성이 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5b55-146">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5b55-147">예제</span><span class="sxs-lookup"><span data-stu-id="d5b55-147">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="d5b55-148">참조</span><span class="sxs-lookup"><span data-stu-id="d5b55-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="d5b55-149">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="d5b55-149">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="d5b55-150">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="d5b55-150">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="d5b55-151">바인딩</span><span class="sxs-lookup"><span data-stu-id="d5b55-151">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d5b55-152">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="d5b55-152">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d5b55-153">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="d5b55-153">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="d5b55-154">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d5b55-154">\<customBinding></span></span>](custombinding.md)
