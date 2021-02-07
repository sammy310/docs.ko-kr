---
description: '다음에 대 한 자세한 정보:: <add><knownCertificates>'
title: <knownCertificates>의 <add>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 1669495e6119a35543e39230fc5dcc986ee2dec5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750288"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="0191f-103">\<knownCertificates>의 \<add></span><span class="sxs-lookup"><span data-stu-id="0191f-103">\<add> of \<knownCertificates></span></span>

<span data-ttu-id="0191f-104">알려진 인증서 컬렉션에 X.509 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-104">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownCertificates>**](knowncertificates.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="0191f-105">구문</span><span class="sxs-lookup"><span data-stu-id="0191f-105">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0191f-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0191f-106">Attributes and Elements</span></span>  

 <span data-ttu-id="0191f-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0191f-108">특성</span><span class="sxs-lookup"><span data-stu-id="0191f-108">Attributes</span></span>  
  
|<span data-ttu-id="0191f-109">attribute</span><span class="sxs-lookup"><span data-stu-id="0191f-109">Attribute</span></span>|<span data-ttu-id="0191f-110">설명</span><span class="sxs-lookup"><span data-stu-id="0191f-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0191f-111">findValue</span><span class="sxs-lookup"><span data-stu-id="0191f-111">findValue</span></span>|<span data-ttu-id="0191f-112">문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-112">String.</span></span> <span data-ttu-id="0191f-113">검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-113">The value to search for.</span></span>|  
|<span data-ttu-id="0191f-114">storeLocation</span><span class="sxs-lookup"><span data-stu-id="0191f-114">storeLocation</span></span>|<span data-ttu-id="0191f-115">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-115">Enumeration.</span></span> <span data-ttu-id="0191f-116">검색할 두 저장소 위치 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-116">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="0191f-117">storeName</span><span class="sxs-lookup"><span data-stu-id="0191f-117">storeName</span></span>|<span data-ttu-id="0191f-118">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-118">Enumeration.</span></span> <span data-ttu-id="0191f-119">검색할 시스템 저장소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-119">One of the system stores to search.</span></span>|  
|<span data-ttu-id="0191f-120">x509FindType</span><span class="sxs-lookup"><span data-stu-id="0191f-120">x509FindType</span></span>|<span data-ttu-id="0191f-121">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-121">Enumeration.</span></span> <span data-ttu-id="0191f-122">검색할 인증서 필드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-122">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="0191f-123">findValue 특성</span><span class="sxs-lookup"><span data-stu-id="0191f-123">findValue Attribute</span></span>  
  
|<span data-ttu-id="0191f-124">값</span><span class="sxs-lookup"><span data-stu-id="0191f-124">Value</span></span>|<span data-ttu-id="0191f-125">Description</span><span class="sxs-lookup"><span data-stu-id="0191f-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0191f-126">String</span><span class="sxs-lookup"><span data-stu-id="0191f-126">String</span></span>|<span data-ttu-id="0191f-127">이 값은 검색 중인 필드(X509FindType 특성으로 지정)에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-127">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="0191f-128">예를 들어, 지문을 검색할 경우 이 값은 16진수 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-128">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="0191f-129">x509FindType 특성</span><span class="sxs-lookup"><span data-stu-id="0191f-129">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="0191f-130">값</span><span class="sxs-lookup"><span data-stu-id="0191f-130">Value</span></span>|<span data-ttu-id="0191f-131">설명</span><span class="sxs-lookup"><span data-stu-id="0191f-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0191f-132">열거형</span><span class="sxs-lookup"><span data-stu-id="0191f-132">Enumeration</span></span>|<span data-ttu-id="0191f-133">값에는 FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-133">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="0191f-134">storeLocation 특성</span><span class="sxs-lookup"><span data-stu-id="0191f-134">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="0191f-135">값</span><span class="sxs-lookup"><span data-stu-id="0191f-135">Value</span></span>|<span data-ttu-id="0191f-136">설명</span><span class="sxs-lookup"><span data-stu-id="0191f-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0191f-137">열거형</span><span class="sxs-lookup"><span data-stu-id="0191f-137">Enumeration</span></span>|<span data-ttu-id="0191f-138">CurrentUser 또는 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-138">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="0191f-139">storeName 특성</span><span class="sxs-lookup"><span data-stu-id="0191f-139">storeName Attribute</span></span>  
  
