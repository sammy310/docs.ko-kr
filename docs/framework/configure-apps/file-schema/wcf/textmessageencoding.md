---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: c5cd8e9e2002f44fd9feebdc6bb7ede023de459a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556449"
---
# \<textMessageEncoding>
<span data-ttu-id="d563e-101">텍스트 기반 XML 메시지에 사용되는 문자 인코딩 및 메시지 버전 관리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-101">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<textMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="d563e-102">구문</span><span class="sxs-lookup"><span data-stu-id="d563e-102">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d563e-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d563e-103">Attributes and Elements</span></span>  
 <span data-ttu-id="d563e-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d563e-105">특성</span><span class="sxs-lookup"><span data-stu-id="d563e-105">Attributes</span></span>  
  
|<span data-ttu-id="d563e-106">attribute</span><span class="sxs-lookup"><span data-stu-id="d563e-106">Attribute</span></span>|<span data-ttu-id="d563e-107">Description</span><span class="sxs-lookup"><span data-stu-id="d563e-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d563e-108">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="d563e-108">maxReadPoolSize</span></span>|<span data-ttu-id="d563e-109">새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-109">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="d563e-110">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-110">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="d563e-111">기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-111">The default is 64.</span></span>|  
|<span data-ttu-id="d563e-112">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="d563e-112">maxWritePoolSize</span></span>|<span data-ttu-id="d563e-113">새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-113">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="d563e-114">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-114">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="d563e-115">기본값은 16입니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-115">The default is 16.</span></span>|  
|<span data-ttu-id="d563e-116">messageVersion</span><span class="sxs-lookup"><span data-stu-id="d563e-116">messageVersion</span></span>|<span data-ttu-id="d563e-117">바인딩을 사용하여 보낸 메시지의 SOAP 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-117">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="d563e-118">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-118">Valid values are</span></span><br /><br /> <span data-ttu-id="d563e-119">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="d563e-119">-   Soap11Addressing10</span></span><br /><span data-ttu-id="d563e-120">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="d563e-120">-   Soap12Addressing10</span></span><br /><span data-ttu-id="d563e-121">- Soap11</span><span class="sxs-lookup"><span data-stu-id="d563e-121">-   Soap11</span></span><br /><span data-ttu-id="d563e-122">- Soap12</span><span class="sxs-lookup"><span data-stu-id="d563e-122">-  Soap12</span></span><br /><br /><span data-ttu-id="d563e-123">기본값은 Soap12Addressing10입니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-123">The default is Soap12Addressing10.</span></span> <span data-ttu-id="d563e-124">이 특성은 <xref:System.ServiceModel.Channels.MessageVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-124">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="d563e-125">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="d563e-125">writeEncoding</span></span>|<span data-ttu-id="d563e-126">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-126">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="d563e-127">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-127">Valid values are</span></span><br /><br /> <span data-ttu-id="d563e-128">-UnicodeFffeTextEncoding: Unicode 이상 Endian encoding</span><span class="sxs-lookup"><span data-stu-id="d563e-128">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="d563e-129">-Utf16TextEncoding: 유니코드 인코딩</span><span class="sxs-lookup"><span data-stu-id="d563e-129">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="d563e-130">-Utf8TextEncoding: 8 비트 인코딩</span><span class="sxs-lookup"><span data-stu-id="d563e-130">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="d563e-131">기본값은 Utf8TextEncoding입니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-131">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="d563e-132">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-132">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d563e-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d563e-133">Child Elements</span></span>  
  
|<span data-ttu-id="d563e-134">요소</span><span class="sxs-lookup"><span data-stu-id="d563e-134">Element</span></span>|<span data-ttu-id="d563e-135">Description</span><span class="sxs-lookup"><span data-stu-id="d563e-135">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="d563e-136">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-136">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d563e-137">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-137">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d563e-138">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d563e-138">Parent Elements</span></span>  
  
|<span data-ttu-id="d563e-139">요소</span><span class="sxs-lookup"><span data-stu-id="d563e-139">Element</span></span>|<span data-ttu-id="d563e-140">Description</span><span class="sxs-lookup"><span data-stu-id="d563e-140">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="d563e-141">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-141">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d563e-142">설명</span><span class="sxs-lookup"><span data-stu-id="d563e-142">Remarks</span></span>  
 <span data-ttu-id="d563e-143">인코딩은 메시지를 바이트 시퀀스로 변형하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-143">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="d563e-144">디코딩은 역프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-144">Decoding is the reverse process.</span></span> <span data-ttu-id="d563e-145">WCF (Windows Communication Foundation)는 SOAP 메시지에 대해 텍스트, 이진 및 MTOM (메시지 전송 최적화 메커니즘)의 세 가지 인코딩 유형을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-145">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="d563e-146">`textMessageEncoding` 요소로 나타낸 텍스트 인코딩은 상호 운용성이 가장 뛰어나지만 XML 메시지에 대해서는 효율성이 가장 낮은 인코더입니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-146">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="d563e-147">텍스트 인코더는 통신 중에 텍스트 기반 메시지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-147">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="d563e-148">이 인코더에서 생성하는 메시지는 WS-\* 기반 interop과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-148">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="d563e-149">웹 서비스 또는 웹 서비스 클라이언트는 일반적으로 텍스트 XML을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-149">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="d563e-150">그러나 큰 이진 데이터 블록을 텍스트 형태로 전송하는 것은 가장 비효율적인 XML 메시지 인코딩 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d563e-150">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d563e-151">예제</span><span class="sxs-lookup"><span data-stu-id="d563e-151">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="d563e-152">참조</span><span class="sxs-lookup"><span data-stu-id="d563e-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="d563e-153">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="d563e-153">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="d563e-154">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="d563e-154">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="d563e-155">바인딩</span><span class="sxs-lookup"><span data-stu-id="d563e-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d563e-156">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="d563e-156">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d563e-157">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="d563e-157">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
