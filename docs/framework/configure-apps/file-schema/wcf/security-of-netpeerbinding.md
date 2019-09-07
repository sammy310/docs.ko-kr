---
title: <netPeerBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 88aa2898472c20c9e52cfd5830c0e41e8ea9ba21
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399811"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="286ac-102">\<netpeerbinding \<의 보안 > ></span><span class="sxs-lookup"><span data-stu-id="286ac-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="286ac-103">메시지 전송에 사용 되는 인증 형식 및 보안을 포함 하 여 [ \<> netpeertcpbinding](netpeertcpbinding.md)의 보안 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="286ac-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
<span data-ttu-id="286ac-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="286ac-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="286ac-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="286ac-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="286ac-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="286ac-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="286ac-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="286ac-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="286ac-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="286ac-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="286ac-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<보안 >**</span><span class="sxs-lookup"><span data-stu-id="286ac-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="286ac-110">구문</span><span class="sxs-lookup"><span data-stu-id="286ac-110">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="286ac-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="286ac-111">Attributes and Elements</span></span>  
 <span data-ttu-id="286ac-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="286ac-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="286ac-113">특성</span><span class="sxs-lookup"><span data-stu-id="286ac-113">Attributes</span></span>  
  
|<span data-ttu-id="286ac-114">특성</span><span class="sxs-lookup"><span data-stu-id="286ac-114">Attribute</span></span>|<span data-ttu-id="286ac-115">Description</span><span class="sxs-lookup"><span data-stu-id="286ac-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="286ac-116">모드</span><span class="sxs-lookup"><span data-stu-id="286ac-116">mode</span></span>|<span data-ttu-id="286ac-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="286ac-117">Optional.</span></span> <span data-ttu-id="286ac-118">이 바인딩으로 구성된 피어에서 사용하는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="286ac-118">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="286ac-119">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="286ac-119">The default value is `Message`.</span></span> <span data-ttu-id="286ac-120">이 특성은 <xref:System.ServiceModel.SecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="286ac-120">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="286ac-121">mode 특성</span><span class="sxs-lookup"><span data-stu-id="286ac-121">mode Attribute</span></span>  
  
|<span data-ttu-id="286ac-122">값</span><span class="sxs-lookup"><span data-stu-id="286ac-122">Value</span></span>|<span data-ttu-id="286ac-123">Description</span><span class="sxs-lookup"><span data-stu-id="286ac-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="286ac-124">메시지</span><span class="sxs-lookup"><span data-stu-id="286ac-124">Message</span></span>|<span data-ttu-id="286ac-125">SOAP 전송은 무결성, 기밀성 및 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="286ac-125">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="286ac-126">없음</span><span class="sxs-lookup"><span data-stu-id="286ac-126">None</span></span>|<span data-ttu-id="286ac-127">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286ac-127">Security is disabled.</span></span>|  
|<span data-ttu-id="286ac-128">전송</span><span class="sxs-lookup"><span data-stu-id="286ac-128">Transport</span></span>|<span data-ttu-id="286ac-129">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="286ac-129">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="286ac-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="286ac-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="286ac-131">HTTPS는 인증 및 기밀성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="286ac-131">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="286ac-132">SOAP 메시지는 다양한 자격 증명 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="286ac-132">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="286ac-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="286ac-133">Child Elements</span></span>  
  
|<span data-ttu-id="286ac-134">요소</span><span class="sxs-lookup"><span data-stu-id="286ac-134">Element</span></span>|<span data-ttu-id="286ac-135">Description</span><span class="sxs-lookup"><span data-stu-id="286ac-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="286ac-136">\<transport></span><span class="sxs-lookup"><span data-stu-id="286ac-136">\<transport></span></span>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="286ac-137">이 바인딩으로 구성된 피어에서 보낸 보안 메시지의 전송 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="286ac-137">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="286ac-138">이 요소는 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="286ac-138">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="286ac-139">부모 요소</span><span class="sxs-lookup"><span data-stu-id="286ac-139">Parent Elements</span></span>  
  
|<span data-ttu-id="286ac-140">요소</span><span class="sxs-lookup"><span data-stu-id="286ac-140">Element</span></span>|<span data-ttu-id="286ac-141">설명</span><span class="sxs-lookup"><span data-stu-id="286ac-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="286ac-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="286ac-142">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="286ac-143">[ \<> Netpeertcpbinding](netpeertcpbinding.md)의 모든 바인딩 기능을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="286ac-143">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="286ac-144">설명</span><span class="sxs-lookup"><span data-stu-id="286ac-144">Remarks</span></span>  
 <span data-ttu-id="286ac-145">보안은 메시지 또는 전송별로 고유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="286ac-145">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="286ac-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="286ac-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="286ac-147">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="286ac-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="286ac-148">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="286ac-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="286ac-149">바인딩</span><span class="sxs-lookup"><span data-stu-id="286ac-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="286ac-150">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="286ac-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="286ac-151">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="286ac-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="286ac-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="286ac-152">\<binding></span></span>](../../../misc/binding.md)
