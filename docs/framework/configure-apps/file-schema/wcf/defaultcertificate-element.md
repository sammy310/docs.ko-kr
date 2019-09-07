---
title: <defaultCertificate> 요소
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: cce236bf80fa00f01a3b5f4680d975f83fde0c16
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400424"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="2255c-102">\<defaultCertificate > 요소</span><span class="sxs-lookup"><span data-stu-id="2255c-102">\<defaultCertificate> Element</span></span>
<span data-ttu-id="2255c-103">서비스 또는 STS가 협상 프로토콜을 통해 인증서를 제공하지 않을 때 사용할 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2255c-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
<span data-ttu-id="2255c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2255c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2255c-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2255c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2255c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2255c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="2255c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2255c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="2255c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2255c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="2255c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="2255c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="2255c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate >** ](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="2255c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="2255c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<defaultCertificate >**</span><span class="sxs-lookup"><span data-stu-id="2255c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2255c-112">구문</span><span class="sxs-lookup"><span data-stu-id="2255c-112">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2255c-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2255c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2255c-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2255c-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2255c-115">특성</span><span class="sxs-lookup"><span data-stu-id="2255c-115">Attributes</span></span>  
  
|<span data-ttu-id="2255c-116">특성</span><span class="sxs-lookup"><span data-stu-id="2255c-116">Attribute</span></span>|<span data-ttu-id="2255c-117">Description</span><span class="sxs-lookup"><span data-stu-id="2255c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2255c-118">findValue</span><span class="sxs-lookup"><span data-stu-id="2255c-118">findValue</span></span>|<span data-ttu-id="2255c-119">문자열.</span><span class="sxs-lookup"><span data-stu-id="2255c-119">String.</span></span> <span data-ttu-id="2255c-120">검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2255c-120">The value to search for.</span></span>|  
|<span data-ttu-id="2255c-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="2255c-121">x509FindType</span></span>|<span data-ttu-id="2255c-122">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="2255c-122">Enumeration.</span></span> <span data-ttu-id="2255c-123">검색할 인증서 필드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2255c-123">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="2255c-124">storeLocation</span><span class="sxs-lookup"><span data-stu-id="2255c-124">storeLocation</span></span>|<span data-ttu-id="2255c-125">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="2255c-125">Enumeration.</span></span> <span data-ttu-id="2255c-126">검색할 두 시스템 저장소 위치 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2255c-126">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="2255c-127">storeName</span><span class="sxs-lookup"><span data-stu-id="2255c-127">storeName</span></span>|<span data-ttu-id="2255c-128">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="2255c-128">Enumeration.</span></span> <span data-ttu-id="2255c-129">검색할 시스템 저장소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2255c-129">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="2255c-130">findValue 특성</span><span class="sxs-lookup"><span data-stu-id="2255c-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="2255c-131">값</span><span class="sxs-lookup"><span data-stu-id="2255c-131">Value</span></span>|<span data-ttu-id="2255c-132">Description</span><span class="sxs-lookup"><span data-stu-id="2255c-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2255c-133">String</span><span class="sxs-lookup"><span data-stu-id="2255c-133">String</span></span>|<span data-ttu-id="2255c-134">이 값은 검색 중인 필드(X509FindType 특성으로 지정)에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2255c-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="2255c-135">예를 들어, 지문을 검색할 경우 이 값은 16진수 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2255c-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="2255c-136">x509FindType 특성</span><span class="sxs-lookup"><span data-stu-id="2255c-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="2255c-137">값</span><span class="sxs-lookup"><span data-stu-id="2255c-137">Value</span></span>|<span data-ttu-id="2255c-138">설명</span><span class="sxs-lookup"><span data-stu-id="2255c-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2255c-139">열거형</span><span class="sxs-lookup"><span data-stu-id="2255c-139">Enumeration</span></span>|<span data-ttu-id="2255c-140">다음과 같은 값이 올 수 있습니다. FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="2255c-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="2255c-141">storeLocation 특성</span><span class="sxs-lookup"><span data-stu-id="2255c-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="2255c-142">값</span><span class="sxs-lookup"><span data-stu-id="2255c-142">Value</span></span>|<span data-ttu-id="2255c-143">설명</span><span class="sxs-lookup"><span data-stu-id="2255c-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2255c-144">열거형</span><span class="sxs-lookup"><span data-stu-id="2255c-144">Enumeration</span></span>|<span data-ttu-id="2255c-145">CurrentUser 또는 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="2255c-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="2255c-146">storeName 특성</span><span class="sxs-lookup"><span data-stu-id="2255c-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="2255c-147">값</span><span class="sxs-lookup"><span data-stu-id="2255c-147">Value</span></span>|<span data-ttu-id="2255c-148">설명</span><span class="sxs-lookup"><span data-stu-id="2255c-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2255c-149">열거형</span><span class="sxs-lookup"><span data-stu-id="2255c-149">Enumeration</span></span>|<span data-ttu-id="2255c-150">다음과 같은 값이 올 수 있습니다. AddressBook, AuthRoot, CertificateAuthority, 허용 안 함, 내, 루트, 사용자 및 개인 게시자.</span><span class="sxs-lookup"><span data-stu-id="2255c-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2255c-151">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2255c-151">Child Elements</span></span>  
 <span data-ttu-id="2255c-152">없음</span><span class="sxs-lookup"><span data-stu-id="2255c-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2255c-153">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2255c-153">Parent Elements</span></span>  
  
|<span data-ttu-id="2255c-154">요소</span><span class="sxs-lookup"><span data-stu-id="2255c-154">Element</span></span>|<span data-ttu-id="2255c-155">Description</span><span class="sxs-lookup"><span data-stu-id="2255c-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2255c-156">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="2255c-156">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="2255c-157">클라이언트에 대해 서비스를 인증할 때 사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2255c-157">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2255c-158">설명</span><span class="sxs-lookup"><span data-stu-id="2255c-158">Remarks</span></span>  
 <span data-ttu-id="2255c-159">인증서 기반 메시지 보안을 사용하는 바인딩의 경우 서비스에 보내는 메시지를 암호화하는 데 이 구성 요소에 지정된 인증서를 사용하며, 서비스에서는 클라이언트로 보내는 회신에 서명하는 데 이 인증서를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2255c-159">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="2255c-160">이 구성 요소는 서비스가 인증서를 지정하지 않을 때 사용되는 단일 인증서를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2255c-160">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2255c-161">예제</span><span class="sxs-lookup"><span data-stu-id="2255c-161">Example</span></span>  
 <span data-ttu-id="2255c-162">다음 예제에서는 URI가로 `http://www.contoso.com` 시작 하는 끝점과 인증서 협상을 수행 하지 않는 다른 모든 끝점에 사용할 인증서를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2255c-162">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2255c-163">참고자료</span><span class="sxs-lookup"><span data-stu-id="2255c-163">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="2255c-164">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="2255c-164">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="2255c-165">\<authentication></span><span class="sxs-lookup"><span data-stu-id="2255c-165">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="2255c-166">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="2255c-166">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="2255c-167">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="2255c-167">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
