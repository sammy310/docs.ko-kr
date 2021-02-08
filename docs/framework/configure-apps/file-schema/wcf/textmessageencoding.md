---
description: 다음에 대해 자세히 알아보세요. <textMessageEncoding>
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: a8c7820b2e22152850d6d21c5091e328feb7a9f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786605"
---
# \<textMessageEncoding>

<span data-ttu-id="2becf-102">텍스트 기반 XML 메시지에 사용되는 문자 인코딩 및 메시지 버전 관리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<textMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="2becf-103">구문</span><span class="sxs-lookup"><span data-stu-id="2becf-103">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2becf-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2becf-104">Attributes and Elements</span></span>  

 <span data-ttu-id="2becf-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2becf-106">특성</span><span class="sxs-lookup"><span data-stu-id="2becf-106">Attributes</span></span>  
  
|<span data-ttu-id="2becf-107">attribute</span><span class="sxs-lookup"><span data-stu-id="2becf-107">Attribute</span></span>|<span data-ttu-id="2becf-108">설명</span><span class="sxs-lookup"><span data-stu-id="2becf-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2becf-109">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="2becf-109">maxReadPoolSize</span></span>|<span data-ttu-id="2becf-110">새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-110">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="2becf-111">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-111">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="2becf-112">기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-112">The default is 64.</span></span>|  
|<span data-ttu-id="2becf-113">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="2becf-113">maxWritePoolSize</span></span>|<span data-ttu-id="2becf-114">새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-114">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="2becf-115">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-115">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="2becf-116">기본값은 16입니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-116">The default is 16.</span></span>|  
|<span data-ttu-id="2becf-117">messageVersion</span><span class="sxs-lookup"><span data-stu-id="2becf-117">messageVersion</span></span>|<span data-ttu-id="2becf-118">바인딩을 사용하여 보낸 메시지의 SOAP 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-118">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="2becf-119">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-119">Valid values are</span></span><br /><br /> <span data-ttu-id="2becf-120">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="2becf-120">-   Soap11Addressing10</span></span><br /><span data-ttu-id="2becf-121">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="2becf-121">-   Soap12Addressing10</span></span><br /><span data-ttu-id="2becf-122">- Soap11</span><span class="sxs-lookup"><span data-stu-id="2becf-122">-   Soap11</span></span><br /><span data-ttu-id="2becf-123">- Soap12</span><span class="sxs-lookup"><span data-stu-id="2becf-123">-  Soap12</span></span><br /><br /><span data-ttu-id="2becf-124">기본값은 Soap12Addressing10입니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-124">The default is Soap12Addressing10.</span></span> <span data-ttu-id="2becf-125">이 특성은 <xref:System.ServiceModel.Channels.MessageVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-125">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="2becf-126">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="2becf-126">writeEncoding</span></span>|<span data-ttu-id="2becf-127">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-127">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="2becf-128">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-128">Valid values are</span></span><br /><br /> <span data-ttu-id="2becf-129">-UnicodeFffeTextEncoding: Unicode 이상 Endian encoding</span><span class="sxs-lookup"><span data-stu-id="2becf-129">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="2becf-130">-Utf16TextEncoding: 유니코드 인코딩</span><span class="sxs-lookup"><span data-stu-id="2becf-130">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="2becf-131">-Utf8TextEncoding: 8 비트 인코딩</span><span class="sxs-lookup"><span data-stu-id="2becf-131">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="2becf-132">기본값은 Utf8TextEncoding입니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-132">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="2becf-133">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-133">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2becf-134">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2becf-134">Child Elements</span></span>  
  
|<span data-ttu-id="2becf-135">요소</span><span class="sxs-lookup"><span data-stu-id="2becf-135">Element</span></span>|<span data-ttu-id="2becf-136">설명</span><span class="sxs-lookup"><span data-stu-id="2becf-136">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="2becf-137">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-137">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="2becf-138">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-138">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2becf-139">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2becf-139">Parent Elements</span></span>  
  
|<span data-ttu-id="2becf-140">요소</span><span class="sxs-lookup"><span data-stu-id="2becf-140">Element</span></span>|<span data-ttu-id="2becf-141">설명</span><span class="sxs-lookup"><span data-stu-id="2becf-141">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="2becf-142">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-142">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2becf-143">설명</span><span class="sxs-lookup"><span data-stu-id="2becf-143">Remarks</span></span>  

 <span data-ttu-id="2becf-144">인코딩은 메시지를 바이트 시퀀스로 변형하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-144">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="2becf-145">디코딩은 역프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-145">Decoding is the reverse process.</span></span> <span data-ttu-id="2becf-146">WCF (Windows Communication Foundation)는 SOAP 메시지에 대해 텍스트, 이진 및 MTOM (메시지 전송 최적화 메커니즘)의 세 가지 인코딩 유형을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-146">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="2becf-147">`textMessageEncoding` 요소로 나타낸 텍스트 인코딩은 상호 운용성이 가장 뛰어나지만 XML 메시지에 대해서는 효율성이 가장 낮은 인코더입니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-147">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="2becf-148">텍스트 인코더는 통신 중에 텍스트 기반 메시지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-148">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="2becf-149">이 인코더에서 생성하는 메시지는 WS-\* 기반 interop과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-149">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="2becf-150">웹 서비스 또는 웹 서비스 클라이언트는 일반적으로 텍스트 XML을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-150">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="2becf-151">그러나 큰 이진 데이터 블록을 텍스트 형태로 전송하는 것은 가장 비효율적인 XML 메시지 인코딩 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2becf-151">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2becf-152">예제</span><span class="sxs-lookup"><span data-stu-id="2becf-152">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="2becf-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2becf-153">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="2becf-154">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="2becf-154">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="2becf-155">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="2becf-155">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="2becf-156">바인딩</span><span class="sxs-lookup"><span data-stu-id="2becf-156">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2becf-157">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="2becf-157">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2becf-158">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="2becf-158">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
