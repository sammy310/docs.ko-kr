---
title: <peerTransport>의 <security>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 270ca844f586be256b6483653c868d1cc4396657
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399779"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="21182-102">\<peertransport > \<의 보안 ></span><span class="sxs-lookup"><span data-stu-id="21182-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="21182-103">메시지 전송에 사용되는 인증 형식 및 보안을 비롯하여 피어 채널과 연결된 보안 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="21182-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
<span data-ttu-id="21182-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="21182-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="21182-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="21182-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="21182-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="21182-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="21182-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="21182-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="21182-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="21182-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="21182-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<peerTransport >** ](peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="21182-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)</span></span>\
<span data-ttu-id="21182-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<보안 >**</span><span class="sxs-lookup"><span data-stu-id="21182-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21182-111">구문</span><span class="sxs-lookup"><span data-stu-id="21182-111">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21182-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="21182-112">Attributes and Elements</span></span>  
 <span data-ttu-id="21182-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="21182-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21182-114">특성</span><span class="sxs-lookup"><span data-stu-id="21182-114">Attributes</span></span>  
  
|<span data-ttu-id="21182-115">특성</span><span class="sxs-lookup"><span data-stu-id="21182-115">Attribute</span></span>|<span data-ttu-id="21182-116">Description</span><span class="sxs-lookup"><span data-stu-id="21182-116">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="21182-117">적용할 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21182-117">Specifies the type of security to be applied.</span></span> <span data-ttu-id="21182-118">기본값은 Message입니다.</span><span class="sxs-lookup"><span data-stu-id="21182-118">The default value is Message.</span></span> <span data-ttu-id="21182-119">이 특성은 <xref:System.ServiceModel.SecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="21182-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="21182-120">mode 특성</span><span class="sxs-lookup"><span data-stu-id="21182-120">mode Attribute</span></span>  
  
|<span data-ttu-id="21182-121">값</span><span class="sxs-lookup"><span data-stu-id="21182-121">Value</span></span>|<span data-ttu-id="21182-122">Description</span><span class="sxs-lookup"><span data-stu-id="21182-122">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="21182-123">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21182-123">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="21182-124">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="21182-124">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="21182-125">SOAP 전송은 무결성, 기밀성 및 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="21182-125">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="21182-126">HTTPS는 인증 및 기밀성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="21182-126">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="21182-127">SOAP 메시지는 다양한 자격 증명 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="21182-127">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21182-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="21182-128">Child Elements</span></span>  
  
|<span data-ttu-id="21182-129">요소</span><span class="sxs-lookup"><span data-stu-id="21182-129">Element</span></span>|<span data-ttu-id="21182-130">Description</span><span class="sxs-lookup"><span data-stu-id="21182-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21182-131">\<transport></span><span class="sxs-lookup"><span data-stu-id="21182-131">\<transport></span></span>](transport-of-peertransport.md)|<span data-ttu-id="21182-132">사용자 지정 바인딩에 대한 피어 전송을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="21182-132">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="21182-133">이 요소에는 서비스와 상호 작용할 때 사용되는 자격 증명을 지정하는 `clientCredentialType` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21182-133">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="21182-134">이 특성은 <xref:System.ServiceModel.PeerTransportCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="21182-134">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="21182-135">이 요소는 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="21182-135">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="21182-136">부모 요소</span><span class="sxs-lookup"><span data-stu-id="21182-136">Parent Elements</span></span>  
  
|<span data-ttu-id="21182-137">요소</span><span class="sxs-lookup"><span data-stu-id="21182-137">Element</span></span>|<span data-ttu-id="21182-138">설명</span><span class="sxs-lookup"><span data-stu-id="21182-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21182-139">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="21182-139">\<peerTransport></span></span>](peertransport.md)|<span data-ttu-id="21182-140">사용자 지정 바인딩에 대한 피어 전송을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="21182-140">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21182-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="21182-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="21182-142">전송 보안</span><span class="sxs-lookup"><span data-stu-id="21182-142">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="21182-143">전송</span><span class="sxs-lookup"><span data-stu-id="21182-143">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="21182-144">전송 선택</span><span class="sxs-lookup"><span data-stu-id="21182-144">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="21182-145">바인딩</span><span class="sxs-lookup"><span data-stu-id="21182-145">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="21182-146">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="21182-146">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="21182-147">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="21182-147">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="21182-148">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="21182-148">\<customBinding></span></span>](custombinding.md)
