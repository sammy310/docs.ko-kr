---
title: <wsHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: b66b5228cab9dbc35502a13a2d0fe56ce4c6a18d
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738588"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="bd0a5-102">\<wsHttpBinding의 \<보안 > ></span><span class="sxs-lookup"><span data-stu-id="bd0a5-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="bd0a5-103">[\<wsHttpBinding >](wshttpbinding.md)의 보안 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
<span data-ttu-id="bd0a5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bd0a5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bd0a5-105">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="bd0a5-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bd0a5-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="bd0a5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="bd0a5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsHttpBinding >** ](wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="bd0a5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)</span></span>\
<span data-ttu-id="bd0a5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="bd0a5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="bd0a5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**보안 >**</span><span class="sxs-lookup"><span data-stu-id="bd0a5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd0a5-110">구문</span><span class="sxs-lookup"><span data-stu-id="bd0a5-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd0a5-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bd0a5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bd0a5-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd0a5-113">특성</span><span class="sxs-lookup"><span data-stu-id="bd0a5-113">Attributes</span></span>  
  
|<span data-ttu-id="bd0a5-114">특성</span><span class="sxs-lookup"><span data-stu-id="bd0a5-114">Attribute</span></span>|<span data-ttu-id="bd0a5-115">설명</span><span class="sxs-lookup"><span data-stu-id="bd0a5-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bd0a5-116">모드</span><span class="sxs-lookup"><span data-stu-id="bd0a5-116">mode</span></span>|<span data-ttu-id="bd0a5-117">필드.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-117">-   Optional.</span></span> <span data-ttu-id="bd0a5-118">적용 되는 보안 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="bd0a5-119">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-119">The default is `Message`.</span></span><br /><span data-ttu-id="bd0a5-120">-이 특성은 <xref:System.ServiceModel.SecurityMode>유형입니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-120">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="bd0a5-121">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="bd0a5-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="bd0a5-122">값</span><span class="sxs-lookup"><span data-stu-id="bd0a5-122">Value</span></span>|<span data-ttu-id="bd0a5-123">설명</span><span class="sxs-lookup"><span data-stu-id="bd0a5-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bd0a5-124">없음</span><span class="sxs-lookup"><span data-stu-id="bd0a5-124">None</span></span>|<span data-ttu-id="bd0a5-125">보안이 사용 하지 않도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-125">Security is disabled.</span></span>|  
|<span data-ttu-id="bd0a5-126">전송</span><span class="sxs-lookup"><span data-stu-id="bd0a5-126">Transport</span></span>|<span data-ttu-id="bd0a5-127">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-127">Security is provided using HTTPS.</span></span> <span data-ttu-id="bd0a5-128">서비스는 SSL 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-128">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="bd0a5-129">메시지는 HTTPS를 사용하여 완전하게 보안 처리되며 서비스의 SSL 인증서를 사용하여 클라이언트에 의해 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-129">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="bd0a5-130">클라이언트 인증은 `ClientCredentials`의</span><span class="sxs-lookup"><span data-stu-id="bd0a5-130">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="bd0a5-131">[\<전송 >](transport-of-wshttpbinding.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-131">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="bd0a5-132">메시지</span><span class="sxs-lookup"><span data-stu-id="bd0a5-132">Message</span></span>|<span data-ttu-id="bd0a5-133">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-133">Security is provided using SOAP message security.</span></span> <span data-ttu-id="bd0a5-134">기본적으로 SOAP 본문은 암호화 및 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-134">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="bd0a5-135">이 모드는 서비스 자격 증명을 클라이언트에서 out of band 방식으로 사용할 수 있는지 여부, 사용할 알고리즘 모음, 그리고 Security.Message 속성을 통해 메시지 본문에 적용될 보호 수준과 같은 다양한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-135">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="bd0a5-136">클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-136">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="bd0a5-137">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="bd0a5-137">TransportWithMessageCredential</span></span>|<span data-ttu-id="bd0a5-138">이 모드에서 HTTPS는 무결성, 기밀성 및 서버 인증을 제공하고 SOAP 메시지 보안은 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-138">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="bd0a5-139">기본적으로 클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-139">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bd0a5-140">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bd0a5-140">Child Elements</span></span>  
  
|<span data-ttu-id="bd0a5-141">요소</span><span class="sxs-lookup"><span data-stu-id="bd0a5-141">Element</span></span>|<span data-ttu-id="bd0a5-142">설명</span><span class="sxs-lookup"><span data-stu-id="bd0a5-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd0a5-143">\<전송 ></span><span class="sxs-lookup"><span data-stu-id="bd0a5-143">\<transport></span></span>](transport-of-wshttpbinding.md)|<span data-ttu-id="bd0a5-144">전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-144">Defines the transport security settings.</span></span> <span data-ttu-id="bd0a5-145">이 요소는 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-145">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="bd0a5-146">\<message ></span><span class="sxs-lookup"><span data-stu-id="bd0a5-146">\<message></span></span>](message-of-wshttpbinding.md)|<span data-ttu-id="bd0a5-147">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-147">Defines the security settings for the message.</span></span> <span data-ttu-id="bd0a5-148">이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-148">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bd0a5-149">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bd0a5-149">Parent Elements</span></span>  
  
|<span data-ttu-id="bd0a5-150">요소</span><span class="sxs-lookup"><span data-stu-id="bd0a5-150">Element</span></span>|<span data-ttu-id="bd0a5-151">설명</span><span class="sxs-lookup"><span data-stu-id="bd0a5-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd0a5-152">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="bd0a5-152">\<wsHttpBinding></span></span>](wshttpbinding.md)|<span data-ttu-id="bd0a5-153">HTTP 전송 애플리케이션에 대한 보안 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-153">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd0a5-154">주의</span><span class="sxs-lookup"><span data-stu-id="bd0a5-154">Remarks</span></span>  
 <span data-ttu-id="bd0a5-155">WSHttpBinding 클래스는 WS-\* 사양을 구현하는 서비스와 상호 운용하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-155">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="bd0a5-156">이 바인딩에 대 한 전송 보안은 HTTP 또는 HTTPS를 통한 SSL(Secure Sockets Layer) (SSL)입니다.</span><span class="sxs-lookup"><span data-stu-id="bd0a5-156">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd0a5-157">참조</span><span class="sxs-lookup"><span data-stu-id="bd0a5-157">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="bd0a5-158">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="bd0a5-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="bd0a5-159">바인딩</span><span class="sxs-lookup"><span data-stu-id="bd0a5-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="bd0a5-160">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="bd0a5-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="bd0a5-161">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="bd0a5-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="bd0a5-162">\<binding ></span><span class="sxs-lookup"><span data-stu-id="bd0a5-162">\<binding></span></span>](bindings.md)
