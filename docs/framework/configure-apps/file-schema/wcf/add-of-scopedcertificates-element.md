---
title: <add>of <scopedCertificates> 요소
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: 9756d37527fcf888cad930b24677ae8e6a2c8fba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920052"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="fc8ba-102">\<\<scopedCertificates > 요소의 > 추가</span><span class="sxs-lookup"><span data-stu-id="fc8ba-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="fc8ba-103">범위가 지정된 인증서 컬렉션에 X.509 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
 <span data-ttu-id="fc8ba-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fc8ba-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fc8ba-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="fc8ba-105">\<behaviors></span></span>  
<span data-ttu-id="fc8ba-106">endpointBehaviors 섹션</span><span class="sxs-lookup"><span data-stu-id="fc8ba-106">endpointBehaviors section</span></span>  
<span data-ttu-id="fc8ba-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fc8ba-107">\<behavior></span></span>  
<span data-ttu-id="fc8ba-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="fc8ba-108">\<clientCredentials></span></span>  
<span data-ttu-id="fc8ba-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="fc8ba-109">\<serviceCertificate></span></span>  
<span data-ttu-id="fc8ba-110">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="fc8ba-110">\<scopedCertificates></span></span>  
<span data-ttu-id="fc8ba-111">\<scopedCertificates >에 대 \<한 > 요소 추가</span><span class="sxs-lookup"><span data-stu-id="fc8ba-111">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc8ba-112">구문</span><span class="sxs-lookup"><span data-stu-id="fc8ba-112">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc8ba-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fc8ba-113">Attributes and Elements</span></span>  
 <span data-ttu-id="fc8ba-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc8ba-115">특성</span><span class="sxs-lookup"><span data-stu-id="fc8ba-115">Attributes</span></span>  
  
|<span data-ttu-id="fc8ba-116">특성</span><span class="sxs-lookup"><span data-stu-id="fc8ba-116">Attribute</span></span>|<span data-ttu-id="fc8ba-117">Description</span><span class="sxs-lookup"><span data-stu-id="fc8ba-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc8ba-118">targetUri</span><span class="sxs-lookup"><span data-stu-id="fc8ba-118">targetUri</span></span>|<span data-ttu-id="fc8ba-119">문자열.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-119">String.</span></span> <span data-ttu-id="fc8ba-120">인증서와 연결된 서비스의 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-120">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="fc8ba-121">findValue</span><span class="sxs-lookup"><span data-stu-id="fc8ba-121">findValue</span></span>|<span data-ttu-id="fc8ba-122">문자열.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-122">String.</span></span> <span data-ttu-id="fc8ba-123">검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-123">The value to search for.</span></span>|  
|<span data-ttu-id="fc8ba-124">x509FindType</span><span class="sxs-lookup"><span data-stu-id="fc8ba-124">x509FindType</span></span>|<span data-ttu-id="fc8ba-125">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-125">Enumeration.</span></span> <span data-ttu-id="fc8ba-126">검색할 인증서 필드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-126">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="fc8ba-127">storeLocation</span><span class="sxs-lookup"><span data-stu-id="fc8ba-127">storeLocation</span></span>|<span data-ttu-id="fc8ba-128">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-128">Enumeration.</span></span> <span data-ttu-id="fc8ba-129">검색할 두 저장소 위치 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-129">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="fc8ba-130">storeName</span><span class="sxs-lookup"><span data-stu-id="fc8ba-130">storeName</span></span>|<span data-ttu-id="fc8ba-131">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-131">Enumeration.</span></span> <span data-ttu-id="fc8ba-132">검색할 시스템 저장소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-132">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="fc8ba-133">findValue 특성</span><span class="sxs-lookup"><span data-stu-id="fc8ba-133">findValue Attribute</span></span>  
  
