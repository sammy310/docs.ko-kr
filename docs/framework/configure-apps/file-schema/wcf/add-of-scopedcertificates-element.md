---
description: '다음에 대 한 자세한 정보: <add> <scopedCertificates> 요소'
title: <add> of <scopedCertificates> 요소
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: 4c267164ccf065edee79a6aaaa9aaddc14d95909
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750275"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="e8e1e-103">\<add> of \<scopedCertificates> 요소</span><span class="sxs-lookup"><span data-stu-id="e8e1e-103">\<add> of \<scopedCertificates> Element</span></span>

<span data-ttu-id="e8e1e-104">범위가 지정된 인증서 컬렉션에 X.509 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-104">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="e8e1e-105">구문</span><span class="sxs-lookup"><span data-stu-id="e8e1e-105">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8e1e-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e8e1e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="e8e1e-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8e1e-108">특성</span><span class="sxs-lookup"><span data-stu-id="e8e1e-108">Attributes</span></span>  
  
|<span data-ttu-id="e8e1e-109">attribute</span><span class="sxs-lookup"><span data-stu-id="e8e1e-109">Attribute</span></span>|<span data-ttu-id="e8e1e-110">설명</span><span class="sxs-lookup"><span data-stu-id="e8e1e-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8e1e-111">targetUri</span><span class="sxs-lookup"><span data-stu-id="e8e1e-111">targetUri</span></span>|<span data-ttu-id="e8e1e-112">문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-112">String.</span></span> <span data-ttu-id="e8e1e-113">인증서와 연결된 서비스의 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-113">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="e8e1e-114">findValue</span><span class="sxs-lookup"><span data-stu-id="e8e1e-114">findValue</span></span>|<span data-ttu-id="e8e1e-115">문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-115">String.</span></span> <span data-ttu-id="e8e1e-116">검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-116">The value to search for.</span></span>|  
|<span data-ttu-id="e8e1e-117">x509FindType</span><span class="sxs-lookup"><span data-stu-id="e8e1e-117">x509FindType</span></span>|<span data-ttu-id="e8e1e-118">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-118">Enumeration.</span></span> <span data-ttu-id="e8e1e-119">검색할 인증서 필드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-119">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="e8e1e-120">storeLocation</span><span class="sxs-lookup"><span data-stu-id="e8e1e-120">storeLocation</span></span>|<span data-ttu-id="e8e1e-121">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-121">Enumeration.</span></span> <span data-ttu-id="e8e1e-122">검색할 두 저장소 위치 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-122">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="e8e1e-123">storeName</span><span class="sxs-lookup"><span data-stu-id="e8e1e-123">storeName</span></span>|<span data-ttu-id="e8e1e-124">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-124">Enumeration.</span></span> <span data-ttu-id="e8e1e-125">검색할 시스템 저장소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-125">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="e8e1e-126">findValue 특성</span><span class="sxs-lookup"><span data-stu-id="e8e1e-126">findValue Attribute</span></span>  
  
|<span data-ttu-id="e8e1e-127">값</span><span class="sxs-lookup"><span data-stu-id="e8e1e-127">Value</span></span>|<span data-ttu-id="e8e1e-128">Description</span><span class="sxs-lookup"><span data-stu-id="e8e1e-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e8e1e-129">String</span><span class="sxs-lookup"><span data-stu-id="e8e1e-129">String</span></span>|<span data-ttu-id="e8e1e-130">이 값은 검색 중인 필드(X509FindType 특성으로 지정)에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-130">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="e8e1e-131">예를 들어, 지문을 검색할 경우 이 값은 16진수 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-131">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="e8e1e-132">x509FindType 특성</span><span class="sxs-lookup"><span data-stu-id="e8e1e-132">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="e8e1e-133">값</span><span class="sxs-lookup"><span data-stu-id="e8e1e-133">Value</span></span>|<span data-ttu-id="e8e1e-134">설명</span><span class="sxs-lookup"><span data-stu-id="e8e1e-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e8e1e-135">열거형</span><span class="sxs-lookup"><span data-stu-id="e8e1e-135">Enumeration</span></span>|<span data-ttu-id="e8e1e-136">값에는 FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-136">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="e8e1e-137">storeLocation 특성</span><span class="sxs-lookup"><span data-stu-id="e8e1e-137">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="e8e1e-138">값</span><span class="sxs-lookup"><span data-stu-id="e8e1e-138">Value</span></span>|<span data-ttu-id="e8e1e-139">설명</span><span class="sxs-lookup"><span data-stu-id="e8e1e-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e8e1e-140">열거형</span><span class="sxs-lookup"><span data-stu-id="e8e1e-140">Enumeration</span></span>|<span data-ttu-id="e8e1e-141">CurrentUser 또는 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-141">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="e8e1e-142">storeName 특성</span><span class="sxs-lookup"><span data-stu-id="e8e1e-142">storeName Attribute</span></span>  
  
