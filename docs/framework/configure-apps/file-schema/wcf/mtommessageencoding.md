---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: cffde19c8fd06836eaaedb5c4fc8687b97ae0afe
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556182"
---
# \<mtomMessageEncoding>
<span data-ttu-id="703ef-101">SOAP MTOM(Message Transmission Optimization Mechanism) 기반 메시지에 사용되는 인코딩 및 메시지 버전 관리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-101">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mtomMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="703ef-102">구문</span><span class="sxs-lookup"><span data-stu-id="703ef-102">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="703ef-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="703ef-103">Attributes and Elements</span></span>  
 <span data-ttu-id="703ef-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="703ef-105">특성</span><span class="sxs-lookup"><span data-stu-id="703ef-105">Attributes</span></span>  
  
|<span data-ttu-id="703ef-106">attribute</span><span class="sxs-lookup"><span data-stu-id="703ef-106">Attribute</span></span>|<span data-ttu-id="703ef-107">Description</span><span class="sxs-lookup"><span data-stu-id="703ef-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="703ef-108">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="703ef-108">maxBufferSize</span></span>|<span data-ttu-id="703ef-109">사용할 수 있는 버퍼의 최대 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-109">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="703ef-110">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="703ef-110">maxReadPoolSize</span></span>|<span data-ttu-id="703ef-111">새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-111">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="703ef-112">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-112">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="703ef-113">기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-113">The default is 64.</span></span>|  
|<span data-ttu-id="703ef-114">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="703ef-114">maxWritePoolSize</span></span>|<span data-ttu-id="703ef-115">새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-115">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="703ef-116">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="703ef-117">기본값은 16입니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-117">The default is 16.</span></span>|  
|<span data-ttu-id="703ef-118">messageVersion</span><span class="sxs-lookup"><span data-stu-id="703ef-118">messageVersion</span></span>|<span data-ttu-id="703ef-119">바인딩을 사용하여 보낸 메시지의 SOAP 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-119">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="703ef-120">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-120">Valid values are</span></span><br /><br /> <span data-ttu-id="703ef-121">- Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="703ef-121">-   Soap11Addressing1</span></span><br /><span data-ttu-id="703ef-122">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="703ef-122">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="703ef-123">기본값은 Soap12Addressing10입니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-123">The default is Soap12Addressing10.</span></span> <span data-ttu-id="703ef-124">이 특성은 <xref:System.ServiceModel.Channels.MessageVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-124">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="703ef-125">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="703ef-125">writeEncoding</span></span>|<span data-ttu-id="703ef-126">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-126">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="703ef-127">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-127">Valid values are</span></span><br /><br /> <span data-ttu-id="703ef-128">-UnicodeFffeTextEncoding: Unicode 이상 Endian encoding</span><span class="sxs-lookup"><span data-stu-id="703ef-128">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="703ef-129">-Utf16TextEncoding: 유니코드 인코딩</span><span class="sxs-lookup"><span data-stu-id="703ef-129">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="703ef-130">-Utf8TextEncoding: 8 비트 인코딩</span><span class="sxs-lookup"><span data-stu-id="703ef-130">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="703ef-131">기본값은 Utf8TextEncoding입니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-131">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="703ef-132">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-132">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="703ef-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="703ef-133">Child Elements</span></span>  
  
|<span data-ttu-id="703ef-134">요소</span><span class="sxs-lookup"><span data-stu-id="703ef-134">Element</span></span>|<span data-ttu-id="703ef-135">Description</span><span class="sxs-lookup"><span data-stu-id="703ef-135">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="703ef-136">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-136">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="703ef-137">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-137">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="703ef-138">부모 요소</span><span class="sxs-lookup"><span data-stu-id="703ef-138">Parent Elements</span></span>  
  
|<span data-ttu-id="703ef-139">요소</span><span class="sxs-lookup"><span data-stu-id="703ef-139">Element</span></span>|<span data-ttu-id="703ef-140">Description</span><span class="sxs-lookup"><span data-stu-id="703ef-140">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="703ef-141">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-141">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="703ef-142">설명</span><span class="sxs-lookup"><span data-stu-id="703ef-142">Remarks</span></span>  
 <span data-ttu-id="703ef-143">인코딩은 메시지를 바이트 시퀀스로 변형하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-143">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="703ef-144">디코딩은 역프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-144">Decoding is the reverse process.</span></span> <span data-ttu-id="703ef-145">WCF (Windows Communication Foundation)는 SOAP 메시지에 대해 텍스트, 이진 및 MTOM (메시지 전송 최적화 메커니즘)의 세 가지 인코딩 유형을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-145">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="703ef-146">`MtomMessageEncoding` 요소는 MTOM(Message Transmission Optimization Mechanism) 인코딩을 사용하는 메시지에 사용되는 문자 인코딩, 메시지 버전 관리 및 기타 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-146">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="703ef-147">MTOM은 WCF 메시지의 이진 데이터를 전송하기 위한 효율적인 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-147">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="703ef-148">MTOM 인코더는 효율성과 상호 운용성 간의 균형을 유지 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-148">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="703ef-149">MTOM 인코딩은 대부분의 XML을 텍스트 형식으로 전송 하지만, base64 인코딩 형식으로 변환 하지 않고 있는 그대로 전송 하 여 큰 이진 데이터 블록을 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="703ef-149">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="703ef-150">예제</span><span class="sxs-lookup"><span data-stu-id="703ef-150">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="703ef-151">참조</span><span class="sxs-lookup"><span data-stu-id="703ef-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="703ef-152">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="703ef-152">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="703ef-153">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="703ef-153">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="703ef-154">바인딩</span><span class="sxs-lookup"><span data-stu-id="703ef-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="703ef-155">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="703ef-155">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="703ef-156">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="703ef-156">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
