---
description: '다음에 대 한 자세한 정보:: <security><netPeerBinding>'
title: <netPeerBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: f67cfa445a5a605b99783cfd67dd1bae6e17b51e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786839"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="5c5a4-103">\<netPeerBinding>의 \<security></span><span class="sxs-lookup"><span data-stu-id="5c5a4-103">\<security> of \<netPeerBinding></span></span>

<span data-ttu-id="5c5a4-104">[\<netPeerTcpBinding>](netpeertcpbinding.md)메시지 전송에 사용 되는 인증 형식 및 보안을 포함 하 여의 보안 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c5a4-104">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="5c5a4-105">구문</span><span class="sxs-lookup"><span data-stu-id="5c5a4-105">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c5a4-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5c5a4-106">Attributes and Elements</span></span>  

 <span data-ttu-id="5c5a4-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5c5a4-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c5a4-108">특성</span><span class="sxs-lookup"><span data-stu-id="5c5a4-108">Attributes</span></span>  
  
|<span data-ttu-id="5c5a4-109">attribute</span><span class="sxs-lookup"><span data-stu-id="5c5a4-109">Attribute</span></span>|<span data-ttu-id="5c5a4-110">설명</span><span class="sxs-lookup"><span data-stu-id="5c5a4-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c5a4-111">mode</span><span class="sxs-lookup"><span data-stu-id="5c5a4-111">mode</span></span>|<span data-ttu-id="5c5a4-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5c5a4-112">Optional.</span></span> <span data-ttu-id="5c5a4-113">이 바인딩으로 구성된 피어에서 사용하는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c5a4-113">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="5c5a4-114">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="5c5a4-114">The default value is `Message`.</span></span> <span data-ttu-id="5c5a4-115">이 특성은 <xref:System.ServiceModel.SecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5c5a4-115">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="5c5a4-116">mode 특성</span><span class="sxs-lookup"><span data-stu-id="5c5a4-116">mode Attribute</span></span>  
  
|<span data-ttu-id="5c5a4-117">값</span><span class="sxs-lookup"><span data-stu-id="5c5a4-117">Value</span></span>|<span data-ttu-id="5c5a4-118">설명</span><span class="sxs-lookup"><span data-stu-id="5c5a4-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5c5a4-119">메시지</span><span class="sxs-lookup"><span data-stu-id="5c5a4-119">Message</span></span>|<span data-ttu-id="5c5a4-120">SOAP 전송은 무결성, 기밀성 및 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5c5a4-120">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="5c5a4-121">없음</span><span class="sxs-lookup"><span data-stu-id="5c5a4-121">None</span></span>|<span data-ttu-id="5c5a4-122">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c5a4-122">Security is disabled.</span></span>|  
|<span data-ttu-id="5c5a4-123">전송</span><span class="sxs-lookup"><span data-stu-id="5c5a4-123">Transport</span></span>|<span data-ttu-id="5c5a4-124">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c5a4-124">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="5c5a4-125">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="5c5a4-125">TransportWithMessageCredential</span></span>|<span data-ttu-id="5c5a4-126">HTTPS는 인증 및 기밀성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5c5a4-126">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="5c5a4-127">SOAP 메시지는 다양한 자격 증명 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5c5a4-127">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c5a4-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5c5a4-128">Child Elements</span></span>  
  
|<span data-ttu-id="5c5a4-129">요소</span><span class="sxs-lookup"><span data-stu-id="5c5a4-129">Element</span></span>|<span data-ttu-id="5c5a4-130">설명</span><span class="sxs-lookup"><span data-stu-id="5c5a4-130">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="5c5a4-131">이 바인딩으로 구성된 피어에서 보낸 보안 메시지의 전송 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5c5a4-131">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="5c5a4-132">이 요소는 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5c5a4-132">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5c5a4-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5c5a4-133">Parent Elements</span></span>  
  
|<span data-ttu-id="5c5a4-134">요소</span><span class="sxs-lookup"><span data-stu-id="5c5a4-134">Element</span></span>|<span data-ttu-id="5c5a4-135">설명</span><span class="sxs-lookup"><span data-stu-id="5c5a4-135">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="5c5a4-136">의 모든 바인딩 기능을 정의 [\<netPeerTcpBinding>](netpeertcpbinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c5a4-136">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c5a4-137">설명</span><span class="sxs-lookup"><span data-stu-id="5c5a4-137">Remarks</span></span>  

 <span data-ttu-id="5c5a4-138">보안은 메시지 또는 전송별로 고유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c5a4-138">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c5a4-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c5a4-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="5c5a4-140">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="5c5a4-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5c5a4-141">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="5c5a4-141">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="5c5a4-142">바인딩</span><span class="sxs-lookup"><span data-stu-id="5c5a4-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5c5a4-143">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="5c5a4-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5c5a4-144">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="5c5a4-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
