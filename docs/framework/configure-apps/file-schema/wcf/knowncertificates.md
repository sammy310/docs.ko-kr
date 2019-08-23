---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 1210e6282a7dd6c40198693d4948a89efe841d59
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913535"
---
# <a name="knowncertificates"></a><span data-ttu-id="8be5a-101">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="8be5a-101">\<knownCertificates></span></span>
<span data-ttu-id="8be5a-102">STS(보안 토큰 서비스)에서 발급한 보안 자격 증명을 인증하기 위해 제공된 X.509 인증서 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8be5a-102">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="8be5a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8be5a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="8be5a-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="8be5a-104">\<behaviors></span></span>  
<span data-ttu-id="8be5a-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="8be5a-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="8be5a-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8be5a-106">\<behavior></span></span>  
<span data-ttu-id="8be5a-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="8be5a-107">\<serviceCredentials></span></span>  
<span data-ttu-id="8be5a-108">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="8be5a-108">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="8be5a-109">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="8be5a-109">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8be5a-110">구문</span><span class="sxs-lookup"><span data-stu-id="8be5a-110">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8be5a-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8be5a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8be5a-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8be5a-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8be5a-113">특성</span><span class="sxs-lookup"><span data-stu-id="8be5a-113">Attributes</span></span>  
 <span data-ttu-id="8be5a-114">없음</span><span class="sxs-lookup"><span data-stu-id="8be5a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8be5a-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8be5a-115">Child Elements</span></span>  
  
|<span data-ttu-id="8be5a-116">요소</span><span class="sxs-lookup"><span data-stu-id="8be5a-116">Element</span></span>|<span data-ttu-id="8be5a-117">설명</span><span class="sxs-lookup"><span data-stu-id="8be5a-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8be5a-118">\<add></span><span class="sxs-lookup"><span data-stu-id="8be5a-118">\<add></span></span>](add-of-knowncertificates.md)|<span data-ttu-id="8be5a-119">컬렉션에 X.509 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8be5a-119">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8be5a-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8be5a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8be5a-121">요소</span><span class="sxs-lookup"><span data-stu-id="8be5a-121">Element</span></span>|<span data-ttu-id="8be5a-122">설명</span><span class="sxs-lookup"><span data-stu-id="8be5a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8be5a-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="8be5a-123">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="8be5a-124">서비스 자격 증명으로 발급된 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8be5a-124">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8be5a-125">설명</span><span class="sxs-lookup"><span data-stu-id="8be5a-125">Remarks</span></span>  
 <span data-ttu-id="8be5a-126">발급된 토큰 시나리오에는 3단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be5a-126">The issued token scenario has three stages.</span></span> <span data-ttu-id="8be5a-127">첫 번째 단계에서는 서비스에 액세스 하려는 클라이언트를 *보안 토큰 서비스*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be5a-127">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="8be5a-128">보안 토큰 서비스는 클라이언트를 인증한 다음 일반적으로 SAML(Security Assertions Markup Language) 토큰이라는 클라이언트 토큰을 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="8be5a-128">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="8be5a-129">클라이언트는 토큰을 통해 서비스에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be5a-129">The client then returns to the service with the token.</span></span> <span data-ttu-id="8be5a-130">서비스는 토큰 및 해당 클라이언트를 인증할 수 있는 데이터의 토큰을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="8be5a-130">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="8be5a-131">토큰을 인증하려면 보안 토큰 서비스가 사용하는 인증서를 서비스가 인식해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be5a-131">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="8be5a-132">IssuedTokenAuthentication > 요소는 이러한 보안 토큰 서비스 인증서에 대 한 리포지토리입니다. [ \<](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="8be5a-132">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="8be5a-133">인증서를 추가 하려면 [ \<knowncertificates > 요소](knowncertificates.md)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be5a-133">To add certificates, use the [\<knownCertificates> element](knowncertificates.md).</span></span> <span data-ttu-id="8be5a-134">다음 예제와 같이 각 인증서에 대 한 [ 추가>를삽입합니다.\<](add-of-knowncertificates.md)</span><span class="sxs-lookup"><span data-stu-id="8be5a-134">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="8be5a-135">기본적으로 인증서는 보안 토큰 서비스에서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be5a-135">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="8be5a-136">이러한 "알려진" 인증서는 올바른 클라이언트만 서비스에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be5a-136">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="8be5a-137">페더레이션 서비스에서 클라이언트를 인증 하는 데 필요한 조건을 검토 하 고이 구성 요소 [를 사용 하는 방법에 대 한 자세한 내용은 방법: 페더레이션 서비스](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)에 대 한 자격 증명을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be5a-137">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="8be5a-138">페더레이션된 시나리오에 대 한 자세한 내용은 [페더레이션 및 발급 된 토큰](../../../wcf/feature-details/federation-and-issued-tokens.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8be5a-138">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="8be5a-139">구성에서 컬렉션을 채우는 방법을 보여 주는 예제는 [ \<추가 >](add-of-knowncertificates.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8be5a-139">For an example that shows how to populate the collection in configuration, see [\<add>](add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be5a-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="8be5a-140">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="8be5a-141">\<add></span><span class="sxs-lookup"><span data-stu-id="8be5a-141">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="8be5a-142">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="8be5a-142">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="8be5a-143">보안 동작</span><span class="sxs-lookup"><span data-stu-id="8be5a-143">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="8be5a-144">방법: 페더레이션 서비스에 대 한 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="8be5a-144">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="8be5a-145">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="8be5a-145">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="8be5a-146">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="8be5a-146">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8be5a-147">\<add></span><span class="sxs-lookup"><span data-stu-id="8be5a-147">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="8be5a-148">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="8be5a-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
