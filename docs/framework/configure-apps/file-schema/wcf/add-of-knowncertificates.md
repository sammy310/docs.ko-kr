---
title: <knownCertificates>의 <add>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 3eb5bf74f909e6036154b7f5f7c6181b09fefbff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077721"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="5e174-102">\<추가 >의 \<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="5e174-102">\<add> of \<knownCertificates></span></span>
<span data-ttu-id="5e174-103">알려진 인증서 컬렉션에 X.509 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
 <span data-ttu-id="5e174-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5e174-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5e174-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="5e174-105">\<behaviors></span></span>  
<span data-ttu-id="5e174-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="5e174-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="5e174-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5e174-107">\<behavior></span></span>  
<span data-ttu-id="5e174-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="5e174-108">\<serviceCredentials></span></span>  
<span data-ttu-id="5e174-109">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="5e174-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="5e174-110">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="5e174-110">\<knownCertificates></span></span>  
<span data-ttu-id="5e174-111">\<add></span><span class="sxs-lookup"><span data-stu-id="5e174-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e174-112">구문</span><span class="sxs-lookup"><span data-stu-id="5e174-112">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e174-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5e174-113">Attributes and Elements</span></span>  
 <span data-ttu-id="5e174-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e174-115">특성</span><span class="sxs-lookup"><span data-stu-id="5e174-115">Attributes</span></span>  
  
|<span data-ttu-id="5e174-116">특성</span><span class="sxs-lookup"><span data-stu-id="5e174-116">Attribute</span></span>|<span data-ttu-id="5e174-117">설명</span><span class="sxs-lookup"><span data-stu-id="5e174-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e174-118">findValue</span><span class="sxs-lookup"><span data-stu-id="5e174-118">findValue</span></span>|<span data-ttu-id="5e174-119">문자열.</span><span class="sxs-lookup"><span data-stu-id="5e174-119">String.</span></span> <span data-ttu-id="5e174-120">검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-120">The value to search for.</span></span>|  
|<span data-ttu-id="5e174-121">storeLocation</span><span class="sxs-lookup"><span data-stu-id="5e174-121">storeLocation</span></span>|<span data-ttu-id="5e174-122">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-122">Enumeration.</span></span> <span data-ttu-id="5e174-123">검색할 두 저장소 위치 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-123">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="5e174-124">storeName</span><span class="sxs-lookup"><span data-stu-id="5e174-124">storeName</span></span>|<span data-ttu-id="5e174-125">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-125">Enumeration.</span></span> <span data-ttu-id="5e174-126">검색할 시스템 저장소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-126">One of the system stores to search.</span></span>|  
|<span data-ttu-id="5e174-127">x509FindType</span><span class="sxs-lookup"><span data-stu-id="5e174-127">x509FindType</span></span>|<span data-ttu-id="5e174-128">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-128">Enumeration.</span></span> <span data-ttu-id="5e174-129">검색할 인증서 필드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-129">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="5e174-130">findValue 특성</span><span class="sxs-lookup"><span data-stu-id="5e174-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="5e174-131">값</span><span class="sxs-lookup"><span data-stu-id="5e174-131">Value</span></span>|<span data-ttu-id="5e174-132">설명</span><span class="sxs-lookup"><span data-stu-id="5e174-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5e174-133">문자열</span><span class="sxs-lookup"><span data-stu-id="5e174-133">String</span></span>|<span data-ttu-id="5e174-134">이 값은 검색 중인 필드(X509FindType 특성으로 지정)에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="5e174-135">예를 들어, 지문을 검색할 경우 이 값은 16진수 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="5e174-136">x509FindType 특성</span><span class="sxs-lookup"><span data-stu-id="5e174-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="5e174-137">값</span><span class="sxs-lookup"><span data-stu-id="5e174-137">Value</span></span>|<span data-ttu-id="5e174-138">설명</span><span class="sxs-lookup"><span data-stu-id="5e174-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5e174-139">열거형</span><span class="sxs-lookup"><span data-stu-id="5e174-139">Enumeration</span></span>|<span data-ttu-id="5e174-140">값은 다음과 같습니다. FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, findbysubjectkeyidentifier가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="5e174-141">storeLocation 특성</span><span class="sxs-lookup"><span data-stu-id="5e174-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="5e174-142">값</span><span class="sxs-lookup"><span data-stu-id="5e174-142">Value</span></span>|<span data-ttu-id="5e174-143">설명</span><span class="sxs-lookup"><span data-stu-id="5e174-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5e174-144">열거형</span><span class="sxs-lookup"><span data-stu-id="5e174-144">Enumeration</span></span>|<span data-ttu-id="5e174-145">CurrentUser 또는 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="5e174-146">storeName 특성</span><span class="sxs-lookup"><span data-stu-id="5e174-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="5e174-147">값</span><span class="sxs-lookup"><span data-stu-id="5e174-147">Value</span></span>|<span data-ttu-id="5e174-148">설명</span><span class="sxs-lookup"><span data-stu-id="5e174-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5e174-149">열거형</span><span class="sxs-lookup"><span data-stu-id="5e174-149">Enumeration</span></span>|<span data-ttu-id="5e174-150">값은 다음과 같습니다. AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, 루트, TrustedPeople 및 TrustedPublisher 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e174-151">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5e174-151">Child Elements</span></span>  
 <span data-ttu-id="5e174-152">없음</span><span class="sxs-lookup"><span data-stu-id="5e174-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5e174-153">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5e174-153">Parent Elements</span></span>  
  
