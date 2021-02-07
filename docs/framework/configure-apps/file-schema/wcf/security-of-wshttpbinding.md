---
description: '다음에 대 한 자세한 정보:: <security><wsHttpBinding>'
title: <wsHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: 646d49bd67b2b544ae2616f206bfdeabf7806579
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683062"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="82aa5-103">\<wsHttpBinding>의 \<security></span><span class="sxs-lookup"><span data-stu-id="82aa5-103">\<security> of \<wsHttpBinding></span></span>

<span data-ttu-id="82aa5-104">의 보안 기능을 나타냅니다 [\<wsHttpBinding>](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="82aa5-104">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="82aa5-105">구문</span><span class="sxs-lookup"><span data-stu-id="82aa5-105">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="String"
             defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             defaultRealm="String" />
  <message clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           establishSecurityContext="Boolean"
           negotiateServiceCredential="Boolean" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82aa5-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="82aa5-106">Attributes and Elements</span></span>  

 <span data-ttu-id="82aa5-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82aa5-108">특성</span><span class="sxs-lookup"><span data-stu-id="82aa5-108">Attributes</span></span>  
  
|<span data-ttu-id="82aa5-109">attribute</span><span class="sxs-lookup"><span data-stu-id="82aa5-109">Attribute</span></span>|<span data-ttu-id="82aa5-110">설명</span><span class="sxs-lookup"><span data-stu-id="82aa5-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="82aa5-111">mode</span><span class="sxs-lookup"><span data-stu-id="82aa5-111">mode</span></span>|<span data-ttu-id="82aa5-112">필드.</span><span class="sxs-lookup"><span data-stu-id="82aa5-112">-   Optional.</span></span> <span data-ttu-id="82aa5-113">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-113">Specifies the type of security that is applied.</span></span> <span data-ttu-id="82aa5-114">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-114">The default is `Message`.</span></span><br /><span data-ttu-id="82aa5-115">-이 특성은 형식입니다 <xref:System.ServiceModel.SecurityMode> .</span><span class="sxs-lookup"><span data-stu-id="82aa5-115">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="82aa5-116">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="82aa5-116">Mode Attribute</span></span>  
  
|<span data-ttu-id="82aa5-117">값</span><span class="sxs-lookup"><span data-stu-id="82aa5-117">Value</span></span>|<span data-ttu-id="82aa5-118">설명</span><span class="sxs-lookup"><span data-stu-id="82aa5-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="82aa5-119">없음</span><span class="sxs-lookup"><span data-stu-id="82aa5-119">None</span></span>|<span data-ttu-id="82aa5-120">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-120">Security is disabled.</span></span>|  
|<span data-ttu-id="82aa5-121">전송</span><span class="sxs-lookup"><span data-stu-id="82aa5-121">Transport</span></span>|<span data-ttu-id="82aa5-122">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-122">Security is provided using HTTPS.</span></span> <span data-ttu-id="82aa5-123">서비스는 SSL 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-123">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="82aa5-124">메시지는 HTTPS를 사용하여 완전하게 보안 처리되며 서비스의 SSL 인증서를 사용하여 클라이언트에 의해 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-124">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="82aa5-125">클라이언트 인증은 `ClientCredentials`의</span><span class="sxs-lookup"><span data-stu-id="82aa5-125">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="82aa5-126">의입니다 [\<transport>](transport-of-wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="82aa5-126">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="82aa5-127">메시지</span><span class="sxs-lookup"><span data-stu-id="82aa5-127">Message</span></span>|<span data-ttu-id="82aa5-128">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-128">Security is provided using SOAP message security.</span></span> <span data-ttu-id="82aa5-129">기본적으로 SOAP 본문은 암호화 및 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-129">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="82aa5-130">이 모드는 서비스 자격 증명을 클라이언트에서 out of band 방식으로 사용할 수 있는지 여부, 사용할 알고리즘 모음, 그리고 Security.Message 속성을 통해 메시지 본문에 적용될 보호 수준과 같은 다양한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-130">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="82aa5-131">클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-131">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="82aa5-132">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="82aa5-132">TransportWithMessageCredential</span></span>|<span data-ttu-id="82aa5-133">이 모드에서 HTTPS는 무결성, 기밀성 및 서버 인증을 제공하고 SOAP 메시지 보안은 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-133">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="82aa5-134">기본적으로 클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-134">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82aa5-135">자식 요소</span><span class="sxs-lookup"><span data-stu-id="82aa5-135">Child Elements</span></span>  
  
|<span data-ttu-id="82aa5-136">요소</span><span class="sxs-lookup"><span data-stu-id="82aa5-136">Element</span></span>|<span data-ttu-id="82aa5-137">설명</span><span class="sxs-lookup"><span data-stu-id="82aa5-137">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-wshttpbinding.md)|<span data-ttu-id="82aa5-138">전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-138">Defines the transport security settings.</span></span> <span data-ttu-id="82aa5-139">이 요소는 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[\<message>](message-of-wshttpbinding.md)|<span data-ttu-id="82aa5-140">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-140">Defines the security settings for the message.</span></span> <span data-ttu-id="82aa5-141">이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-141">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="82aa5-142">부모 요소</span><span class="sxs-lookup"><span data-stu-id="82aa5-142">Parent Elements</span></span>  
  
|<span data-ttu-id="82aa5-143">요소</span><span class="sxs-lookup"><span data-stu-id="82aa5-143">Element</span></span>|<span data-ttu-id="82aa5-144">설명</span><span class="sxs-lookup"><span data-stu-id="82aa5-144">Description</span></span>|  
|-------------|-----------------|  
|[\<wsHttpBinding>](wshttpbinding.md)|<span data-ttu-id="82aa5-145">HTTP 전송 애플리케이션에 대한 보안 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-145">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82aa5-146">설명</span><span class="sxs-lookup"><span data-stu-id="82aa5-146">Remarks</span></span>  

 <span data-ttu-id="82aa5-147">WSHttpBinding 클래스는 WS-\* 사양을 구현하는 서비스와 상호 운용하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-147">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="82aa5-148">이 바인딩의 전송 보안은 HTTP 또는 SSL(Secure Sockets Layer) over HTTP입니다.</span><span class="sxs-lookup"><span data-stu-id="82aa5-148">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82aa5-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82aa5-149">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="82aa5-150">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="82aa5-150">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="82aa5-151">바인딩</span><span class="sxs-lookup"><span data-stu-id="82aa5-151">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="82aa5-152">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="82aa5-152">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="82aa5-153">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="82aa5-153">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
