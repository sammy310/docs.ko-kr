---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 5d78aed78a5c3a10aecac53bda02d6c640bc71ae
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400581"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="4e88e-101">\<byteStreamMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="4e88e-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="4e88e-102">문자 인코딩을 지정하는 옵션을 사용하여 메시지 인코딩을 바이트 스트림으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e88e-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
<span data-ttu-id="4e88e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4e88e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4e88e-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4e88e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4e88e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="4e88e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="4e88e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="4e88e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="4e88e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="4e88e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="4e88e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<byteStreamMessageEncoding >**</span><span class="sxs-lookup"><span data-stu-id="4e88e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e88e-109">구문</span><span class="sxs-lookup"><span data-stu-id="4e88e-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e88e-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4e88e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4e88e-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e88e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e88e-112">특성</span><span class="sxs-lookup"><span data-stu-id="4e88e-112">Attributes</span></span>  
  
|<span data-ttu-id="4e88e-113">특성</span><span class="sxs-lookup"><span data-stu-id="4e88e-113">Attribute</span></span>|<span data-ttu-id="4e88e-114">설명</span><span class="sxs-lookup"><span data-stu-id="4e88e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4e88e-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="4e88e-115">messageVersion</span></span>|<span data-ttu-id="4e88e-116">바인딩을 사용하여 보낸 메시지의 SOAP 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e88e-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="4e88e-117">이 속성은 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>의 메시지 버전 값으로만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e88e-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="4e88e-118">바이트 스트림 메시지 인코더는 다른 메시지 버전을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e88e-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="4e88e-119">이 특성은 <xref:System.ServiceModel.Channels.MessageVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4e88e-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e88e-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4e88e-120">Child Elements</span></span>  
  
|<span data-ttu-id="4e88e-121">요소</span><span class="sxs-lookup"><span data-stu-id="4e88e-121">Element</span></span>|<span data-ttu-id="4e88e-122">설명</span><span class="sxs-lookup"><span data-stu-id="4e88e-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4e88e-123">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4e88e-123">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="4e88e-124">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4e88e-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="4e88e-125">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4e88e-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4e88e-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4e88e-126">Parent Elements</span></span>  
  
|<span data-ttu-id="4e88e-127">요소</span><span class="sxs-lookup"><span data-stu-id="4e88e-127">Element</span></span>|<span data-ttu-id="4e88e-128">설명</span><span class="sxs-lookup"><span data-stu-id="4e88e-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e88e-129">\<binding></span><span class="sxs-lookup"><span data-stu-id="4e88e-129">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="4e88e-130">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4e88e-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e88e-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="4e88e-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="4e88e-132">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="4e88e-132">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="4e88e-133">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="4e88e-133">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="4e88e-134">바인딩</span><span class="sxs-lookup"><span data-stu-id="4e88e-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4e88e-135">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="4e88e-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4e88e-136">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="4e88e-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="4e88e-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4e88e-137">\<customBinding></span></span>](custombinding.md)