|<span data-ttu-id="fc8ba-134">값</span><span class="sxs-lookup"><span data-stu-id="fc8ba-134">Value</span></span>|<span data-ttu-id="fc8ba-135">설명</span><span class="sxs-lookup"><span data-stu-id="fc8ba-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fc8ba-136">문자열</span><span class="sxs-lookup"><span data-stu-id="fc8ba-136">String</span></span>|<span data-ttu-id="fc8ba-137">이 값은 검색 중인 필드(X509FindType 특성으로 지정)에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-137">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="fc8ba-138">예를 들어, 지문을 검색할 경우 이 값은 16진수 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-138">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="fc8ba-139">x509FindType 특성</span><span class="sxs-lookup"><span data-stu-id="fc8ba-139">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="fc8ba-140">값</span><span class="sxs-lookup"><span data-stu-id="fc8ba-140">Value</span></span>|<span data-ttu-id="fc8ba-141">설명</span><span class="sxs-lookup"><span data-stu-id="fc8ba-141">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fc8ba-142">열거형</span><span class="sxs-lookup"><span data-stu-id="fc8ba-142">Enumeration</span></span>|<span data-ttu-id="fc8ba-143">다음과 같은 값이 올 수 있습니다. FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-143">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="fc8ba-144">storeLocation 특성</span><span class="sxs-lookup"><span data-stu-id="fc8ba-144">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="fc8ba-145">값</span><span class="sxs-lookup"><span data-stu-id="fc8ba-145">Value</span></span>|<span data-ttu-id="fc8ba-146">Description</span><span class="sxs-lookup"><span data-stu-id="fc8ba-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fc8ba-147">열거형</span><span class="sxs-lookup"><span data-stu-id="fc8ba-147">Enumeration</span></span>|<span data-ttu-id="fc8ba-148">CurrentUser 또는 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-148">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="fc8ba-149">storeName 특성</span><span class="sxs-lookup"><span data-stu-id="fc8ba-149">storeName Attribute</span></span>  
  
|<span data-ttu-id="fc8ba-150">값</span><span class="sxs-lookup"><span data-stu-id="fc8ba-150">Value</span></span>|<span data-ttu-id="fc8ba-151">설명</span><span class="sxs-lookup"><span data-stu-id="fc8ba-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fc8ba-152">열거형</span><span class="sxs-lookup"><span data-stu-id="fc8ba-152">Enumeration</span></span>|<span data-ttu-id="fc8ba-153">다음과 같은 값이 올 수 있습니다. AddressBook, AuthRoot, CertificateAuthority, 허용 안 함, 내, 루트, 사용자 및 개인 게시자.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-153">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc8ba-154">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fc8ba-154">Child Elements</span></span>  
 <span data-ttu-id="fc8ba-155">없음</span><span class="sxs-lookup"><span data-stu-id="fc8ba-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc8ba-156">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fc8ba-156">Parent Elements</span></span>  
  
|<span data-ttu-id="fc8ba-157">요소</span><span class="sxs-lookup"><span data-stu-id="fc8ba-157">Element</span></span>|<span data-ttu-id="fc8ba-158">설명</span><span class="sxs-lookup"><span data-stu-id="fc8ba-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc8ba-159">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="fc8ba-159">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="fc8ba-160">인증에 대해 범위가 지정된 특정 서비스가 제공하는 X.509 인증서 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-160">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc8ba-161">설명</span><span class="sxs-lookup"><span data-stu-id="fc8ba-161">Remarks</span></span>  
 <span data-ttu-id="fc8ba-162">이 요소를 사용하면 클라이언트가 통신할 서비스의 URL을 기반으로 사용할 서비스 인증서를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-162">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="fc8ba-163">이는 클라이언트가 중간 보안 토큰 서비스뿐 아니라 끝 서비스 등의 여러 서비스와 통신할 수 있는 발급된 토큰 시나리오에서 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-163">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="fc8ba-164">인증서 기반 메시지 보안을 사용하는 바인딩의 경우 서비스에 보내는 메시지를 암호화하는 데 이 인증서를 사용하며, 서비스에서는 클라이언트로 보내는 회신에 서명하는 데 이 인증서를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-164">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="fc8ba-165">바인딩을 수행할 때 서비스용 인증서가 필요하고 서비스 URL에 대한 특정 인증서를 ScopedCertificates에서 찾을 수 없는 경우, 기본 인증서가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-165">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="fc8ba-166">자세한 내용은 [How to: "범위 인증서" 섹션을 참조 하세요. 페더레이션된 클라이언트](../../../wcf/feature-details/how-to-create-a-federated-client.md)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-166">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc8ba-167">예제</span><span class="sxs-lookup"><span data-stu-id="fc8ba-167">Example</span></span>  
 <span data-ttu-id="fc8ba-168">다음 예제에서는 컬렉션에 X.509 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8ba-168">The following example adds an X.509 certificate the collection.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <serviceCertificate>
          <scopedCertificates>
            <add targetUri="http://www.contoso.com"
                 findValue="www.Contoso.com"
                 storeLocation="LocalMachine"
                 storeName="Root"
                 x509FindType="FindByIssuerName" />
          </scopedCertificates>
        </serviceCertificate>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="fc8ba-169">참고자료</span><span class="sxs-lookup"><span data-stu-id="fc8ba-169">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="fc8ba-170">방법: 페더레이션된 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="fc8ba-170">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="fc8ba-171">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="fc8ba-171">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="fc8ba-172">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="fc8ba-172">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="fc8ba-173">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="fc8ba-173">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
