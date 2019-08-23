---
title: <webHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 806cf8524ed1a1439ca85a4b918e8e486e5dc94b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936585"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="11f1c-102">\<webHttpBinding >의 \<보안 ></span><span class="sxs-lookup"><span data-stu-id="11f1c-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="11f1c-103">[ \<WebHttpBinding >](webhttpbinding.md)구성 된 끝점에 대 한 보안 요구 사항을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="11f1c-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
 <span data-ttu-id="11f1c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="11f1c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="11f1c-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="11f1c-105">\<bindings></span></span>  
<span data-ttu-id="11f1c-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="11f1c-106">\<webHttpBinding></span></span>  
<span data-ttu-id="11f1c-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="11f1c-107">\<binding></span></span>  
<span data-ttu-id="11f1c-108">\<security></span><span class="sxs-lookup"><span data-stu-id="11f1c-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11f1c-109">구문</span><span class="sxs-lookup"><span data-stu-id="11f1c-109">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <bindings>
    <webHttpBinding>
      <binding name = "String">
        <security mode="None/Transport/TransportCredentialOnly">
          <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                     realm="String" />
        </security>
      </binding>
    </webHttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11f1c-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="11f1c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="11f1c-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="11f1c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11f1c-112">특성</span><span class="sxs-lookup"><span data-stu-id="11f1c-112">Attributes</span></span>  
  
|<span data-ttu-id="11f1c-113">특성</span><span class="sxs-lookup"><span data-stu-id="11f1c-113">Attribute</span></span>|<span data-ttu-id="11f1c-114">Description</span><span class="sxs-lookup"><span data-stu-id="11f1c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="11f1c-115">모드</span><span class="sxs-lookup"><span data-stu-id="11f1c-115">mode</span></span>|<span data-ttu-id="11f1c-116">엔드포인트에서 전송 수준 보안을 사용하거나 보안을 사용하지 않는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="11f1c-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="11f1c-117">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="11f1c-117">The default is `None`.</span></span> <span data-ttu-id="11f1c-118">이 특성은 <xref:System.ServiceModel.WebHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="11f1c-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="11f1c-119">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="11f1c-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="11f1c-120">값</span><span class="sxs-lookup"><span data-stu-id="11f1c-120">Value</span></span>|<span data-ttu-id="11f1c-121">설명</span><span class="sxs-lookup"><span data-stu-id="11f1c-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="11f1c-122">없음</span><span class="sxs-lookup"><span data-stu-id="11f1c-122">None</span></span>|<span data-ttu-id="11f1c-123">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11f1c-123">Security is disabled.</span></span>|  
|<span data-ttu-id="11f1c-124">전송</span><span class="sxs-lookup"><span data-stu-id="11f1c-124">Transport</span></span>|<span data-ttu-id="11f1c-125">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="11f1c-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="11f1c-126">서비스는 SSL 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11f1c-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="11f1c-127">메시지는 HTTPS를 사용하여 완전하게 보안 처리되며, 서비스는 서비스의 SSL 인증서를 사용하여 클라이언트에 의해 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="11f1c-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="11f1c-128">클라이언트 인증은 `ClientCredentialType` [ \<전송 >](transport-of-webhttpbinding.md)의 특성을 통해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11f1c-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="11f1c-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="11f1c-129">TransportCredentialOnly</span></span>|<span data-ttu-id="11f1c-130">이 모드는 메시지 무결성 및 기밀성을 제공하지 않으나</span><span class="sxs-lookup"><span data-stu-id="11f1c-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="11f1c-131">HTTP 기반 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="11f1c-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="11f1c-132">이 모드는 주의해서 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11f1c-132">This mode should be used with caution.</span></span> <span data-ttu-id="11f1c-133">다른 방법 (예: IPSec)에서 전송 보안을 제공 하는 환경에서 사용 해야 하며, WCF 인프라에서 클라이언트 인증만 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="11f1c-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11f1c-134">자식 요소</span><span class="sxs-lookup"><span data-stu-id="11f1c-134">Child Elements</span></span>  
  
|<span data-ttu-id="11f1c-135">요소</span><span class="sxs-lookup"><span data-stu-id="11f1c-135">Element</span></span>|<span data-ttu-id="11f1c-136">설명</span><span class="sxs-lookup"><span data-stu-id="11f1c-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11f1c-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="11f1c-137">\<transport></span></span>](transport-of-webhttpbinding.md)|<span data-ttu-id="11f1c-138">전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="11f1c-138">Defines the transport security settings.</span></span> <span data-ttu-id="11f1c-139">이 요소는 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="11f1c-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="11f1c-140">부모 요소</span><span class="sxs-lookup"><span data-stu-id="11f1c-140">Parent Elements</span></span>  
  
|<span data-ttu-id="11f1c-141">요소</span><span class="sxs-lookup"><span data-stu-id="11f1c-141">Element</span></span>|<span data-ttu-id="11f1c-142">설명</span><span class="sxs-lookup"><span data-stu-id="11f1c-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11f1c-143">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="11f1c-143">\<webHttpBinding></span></span>](webhttpbinding.md)|<span data-ttu-id="11f1c-144">SOAP 메시지 대신 HTTP 요청에 응답 하는 WCF (Windows Communication Foundation) 웹 서비스에 대 한 끝점을 구성 하는 데 사용 되는 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="11f1c-144">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11f1c-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="11f1c-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="11f1c-146">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="11f1c-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="11f1c-147">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="11f1c-147">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="11f1c-148">바인딩</span><span class="sxs-lookup"><span data-stu-id="11f1c-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="11f1c-149">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="11f1c-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="11f1c-150">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="11f1c-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="11f1c-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="11f1c-151">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="11f1c-152">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="11f1c-152">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
