---
description: 다음에 대해 자세히 알아보세요. <binaryMessageEncoding>
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: 910b8b70bab40c1eb099ed2b54c0545e73e96c6f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639499"
---
# \<binaryMessageEncoding>

<span data-ttu-id="1799a-102">통신 중에 WCF(Windows Communication Foundation) 메시지를 이진 형식으로 인코딩하는 이진 메시지 인코더를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-102">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binaryMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="1799a-103">구문</span><span class="sxs-lookup"><span data-stu-id="1799a-103">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1799a-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1799a-104">Attributes and Elements</span></span>  

 <span data-ttu-id="1799a-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1799a-106">특성</span><span class="sxs-lookup"><span data-stu-id="1799a-106">Attributes</span></span>  
  
|<span data-ttu-id="1799a-107">attribute</span><span class="sxs-lookup"><span data-stu-id="1799a-107">Attribute</span></span>|<span data-ttu-id="1799a-108">설명</span><span class="sxs-lookup"><span data-stu-id="1799a-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1799a-109">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="1799a-109">maxReadPoolSize</span></span>|<span data-ttu-id="1799a-110">새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-110">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="1799a-111">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-111">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="1799a-112">기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-112">The default is 64.</span></span>|  
|<span data-ttu-id="1799a-113">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="1799a-113">maxSessionSize</span></span>|<span data-ttu-id="1799a-114">인코딩에 사용되는 버퍼의 크기(바이트)를 설정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-114">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="1799a-115">버퍼가 크면 작업 집합의 크기 문제가 생기지만 인코딩 속도가 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-115">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="1799a-116">기본값은 2048입니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-116">The default is 2048.</span></span>|  
|<span data-ttu-id="1799a-117">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="1799a-117">maxWritePoolSize</span></span>|<span data-ttu-id="1799a-118">새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-118">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="1799a-119">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-119">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="1799a-120">기본값은 16입니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-120">The default is 16.</span></span>|  
|<span data-ttu-id="1799a-121">messageVersion</span><span class="sxs-lookup"><span data-stu-id="1799a-121">messageVersion</span></span>|<span data-ttu-id="1799a-122">사용되거나 필요한 SOAP 메시지 및 WS-Addressing 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-122">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1799a-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1799a-123">Child Elements</span></span>  
  
|<span data-ttu-id="1799a-124">요소</span><span class="sxs-lookup"><span data-stu-id="1799a-124">Element</span></span>|<span data-ttu-id="1799a-125">설명</span><span class="sxs-lookup"><span data-stu-id="1799a-125">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="1799a-126">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-126">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="1799a-127">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-127">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1799a-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1799a-128">Parent Elements</span></span>  
  
|<span data-ttu-id="1799a-129">요소</span><span class="sxs-lookup"><span data-stu-id="1799a-129">Element</span></span>|<span data-ttu-id="1799a-130">설명</span><span class="sxs-lookup"><span data-stu-id="1799a-130">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="1799a-131">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1799a-132">설명</span><span class="sxs-lookup"><span data-stu-id="1799a-132">Remarks</span></span>  

 <span data-ttu-id="1799a-133">인코딩은 메시지를 바이트 시퀀스로 변형하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-133">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="1799a-134">디코딩은 역프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-134">Decoding is the reverse process.</span></span> <span data-ttu-id="1799a-135">WCF (Windows Communication Foundation)는 SOAP 메시지에 대해 텍스트, 이진 및 MTOM (메시지 전송 최적화 메커니즘)의 세 가지 인코딩 유형을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-135">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="1799a-136">`binaryMessageEncoding` 요소는 XML에 대한 .NET 이진 형식을 지정하며, 사용할 SOAP 및 WS-Addressing 버전과 문자 인코딩을 지정하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-136">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="1799a-137">이진 메시지 인코더는 통신 중에 WCF(Windows Communication Foundation) 메시지를 이진 형식으로 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-137">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="1799a-138">이 인코딩은 전송 속도가 매우 빠르지만 WS-\* 표준과 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1799a-138">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1799a-139">예제</span><span class="sxs-lookup"><span data-stu-id="1799a-139">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="1799a-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1799a-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="1799a-141">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="1799a-141">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="1799a-142">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="1799a-142">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="1799a-143">바인딩</span><span class="sxs-lookup"><span data-stu-id="1799a-143">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1799a-144">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="1799a-144">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="1799a-145">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="1799a-145">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
