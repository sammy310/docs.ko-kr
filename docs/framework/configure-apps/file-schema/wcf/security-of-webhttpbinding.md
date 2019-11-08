---
title: <webHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 77009dc950a608da9e0db3a7d09be67e1ed46137
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738628"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="66686-102">\<보안 > \<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="66686-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="66686-103">[\<webHttpBinding >](webhttpbinding.md)구성 된 끝점에 대 한 보안 요구 사항을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66686-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
<span data-ttu-id="66686-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="66686-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="66686-105">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="66686-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="66686-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="66686-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="66686-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<webHttpBinding >** ](webhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="66686-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)</span></span>\
<span data-ttu-id="66686-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="66686-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="66686-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**보안 >**</span><span class="sxs-lookup"><span data-stu-id="66686-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66686-110">구문</span><span class="sxs-lookup"><span data-stu-id="66686-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66686-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="66686-111">Attributes and Elements</span></span>  
 <span data-ttu-id="66686-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="66686-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66686-113">특성</span><span class="sxs-lookup"><span data-stu-id="66686-113">Attributes</span></span>  
  
|<span data-ttu-id="66686-114">특성</span><span class="sxs-lookup"><span data-stu-id="66686-114">Attribute</span></span>|<span data-ttu-id="66686-115">설명</span><span class="sxs-lookup"><span data-stu-id="66686-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="66686-116">모드</span><span class="sxs-lookup"><span data-stu-id="66686-116">mode</span></span>|<span data-ttu-id="66686-117">엔드포인트에서 전송 수준 보안을 사용하거나 보안을 사용하지 않는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66686-117">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="66686-118">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="66686-118">The default is `None`.</span></span> <span data-ttu-id="66686-119">이 특성은 <xref:System.ServiceModel.WebHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="66686-119">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="66686-120">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="66686-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="66686-121">값</span><span class="sxs-lookup"><span data-stu-id="66686-121">Value</span></span>|<span data-ttu-id="66686-122">설명</span><span class="sxs-lookup"><span data-stu-id="66686-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="66686-123">없음</span><span class="sxs-lookup"><span data-stu-id="66686-123">None</span></span>|<span data-ttu-id="66686-124">보안이 사용 하지 않도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="66686-124">Security is disabled.</span></span>|  
|<span data-ttu-id="66686-125">전송</span><span class="sxs-lookup"><span data-stu-id="66686-125">Transport</span></span>|<span data-ttu-id="66686-126">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="66686-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="66686-127">서비스는 SSL 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66686-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="66686-128">메시지는 HTTPS를 사용하여 완전하게 보안 처리되며, 서비스는 서비스의 SSL 인증서를 사용하여 클라이언트에 의해 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="66686-128">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="66686-129">클라이언트 인증은 [\<전송 >](transport-of-webhttpbinding.md)의 `ClientCredentialType` 특성을 통해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66686-129">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="66686-130">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="66686-130">TransportCredentialOnly</span></span>|<span data-ttu-id="66686-131">이 모드는 메시지 무결성 및 기밀성을 제공하지 않으나</span><span class="sxs-lookup"><span data-stu-id="66686-131">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="66686-132">HTTP 기반 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="66686-132">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="66686-133">이 모드는 주의 해 서 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66686-133">This mode should be used with caution.</span></span> <span data-ttu-id="66686-134">다른 방법 (예: IPSec)에서 전송 보안을 제공 하는 환경에서 사용 해야 하며, WCF 인프라에서 클라이언트 인증만 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="66686-134">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66686-135">자식 요소</span><span class="sxs-lookup"><span data-stu-id="66686-135">Child Elements</span></span>  
  
|<span data-ttu-id="66686-136">요소</span><span class="sxs-lookup"><span data-stu-id="66686-136">Element</span></span>|<span data-ttu-id="66686-137">설명</span><span class="sxs-lookup"><span data-stu-id="66686-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66686-138">\<전송 ></span><span class="sxs-lookup"><span data-stu-id="66686-138">\<transport></span></span>](transport-of-webhttpbinding.md)|<span data-ttu-id="66686-139">전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="66686-139">Defines the transport security settings.</span></span> <span data-ttu-id="66686-140">이 요소는 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="66686-140">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="66686-141">부모 요소</span><span class="sxs-lookup"><span data-stu-id="66686-141">Parent Elements</span></span>  
  
|<span data-ttu-id="66686-142">요소</span><span class="sxs-lookup"><span data-stu-id="66686-142">Element</span></span>|<span data-ttu-id="66686-143">설명</span><span class="sxs-lookup"><span data-stu-id="66686-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66686-144">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="66686-144">\<webHttpBinding></span></span>](webhttpbinding.md)|<span data-ttu-id="66686-145">SOAP 메시지 대신 HTTP 요청에 응답 하는 WCF (Windows Communication Foundation) 웹 서비스에 대 한 끝점을 구성 하는 데 사용 되는 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="66686-145">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="66686-146">참조</span><span class="sxs-lookup"><span data-stu-id="66686-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="66686-147">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="66686-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="66686-148">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="66686-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="66686-149">바인딩</span><span class="sxs-lookup"><span data-stu-id="66686-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="66686-150">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="66686-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="66686-151">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="66686-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="66686-152">\<binding ></span><span class="sxs-lookup"><span data-stu-id="66686-152">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="66686-153">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="66686-153">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
