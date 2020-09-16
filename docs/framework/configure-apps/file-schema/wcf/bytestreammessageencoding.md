---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: e2b92b88c3e2a8abb14f58af90aab6e2e58ce14a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557296"
---
# \<byteStreamMessageEncoding>
<span data-ttu-id="1ce1a-101">문자 인코딩을 지정하는 옵션을 사용하여 메시지 인코딩을 바이트 스트림으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce1a-101">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="1ce1a-102">구문</span><span class="sxs-lookup"><span data-stu-id="1ce1a-102">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ce1a-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1ce1a-103">Attributes and Elements</span></span>  
 <span data-ttu-id="1ce1a-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce1a-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ce1a-105">특성</span><span class="sxs-lookup"><span data-stu-id="1ce1a-105">Attributes</span></span>  
  
|<span data-ttu-id="1ce1a-106">attribute</span><span class="sxs-lookup"><span data-stu-id="1ce1a-106">Attribute</span></span>|<span data-ttu-id="1ce1a-107">Description</span><span class="sxs-lookup"><span data-stu-id="1ce1a-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ce1a-108">messageVersion</span><span class="sxs-lookup"><span data-stu-id="1ce1a-108">messageVersion</span></span>|<span data-ttu-id="1ce1a-109">바인딩을 사용하여 보낸 메시지의 SOAP 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce1a-109">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="1ce1a-110">이 속성은 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>의 메시지 버전 값으로만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ce1a-110">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="1ce1a-111">바이트 스트림 메시지 인코더는 다른 메시지 버전을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ce1a-111">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="1ce1a-112">이 특성은 <xref:System.ServiceModel.Channels.MessageVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1ce1a-112">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ce1a-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1ce1a-113">Child Elements</span></span>  
  
|<span data-ttu-id="1ce1a-114">요소</span><span class="sxs-lookup"><span data-stu-id="1ce1a-114">Element</span></span>|<span data-ttu-id="1ce1a-115">Description</span><span class="sxs-lookup"><span data-stu-id="1ce1a-115">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="1ce1a-116">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce1a-116">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="1ce1a-117">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1ce1a-117">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1ce1a-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1ce1a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1ce1a-119">요소</span><span class="sxs-lookup"><span data-stu-id="1ce1a-119">Element</span></span>|<span data-ttu-id="1ce1a-120">Description</span><span class="sxs-lookup"><span data-stu-id="1ce1a-120">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="1ce1a-121">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce1a-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ce1a-122">참조</span><span class="sxs-lookup"><span data-stu-id="1ce1a-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="1ce1a-123">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="1ce1a-123">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="1ce1a-124">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="1ce1a-124">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="1ce1a-125">바인딩</span><span class="sxs-lookup"><span data-stu-id="1ce1a-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1ce1a-126">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="1ce1a-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="1ce1a-127">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="1ce1a-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
