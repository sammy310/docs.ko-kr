---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: e6e6d1907d89a09a72594a836f2192e9ad9c4290
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758290"
---
# <a name="textmessageencoding"></a><span data-ttu-id="e3aed-101">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="e3aed-101">\<textMessageEncoding></span></span>
<span data-ttu-id="e3aed-102">텍스트 기반 XML 메시지에 사용되는 문자 인코딩 및 메시지 버전 관리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="e3aed-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e3aed-103">\<system.serviceModel></span></span>  
<span data-ttu-id="e3aed-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e3aed-104">\<bindings></span></span>  
<span data-ttu-id="e3aed-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e3aed-105">\<customBinding></span></span>  
<span data-ttu-id="e3aed-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="e3aed-106">\<binding></span></span>  
<span data-ttu-id="e3aed-107">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="e3aed-107">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3aed-108">구문</span><span class="sxs-lookup"><span data-stu-id="e3aed-108">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3aed-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e3aed-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e3aed-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3aed-111">특성</span><span class="sxs-lookup"><span data-stu-id="e3aed-111">Attributes</span></span>  
  
|<span data-ttu-id="e3aed-112">특성</span><span class="sxs-lookup"><span data-stu-id="e3aed-112">Attribute</span></span>|<span data-ttu-id="e3aed-113">설명</span><span class="sxs-lookup"><span data-stu-id="e3aed-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e3aed-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="e3aed-114">maxReadPoolSize</span></span>|<span data-ttu-id="e3aed-115">새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-115">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="e3aed-116">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="e3aed-117">기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-117">The default is 64.</span></span>|  
|<span data-ttu-id="e3aed-118">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="e3aed-118">maxWritePoolSize</span></span>|<span data-ttu-id="e3aed-119">새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-119">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="e3aed-120">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="e3aed-121">기본값은 16입니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-121">The default is 16.</span></span>|  
|<span data-ttu-id="e3aed-122">messageVersion</span><span class="sxs-lookup"><span data-stu-id="e3aed-122">messageVersion</span></span>|<span data-ttu-id="e3aed-123">바인딩을 사용하여 보낸 메시지의 SOAP 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-123">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="e3aed-124">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-124">Valid values are</span></span><br /><br /> <span data-ttu-id="e3aed-125">-   Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="e3aed-125">-   Soap11Addressing10</span></span><br /><span data-ttu-id="e3aed-126">-Soap12addressing10</span><span class="sxs-lookup"><span data-stu-id="e3aed-126">-   Soap12Addressing10</span></span><br /><span data-ttu-id="e3aed-127">-   Soap11</span><span class="sxs-lookup"><span data-stu-id="e3aed-127">-   Soap11</span></span><br /><span data-ttu-id="e3aed-128">-Soap12</span><span class="sxs-lookup"><span data-stu-id="e3aed-128">-  Soap12</span></span><br /><br /><span data-ttu-id="e3aed-129">기본값은 Soap12Addressing10입니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-129">The default is Soap12Addressing10.</span></span> <span data-ttu-id="e3aed-130">이 특성은 <xref:System.ServiceModel.Channels.MessageVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-130">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="e3aed-131">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="e3aed-131">writeEncoding</span></span>|<span data-ttu-id="e3aed-132">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-132">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="e3aed-133">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-133">Valid values are</span></span><br /><br /> <span data-ttu-id="e3aed-134">-   UnicodeFffeTextEncoding: 유니코드 BigEndian 인코딩</span><span class="sxs-lookup"><span data-stu-id="e3aed-134">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="e3aed-135">-   Utf16TextEncoding: 유니코드 인코딩</span><span class="sxs-lookup"><span data-stu-id="e3aed-135">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="e3aed-136">-   Utf8TextEncoding: 8 비트 인코딩</span><span class="sxs-lookup"><span data-stu-id="e3aed-136">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="e3aed-137">기본값은 Utf8TextEncoding입니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-137">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="e3aed-138">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-138">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3aed-139">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e3aed-139">Child Elements</span></span>  
  
|<span data-ttu-id="e3aed-140">요소</span><span class="sxs-lookup"><span data-stu-id="e3aed-140">Element</span></span>|<span data-ttu-id="e3aed-141">설명</span><span class="sxs-lookup"><span data-stu-id="e3aed-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3aed-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e3aed-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="e3aed-143">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-143">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="e3aed-144">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-144">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e3aed-145">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e3aed-145">Parent Elements</span></span>  
  
|<span data-ttu-id="e3aed-146">요소</span><span class="sxs-lookup"><span data-stu-id="e3aed-146">Element</span></span>|<span data-ttu-id="e3aed-147">설명</span><span class="sxs-lookup"><span data-stu-id="e3aed-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3aed-148">\<binding></span><span class="sxs-lookup"><span data-stu-id="e3aed-148">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="e3aed-149">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-149">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3aed-150">설명</span><span class="sxs-lookup"><span data-stu-id="e3aed-150">Remarks</span></span>  
 <span data-ttu-id="e3aed-151">인코딩은 메시지를 바이트 시퀀스로 변형하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-151">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="e3aed-152">디코딩은 역프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-152">Decoding is the reverse process.</span></span> <span data-ttu-id="e3aed-153">Windows Communication Foundation (WCF)에 세 가지 유형의 SOAP 메시지에 대 한 인코딩을 포함 됩니다. 텍스트, 이진 및 (MTOM) Message Transmission Optimization Mechanism 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-153">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="e3aed-154">`textMessageEncoding` 요소로 나타낸 텍스트 인코딩은 상호 운용성이 가장 뛰어나지만 XML 메시지에 대해서는 효율성이 가장 낮은 인코더입니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-154">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="e3aed-155">텍스트 인코더는 통신 중에 텍스트 기반 메시지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-155">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="e3aed-156">이 인코더에서 생성하는 메시지는 WS-\* 기반 interop과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-156">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="e3aed-157">웹 서비스 또는 웹 서비스 클라이언트는 일반적으로 텍스트 XML을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-157">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="e3aed-158">그러나 큰 이진 데이터 블록을 텍스트 형태로 전송하는 것은 가장 비효율적인 XML 메시지 인코딩 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e3aed-158">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3aed-159">예제</span><span class="sxs-lookup"><span data-stu-id="e3aed-159">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="e3aed-160">참고자료</span><span class="sxs-lookup"><span data-stu-id="e3aed-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="e3aed-161">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="e3aed-161">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="e3aed-162">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="e3aed-162">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="e3aed-163">바인딩</span><span class="sxs-lookup"><span data-stu-id="e3aed-163">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="e3aed-164">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="e3aed-164">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e3aed-165">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="e3aed-165">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e3aed-166">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e3aed-166">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
