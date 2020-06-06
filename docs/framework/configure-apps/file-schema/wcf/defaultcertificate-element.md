---
title: <defaultCertificate> 요소
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: cce236bf80fa00f01a3b5f4680d975f83fde0c16
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400424"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="bbed3-102">\<defaultCertificate> 요소</span><span class="sxs-lookup"><span data-stu-id="bbed3-102">\<defaultCertificate> Element</span></span>
<span data-ttu-id="bbed3-103">서비스 또는 STS가 협상 프로토콜을 통해 인증서를 제공하지 않을 때 사용할 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="bbed3-104">구문</span><span class="sxs-lookup"><span data-stu-id="bbed3-104">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bbed3-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bbed3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="bbed3-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bbed3-107">특성</span><span class="sxs-lookup"><span data-stu-id="bbed3-107">Attributes</span></span>  
  
|<span data-ttu-id="bbed3-108">attribute</span><span class="sxs-lookup"><span data-stu-id="bbed3-108">Attribute</span></span>|<span data-ttu-id="bbed3-109">Description</span><span class="sxs-lookup"><span data-stu-id="bbed3-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bbed3-110">findValue</span><span class="sxs-lookup"><span data-stu-id="bbed3-110">findValue</span></span>|<span data-ttu-id="bbed3-111">문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-111">String.</span></span> <span data-ttu-id="bbed3-112">검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-112">The value to search for.</span></span>|  
|<span data-ttu-id="bbed3-113">x509FindType</span><span class="sxs-lookup"><span data-stu-id="bbed3-113">x509FindType</span></span>|<span data-ttu-id="bbed3-114">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-114">Enumeration.</span></span> <span data-ttu-id="bbed3-115">검색할 인증서 필드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-115">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="bbed3-116">storeLocation</span><span class="sxs-lookup"><span data-stu-id="bbed3-116">storeLocation</span></span>|<span data-ttu-id="bbed3-117">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-117">Enumeration.</span></span> <span data-ttu-id="bbed3-118">검색할 두 시스템 저장소 위치 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-118">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="bbed3-119">storeName</span><span class="sxs-lookup"><span data-stu-id="bbed3-119">storeName</span></span>|<span data-ttu-id="bbed3-120">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-120">Enumeration.</span></span> <span data-ttu-id="bbed3-121">검색할 시스템 저장소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-121">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="bbed3-122">findValue 특성</span><span class="sxs-lookup"><span data-stu-id="bbed3-122">findValue Attribute</span></span>  
  
|<span data-ttu-id="bbed3-123">값</span><span class="sxs-lookup"><span data-stu-id="bbed3-123">Value</span></span>|<span data-ttu-id="bbed3-124">Description</span><span class="sxs-lookup"><span data-stu-id="bbed3-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bbed3-125">String</span><span class="sxs-lookup"><span data-stu-id="bbed3-125">String</span></span>|<span data-ttu-id="bbed3-126">이 값은 검색 중인 필드(X509FindType 특성으로 지정)에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-126">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="bbed3-127">예를 들어, 지문을 검색할 경우 이 값은 16진수 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-127">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="bbed3-128">x509FindType 특성</span><span class="sxs-lookup"><span data-stu-id="bbed3-128">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="bbed3-129">값</span><span class="sxs-lookup"><span data-stu-id="bbed3-129">Value</span></span>|<span data-ttu-id="bbed3-130">Description</span><span class="sxs-lookup"><span data-stu-id="bbed3-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bbed3-131">열거형</span><span class="sxs-lookup"><span data-stu-id="bbed3-131">Enumeration</span></span>|<span data-ttu-id="bbed3-132">값에는 FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-132">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="bbed3-133">storeLocation 특성</span><span class="sxs-lookup"><span data-stu-id="bbed3-133">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="bbed3-134">값</span><span class="sxs-lookup"><span data-stu-id="bbed3-134">Value</span></span>|<span data-ttu-id="bbed3-135">Description</span><span class="sxs-lookup"><span data-stu-id="bbed3-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bbed3-136">열거형</span><span class="sxs-lookup"><span data-stu-id="bbed3-136">Enumeration</span></span>|<span data-ttu-id="bbed3-137">CurrentUser 또는 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-137">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="bbed3-138">storeName 특성</span><span class="sxs-lookup"><span data-stu-id="bbed3-138">storeName Attribute</span></span>  
  
|<span data-ttu-id="bbed3-139">값</span><span class="sxs-lookup"><span data-stu-id="bbed3-139">Value</span></span>|<span data-ttu-id="bbed3-140">Description</span><span class="sxs-lookup"><span data-stu-id="bbed3-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bbed3-141">열거형</span><span class="sxs-lookup"><span data-stu-id="bbed3-141">Enumeration</span></span>|<span data-ttu-id="bbed3-142">값에는 AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople 및 TrustedPublisher가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-142">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bbed3-143">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bbed3-143">Child Elements</span></span>  
 <span data-ttu-id="bbed3-144">없음</span><span class="sxs-lookup"><span data-stu-id="bbed3-144">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bbed3-145">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bbed3-145">Parent Elements</span></span>  
  
|<span data-ttu-id="bbed3-146">요소</span><span class="sxs-lookup"><span data-stu-id="bbed3-146">Element</span></span>|<span data-ttu-id="bbed3-147">Description</span><span class="sxs-lookup"><span data-stu-id="bbed3-147">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="bbed3-148">클라이언트에 대해 서비스를 인증할 때 사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-148">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbed3-149">설명</span><span class="sxs-lookup"><span data-stu-id="bbed3-149">Remarks</span></span>  
 <span data-ttu-id="bbed3-150">인증서 기반 메시지 보안을 사용하는 바인딩의 경우 서비스에 보내는 메시지를 암호화하는 데 이 구성 요소에 지정된 인증서를 사용하며, 서비스에서는 클라이언트로 보내는 회신에 서명하는 데 이 인증서를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-150">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="bbed3-151">이 구성 요소는 서비스가 인증서를 지정하지 않을 때 사용되는 단일 인증서를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-151">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbed3-152">예제</span><span class="sxs-lookup"><span data-stu-id="bbed3-152">Example</span></span>  
 <span data-ttu-id="bbed3-153">다음 예제에서는 URI가로 시작 하 `http://www.contoso.com` 는 끝점과 인증서 협상을 수행 하지 않는 다른 모든 끝점에 사용할 인증서를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbed3-153">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bbed3-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bbed3-154">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="bbed3-155">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="bbed3-155">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="bbed3-156">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="bbed3-156">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="bbed3-157">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="bbed3-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