|<span data-ttu-id="5e174-154">요소</span><span class="sxs-lookup"><span data-stu-id="5e174-154">Element</span></span>|<span data-ttu-id="5e174-155">설명</span><span class="sxs-lookup"><span data-stu-id="5e174-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e174-156">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="5e174-156">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)|<span data-ttu-id="5e174-157">보안 토큰의 유효성을 검사하기 위해 STS(보안 토큰 서비스)에서 제공하는 X.509 인증서 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-157">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e174-158">설명</span><span class="sxs-lookup"><span data-stu-id="5e174-158">Remarks</span></span>  
 <span data-ttu-id="5e174-159">발급된 토큰 시나리오에는 3단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-159">The issued token scenario has three stages.</span></span> <span data-ttu-id="5e174-160">첫 번째 단계에서는 서비스에 액세스 하려는 클라이언트 라고 한 *보안 토큰 서비스*합니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-160">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="5e174-161">보안 토큰 서비스는 클라이언트를 인증한 다음 일반적으로 SAML(Security Assertions Markup Language) 토큰이라는 클라이언트 토큰을 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-161">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="5e174-162">클라이언트는 토큰을 통해 서비스에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-162">The client then returns to the service with the token.</span></span> <span data-ttu-id="5e174-163">서비스는 토큰 및 해당 클라이언트를 인증할 수 있는 데이터의 토큰을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-163">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="5e174-164">토큰을 인증하려면 보안 토큰 서비스가 사용하는 인증서를 서비스가 인식해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-164">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="5e174-165">합니다 [ \<issuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) 요소는 이러한 보안 토큰 서비스 인증서에 대 한 리포지토리입니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-165">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="5e174-166">인증서를 추가 하려면 사용 합니다 [ \<knownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-166">To add certificates, use the [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="5e174-167">삽입 된 [ \<추가 > 요소 \<knownCertificates > 요소](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) 다음 예와에서 같이 각 인증서에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-167">Insert an [\<add> element \<knownCertificates> Element](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="5e174-168">기본적으로 인증서는 보안 토큰 서비스에서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-168">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="5e174-169">이러한 "알려진" 인증서는 올바른 클라이언트만 서비스에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-169">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="5e174-170">이 구성 요소를 사용 하 여 자세한 정보 뿐만 아니라 페더레이션된 서비스에 의해 인증 되어야 클라이언트에 대 한 필수 조건, 참조 [방법: 페더레이션 서비스에서 자격 증명 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-170">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="5e174-171">페더레이션된 시나리오에 대 한 자세한 내용은 참조 하세요. [페더레이션 및 발급 된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-171">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e174-172">예제</span><span class="sxs-lookup"><span data-stu-id="5e174-172">Example</span></span>  
 <span data-ttu-id="5e174-173">다음 예제에서는 모든 STS 인증서에 대해 리포지토리에 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5e174-173">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <serviceCredentials>
      <issuedTokenAuthentication>
        <knownCertificates>
          <add findValue="www.contoso.com"
               storeLocation="LocalMachine"
               storeName="CertificateAuthority"
               x509FindType="FindByIssuerName" />
        </knownCertificates>
      </issuedTokenAuthentication>
    </serviceCredentials>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="5e174-174">참고자료</span><span class="sxs-lookup"><span data-stu-id="5e174-174">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="5e174-175">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="5e174-175">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)
- [<span data-ttu-id="5e174-176">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="5e174-176">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="5e174-177">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="5e174-177">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5e174-178">방법: 페더레이션 서비스에서 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="5e174-178">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="5e174-179">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="5e174-179">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
