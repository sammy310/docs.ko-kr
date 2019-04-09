---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: ce9f282ea1101befe3bf99762efa61e9b47b74cf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109904"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="858bb-101">\<byteStreamMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="858bb-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="858bb-102">문자 인코딩을 지정하는 옵션을 사용하여 메시지 인코딩을 바이트 스트림으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="858bb-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="858bb-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="858bb-103">\<system.serviceModel></span></span>  
<span data-ttu-id="858bb-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="858bb-104">\<bindings></span></span>  
<span data-ttu-id="858bb-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="858bb-105">\<customBinding></span></span>  
<span data-ttu-id="858bb-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="858bb-106">\<binding></span></span>  
<span data-ttu-id="858bb-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="858bb-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="858bb-108">구문</span><span class="sxs-lookup"><span data-stu-id="858bb-108">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="858bb-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="858bb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="858bb-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="858bb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="858bb-111">특성</span><span class="sxs-lookup"><span data-stu-id="858bb-111">Attributes</span></span>  
  
|<span data-ttu-id="858bb-112">특성</span><span class="sxs-lookup"><span data-stu-id="858bb-112">Attribute</span></span>|<span data-ttu-id="858bb-113">설명</span><span class="sxs-lookup"><span data-stu-id="858bb-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="858bb-114">messageVersion</span><span class="sxs-lookup"><span data-stu-id="858bb-114">messageVersion</span></span>|<span data-ttu-id="858bb-115">바인딩을 사용하여 보낸 메시지의 SOAP 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="858bb-115">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="858bb-116">이 속성은 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>의 메시지 버전 값으로만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="858bb-116">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="858bb-117">바이트 스트림 메시지 인코더는 다른 메시지 버전을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="858bb-117">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="858bb-118">이 특성은 <xref:System.ServiceModel.Channels.MessageVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="858bb-118">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="858bb-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="858bb-119">Child Elements</span></span>  
  
|<span data-ttu-id="858bb-120">요소</span><span class="sxs-lookup"><span data-stu-id="858bb-120">Element</span></span>|<span data-ttu-id="858bb-121">설명</span><span class="sxs-lookup"><span data-stu-id="858bb-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="858bb-122">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="858bb-122">\<readerQuotas></span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="858bb-123">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="858bb-123">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="858bb-124">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="858bb-124">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="858bb-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="858bb-125">Parent Elements</span></span>  
  
|<span data-ttu-id="858bb-126">요소</span><span class="sxs-lookup"><span data-stu-id="858bb-126">Element</span></span>|<span data-ttu-id="858bb-127">설명</span><span class="sxs-lookup"><span data-stu-id="858bb-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="858bb-128">\<binding></span><span class="sxs-lookup"><span data-stu-id="858bb-128">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="858bb-129">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="858bb-129">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="858bb-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="858bb-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="858bb-131">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="858bb-131">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="858bb-132">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="858bb-132">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="858bb-133">바인딩</span><span class="sxs-lookup"><span data-stu-id="858bb-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="858bb-134">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="858bb-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="858bb-135">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="858bb-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="858bb-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="858bb-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
