---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 70a124fda5bc0e52e1271716f7e2166b7717b49a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933194"
---
# <a name="mtommessageencoding"></a><span data-ttu-id="d0f9a-101">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="d0f9a-101">\<mtomMessageEncoding></span></span>
<span data-ttu-id="d0f9a-102">SOAP MTOM(Message Transmission Optimization Mechanism) 기반 메시지에 사용되는 인코딩 및 메시지 버전 관리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-102">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
 <span data-ttu-id="d0f9a-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d0f9a-103">\<system.serviceModel></span></span>  
<span data-ttu-id="d0f9a-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d0f9a-104">\<bindings></span></span>  
<span data-ttu-id="d0f9a-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d0f9a-105">\<customBinding></span></span>  
<span data-ttu-id="d0f9a-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="d0f9a-106">\<binding></span></span>  
<span data-ttu-id="d0f9a-107">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="d0f9a-107">\<mtomMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0f9a-108">구문</span><span class="sxs-lookup"><span data-stu-id="d0f9a-108">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0f9a-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d0f9a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d0f9a-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0f9a-111">특성</span><span class="sxs-lookup"><span data-stu-id="d0f9a-111">Attributes</span></span>  
  
|<span data-ttu-id="d0f9a-112">특성</span><span class="sxs-lookup"><span data-stu-id="d0f9a-112">Attribute</span></span>|<span data-ttu-id="d0f9a-113">설명</span><span class="sxs-lookup"><span data-stu-id="d0f9a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d0f9a-114">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="d0f9a-114">maxBufferSize</span></span>|<span data-ttu-id="d0f9a-115">사용할 수 있는 버퍼의 최대 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-115">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="d0f9a-116">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="d0f9a-116">maxReadPoolSize</span></span>|<span data-ttu-id="d0f9a-117">새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-117">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="d0f9a-118">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-118">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="d0f9a-119">기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-119">The default is 64.</span></span>|  
|<span data-ttu-id="d0f9a-120">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="d0f9a-120">maxWritePoolSize</span></span>|<span data-ttu-id="d0f9a-121">새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-121">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="d0f9a-122">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-122">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="d0f9a-123">기본값은 16입니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-123">The default is 16.</span></span>|  
|<span data-ttu-id="d0f9a-124">messageVersion</span><span class="sxs-lookup"><span data-stu-id="d0f9a-124">messageVersion</span></span>|<span data-ttu-id="d0f9a-125">바인딩을 사용하여 보낸 메시지의 SOAP 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-125">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="d0f9a-126">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-126">Valid values are</span></span><br /><br /> <span data-ttu-id="d0f9a-127">- Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="d0f9a-127">-   Soap11Addressing1</span></span><br /><span data-ttu-id="d0f9a-128">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="d0f9a-128">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="d0f9a-129">기본값은 Soap12Addressing10입니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-129">The default is Soap12Addressing10.</span></span> <span data-ttu-id="d0f9a-130">이 특성은 <xref:System.ServiceModel.Channels.MessageVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-130">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="d0f9a-131">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="d0f9a-131">writeEncoding</span></span>|<span data-ttu-id="d0f9a-132">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-132">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="d0f9a-133">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-133">Valid values are</span></span><br /><br /> <span data-ttu-id="d0f9a-134">-   UnicodeFffeTextEncoding: 유니코드가 나 Endian 인코딩</span><span class="sxs-lookup"><span data-stu-id="d0f9a-134">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="d0f9a-135">-   Utf16TextEncoding: 유니코드 인코딩</span><span class="sxs-lookup"><span data-stu-id="d0f9a-135">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="d0f9a-136">-   Utf8TextEncoding: 8 비트 인코딩</span><span class="sxs-lookup"><span data-stu-id="d0f9a-136">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="d0f9a-137">기본값은 Utf8TextEncoding입니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-137">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="d0f9a-138">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-138">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0f9a-139">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d0f9a-139">Child Elements</span></span>  
  
|<span data-ttu-id="d0f9a-140">요소</span><span class="sxs-lookup"><span data-stu-id="d0f9a-140">Element</span></span>|<span data-ttu-id="d0f9a-141">설명</span><span class="sxs-lookup"><span data-stu-id="d0f9a-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d0f9a-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d0f9a-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="d0f9a-143">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-143">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d0f9a-144">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-144">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d0f9a-145">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d0f9a-145">Parent Elements</span></span>  
  
|<span data-ttu-id="d0f9a-146">요소</span><span class="sxs-lookup"><span data-stu-id="d0f9a-146">Element</span></span>|<span data-ttu-id="d0f9a-147">설명</span><span class="sxs-lookup"><span data-stu-id="d0f9a-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0f9a-148">\<binding></span><span class="sxs-lookup"><span data-stu-id="d0f9a-148">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="d0f9a-149">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-149">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0f9a-150">설명</span><span class="sxs-lookup"><span data-stu-id="d0f9a-150">Remarks</span></span>  
 <span data-ttu-id="d0f9a-151">인코딩은 메시지를 바이트 시퀀스로 변형하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-151">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="d0f9a-152">디코딩은 역프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-152">Decoding is the reverse process.</span></span> <span data-ttu-id="d0f9a-153">WCF (Windows Communication Foundation)에는 SOAP 메시지에 대 한 세 가지 유형의 인코딩이 있습니다. 텍스트, 이진 및 MTOM (메시지 전송 최적화 메커니즘)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-153">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="d0f9a-154">`MtomMessageEncoding` 요소는 MTOM(Message Transmission Optimization Mechanism) 인코딩을 사용하는 메시지에 사용되는 문자 인코딩, 메시지 버전 관리 및 기타 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-154">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="d0f9a-155">MTOM은 WCF 메시지의 이진 데이터를 전송하기 위한 효율적인 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-155">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="d0f9a-156">MTOM 인코더는 효율성과 상호 운용성 간의 균형을 유지하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-156">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="d0f9a-157">MTOM 인코딩은 대부분의 XML을 텍스트 형식으로 전송하지만, 대량의 이진 데이터 블록의 경우는 base64 인코딩 형식으로 변환하지 않고 있는 그대로 전송하여 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-157">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0f9a-158">예제</span><span class="sxs-lookup"><span data-stu-id="d0f9a-158">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="d0f9a-159">참고자료</span><span class="sxs-lookup"><span data-stu-id="d0f9a-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="d0f9a-160">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="d0f9a-160">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="d0f9a-161">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="d0f9a-161">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="d0f9a-162">바인딩</span><span class="sxs-lookup"><span data-stu-id="d0f9a-162">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d0f9a-163">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="d0f9a-163">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d0f9a-164">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="d0f9a-164">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="d0f9a-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d0f9a-165">\<customBinding></span></span>](custombinding.md)
