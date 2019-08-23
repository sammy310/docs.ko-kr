---
title: <netPeerBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: be5ebacec466caf8d8a77bf552f42da1861e77a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936621"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="ea0a9-102">\<netpeerbinding \<의 보안 > ></span><span class="sxs-lookup"><span data-stu-id="ea0a9-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="ea0a9-103">메시지 전송에 사용 되는 인증 형식 및 보안을 포함 하 여 [ \<> netpeertcpbinding](netpeertcpbinding.md)의 보안 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0a9-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="ea0a9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ea0a9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ea0a9-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ea0a9-105">\<bindings></span></span>  
<span data-ttu-id="ea0a9-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="ea0a9-106">\<netPeerBinding></span></span>  
<span data-ttu-id="ea0a9-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="ea0a9-107">\<binding></span></span>  
<span data-ttu-id="ea0a9-108">\<security></span><span class="sxs-lookup"><span data-stu-id="ea0a9-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea0a9-109">구문</span><span class="sxs-lookup"><span data-stu-id="ea0a9-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea0a9-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ea0a9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ea0a9-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0a9-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea0a9-112">특성</span><span class="sxs-lookup"><span data-stu-id="ea0a9-112">Attributes</span></span>  
  
|<span data-ttu-id="ea0a9-113">특성</span><span class="sxs-lookup"><span data-stu-id="ea0a9-113">Attribute</span></span>|<span data-ttu-id="ea0a9-114">Description</span><span class="sxs-lookup"><span data-stu-id="ea0a9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ea0a9-115">모드</span><span class="sxs-lookup"><span data-stu-id="ea0a9-115">mode</span></span>|<span data-ttu-id="ea0a9-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ea0a9-116">Optional.</span></span> <span data-ttu-id="ea0a9-117">이 바인딩으로 구성된 피어에서 사용하는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0a9-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="ea0a9-118">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="ea0a9-118">The default value is `Message`.</span></span> <span data-ttu-id="ea0a9-119">이 특성은 <xref:System.ServiceModel.SecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ea0a9-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="ea0a9-120">mode 특성</span><span class="sxs-lookup"><span data-stu-id="ea0a9-120">mode Attribute</span></span>  
  
|<span data-ttu-id="ea0a9-121">값</span><span class="sxs-lookup"><span data-stu-id="ea0a9-121">Value</span></span>|<span data-ttu-id="ea0a9-122">Description</span><span class="sxs-lookup"><span data-stu-id="ea0a9-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ea0a9-123">메시지</span><span class="sxs-lookup"><span data-stu-id="ea0a9-123">Message</span></span>|<span data-ttu-id="ea0a9-124">SOAP 전송은 무결성, 기밀성 및 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0a9-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="ea0a9-125">없음</span><span class="sxs-lookup"><span data-stu-id="ea0a9-125">None</span></span>|<span data-ttu-id="ea0a9-126">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0a9-126">Security is disabled.</span></span>|  
|<span data-ttu-id="ea0a9-127">전송</span><span class="sxs-lookup"><span data-stu-id="ea0a9-127">Transport</span></span>|<span data-ttu-id="ea0a9-128">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea0a9-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="ea0a9-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="ea0a9-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="ea0a9-130">HTTPS는 인증 및 기밀성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0a9-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="ea0a9-131">SOAP 메시지는 다양한 자격 증명 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0a9-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea0a9-132">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ea0a9-132">Child Elements</span></span>  
  
|<span data-ttu-id="ea0a9-133">요소</span><span class="sxs-lookup"><span data-stu-id="ea0a9-133">Element</span></span>|<span data-ttu-id="ea0a9-134">Description</span><span class="sxs-lookup"><span data-stu-id="ea0a9-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea0a9-135">\<transport></span><span class="sxs-lookup"><span data-stu-id="ea0a9-135">\<transport></span></span>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="ea0a9-136">이 바인딩으로 구성된 피어에서 보낸 보안 메시지의 전송 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0a9-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="ea0a9-137">이 요소는 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ea0a9-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ea0a9-138">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ea0a9-138">Parent Elements</span></span>  
  
|<span data-ttu-id="ea0a9-139">요소</span><span class="sxs-lookup"><span data-stu-id="ea0a9-139">Element</span></span>|<span data-ttu-id="ea0a9-140">설명</span><span class="sxs-lookup"><span data-stu-id="ea0a9-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea0a9-141">\<binding></span><span class="sxs-lookup"><span data-stu-id="ea0a9-141">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="ea0a9-142">[ \<> Netpeertcpbinding](netpeertcpbinding.md)의 모든 바인딩 기능을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0a9-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea0a9-143">설명</span><span class="sxs-lookup"><span data-stu-id="ea0a9-143">Remarks</span></span>  
 <span data-ttu-id="ea0a9-144">보안은 메시지 또는 전송별로 고유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0a9-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea0a9-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="ea0a9-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="ea0a9-146">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="ea0a9-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ea0a9-147">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="ea0a9-147">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="ea0a9-148">바인딩</span><span class="sxs-lookup"><span data-stu-id="ea0a9-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ea0a9-149">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="ea0a9-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ea0a9-150">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="ea0a9-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ea0a9-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="ea0a9-151">\<binding></span></span>](../../../misc/binding.md)
