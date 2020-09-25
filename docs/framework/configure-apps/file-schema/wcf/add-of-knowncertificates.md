---
title: <knownCertificates>의 <add>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 453593918de15613edb801cca8a16c9dbf71aa90
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176086"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="fee60-102">\<knownCertificates>의 \<add></span><span class="sxs-lookup"><span data-stu-id="fee60-102">\<add> of \<knownCertificates></span></span>

<span data-ttu-id="fee60-103">알려진 인증서 컬렉션에 X.509 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownCertificates>**](knowncertificates.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="fee60-104">구문</span><span class="sxs-lookup"><span data-stu-id="fee60-104">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fee60-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fee60-105">Attributes and Elements</span></span>  

 <span data-ttu-id="fee60-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fee60-107">특성</span><span class="sxs-lookup"><span data-stu-id="fee60-107">Attributes</span></span>  
  
|<span data-ttu-id="fee60-108">attribute</span><span class="sxs-lookup"><span data-stu-id="fee60-108">Attribute</span></span>|<span data-ttu-id="fee60-109">설명</span><span class="sxs-lookup"><span data-stu-id="fee60-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fee60-110">findValue</span><span class="sxs-lookup"><span data-stu-id="fee60-110">findValue</span></span>|<span data-ttu-id="fee60-111">문자열.</span><span class="sxs-lookup"><span data-stu-id="fee60-111">String.</span></span> <span data-ttu-id="fee60-112">검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-112">The value to search for.</span></span>|  
|<span data-ttu-id="fee60-113">storeLocation</span><span class="sxs-lookup"><span data-stu-id="fee60-113">storeLocation</span></span>|<span data-ttu-id="fee60-114">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-114">Enumeration.</span></span> <span data-ttu-id="fee60-115">검색할 두 저장소 위치 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-115">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="fee60-116">storeName</span><span class="sxs-lookup"><span data-stu-id="fee60-116">storeName</span></span>|<span data-ttu-id="fee60-117">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-117">Enumeration.</span></span> <span data-ttu-id="fee60-118">검색할 시스템 저장소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-118">One of the system stores to search.</span></span>|  
|<span data-ttu-id="fee60-119">x509FindType</span><span class="sxs-lookup"><span data-stu-id="fee60-119">x509FindType</span></span>|<span data-ttu-id="fee60-120">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-120">Enumeration.</span></span> <span data-ttu-id="fee60-121">검색할 인증서 필드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-121">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="fee60-122">findValue 특성</span><span class="sxs-lookup"><span data-stu-id="fee60-122">findValue Attribute</span></span>  
  
|<span data-ttu-id="fee60-123">Value</span><span class="sxs-lookup"><span data-stu-id="fee60-123">Value</span></span>|<span data-ttu-id="fee60-124">Description</span><span class="sxs-lookup"><span data-stu-id="fee60-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fee60-125">String</span><span class="sxs-lookup"><span data-stu-id="fee60-125">String</span></span>|<span data-ttu-id="fee60-126">이 값은 검색 중인 필드(X509FindType 특성으로 지정)에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-126">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="fee60-127">예를 들어, 지문을 검색할 경우 이 값은 16진수 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-127">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="fee60-128">x509FindType 특성</span><span class="sxs-lookup"><span data-stu-id="fee60-128">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="fee60-129">Value</span><span class="sxs-lookup"><span data-stu-id="fee60-129">Value</span></span>|<span data-ttu-id="fee60-130">설명</span><span class="sxs-lookup"><span data-stu-id="fee60-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fee60-131">열거형</span><span class="sxs-lookup"><span data-stu-id="fee60-131">Enumeration</span></span>|<span data-ttu-id="fee60-132">값에는 FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-132">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="fee60-133">storeLocation 특성</span><span class="sxs-lookup"><span data-stu-id="fee60-133">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="fee60-134">Value</span><span class="sxs-lookup"><span data-stu-id="fee60-134">Value</span></span>|<span data-ttu-id="fee60-135">설명</span><span class="sxs-lookup"><span data-stu-id="fee60-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fee60-136">열거형</span><span class="sxs-lookup"><span data-stu-id="fee60-136">Enumeration</span></span>|<span data-ttu-id="fee60-137">CurrentUser 또는 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-137">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="fee60-138">storeName 특성</span><span class="sxs-lookup"><span data-stu-id="fee60-138">storeName Attribute</span></span>  
  
|<span data-ttu-id="fee60-139">Value</span><span class="sxs-lookup"><span data-stu-id="fee60-139">Value</span></span>|<span data-ttu-id="fee60-140">설명</span><span class="sxs-lookup"><span data-stu-id="fee60-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fee60-141">열거형</span><span class="sxs-lookup"><span data-stu-id="fee60-141">Enumeration</span></span>|<span data-ttu-id="fee60-142">값에는 AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople 및 TrustedPublisher가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-142">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fee60-143">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fee60-143">Child Elements</span></span>  

 <span data-ttu-id="fee60-144">없음</span><span class="sxs-lookup"><span data-stu-id="fee60-144">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fee60-145">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fee60-145">Parent Elements</span></span>  
  
|<span data-ttu-id="fee60-146">요소</span><span class="sxs-lookup"><span data-stu-id="fee60-146">Element</span></span>|<span data-ttu-id="fee60-147">설명</span><span class="sxs-lookup"><span data-stu-id="fee60-147">Description</span></span>|  
|-------------|-----------------|  
|[\<knownCertificates>](knowncertificates.md)|<span data-ttu-id="fee60-148">보안 토큰의 유효성을 검사하기 위해 STS(보안 토큰 서비스)에서 제공하는 X.509 인증서 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-148">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fee60-149">설명</span><span class="sxs-lookup"><span data-stu-id="fee60-149">Remarks</span></span>  

 <span data-ttu-id="fee60-150">발급된 토큰 시나리오에는 3단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-150">The issued token scenario has three stages.</span></span> <span data-ttu-id="fee60-151">첫 번째 단계에서는 서비스에 액세스 하려는 클라이언트를 *보안 토큰 서비스*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-151">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="fee60-152">보안 토큰 서비스는 클라이언트를 인증한 다음 일반적으로 SAML(Security Assertions Markup Language) 토큰이라는 클라이언트 토큰을 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-152">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="fee60-153">클라이언트는 토큰을 통해 서비스에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-153">The client then returns to the service with the token.</span></span> <span data-ttu-id="fee60-154">서비스는 토큰 및 해당 클라이언트를 인증할 수 있는 데이터의 토큰을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-154">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="fee60-155">토큰을 인증하려면 보안 토큰 서비스가 사용하는 인증서를 서비스가 인식해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-155">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="fee60-156">[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)요소는 이러한 보안 토큰 서비스 인증서에 대 한 리포지토리입니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-156">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="fee60-157">인증서를 추가 하려면를 사용 [\<knownCertificates>](knowncertificates.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-157">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="fee60-158">다음 예제와 같이 각 인증서에 대 한 [ \<add> 요소 \<knownCertificates> 요소](add-of-knowncertificates.md) 를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-158">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="fee60-159">기본적으로 인증서는 보안 토큰 서비스에서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-159">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="fee60-160">이러한 "알려진" 인증서는 올바른 클라이언트만 서비스에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-160">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="fee60-161">페더레이션 서비스에서 클라이언트를 인증 하는 데 필요한 조건을 검토 하 고이 구성 요소를 사용 하는 방법에 대 한 자세한 내용은 [방법: 페더레이션 서비스에서 자격 증명 구성](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fee60-161">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="fee60-162">페더레이션된 시나리오에 대 한 자세한 내용은 [페더레이션 및 발급 된 토큰](../../../wcf/feature-details/federation-and-issued-tokens.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fee60-162">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fee60-163">예제</span><span class="sxs-lookup"><span data-stu-id="fee60-163">Example</span></span>  

 <span data-ttu-id="fee60-164">다음 예제에서는 모든 STS 인증서에 대해 리포지토리에 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fee60-164">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fee60-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fee60-165">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<knownCertificates>](knowncertificates.md)
- [<span data-ttu-id="fee60-166">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="fee60-166">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="fee60-167">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="fee60-167">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="fee60-168">방법: 페더레이션 서비스에서 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="fee60-168">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="fee60-169">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="fee60-169">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
