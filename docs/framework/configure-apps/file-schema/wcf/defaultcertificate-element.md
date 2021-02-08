---
description: '다음에 대 한 자세한 정보: <defaultCertificate> 요소'
title: <defaultCertificate> 요소
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: 580236e521e91c8b475586f6c6378630960f233c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803921"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="bab07-103">\<defaultCertificate> 요소</span><span class="sxs-lookup"><span data-stu-id="bab07-103">\<defaultCertificate> Element</span></span>

<span data-ttu-id="bab07-104">서비스 또는 STS가 협상 프로토콜을 통해 인증서를 제공하지 않을 때 사용할 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-104">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="bab07-105">구문</span><span class="sxs-lookup"><span data-stu-id="bab07-105">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bab07-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bab07-106">Attributes and Elements</span></span>  

 <span data-ttu-id="bab07-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bab07-108">특성</span><span class="sxs-lookup"><span data-stu-id="bab07-108">Attributes</span></span>  
  
|<span data-ttu-id="bab07-109">attribute</span><span class="sxs-lookup"><span data-stu-id="bab07-109">Attribute</span></span>|<span data-ttu-id="bab07-110">설명</span><span class="sxs-lookup"><span data-stu-id="bab07-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bab07-111">findValue</span><span class="sxs-lookup"><span data-stu-id="bab07-111">findValue</span></span>|<span data-ttu-id="bab07-112">문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-112">String.</span></span> <span data-ttu-id="bab07-113">검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-113">The value to search for.</span></span>|  
|<span data-ttu-id="bab07-114">x509FindType</span><span class="sxs-lookup"><span data-stu-id="bab07-114">x509FindType</span></span>|<span data-ttu-id="bab07-115">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-115">Enumeration.</span></span> <span data-ttu-id="bab07-116">검색할 인증서 필드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-116">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="bab07-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="bab07-117">storeLocation</span></span>|<span data-ttu-id="bab07-118">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-118">Enumeration.</span></span> <span data-ttu-id="bab07-119">검색할 두 시스템 저장소 위치 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-119">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="bab07-120">storeName</span><span class="sxs-lookup"><span data-stu-id="bab07-120">storeName</span></span>|<span data-ttu-id="bab07-121">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-121">Enumeration.</span></span> <span data-ttu-id="bab07-122">검색할 시스템 저장소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-122">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="bab07-123">findValue 특성</span><span class="sxs-lookup"><span data-stu-id="bab07-123">findValue Attribute</span></span>  
  
|<span data-ttu-id="bab07-124">값</span><span class="sxs-lookup"><span data-stu-id="bab07-124">Value</span></span>|<span data-ttu-id="bab07-125">Description</span><span class="sxs-lookup"><span data-stu-id="bab07-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bab07-126">String</span><span class="sxs-lookup"><span data-stu-id="bab07-126">String</span></span>|<span data-ttu-id="bab07-127">이 값은 검색 중인 필드(X509FindType 특성으로 지정)에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-127">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="bab07-128">예를 들어, 지문을 검색할 경우 이 값은 16진수 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-128">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="bab07-129">x509FindType 특성</span><span class="sxs-lookup"><span data-stu-id="bab07-129">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="bab07-130">값</span><span class="sxs-lookup"><span data-stu-id="bab07-130">Value</span></span>|<span data-ttu-id="bab07-131">설명</span><span class="sxs-lookup"><span data-stu-id="bab07-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bab07-132">열거형</span><span class="sxs-lookup"><span data-stu-id="bab07-132">Enumeration</span></span>|<span data-ttu-id="bab07-133">값에는 FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-133">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="bab07-134">storeLocation 특성</span><span class="sxs-lookup"><span data-stu-id="bab07-134">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="bab07-135">값</span><span class="sxs-lookup"><span data-stu-id="bab07-135">Value</span></span>|<span data-ttu-id="bab07-136">설명</span><span class="sxs-lookup"><span data-stu-id="bab07-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bab07-137">열거형</span><span class="sxs-lookup"><span data-stu-id="bab07-137">Enumeration</span></span>|<span data-ttu-id="bab07-138">CurrentUser 또는 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-138">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="bab07-139">storeName 특성</span><span class="sxs-lookup"><span data-stu-id="bab07-139">storeName Attribute</span></span>  
  
|<span data-ttu-id="bab07-140">값</span><span class="sxs-lookup"><span data-stu-id="bab07-140">Value</span></span>|<span data-ttu-id="bab07-141">설명</span><span class="sxs-lookup"><span data-stu-id="bab07-141">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bab07-142">열거형</span><span class="sxs-lookup"><span data-stu-id="bab07-142">Enumeration</span></span>|<span data-ttu-id="bab07-143">값에는 AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople 및 TrustedPublisher가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-143">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bab07-144">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bab07-144">Child Elements</span></span>  

 <span data-ttu-id="bab07-145">없음</span><span class="sxs-lookup"><span data-stu-id="bab07-145">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bab07-146">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bab07-146">Parent Elements</span></span>  
  
|<span data-ttu-id="bab07-147">요소</span><span class="sxs-lookup"><span data-stu-id="bab07-147">Element</span></span>|<span data-ttu-id="bab07-148">설명</span><span class="sxs-lookup"><span data-stu-id="bab07-148">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="bab07-149">클라이언트에 대해 서비스를 인증할 때 사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-149">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bab07-150">설명</span><span class="sxs-lookup"><span data-stu-id="bab07-150">Remarks</span></span>  

 <span data-ttu-id="bab07-151">인증서 기반 메시지 보안을 사용하는 바인딩의 경우 서비스에 보내는 메시지를 암호화하는 데 이 구성 요소에 지정된 인증서를 사용하며, 서비스에서는 클라이언트로 보내는 회신에 서명하는 데 이 인증서를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-151">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="bab07-152">이 구성 요소는 서비스가 인증서를 지정하지 않을 때 사용되는 단일 인증서를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-152">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bab07-153">예제</span><span class="sxs-lookup"><span data-stu-id="bab07-153">Example</span></span>  

 <span data-ttu-id="bab07-154">다음 예제에서는 URI가로 시작 하 `http://www.contoso.com` 는 끝점과 인증서 협상을 수행 하지 않는 다른 모든 끝점에 사용할 인증서를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bab07-154">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bab07-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bab07-155">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="bab07-156">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="bab07-156">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="bab07-157">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="bab07-157">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="bab07-158">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="bab07-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
