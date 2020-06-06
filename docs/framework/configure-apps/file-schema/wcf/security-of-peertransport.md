---
title: <peerTransport>의 <security>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 270ca844f586be256b6483653c868d1cc4396657
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399779"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="e244d-102">\<peerTransport>의 \<security></span><span class="sxs-lookup"><span data-stu-id="e244d-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="e244d-103">메시지 전송에 사용되는 인증 형식 및 보안을 비롯하여 피어 채널과 연결된 보안 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e244d-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="e244d-104">구문</span><span class="sxs-lookup"><span data-stu-id="e244d-104">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e244d-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e244d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e244d-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e244d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e244d-107">특성</span><span class="sxs-lookup"><span data-stu-id="e244d-107">Attributes</span></span>  
  
|<span data-ttu-id="e244d-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e244d-108">Attribute</span></span>|<span data-ttu-id="e244d-109">Description</span><span class="sxs-lookup"><span data-stu-id="e244d-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="e244d-110">적용할 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e244d-110">Specifies the type of security to be applied.</span></span> <span data-ttu-id="e244d-111">기본값은 Message입니다.</span><span class="sxs-lookup"><span data-stu-id="e244d-111">The default value is Message.</span></span> <span data-ttu-id="e244d-112">이 특성은 <xref:System.ServiceModel.SecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e244d-112">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="e244d-113">mode 특성</span><span class="sxs-lookup"><span data-stu-id="e244d-113">mode Attribute</span></span>  
  
|<span data-ttu-id="e244d-114">값</span><span class="sxs-lookup"><span data-stu-id="e244d-114">Value</span></span>|<span data-ttu-id="e244d-115">Description</span><span class="sxs-lookup"><span data-stu-id="e244d-115">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="e244d-116">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e244d-116">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="e244d-117">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e244d-117">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="e244d-118">SOAP 전송은 무결성, 기밀성 및 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e244d-118">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="e244d-119">HTTPS는 인증 및 기밀성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e244d-119">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="e244d-120">SOAP 메시지는 다양한 자격 증명 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e244d-120">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e244d-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e244d-121">Child Elements</span></span>  
  
|<span data-ttu-id="e244d-122">요소</span><span class="sxs-lookup"><span data-stu-id="e244d-122">Element</span></span>|<span data-ttu-id="e244d-123">Description</span><span class="sxs-lookup"><span data-stu-id="e244d-123">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-peertransport.md)|<span data-ttu-id="e244d-124">사용자 지정 바인딩에 대한 피어 전송을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e244d-124">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="e244d-125">이 요소에는 서비스와 상호 작용할 때 사용되는 자격 증명을 지정하는 `clientCredentialType` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e244d-125">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="e244d-126">이 특성은 <xref:System.ServiceModel.PeerTransportCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e244d-126">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="e244d-127">이 요소는 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e244d-127">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e244d-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e244d-128">Parent Elements</span></span>  
  
|<span data-ttu-id="e244d-129">요소</span><span class="sxs-lookup"><span data-stu-id="e244d-129">Element</span></span>|<span data-ttu-id="e244d-130">Description</span><span class="sxs-lookup"><span data-stu-id="e244d-130">Description</span></span>|  
|-------------|-----------------|  
|[\<peerTransport>](peertransport.md)|<span data-ttu-id="e244d-131">사용자 지정 바인딩에 대한 피어 전송을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e244d-131">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e244d-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e244d-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e244d-133">전송 보안</span><span class="sxs-lookup"><span data-stu-id="e244d-133">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="e244d-134">전송</span><span class="sxs-lookup"><span data-stu-id="e244d-134">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="e244d-135">전송 선택</span><span class="sxs-lookup"><span data-stu-id="e244d-135">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="e244d-136">바인딩</span><span class="sxs-lookup"><span data-stu-id="e244d-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e244d-137">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="e244d-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e244d-138">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="e244d-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
