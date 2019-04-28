---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: e02ed6ef79fcf52bbe9c33bd9b36a14113e19d1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673448"
---
# <a name="binarymessageencoding"></a><span data-ttu-id="434b4-101">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="434b4-101">\<binaryMessageEncoding></span></span>
<span data-ttu-id="434b4-102">통신 중에 WCF(Windows Communication Foundation) 메시지를 이진 형식으로 인코딩하는 이진 메시지 인코더를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-102">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="434b4-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="434b4-103">\<system.serviceModel></span></span>  
<span data-ttu-id="434b4-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="434b4-104">\<bindings></span></span>  
<span data-ttu-id="434b4-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="434b4-105">\<customBinding></span></span>  
<span data-ttu-id="434b4-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="434b4-106">\<binding></span></span>  
<span data-ttu-id="434b4-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="434b4-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="434b4-108">구문</span><span class="sxs-lookup"><span data-stu-id="434b4-108">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="434b4-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="434b4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="434b4-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="434b4-111">특성</span><span class="sxs-lookup"><span data-stu-id="434b4-111">Attributes</span></span>  
  
|<span data-ttu-id="434b4-112">특성</span><span class="sxs-lookup"><span data-stu-id="434b4-112">Attribute</span></span>|<span data-ttu-id="434b4-113">설명</span><span class="sxs-lookup"><span data-stu-id="434b4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="434b4-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="434b4-114">maxReadPoolSize</span></span>|<span data-ttu-id="434b4-115">새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-115">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="434b4-116">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="434b4-117">기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-117">The default is 64.</span></span>|  
|<span data-ttu-id="434b4-118">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="434b4-118">maxSessionSize</span></span>|<span data-ttu-id="434b4-119">인코딩에 사용되는 버퍼의 크기(바이트)를 설정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-119">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="434b4-120">버퍼가 크면 작업 집합의 크기 문제가 생기지만 인코딩 속도가 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-120">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="434b4-121">기본값은 2048입니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-121">The default is 2048.</span></span>|  
|<span data-ttu-id="434b4-122">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="434b4-122">maxWritePoolSize</span></span>|<span data-ttu-id="434b4-123">새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-123">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="434b4-124">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-124">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="434b4-125">기본값은 16입니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-125">The default is 16.</span></span>|  
|<span data-ttu-id="434b4-126">messageVersion</span><span class="sxs-lookup"><span data-stu-id="434b4-126">messageVersion</span></span>|<span data-ttu-id="434b4-127">사용되거나 필요한 SOAP 메시지 및 WS-Addressing 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-127">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="434b4-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="434b4-128">Child Elements</span></span>  
  
|<span data-ttu-id="434b4-129">요소</span><span class="sxs-lookup"><span data-stu-id="434b4-129">Element</span></span>|<span data-ttu-id="434b4-130">설명</span><span class="sxs-lookup"><span data-stu-id="434b4-130">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="434b4-131">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="434b4-131">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="434b4-132">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-132">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="434b4-133">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-133">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="434b4-134">부모 요소</span><span class="sxs-lookup"><span data-stu-id="434b4-134">Parent Elements</span></span>  
  
|<span data-ttu-id="434b4-135">요소</span><span class="sxs-lookup"><span data-stu-id="434b4-135">Element</span></span>|<span data-ttu-id="434b4-136">설명</span><span class="sxs-lookup"><span data-stu-id="434b4-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="434b4-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="434b4-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="434b4-138">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-138">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="434b4-139">설명</span><span class="sxs-lookup"><span data-stu-id="434b4-139">Remarks</span></span>  
 <span data-ttu-id="434b4-140">인코딩은 메시지를 바이트 시퀀스로 변형하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-140">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="434b4-141">디코딩은 역프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-141">Decoding is the reverse process.</span></span> <span data-ttu-id="434b4-142">Windows Communication Foundation (WCF)에 세 가지 유형의 SOAP 메시지에 대 한 인코딩을 포함 됩니다. 텍스트, 이진 및 (MTOM) Message Transmission Optimization Mechanism 합니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-142">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="434b4-143">`binaryMessageEncoding` 요소는 XML에 대한 .NET 이진 형식을 지정하며, 사용할 SOAP 및 WS-Addressing 버전과 문자 인코딩을 지정하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-143">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="434b4-144">이진 메시지 인코더는 통신 중에 WCF(Windows Communication Foundation) 메시지를 이진 형식으로 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-144">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="434b4-145">이 인코딩은 전송 속도가 매우 빠르지만 WS-\* 표준과 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="434b4-145">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="434b4-146">예제</span><span class="sxs-lookup"><span data-stu-id="434b4-146">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="434b4-147">참고자료</span><span class="sxs-lookup"><span data-stu-id="434b4-147">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="434b4-148">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="434b4-148">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="434b4-149">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="434b4-149">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="434b4-150">바인딩</span><span class="sxs-lookup"><span data-stu-id="434b4-150">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="434b4-151">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="434b4-151">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="434b4-152">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="434b4-152">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="434b4-153">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="434b4-153">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