|<span data-ttu-id="e8e1e-143">값</span><span class="sxs-lookup"><span data-stu-id="e8e1e-143">Value</span></span>|<span data-ttu-id="e8e1e-144">설명</span><span class="sxs-lookup"><span data-stu-id="e8e1e-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e8e1e-145">열거형</span><span class="sxs-lookup"><span data-stu-id="e8e1e-145">Enumeration</span></span>|<span data-ttu-id="e8e1e-146">값에는 AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople 및 TrustedPublisher가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-146">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8e1e-147">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e8e1e-147">Child Elements</span></span>  

 <span data-ttu-id="e8e1e-148">없음</span><span class="sxs-lookup"><span data-stu-id="e8e1e-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8e1e-149">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e8e1e-149">Parent Elements</span></span>  
  
|<span data-ttu-id="e8e1e-150">요소</span><span class="sxs-lookup"><span data-stu-id="e8e1e-150">Element</span></span>|<span data-ttu-id="e8e1e-151">설명</span><span class="sxs-lookup"><span data-stu-id="e8e1e-151">Description</span></span>|  
|-------------|-----------------|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="e8e1e-152">인증에 대해 범위가 지정된 특정 서비스가 제공하는 X.509 인증서 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-152">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8e1e-153">설명</span><span class="sxs-lookup"><span data-stu-id="e8e1e-153">Remarks</span></span>  

 <span data-ttu-id="e8e1e-154">이 요소를 사용하면 클라이언트가 통신할 서비스의 URL을 기반으로 사용할 서비스 인증서를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-154">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="e8e1e-155">이는 클라이언트가 여러 서비스 (종료 서비스 및 중간 보안 토큰 서비스)와 통신할 수 있는 발급 된 토큰 시나리오에서 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-155">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="e8e1e-156">인증서 기반 메시지 보안을 사용 하는 바인딩의 경우이 인증서는 서비스에 대 한 메시지를 암호화 하는 데 사용 되며, 클라이언트에 응답을 서명 하는 데 서비스에서 사용 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-156">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="e8e1e-157">바인딩을 수행할 때 서비스용 인증서가 필요하고 서비스 URL에 대한 특정 인증서를 ScopedCertificates에서 찾을 수 없는 경우, 기본 인증서가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-157">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="e8e1e-158">자세한 내용은 [방법: 페더레이션된 클라이언트 만들기](../../../wcf/feature-details/how-to-create-a-federated-client.md)의 "범위 인증서" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-158">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8e1e-159">예제</span><span class="sxs-lookup"><span data-stu-id="e8e1e-159">Example</span></span>  

 <span data-ttu-id="e8e1e-160">다음 예제에서는 컬렉션에 X.509 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e8e1e-160">The following example adds an X.509 certificate the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e8e1e-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8e1e-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="e8e1e-162">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="e8e1e-162">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="e8e1e-163">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="e8e1e-163">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="e8e1e-164">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="e8e1e-164">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="e8e1e-165">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="e8e1e-165">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
