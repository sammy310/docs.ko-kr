---
title: <add>of <scopedCertificates> 요소
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: b00a342108beca69a906fbf6212915768e98778f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398341"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="0f8cd-102">\<\<scopedCertificates > 요소의 > 추가</span><span class="sxs-lookup"><span data-stu-id="0f8cd-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="0f8cd-103">범위가 지정된 인증서 컬렉션에 X.509 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
<span data-ttu-id="0f8cd-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0f8cd-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0f8cd-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0f8cd-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0f8cd-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0f8cd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="0f8cd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0f8cd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="0f8cd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0f8cd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="0f8cd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="0f8cd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="0f8cd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate >** ](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="0f8cd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="0f8cd-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<scopedCertificates >** ](scopedcertificates-element.md)</span><span class="sxs-lookup"><span data-stu-id="0f8cd-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)</span></span>\
<span data-ttu-id="0f8cd-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="0f8cd-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f8cd-113">구문</span><span class="sxs-lookup"><span data-stu-id="0f8cd-113">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f8cd-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0f8cd-114">Attributes and Elements</span></span>  
 <span data-ttu-id="0f8cd-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f8cd-116">특성</span><span class="sxs-lookup"><span data-stu-id="0f8cd-116">Attributes</span></span>  
  
|<span data-ttu-id="0f8cd-117">특성</span><span class="sxs-lookup"><span data-stu-id="0f8cd-117">Attribute</span></span>|<span data-ttu-id="0f8cd-118">Description</span><span class="sxs-lookup"><span data-stu-id="0f8cd-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0f8cd-119">targetUri</span><span class="sxs-lookup"><span data-stu-id="0f8cd-119">targetUri</span></span>|<span data-ttu-id="0f8cd-120">문자열.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-120">String.</span></span> <span data-ttu-id="0f8cd-121">인증서와 연결된 서비스의 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-121">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="0f8cd-122">findValue</span><span class="sxs-lookup"><span data-stu-id="0f8cd-122">findValue</span></span>|<span data-ttu-id="0f8cd-123">문자열.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-123">String.</span></span> <span data-ttu-id="0f8cd-124">검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-124">The value to search for.</span></span>|  
|<span data-ttu-id="0f8cd-125">x509FindType</span><span class="sxs-lookup"><span data-stu-id="0f8cd-125">x509FindType</span></span>|<span data-ttu-id="0f8cd-126">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-126">Enumeration.</span></span> <span data-ttu-id="0f8cd-127">검색할 인증서 필드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-127">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="0f8cd-128">storeLocation</span><span class="sxs-lookup"><span data-stu-id="0f8cd-128">storeLocation</span></span>|<span data-ttu-id="0f8cd-129">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-129">Enumeration.</span></span> <span data-ttu-id="0f8cd-130">검색할 두 저장소 위치 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-130">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="0f8cd-131">storeName</span><span class="sxs-lookup"><span data-stu-id="0f8cd-131">storeName</span></span>|<span data-ttu-id="0f8cd-132">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-132">Enumeration.</span></span> <span data-ttu-id="0f8cd-133">검색할 시스템 저장소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-133">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="0f8cd-134">findValue 특성</span><span class="sxs-lookup"><span data-stu-id="0f8cd-134">findValue Attribute</span></span>  
  
