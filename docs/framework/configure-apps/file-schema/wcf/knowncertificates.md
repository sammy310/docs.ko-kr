---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 23fe19258e09e9e8a5e05a94ccef0e40ee1cb5fd
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400331"
---
# <a name="knowncertificates"></a><span data-ttu-id="80165-101">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="80165-101">\<knownCertificates></span></span>
<span data-ttu-id="80165-102">STS(보안 토큰 서비스)에서 발급한 보안 자격 증명을 인증하기 위해 제공된 X.509 인증서 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80165-102">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
<span data-ttu-id="80165-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="80165-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="80165-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="80165-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="80165-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="80165-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="80165-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="80165-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="80165-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="80165-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="80165-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="80165-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="80165-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenAuthentication >** ](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="80165-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)</span></span>\
<span data-ttu-id="80165-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<knownCertificates >**</span><span class="sxs-lookup"><span data-stu-id="80165-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownCertificates>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80165-111">구문</span><span class="sxs-lookup"><span data-stu-id="80165-111">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80165-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="80165-112">Attributes and Elements</span></span>  
 <span data-ttu-id="80165-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="80165-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80165-114">특성</span><span class="sxs-lookup"><span data-stu-id="80165-114">Attributes</span></span>  
 <span data-ttu-id="80165-115">없음</span><span class="sxs-lookup"><span data-stu-id="80165-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="80165-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="80165-116">Child Elements</span></span>  
  
|<span data-ttu-id="80165-117">요소</span><span class="sxs-lookup"><span data-stu-id="80165-117">Element</span></span>|<span data-ttu-id="80165-118">설명</span><span class="sxs-lookup"><span data-stu-id="80165-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80165-119">\<add></span><span class="sxs-lookup"><span data-stu-id="80165-119">\<add></span></span>](add-of-knowncertificates.md)|<span data-ttu-id="80165-120">컬렉션에 X.509 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="80165-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80165-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="80165-121">Parent Elements</span></span>  
  
|<span data-ttu-id="80165-122">요소</span><span class="sxs-lookup"><span data-stu-id="80165-122">Element</span></span>|<span data-ttu-id="80165-123">설명</span><span class="sxs-lookup"><span data-stu-id="80165-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80165-124">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="80165-124">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="80165-125">서비스 자격 증명으로 발급된 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="80165-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80165-126">설명</span><span class="sxs-lookup"><span data-stu-id="80165-126">Remarks</span></span>  
 <span data-ttu-id="80165-127">발급된 토큰 시나리오에는 3단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80165-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="80165-128">첫 번째 단계에서는 서비스에 액세스 하려는 클라이언트를 *보안 토큰 서비스*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="80165-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="80165-129">보안 토큰 서비스는 클라이언트를 인증한 다음 일반적으로 SAML(Security Assertions Markup Language) 토큰이라는 클라이언트 토큰을 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="80165-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="80165-130">클라이언트는 토큰을 통해 서비스에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="80165-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="80165-131">서비스는 토큰 및 해당 클라이언트를 인증할 수 있는 데이터의 토큰을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="80165-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="80165-132">토큰을 인증하려면 보안 토큰 서비스가 사용하는 인증서를 서비스가 인식해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80165-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="80165-133">IssuedTokenAuthentication > 요소는 이러한 보안 토큰 서비스 인증서에 대 한 리포지토리입니다. [ \<](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="80165-133">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="80165-134">인증서를 추가 하려면 [ \<knowncertificates > 요소](knowncertificates.md)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="80165-134">To add certificates, use the [\<knownCertificates> element](knowncertificates.md).</span></span> <span data-ttu-id="80165-135">다음 예제와 같이 각 인증서에 대 한 [ 추가>를삽입합니다.\<](add-of-knowncertificates.md)</span><span class="sxs-lookup"><span data-stu-id="80165-135">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>
  <knownCertificates>
    <add findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="My"
         X509FindType="FindBySubjectName" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
 <span data-ttu-id="80165-136">기본적으로 인증서는 보안 토큰 서비스에서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80165-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="80165-137">이러한 "알려진" 인증서는 올바른 클라이언트만 서비스에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="80165-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="80165-138">페더레이션 서비스에서 클라이언트를 인증 하는 데 필요한 조건을 검토 하 고이 구성 요소 [를 사용 하는 방법에 대 한 자세한 내용은 방법: 페더레이션 서비스](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)에 대 한 자격 증명을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="80165-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="80165-139">페더레이션된 시나리오에 대 한 자세한 내용은 [페더레이션 및 발급 된 토큰](../../../wcf/feature-details/federation-and-issued-tokens.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="80165-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="80165-140">구성에서 컬렉션을 채우는 방법을 보여 주는 예제는 [ \<추가 >](add-of-knowncertificates.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="80165-140">For an example that shows how to populate the collection in configuration, see [\<add>](add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80165-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="80165-141">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="80165-142">\<add></span><span class="sxs-lookup"><span data-stu-id="80165-142">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="80165-143">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="80165-143">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="80165-144">보안 동작</span><span class="sxs-lookup"><span data-stu-id="80165-144">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="80165-145">방법: 페더레이션 서비스에 대 한 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="80165-145">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="80165-146">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="80165-146">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="80165-147">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="80165-147">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="80165-148">\<add></span><span class="sxs-lookup"><span data-stu-id="80165-148">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="80165-149">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="80165-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
