---
title: <defaultCertificate> 요소
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: 93410e815a156f91db1962f05fb1aa6baca7f955
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919248"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="89306-102">\<defaultCertificate > 요소</span><span class="sxs-lookup"><span data-stu-id="89306-102">\<defaultCertificate> Element</span></span>
<span data-ttu-id="89306-103">서비스 또는 STS가 협상 프로토콜을 통해 인증서를 제공하지 않을 때 사용할 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89306-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
 <span data-ttu-id="89306-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="89306-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="89306-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="89306-105">\<behaviors></span></span>  
<span data-ttu-id="89306-106">endpointBehaviors 섹션</span><span class="sxs-lookup"><span data-stu-id="89306-106">endpointBehaviors section</span></span>  
<span data-ttu-id="89306-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="89306-107">\<behavior></span></span>  
<span data-ttu-id="89306-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="89306-108">\<clientCredentials></span></span>  
<span data-ttu-id="89306-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="89306-109">\<serviceCertificate></span></span>  
<span data-ttu-id="89306-110">\<defaultCertificate></span><span class="sxs-lookup"><span data-stu-id="89306-110">\<defaultCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89306-111">구문</span><span class="sxs-lookup"><span data-stu-id="89306-111">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89306-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="89306-112">Attributes and Elements</span></span>  
 <span data-ttu-id="89306-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="89306-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89306-114">특성</span><span class="sxs-lookup"><span data-stu-id="89306-114">Attributes</span></span>  
  
|<span data-ttu-id="89306-115">특성</span><span class="sxs-lookup"><span data-stu-id="89306-115">Attribute</span></span>|<span data-ttu-id="89306-116">Description</span><span class="sxs-lookup"><span data-stu-id="89306-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89306-117">findValue</span><span class="sxs-lookup"><span data-stu-id="89306-117">findValue</span></span>|<span data-ttu-id="89306-118">문자열.</span><span class="sxs-lookup"><span data-stu-id="89306-118">String.</span></span> <span data-ttu-id="89306-119">검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="89306-119">The value to search for.</span></span>|  
|<span data-ttu-id="89306-120">x509FindType</span><span class="sxs-lookup"><span data-stu-id="89306-120">x509FindType</span></span>|<span data-ttu-id="89306-121">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="89306-121">Enumeration.</span></span> <span data-ttu-id="89306-122">검색할 인증서 필드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="89306-122">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="89306-123">storeLocation</span><span class="sxs-lookup"><span data-stu-id="89306-123">storeLocation</span></span>|<span data-ttu-id="89306-124">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="89306-124">Enumeration.</span></span> <span data-ttu-id="89306-125">검색할 두 시스템 저장소 위치 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="89306-125">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="89306-126">storeName</span><span class="sxs-lookup"><span data-stu-id="89306-126">storeName</span></span>|<span data-ttu-id="89306-127">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="89306-127">Enumeration.</span></span> <span data-ttu-id="89306-128">검색할 시스템 저장소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="89306-128">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="89306-129">findValue 특성</span><span class="sxs-lookup"><span data-stu-id="89306-129">findValue Attribute</span></span>  
  
|<span data-ttu-id="89306-130">값</span><span class="sxs-lookup"><span data-stu-id="89306-130">Value</span></span>|<span data-ttu-id="89306-131">Description</span><span class="sxs-lookup"><span data-stu-id="89306-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="89306-132">String</span><span class="sxs-lookup"><span data-stu-id="89306-132">String</span></span>|<span data-ttu-id="89306-133">이 값은 검색 중인 필드(X509FindType 특성으로 지정)에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="89306-133">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="89306-134">예를 들어, 지문을 검색할 경우 이 값은 16진수 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89306-134">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="89306-135">x509FindType 특성</span><span class="sxs-lookup"><span data-stu-id="89306-135">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="89306-136">값</span><span class="sxs-lookup"><span data-stu-id="89306-136">Value</span></span>|<span data-ttu-id="89306-137">Description</span><span class="sxs-lookup"><span data-stu-id="89306-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="89306-138">열거형</span><span class="sxs-lookup"><span data-stu-id="89306-138">Enumeration</span></span>|<span data-ttu-id="89306-139">다음과 같은 값이 올 수 있습니다. FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="89306-139">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="89306-140">storeLocation 특성</span><span class="sxs-lookup"><span data-stu-id="89306-140">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="89306-141">값</span><span class="sxs-lookup"><span data-stu-id="89306-141">Value</span></span>|<span data-ttu-id="89306-142">설명</span><span class="sxs-lookup"><span data-stu-id="89306-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="89306-143">열거형</span><span class="sxs-lookup"><span data-stu-id="89306-143">Enumeration</span></span>|<span data-ttu-id="89306-144">CurrentUser 또는 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="89306-144">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="89306-145">storeName 특성</span><span class="sxs-lookup"><span data-stu-id="89306-145">storeName Attribute</span></span>  
  
|<span data-ttu-id="89306-146">값</span><span class="sxs-lookup"><span data-stu-id="89306-146">Value</span></span>|<span data-ttu-id="89306-147">설명</span><span class="sxs-lookup"><span data-stu-id="89306-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="89306-148">열거형</span><span class="sxs-lookup"><span data-stu-id="89306-148">Enumeration</span></span>|<span data-ttu-id="89306-149">다음과 같은 값이 올 수 있습니다. AddressBook, AuthRoot, CertificateAuthority, 허용 안 함, 내, 루트, 사용자 및 개인 게시자.</span><span class="sxs-lookup"><span data-stu-id="89306-149">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89306-150">자식 요소</span><span class="sxs-lookup"><span data-stu-id="89306-150">Child Elements</span></span>  
 <span data-ttu-id="89306-151">없음</span><span class="sxs-lookup"><span data-stu-id="89306-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89306-152">부모 요소</span><span class="sxs-lookup"><span data-stu-id="89306-152">Parent Elements</span></span>  
  
|<span data-ttu-id="89306-153">요소</span><span class="sxs-lookup"><span data-stu-id="89306-153">Element</span></span>|<span data-ttu-id="89306-154">Description</span><span class="sxs-lookup"><span data-stu-id="89306-154">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89306-155">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="89306-155">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="89306-156">클라이언트에 대해 서비스를 인증할 때 사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89306-156">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89306-157">설명</span><span class="sxs-lookup"><span data-stu-id="89306-157">Remarks</span></span>  
 <span data-ttu-id="89306-158">인증서 기반 메시지 보안을 사용하는 바인딩의 경우 서비스에 보내는 메시지를 암호화하는 데 이 구성 요소에 지정된 인증서를 사용하며, 서비스에서는 클라이언트로 보내는 회신에 서명하는 데 이 인증서를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89306-158">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="89306-159">이 구성 요소는 서비스가 인증서를 지정하지 않을 때 사용되는 단일 인증서를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="89306-159">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89306-160">예제</span><span class="sxs-lookup"><span data-stu-id="89306-160">Example</span></span>  
 <span data-ttu-id="89306-161">다음 예제에서는 URI가로 `http://www.contoso.com` 시작 하는 끝점과 인증서 협상을 수행 하지 않는 다른 모든 끝점에 사용할 인증서를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="89306-161">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="89306-162">참고자료</span><span class="sxs-lookup"><span data-stu-id="89306-162">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="89306-163">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="89306-163">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="89306-164">\<authentication></span><span class="sxs-lookup"><span data-stu-id="89306-164">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="89306-165">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="89306-165">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="89306-166">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="89306-166">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