|<span data-ttu-id="0191f-140">값</span><span class="sxs-lookup"><span data-stu-id="0191f-140">Value</span></span>|<span data-ttu-id="0191f-141">설명</span><span class="sxs-lookup"><span data-stu-id="0191f-141">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0191f-142">열거형</span><span class="sxs-lookup"><span data-stu-id="0191f-142">Enumeration</span></span>|<span data-ttu-id="0191f-143">값에는 AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople 및 TrustedPublisher가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-143">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0191f-144">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0191f-144">Child Elements</span></span>  

 <span data-ttu-id="0191f-145">없음</span><span class="sxs-lookup"><span data-stu-id="0191f-145">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0191f-146">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0191f-146">Parent Elements</span></span>  
  
|<span data-ttu-id="0191f-147">요소</span><span class="sxs-lookup"><span data-stu-id="0191f-147">Element</span></span>|<span data-ttu-id="0191f-148">설명</span><span class="sxs-lookup"><span data-stu-id="0191f-148">Description</span></span>|  
|-------------|-----------------|  
|[\<knownCertificates>](knowncertificates.md)|<span data-ttu-id="0191f-149">보안 토큰의 유효성을 검사하기 위해 STS(보안 토큰 서비스)에서 제공하는 X.509 인증서 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-149">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0191f-150">설명</span><span class="sxs-lookup"><span data-stu-id="0191f-150">Remarks</span></span>  

 <span data-ttu-id="0191f-151">발급된 토큰 시나리오에는 3단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-151">The issued token scenario has three stages.</span></span> <span data-ttu-id="0191f-152">첫 번째 단계에서는 서비스에 액세스 하려는 클라이언트를 *보안 토큰 서비스* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-152">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="0191f-153">보안 토큰 서비스는 클라이언트를 인증한 다음 일반적으로 SAML(Security Assertions Markup Language) 토큰이라는 클라이언트 토큰을 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-153">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="0191f-154">클라이언트는 토큰을 통해 서비스에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-154">The client then returns to the service with the token.</span></span> <span data-ttu-id="0191f-155">서비스는 토큰 및 해당 클라이언트를 인증할 수 있는 데이터의 토큰을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-155">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="0191f-156">토큰을 인증하려면 보안 토큰 서비스가 사용하는 인증서를 서비스가 인식해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-156">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="0191f-157">[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)요소는 이러한 보안 토큰 서비스 인증서에 대 한 리포지토리입니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-157">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="0191f-158">인증서를 추가 하려면를 사용 [\<knownCertificates>](knowncertificates.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-158">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="0191f-159">다음 예제와 같이 각 인증서에 대 한 [ \<add> 요소 \<knownCertificates> 요소](add-of-knowncertificates.md) 를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-159">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="0191f-160">기본적으로 인증서는 보안 토큰 서비스에서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-160">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="0191f-161">이러한 "알려진" 인증서는 올바른 클라이언트만 서비스에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-161">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="0191f-162">페더레이션 서비스에서 클라이언트를 인증 하는 데 필요한 조건을 검토 하 고이 구성 요소를 사용 하는 방법에 대 한 자세한 내용은 [방법: 페더레이션 서비스에서 자격 증명 구성](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0191f-162">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="0191f-163">페더레이션된 시나리오에 대 한 자세한 내용은 [페더레이션 및 발급 된 토큰](../../../wcf/feature-details/federation-and-issued-tokens.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0191f-163">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0191f-164">예제</span><span class="sxs-lookup"><span data-stu-id="0191f-164">Example</span></span>  

 <span data-ttu-id="0191f-165">다음 예제에서는 모든 STS 인증서에 대해 리포지토리에 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0191f-165">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0191f-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0191f-166">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<knownCertificates>](knowncertificates.md)
- [<span data-ttu-id="0191f-167">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="0191f-167">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="0191f-168">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="0191f-168">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0191f-169">방법: 페더레이션 서비스에서 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="0191f-169">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="0191f-170">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="0191f-170">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
