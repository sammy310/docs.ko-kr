---
title: <knownCertificates>의 <add>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 29b067e6ec20992084f9ab3bab087222bdd56da2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400618"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="5d704-102">\<knowncertificates의 \<> 추가 ></span><span class="sxs-lookup"><span data-stu-id="5d704-102">\<add> of \<knownCertificates></span></span>
<span data-ttu-id="5d704-103">알려진 인증서 컬렉션에 X.509 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
<span data-ttu-id="5d704-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5d704-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5d704-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5d704-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5d704-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5d704-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="5d704-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5d704-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="5d704-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5d704-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="5d704-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="5d704-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="5d704-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenAuthentication >** ](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="5d704-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)</span></span>\
<span data-ttu-id="5d704-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<knownCertificates >** ](knowncertificates.md)</span><span class="sxs-lookup"><span data-stu-id="5d704-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownCertificates>**](knowncertificates.md)</span></span>\
<span data-ttu-id="5d704-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="5d704-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d704-113">구문</span><span class="sxs-lookup"><span data-stu-id="5d704-113">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d704-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5d704-114">Attributes and Elements</span></span>  
 <span data-ttu-id="5d704-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d704-116">특성</span><span class="sxs-lookup"><span data-stu-id="5d704-116">Attributes</span></span>  
  
|<span data-ttu-id="5d704-117">특성</span><span class="sxs-lookup"><span data-stu-id="5d704-117">Attribute</span></span>|<span data-ttu-id="5d704-118">Description</span><span class="sxs-lookup"><span data-stu-id="5d704-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d704-119">findValue</span><span class="sxs-lookup"><span data-stu-id="5d704-119">findValue</span></span>|<span data-ttu-id="5d704-120">문자열.</span><span class="sxs-lookup"><span data-stu-id="5d704-120">String.</span></span> <span data-ttu-id="5d704-121">검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-121">The value to search for.</span></span>|  
|<span data-ttu-id="5d704-122">storeLocation</span><span class="sxs-lookup"><span data-stu-id="5d704-122">storeLocation</span></span>|<span data-ttu-id="5d704-123">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-123">Enumeration.</span></span> <span data-ttu-id="5d704-124">검색할 두 저장소 위치 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-124">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="5d704-125">storeName</span><span class="sxs-lookup"><span data-stu-id="5d704-125">storeName</span></span>|<span data-ttu-id="5d704-126">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-126">Enumeration.</span></span> <span data-ttu-id="5d704-127">검색할 시스템 저장소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-127">One of the system stores to search.</span></span>|  
|<span data-ttu-id="5d704-128">x509FindType</span><span class="sxs-lookup"><span data-stu-id="5d704-128">x509FindType</span></span>|<span data-ttu-id="5d704-129">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-129">Enumeration.</span></span> <span data-ttu-id="5d704-130">검색할 인증서 필드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-130">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="5d704-131">findValue 특성</span><span class="sxs-lookup"><span data-stu-id="5d704-131">findValue Attribute</span></span>  
  
|<span data-ttu-id="5d704-132">값</span><span class="sxs-lookup"><span data-stu-id="5d704-132">Value</span></span>|<span data-ttu-id="5d704-133">설명</span><span class="sxs-lookup"><span data-stu-id="5d704-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5d704-134">문자열</span><span class="sxs-lookup"><span data-stu-id="5d704-134">String</span></span>|<span data-ttu-id="5d704-135">이 값은 검색 중인 필드(X509FindType 특성으로 지정)에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-135">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="5d704-136">예를 들어, 지문을 검색할 경우 이 값은 16진수 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-136">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="5d704-137">x509FindType 특성</span><span class="sxs-lookup"><span data-stu-id="5d704-137">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="5d704-138">값</span><span class="sxs-lookup"><span data-stu-id="5d704-138">Value</span></span>|<span data-ttu-id="5d704-139">설명</span><span class="sxs-lookup"><span data-stu-id="5d704-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5d704-140">열거형</span><span class="sxs-lookup"><span data-stu-id="5d704-140">Enumeration</span></span>|<span data-ttu-id="5d704-141">다음과 같은 값이 올 수 있습니다. FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="5d704-141">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="5d704-142">storeLocation 특성</span><span class="sxs-lookup"><span data-stu-id="5d704-142">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="5d704-143">값</span><span class="sxs-lookup"><span data-stu-id="5d704-143">Value</span></span>|<span data-ttu-id="5d704-144">Description</span><span class="sxs-lookup"><span data-stu-id="5d704-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5d704-145">열거형</span><span class="sxs-lookup"><span data-stu-id="5d704-145">Enumeration</span></span>|<span data-ttu-id="5d704-146">CurrentUser 또는 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-146">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="5d704-147">storeName 특성</span><span class="sxs-lookup"><span data-stu-id="5d704-147">storeName Attribute</span></span>  
  
