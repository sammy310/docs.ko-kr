---
description: 다음에 대해 자세히 알아보세요. <byteStreamMessageEncoding>
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 9cbb4eacb1a960481ee262db662160b5a342e27f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639291"
---
# \<byteStreamMessageEncoding>

<span data-ttu-id="b3226-102">문자 인코딩을 지정하는 옵션을 사용하여 메시지 인코딩을 바이트 스트림으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b3226-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="b3226-103">구문</span><span class="sxs-lookup"><span data-stu-id="b3226-103">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3226-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b3226-104">Attributes and Elements</span></span>  

 <span data-ttu-id="b3226-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b3226-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3226-106">특성</span><span class="sxs-lookup"><span data-stu-id="b3226-106">Attributes</span></span>  
  
|<span data-ttu-id="b3226-107">attribute</span><span class="sxs-lookup"><span data-stu-id="b3226-107">Attribute</span></span>|<span data-ttu-id="b3226-108">설명</span><span class="sxs-lookup"><span data-stu-id="b3226-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b3226-109">messageVersion</span><span class="sxs-lookup"><span data-stu-id="b3226-109">messageVersion</span></span>|<span data-ttu-id="b3226-110">바인딩을 사용하여 보낸 메시지의 SOAP 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b3226-110">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="b3226-111">이 속성은 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>의 메시지 버전 값으로만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3226-111">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="b3226-112">바이트 스트림 메시지 인코더는 다른 메시지 버전을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3226-112">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="b3226-113">이 특성은 <xref:System.ServiceModel.Channels.MessageVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b3226-113">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3226-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b3226-114">Child Elements</span></span>  
  
|<span data-ttu-id="b3226-115">요소</span><span class="sxs-lookup"><span data-stu-id="b3226-115">Element</span></span>|<span data-ttu-id="b3226-116">설명</span><span class="sxs-lookup"><span data-stu-id="b3226-116">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="b3226-117">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b3226-117">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="b3226-118">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b3226-118">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b3226-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b3226-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b3226-120">요소</span><span class="sxs-lookup"><span data-stu-id="b3226-120">Element</span></span>|<span data-ttu-id="b3226-121">설명</span><span class="sxs-lookup"><span data-stu-id="b3226-121">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="b3226-122">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b3226-122">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b3226-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3226-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="b3226-124">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="b3226-124">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="b3226-125">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="b3226-125">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="b3226-126">바인딩</span><span class="sxs-lookup"><span data-stu-id="b3226-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b3226-127">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="b3226-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b3226-128">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="b3226-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
