---
title: <serviceCredentials>의 <issuedTokenAuthentication>
ms.date: 03/30/2017
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
ms.openlocfilehash: 6d468a27ee05fb4dd8cf087d10e5d170783d3454
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400353"
---
# <a name="issuedtokenauthentication-of-servicecredentials"></a><span data-ttu-id="8211c-102">\<serviceCredentials의 \<issuedTokenAuthentication > ></span><span class="sxs-lookup"><span data-stu-id="8211c-102">\<issuedTokenAuthentication> of \<serviceCredentials></span></span>
<span data-ttu-id="8211c-103">서비스 자격 증명으로 발급된 사용자 지정 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-103">Specifies a custom token issued as a service credential.</span></span>  
  
<span data-ttu-id="8211c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8211c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8211c-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8211c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8211c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8211c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="8211c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8211c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="8211c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8211c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="8211c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="8211c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="8211c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuedTokenAuthentication >**</span><span class="sxs-lookup"><span data-stu-id="8211c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8211c-111">구문</span><span class="sxs-lookup"><span data-stu-id="8211c-111">Syntax</span></span>  
  
```xml  
<issuedTokenAuthentication allowUntrustedRsaIssuers="Boolean"
                           audienceUriMode="Always/BearerKeyOnly/Never"
                           customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                           certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                           revocationMode="NoCheck/Online/Offline"
                           samlSerializer="String"
                           trustedStoreLocation="CurrentUser/LocalMachine">
  <allowedAudienceUris>
    <add allowedAudienceUri="String" />
  </allowedAudienceUris>
  <knownCertificates>
    <add findValue="String"
         storeLocation="CurrentUser/LocalMachine"
         storeName=" CurrentUser/LocalMachine"
         x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8211c-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8211c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8211c-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8211c-114">특성</span><span class="sxs-lookup"><span data-stu-id="8211c-114">Attributes</span></span>  
  
|<span data-ttu-id="8211c-115">특성</span><span class="sxs-lookup"><span data-stu-id="8211c-115">Attribute</span></span>|<span data-ttu-id="8211c-116">설명</span><span class="sxs-lookup"><span data-stu-id="8211c-116">Description</span></span>|  
|---------------|-----------------|  
|`allowedAudienceUris`|<span data-ttu-id="8211c-117"><xref:System.IdentityModel.Tokens.SamlSecurityToken> 인스턴스에서 유효한 대상으로 지정할 수 있는 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 보안 토큰의 대상 URI 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-117">Gets the set of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span> <span data-ttu-id="8211c-118">이 특성 사용에 대한 자세한 내용은 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8211c-118">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span></span>|  
|`allowUntrustedRsaIssuers`|<span data-ttu-id="8211c-119">신뢰할 수 없는 RSA 인증서 발급자에 대한 허용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-119">A Boolean value that specifies if untrusted RSA certificate issuers are allowed.</span></span><br /><br /> <span data-ttu-id="8211c-120">인증서는 신뢰성 확인을 위해 CA(인증 기관)의 서명을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-120">Certificates are signed by certification authorities (CAs) to verify authenticity.</span></span> <span data-ttu-id="8211c-121">신뢰할 수 없는 발급자는 인증서 서명을 위한 신뢰성이 지정되지 않은 CA입니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-121">An untrusted issuer is a CA that is not specified to be trusted to sign certificates.</span></span>|  
|`audienceUriMode`|<span data-ttu-id="8211c-122"><xref:System.IdentityModel.Tokens.SamlSecurityToken> 보안 토큰의 <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>에 대해 유효성을 검사해야 하는지 여부를 지정하는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-122">Gets a value that specifies whether the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token's <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> should be validated.</span></span> <span data-ttu-id="8211c-123">이 값은 <xref:System.IdentityModel.Selectors.AudienceUriMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-123">This value is of type <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span></span> <span data-ttu-id="8211c-124">이 특성 사용에 대한 자세한 내용은 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8211c-124">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="8211c-125">인증서 유효성 검사 모드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-125">Sets the certificate validation mode.</span></span> <span data-ttu-id="8211c-126"><xref:System.ServiceModel.Security.X509CertificateValidationMode>의 유효한 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-126">One of the valid values of <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="8211c-127">`Custom`으로 설정되면 `customCertificateValidator`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-127">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="8211c-128">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-128">The default is `ChainTrust`.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="8211c-129">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-129">Optional string.</span></span> <span data-ttu-id="8211c-130">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-130">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="8211c-131">이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-131">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`revocationMode`|<span data-ttu-id="8211c-132">해지 검사의 수행 여부 및 이를 온라인 또는 오프라인으로 수행할지를 지정하는 해지 모드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-132">Sets the revocation mode that specifies whether a revocation check occurs, and if it is performed online or offline.</span></span> <span data-ttu-id="8211c-133">이 특성은 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-133">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span>|  
|`samlSerializer`|<span data-ttu-id="8211c-134">서비스 자격 증명에 사용되는 SamlSerializer의 형식을 지정하는 선택적 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-134">An optional string attribute that specifies the type of SamlSerializer that is used for the service credential.</span></span> <span data-ttu-id="8211c-135">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-135">The default is an empty string.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="8211c-136">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-136">Optional enumeration.</span></span> <span data-ttu-id="8211c-137">시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-137">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8211c-138">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8211c-138">Child Elements</span></span>  
  
|<span data-ttu-id="8211c-139">요소</span><span class="sxs-lookup"><span data-stu-id="8211c-139">Element</span></span>|<span data-ttu-id="8211c-140">Description</span><span class="sxs-lookup"><span data-stu-id="8211c-140">Description</span></span>|  
|-------------|-----------------|  
|`knownCertificates`|<span data-ttu-id="8211c-141">서비스 자격 증명에 대해 신뢰할 수 있는 발급자를 지정하는 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> 요소의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-141">Specifies a collection of <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> elements that specifies trusted issuers for the service credential.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8211c-142">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8211c-142">Parent Elements</span></span>  
  
|<span data-ttu-id="8211c-143">요소</span><span class="sxs-lookup"><span data-stu-id="8211c-143">Element</span></span>|<span data-ttu-id="8211c-144">설명</span><span class="sxs-lookup"><span data-stu-id="8211c-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8211c-145">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="8211c-145">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="8211c-146">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-146">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8211c-147">설명</span><span class="sxs-lookup"><span data-stu-id="8211c-147">Remarks</span></span>  
 <span data-ttu-id="8211c-148">발급된 토큰 시나리오에는 3단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-148">The issued token scenario has three stages.</span></span> <span data-ttu-id="8211c-149">첫 번째 단계에서는 서비스에 액세스 하려는 클라이언트를 *보안 토큰 서비스*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-149">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="8211c-150">보안 토큰 서비스는 클라이언트를 인증한 다음 일반적으로 SAML(Security Assertions Markup Language) 토큰이라는 클라이언트 토큰을 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-150">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="8211c-151">클라이언트는 토큰을 통해 서비스에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-151">The client then returns to the service with the token.</span></span> <span data-ttu-id="8211c-152">서비스는 토큰 및 해당 클라이언트를 인증할 수 있는 데이터의 토큰을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-152">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="8211c-153">토큰을 인증하려면 보안 토큰 서비스가 사용하는 인증서를 서비스가 인식해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-153">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="8211c-154">이 요소는 이러한 보안 토큰 서비스 인증서에 대한 리포지토리입니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-154">This element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="8211c-155">인증서를 추가 하려면 [ \<> knowncertificates](knowncertificates.md)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-155">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="8211c-156">다음 예제와 같이 각 인증서에 대 한 [ 추가>를삽입합니다.\<](add-of-knowncertificates.md)</span><span class="sxs-lookup"><span data-stu-id="8211c-156">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="8211c-157">기본적으로 인증서는 보안 토큰 서비스에서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-157">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="8211c-158">이러한 "알려진" 인증서는 올바른 클라이언트만 서비스에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-158">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="8211c-159">이 구성 요소를 [사용 하는 방법에 대 한 자세한 내용은 방법: 페더레이션 서비스](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)에 대 한 자격 증명을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8211c-159">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8211c-160">참고자료</span><span class="sxs-lookup"><span data-stu-id="8211c-160">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>
- [<span data-ttu-id="8211c-161">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="8211c-161">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8211c-162">방법: 페더레이션 서비스에 대 한 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="8211c-162">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
