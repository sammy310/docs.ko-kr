---
title: <netPeerBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 3d1ac85073c44f683fe0c054737c5ec7ed1cbf52
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738665"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="97a3e-102">\<netPeerBinding>의 \<security></span><span class="sxs-lookup"><span data-stu-id="97a3e-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="97a3e-103">[\<netPeerTcpBinding>](netpeertcpbinding.md)메시지 전송에 사용 되는 인증 형식 및 보안을 포함 하 여의 보안 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="97a3e-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="97a3e-104">구문</span><span class="sxs-lookup"><span data-stu-id="97a3e-104">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97a3e-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="97a3e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="97a3e-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97a3e-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97a3e-107">특성</span><span class="sxs-lookup"><span data-stu-id="97a3e-107">Attributes</span></span>  
  
|<span data-ttu-id="97a3e-108">attribute</span><span class="sxs-lookup"><span data-stu-id="97a3e-108">Attribute</span></span>|<span data-ttu-id="97a3e-109">Description</span><span class="sxs-lookup"><span data-stu-id="97a3e-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="97a3e-110">mode</span><span class="sxs-lookup"><span data-stu-id="97a3e-110">mode</span></span>|<span data-ttu-id="97a3e-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="97a3e-111">Optional.</span></span> <span data-ttu-id="97a3e-112">이 바인딩으로 구성된 피어에서 사용하는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97a3e-112">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="97a3e-113">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="97a3e-113">The default value is `Message`.</span></span> <span data-ttu-id="97a3e-114">이 특성은 <xref:System.ServiceModel.SecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="97a3e-114">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="97a3e-115">mode 특성</span><span class="sxs-lookup"><span data-stu-id="97a3e-115">mode Attribute</span></span>  
  
|<span data-ttu-id="97a3e-116">값</span><span class="sxs-lookup"><span data-stu-id="97a3e-116">Value</span></span>|<span data-ttu-id="97a3e-117">Description</span><span class="sxs-lookup"><span data-stu-id="97a3e-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="97a3e-118">메시지</span><span class="sxs-lookup"><span data-stu-id="97a3e-118">Message</span></span>|<span data-ttu-id="97a3e-119">SOAP 전송은 무결성, 기밀성 및 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="97a3e-119">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="97a3e-120">None</span><span class="sxs-lookup"><span data-stu-id="97a3e-120">None</span></span>|<span data-ttu-id="97a3e-121">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97a3e-121">Security is disabled.</span></span>|  
|<span data-ttu-id="97a3e-122">전송</span><span class="sxs-lookup"><span data-stu-id="97a3e-122">Transport</span></span>|<span data-ttu-id="97a3e-123">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="97a3e-123">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="97a3e-124">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="97a3e-124">TransportWithMessageCredential</span></span>|<span data-ttu-id="97a3e-125">HTTPS는 인증 및 기밀성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="97a3e-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="97a3e-126">SOAP 메시지는 다양한 자격 증명 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="97a3e-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97a3e-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="97a3e-127">Child Elements</span></span>  
  
|<span data-ttu-id="97a3e-128">요소</span><span class="sxs-lookup"><span data-stu-id="97a3e-128">Element</span></span>|<span data-ttu-id="97a3e-129">Description</span><span class="sxs-lookup"><span data-stu-id="97a3e-129">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="97a3e-130">이 바인딩으로 구성된 피어에서 보낸 보안 메시지의 전송 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="97a3e-130">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="97a3e-131">이 요소는 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="97a3e-131">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="97a3e-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="97a3e-132">Parent Elements</span></span>  
  
|<span data-ttu-id="97a3e-133">요소</span><span class="sxs-lookup"><span data-stu-id="97a3e-133">Element</span></span>|<span data-ttu-id="97a3e-134">Description</span><span class="sxs-lookup"><span data-stu-id="97a3e-134">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="97a3e-135">의 모든 바인딩 기능을 정의 [\<netPeerTcpBinding>](netpeertcpbinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="97a3e-135">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97a3e-136">설명</span><span class="sxs-lookup"><span data-stu-id="97a3e-136">Remarks</span></span>  
 <span data-ttu-id="97a3e-137">보안은 메시지 또는 전송별로 고유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97a3e-137">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97a3e-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97a3e-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="97a3e-139">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="97a3e-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="97a3e-140">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="97a3e-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="97a3e-141">바인딩</span><span class="sxs-lookup"><span data-stu-id="97a3e-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="97a3e-142">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="97a3e-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="97a3e-143">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="97a3e-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