|<span data-ttu-id="0f8cd-135">값</span><span class="sxs-lookup"><span data-stu-id="0f8cd-135">Value</span></span>|<span data-ttu-id="0f8cd-136">설명</span><span class="sxs-lookup"><span data-stu-id="0f8cd-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f8cd-137">String</span><span class="sxs-lookup"><span data-stu-id="0f8cd-137">String</span></span>|<span data-ttu-id="0f8cd-138">이 값은 검색 중인 필드(X509FindType 특성으로 지정)에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-138">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="0f8cd-139">예를 들어, 지문을 검색할 경우 이 값은 16진수 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-139">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="0f8cd-140">x509FindType 특성</span><span class="sxs-lookup"><span data-stu-id="0f8cd-140">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="0f8cd-141">값</span><span class="sxs-lookup"><span data-stu-id="0f8cd-141">Value</span></span>|<span data-ttu-id="0f8cd-142">Description</span><span class="sxs-lookup"><span data-stu-id="0f8cd-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f8cd-143">열거형</span><span class="sxs-lookup"><span data-stu-id="0f8cd-143">Enumeration</span></span>|<span data-ttu-id="0f8cd-144">다음과 같은 값이 올 수 있습니다. FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-144">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="0f8cd-145">storeLocation 특성</span><span class="sxs-lookup"><span data-stu-id="0f8cd-145">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="0f8cd-146">값</span><span class="sxs-lookup"><span data-stu-id="0f8cd-146">Value</span></span>|<span data-ttu-id="0f8cd-147">설명</span><span class="sxs-lookup"><span data-stu-id="0f8cd-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f8cd-148">열거형</span><span class="sxs-lookup"><span data-stu-id="0f8cd-148">Enumeration</span></span>|<span data-ttu-id="0f8cd-149">CurrentUser 또는 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-149">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="0f8cd-150">storeName 특성</span><span class="sxs-lookup"><span data-stu-id="0f8cd-150">storeName Attribute</span></span>  
  
|<span data-ttu-id="0f8cd-151">값</span><span class="sxs-lookup"><span data-stu-id="0f8cd-151">Value</span></span>|<span data-ttu-id="0f8cd-152">설명</span><span class="sxs-lookup"><span data-stu-id="0f8cd-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f8cd-153">열거형</span><span class="sxs-lookup"><span data-stu-id="0f8cd-153">Enumeration</span></span>|<span data-ttu-id="0f8cd-154">다음과 같은 값이 올 수 있습니다. AddressBook, AuthRoot, CertificateAuthority, 허용 안 함, 내, 루트, 사용자 및 개인 게시자.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-154">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f8cd-155">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0f8cd-155">Child Elements</span></span>  
 <span data-ttu-id="0f8cd-156">없음</span><span class="sxs-lookup"><span data-stu-id="0f8cd-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f8cd-157">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0f8cd-157">Parent Elements</span></span>  
  
|<span data-ttu-id="0f8cd-158">요소</span><span class="sxs-lookup"><span data-stu-id="0f8cd-158">Element</span></span>|<span data-ttu-id="0f8cd-159">Description</span><span class="sxs-lookup"><span data-stu-id="0f8cd-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f8cd-160">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="0f8cd-160">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="0f8cd-161">인증에 대해 범위가 지정된 특정 서비스가 제공하는 X.509 인증서 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-161">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f8cd-162">설명</span><span class="sxs-lookup"><span data-stu-id="0f8cd-162">Remarks</span></span>  
 <span data-ttu-id="0f8cd-163">이 요소를 사용하면 클라이언트가 통신할 서비스의 URL을 기반으로 사용할 서비스 인증서를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-163">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="0f8cd-164">이는 클라이언트가 중간 보안 토큰 서비스뿐 아니라 끝 서비스 등의 여러 서비스와 통신할 수 있는 발급된 토큰 시나리오에서 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-164">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="0f8cd-165">인증서 기반 메시지 보안을 사용하는 바인딩의 경우 서비스에 보내는 메시지를 암호화하는 데 이 인증서를 사용하며, 서비스에서는 클라이언트로 보내는 회신에 서명하는 데 이 인증서를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-165">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="0f8cd-166">바인딩을 수행할 때 서비스용 인증서가 필요하고 서비스 URL에 대한 특정 인증서를 ScopedCertificates에서 찾을 수 없는 경우, 기본 인증서가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-166">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="0f8cd-167">자세한 내용은 [How to: "범위 인증서" 섹션을 참조 하세요. 페더레이션된 클라이언트](../../../wcf/feature-details/how-to-create-a-federated-client.md)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-167">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f8cd-168">예제</span><span class="sxs-lookup"><span data-stu-id="0f8cd-168">Example</span></span>  
 <span data-ttu-id="0f8cd-169">다음 예제에서는 컬렉션에 X.509 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0f8cd-169">The following example adds an X.509 certificate the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0f8cd-170">참고자료</span><span class="sxs-lookup"><span data-stu-id="0f8cd-170">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="0f8cd-171">방법: 페더레이션된 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="0f8cd-171">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="0f8cd-172">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="0f8cd-172">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="0f8cd-173">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="0f8cd-173">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="0f8cd-174">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="0f8cd-174">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
