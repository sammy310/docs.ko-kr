---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: 1b72b73f0d9d312fd54ea6a5517d55bf251c0e05
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201475"
---
# \<binaryMessageEncoding>

<span data-ttu-id="bb495-101">통신 중에 WCF(Windows Communication Foundation) 메시지를 이진 형식으로 인코딩하는 이진 메시지 인코더를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-101">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binaryMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="bb495-102">구문</span><span class="sxs-lookup"><span data-stu-id="bb495-102">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb495-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bb495-103">Attributes and Elements</span></span>  

 <span data-ttu-id="bb495-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb495-105">특성</span><span class="sxs-lookup"><span data-stu-id="bb495-105">Attributes</span></span>  
  
|<span data-ttu-id="bb495-106">attribute</span><span class="sxs-lookup"><span data-stu-id="bb495-106">Attribute</span></span>|<span data-ttu-id="bb495-107">설명</span><span class="sxs-lookup"><span data-stu-id="bb495-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bb495-108">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="bb495-108">maxReadPoolSize</span></span>|<span data-ttu-id="bb495-109">새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-109">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="bb495-110">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-110">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="bb495-111">기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-111">The default is 64.</span></span>|  
|<span data-ttu-id="bb495-112">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="bb495-112">maxSessionSize</span></span>|<span data-ttu-id="bb495-113">인코딩에 사용되는 버퍼의 크기(바이트)를 설정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-113">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="bb495-114">버퍼가 크면 작업 집합의 크기 문제가 생기지만 인코딩 속도가 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-114">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="bb495-115">기본값은 2048입니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-115">The default is 2048.</span></span>|  
|<span data-ttu-id="bb495-116">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="bb495-116">maxWritePoolSize</span></span>|<span data-ttu-id="bb495-117">새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-117">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="bb495-118">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-118">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="bb495-119">기본값은 16입니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-119">The default is 16.</span></span>|  
|<span data-ttu-id="bb495-120">messageVersion</span><span class="sxs-lookup"><span data-stu-id="bb495-120">messageVersion</span></span>|<span data-ttu-id="bb495-121">사용되거나 필요한 SOAP 메시지 및 WS-Addressing 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-121">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb495-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bb495-122">Child Elements</span></span>  
  
|<span data-ttu-id="bb495-123">요소</span><span class="sxs-lookup"><span data-stu-id="bb495-123">Element</span></span>|<span data-ttu-id="bb495-124">설명</span><span class="sxs-lookup"><span data-stu-id="bb495-124">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="bb495-125">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-125">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="bb495-126">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-126">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bb495-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bb495-127">Parent Elements</span></span>  
  
|<span data-ttu-id="bb495-128">요소</span><span class="sxs-lookup"><span data-stu-id="bb495-128">Element</span></span>|<span data-ttu-id="bb495-129">설명</span><span class="sxs-lookup"><span data-stu-id="bb495-129">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="bb495-130">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb495-131">설명</span><span class="sxs-lookup"><span data-stu-id="bb495-131">Remarks</span></span>  

 <span data-ttu-id="bb495-132">인코딩은 메시지를 바이트 시퀀스로 변형하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-132">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="bb495-133">디코딩은 역프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-133">Decoding is the reverse process.</span></span> <span data-ttu-id="bb495-134">WCF (Windows Communication Foundation)는 SOAP 메시지에 대해 텍스트, 이진 및 MTOM (메시지 전송 최적화 메커니즘)의 세 가지 인코딩 유형을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-134">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="bb495-135">`binaryMessageEncoding` 요소는 XML에 대한 .NET 이진 형식을 지정하며, 사용할 SOAP 및 WS-Addressing 버전과 문자 인코딩을 지정하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-135">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="bb495-136">이진 메시지 인코더는 통신 중에 WCF(Windows Communication Foundation) 메시지를 이진 형식으로 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-136">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="bb495-137">이 인코딩은 전송 속도가 매우 빠르지만 WS-\* 표준과 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb495-137">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb495-138">예제</span><span class="sxs-lookup"><span data-stu-id="bb495-138">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="bb495-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb495-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="bb495-140">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="bb495-140">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="bb495-141">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="bb495-141">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="bb495-142">바인딩하</span><span class="sxs-lookup"><span data-stu-id="bb495-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="bb495-143">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="bb495-143">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="bb495-144">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="bb495-144">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
