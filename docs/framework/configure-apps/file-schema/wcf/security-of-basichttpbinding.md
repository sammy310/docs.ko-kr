---
title: <basicHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: c8e4f2d000a155eecd2a6c7faaaf4af525b24ca3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738708"
---
# <a name="security-of-basichttpbinding"></a><span data-ttu-id="9a29d-102">\<basicHttpBinding>의 \<security></span><span class="sxs-lookup"><span data-stu-id="9a29d-102">\<security> of \<basicHttpBinding></span></span>
<span data-ttu-id="9a29d-103">의 보안 기능을 정의 합니다 [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="9a29d-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="9a29d-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a29d-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a29d-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9a29d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9a29d-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a29d-107">특성</span><span class="sxs-lookup"><span data-stu-id="9a29d-107">Attributes</span></span>  
  
|<span data-ttu-id="9a29d-108">attribute</span><span class="sxs-lookup"><span data-stu-id="9a29d-108">Attribute</span></span>|<span data-ttu-id="9a29d-109">Description</span><span class="sxs-lookup"><span data-stu-id="9a29d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a29d-110">mode</span><span class="sxs-lookup"><span data-stu-id="9a29d-110">mode</span></span>|<span data-ttu-id="9a29d-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-111">Optional.</span></span> <span data-ttu-id="9a29d-112">사용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-112">Specifies the type of security that is used.</span></span> <span data-ttu-id="9a29d-113">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-113">The default is `None`.</span></span> <span data-ttu-id="9a29d-114">이 특성은 <xref:System.ServiceModel.BasicHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-114">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="9a29d-115">mode 특성</span><span class="sxs-lookup"><span data-stu-id="9a29d-115">mode Attribute</span></span>  
  
|<span data-ttu-id="9a29d-116">값</span><span class="sxs-lookup"><span data-stu-id="9a29d-116">Value</span></span>|<span data-ttu-id="9a29d-117">Description</span><span class="sxs-lookup"><span data-stu-id="9a29d-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9a29d-118">None</span><span class="sxs-lookup"><span data-stu-id="9a29d-118">None</span></span>|<span data-ttu-id="9a29d-119">-전송 중에는 메시지의 보안이 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-119">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="9a29d-120">전송</span><span class="sxs-lookup"><span data-stu-id="9a29d-120">Transport</span></span>|<span data-ttu-id="9a29d-121">HTTPS 전송을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-121">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="9a29d-122">SOAP 메시지는 HTTPS를 통해 보안이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-122">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="9a29d-123">이 서비스는 서비스의 X.509 인증서를 사용하여 클라이언트에 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-123">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="9a29d-124">클라이언트는 제공된 ClientCredentialType을 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-124">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="9a29d-125">을 참조 하십시오 [\<transport>](transport-of-basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="9a29d-125">See the [\<transport>](transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="9a29d-126">메시지</span><span class="sxs-lookup"><span data-stu-id="9a29d-126">Message</span></span>|<span data-ttu-id="9a29d-127">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="9a29d-128">기본적으로 본문에는 암호화 및 서명이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-128">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="9a29d-129">이 바인딩에서는 클라이언트에 out of band 방식으로 서버 인증서가 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-129">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="9a29d-130">이 바인딩의 유효한 `ClientCredentialType`은 `Certificate`뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-130">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="9a29d-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="9a29d-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="9a29d-132">전송 보안에 의해 무결성, 기밀성 및 서버 인증이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-132">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="9a29d-133">클라이언트 인증은 SOAP 메시지 보안에 의해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-133">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="9a29d-134">이 모드는 사용자가 사용자 이름/암호를 사용하여 인증되며 메시지 전송 보호를 위한 기존의 HTTP 배포가 있는 경우에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-134">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="9a29d-135">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="9a29d-135">TransportCredentialOnly</span></span>|<span data-ttu-id="9a29d-136">이 모드는 메시지 무결성 및 기밀성을 제공하지 않으나</span><span class="sxs-lookup"><span data-stu-id="9a29d-136">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="9a29d-137">http 기반 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-137">It provides http-based client authentication.</span></span> <span data-ttu-id="9a29d-138">이 모드는 주의해서 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-138">This mode should be used with caution.</span></span> <span data-ttu-id="9a29d-139">다른 방법 (예: IPSec)에서 전송 보안을 제공 하는 환경에서 사용 해야 하며, WCF 인프라에서 클라이언트 인증만 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-139">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a29d-140">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9a29d-140">Child Elements</span></span>  
  
|<span data-ttu-id="9a29d-141">요소</span><span class="sxs-lookup"><span data-stu-id="9a29d-141">Element</span></span>|<span data-ttu-id="9a29d-142">Description</span><span class="sxs-lookup"><span data-stu-id="9a29d-142">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-basichttpbinding.md)|<span data-ttu-id="9a29d-143">기본 HTTP 서비스에 대한 전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-143">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="9a29d-144">이 요소는 <xref:System.ServiceModel.HttpTransportSecurity>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-144">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[\<message>](message-of-basichttpbinding.md)|<span data-ttu-id="9a29d-145">기본 HTTP 서비스에 대한 메시지 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-145">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="9a29d-146">이 요소는 <xref:System.ServiceModel.BasicHttpMessageSecurity>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-146">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9a29d-147">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9a29d-147">Parent Elements</span></span>  
  
|<span data-ttu-id="9a29d-148">요소</span><span class="sxs-lookup"><span data-stu-id="9a29d-148">Element</span></span>|<span data-ttu-id="9a29d-149">Description</span><span class="sxs-lookup"><span data-stu-id="9a29d-149">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a29d-150">바인딩</span><span class="sxs-lookup"><span data-stu-id="9a29d-150">binding</span></span>|<span data-ttu-id="9a29d-151">의 바인딩 요소 [\<basicHttpBinding>](basichttpbinding.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-151">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a29d-152">설명</span><span class="sxs-lookup"><span data-stu-id="9a29d-152">Remarks</span></span>  
 <span data-ttu-id="9a29d-153">기본적으로 SOAP 메시지는 보안이 설정 되지 않으며 클라이언트는 인증 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-153">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="9a29d-154">이 요소를 사용하면 `basicHttpBinding` 요소에 대한 추가 보안 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a29d-154">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a29d-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a29d-155">See also</span></span>

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="9a29d-156">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="9a29d-156">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9a29d-157">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="9a29d-157">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="9a29d-158">바인딩</span><span class="sxs-lookup"><span data-stu-id="9a29d-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9a29d-159">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="9a29d-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9a29d-160">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="9a29d-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
