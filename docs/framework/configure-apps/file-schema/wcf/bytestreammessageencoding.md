---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: b11f472c0e33003e50be4b45bb49196c64ecb70d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919727"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="b405b-101">\<byteStreamMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="b405b-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="b405b-102">문자 인코딩을 지정하는 옵션을 사용하여 메시지 인코딩을 바이트 스트림으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b405b-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="b405b-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b405b-103">\<system.serviceModel></span></span>  
<span data-ttu-id="b405b-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b405b-104">\<bindings></span></span>  
<span data-ttu-id="b405b-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b405b-105">\<customBinding></span></span>  
<span data-ttu-id="b405b-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="b405b-106">\<binding></span></span>  
<span data-ttu-id="b405b-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="b405b-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b405b-108">구문</span><span class="sxs-lookup"><span data-stu-id="b405b-108">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b405b-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b405b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b405b-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b405b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b405b-111">특성</span><span class="sxs-lookup"><span data-stu-id="b405b-111">Attributes</span></span>  
  
|<span data-ttu-id="b405b-112">특성</span><span class="sxs-lookup"><span data-stu-id="b405b-112">Attribute</span></span>|<span data-ttu-id="b405b-113">Description</span><span class="sxs-lookup"><span data-stu-id="b405b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b405b-114">messageVersion</span><span class="sxs-lookup"><span data-stu-id="b405b-114">messageVersion</span></span>|<span data-ttu-id="b405b-115">바인딩을 사용하여 보낸 메시지의 SOAP 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b405b-115">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="b405b-116">이 속성은 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>의 메시지 버전 값으로만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b405b-116">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="b405b-117">바이트 스트림 메시지 인코더는 다른 메시지 버전을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b405b-117">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="b405b-118">이 특성은 <xref:System.ServiceModel.Channels.MessageVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b405b-118">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b405b-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b405b-119">Child Elements</span></span>  
  
|<span data-ttu-id="b405b-120">요소</span><span class="sxs-lookup"><span data-stu-id="b405b-120">Element</span></span>|<span data-ttu-id="b405b-121">설명</span><span class="sxs-lookup"><span data-stu-id="b405b-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b405b-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b405b-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="b405b-123">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b405b-123">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="b405b-124">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b405b-124">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b405b-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b405b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="b405b-126">요소</span><span class="sxs-lookup"><span data-stu-id="b405b-126">Element</span></span>|<span data-ttu-id="b405b-127">설명</span><span class="sxs-lookup"><span data-stu-id="b405b-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b405b-128">\<binding></span><span class="sxs-lookup"><span data-stu-id="b405b-128">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="b405b-129">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b405b-129">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b405b-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="b405b-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="b405b-131">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="b405b-131">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="b405b-132">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="b405b-132">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="b405b-133">바인딩</span><span class="sxs-lookup"><span data-stu-id="b405b-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b405b-134">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="b405b-134">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b405b-135">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="b405b-135">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b405b-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b405b-136">\<customBinding></span></span>](custombinding.md)