|<span data-ttu-id="5d704-148">값</span><span class="sxs-lookup"><span data-stu-id="5d704-148">Value</span></span>|<span data-ttu-id="5d704-149">Description</span><span class="sxs-lookup"><span data-stu-id="5d704-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5d704-150">열거형</span><span class="sxs-lookup"><span data-stu-id="5d704-150">Enumeration</span></span>|<span data-ttu-id="5d704-151">다음과 같은 값이 올 수 있습니다. AddressBook, AuthRoot, CertificateAuthority, 허용 안 함, 내, 루트, 사용자 및 개인 게시자.</span><span class="sxs-lookup"><span data-stu-id="5d704-151">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d704-152">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5d704-152">Child Elements</span></span>  
 <span data-ttu-id="5d704-153">없음</span><span class="sxs-lookup"><span data-stu-id="5d704-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d704-154">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5d704-154">Parent Elements</span></span>  
  
|<span data-ttu-id="5d704-155">요소</span><span class="sxs-lookup"><span data-stu-id="5d704-155">Element</span></span>|<span data-ttu-id="5d704-156">Description</span><span class="sxs-lookup"><span data-stu-id="5d704-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d704-157">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="5d704-157">\<knownCertificates></span></span>](knowncertificates.md)|<span data-ttu-id="5d704-158">보안 토큰의 유효성을 검사하기 위해 STS(보안 토큰 서비스)에서 제공하는 X.509 인증서 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-158">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d704-159">설명</span><span class="sxs-lookup"><span data-stu-id="5d704-159">Remarks</span></span>  
 <span data-ttu-id="5d704-160">발급된 토큰 시나리오에는 3단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-160">The issued token scenario has three stages.</span></span> <span data-ttu-id="5d704-161">첫 번째 단계에서는 서비스에 액세스 하려는 클라이언트를 *보안 토큰 서비스*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-161">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="5d704-162">보안 토큰 서비스는 클라이언트를 인증한 다음 일반적으로 SAML(Security Assertions Markup Language) 토큰이라는 클라이언트 토큰을 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-162">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="5d704-163">클라이언트는 토큰을 통해 서비스에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-163">The client then returns to the service with the token.</span></span> <span data-ttu-id="5d704-164">서비스는 토큰 및 해당 클라이언트를 인증할 수 있는 데이터의 토큰을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-164">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="5d704-165">토큰을 인증하려면 보안 토큰 서비스가 사용하는 인증서를 서비스가 인식해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-165">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="5d704-166">IssuedTokenAuthentication > 요소는 이러한 보안 토큰 서비스 인증서에 대 한 리포지토리입니다. [ \<](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="5d704-166">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="5d704-167">인증서를 추가 하려면 [ \<> knowncertificates](knowncertificates.md)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-167">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="5d704-168">다음 예제와 같이 각 인증서에 대 한 [ \<추가 > 요소 knowncertificates > 요소를 삽입 합니다. \<](add-of-knowncertificates.md)</span><span class="sxs-lookup"><span data-stu-id="5d704-168">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="5d704-169">기본적으로 인증서는 보안 토큰 서비스에서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-169">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="5d704-170">이러한 "알려진" 인증서는 올바른 클라이언트만 서비스에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-170">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="5d704-171">페더레이션 서비스에서 클라이언트를 인증 하는 데 필요한 조건을 검토 하 고이 구성 요소 [를 사용 하는 방법에 대 한 자세한 내용은 방법: 페더레이션 서비스](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)에 대 한 자격 증명을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-171">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="5d704-172">페더레이션된 시나리오에 대 한 자세한 내용은 [페더레이션 및 발급 된 토큰](../../../wcf/feature-details/federation-and-issued-tokens.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d704-172">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d704-173">예제</span><span class="sxs-lookup"><span data-stu-id="5d704-173">Example</span></span>  
 <span data-ttu-id="5d704-174">다음 예제에서는 모든 STS 인증서에 대해 리포지토리에 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5d704-174">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5d704-175">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d704-175">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="5d704-176">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="5d704-176">\<knownCertificates></span></span>](knowncertificates.md)
- [<span data-ttu-id="5d704-177">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="5d704-177">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="5d704-178">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="5d704-178">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5d704-179">방법: 페더레이션 서비스에 대 한 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="5d704-179">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="5d704-180">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="5d704-180">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
