---
description: '다음에 대 한 자세한 정보: <clientCertificate> <clientCredentials> 요소'
title: <clientCertificate> of <clientCredentials> 요소
ms.date: 03/30/2017
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
ms.openlocfilehash: 4305b94e62c76436a6bce91251049b3eebd2db2c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638836"
---
# <a name="clientcertificate-of-clientcredentials-element"></a><span data-ttu-id="7a7b1-103">\<clientCertificate> of \<clientCredentials> 요소</span><span class="sxs-lookup"><span data-stu-id="7a7b1-103">\<clientCertificate> of \<clientCredentials> Element</span></span>

<span data-ttu-id="7a7b1-104">서비스에 클라이언트를 인증하는 데 사용되는 X.509 인증서를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-104">Defines an X.509 certificate used to authenticate a client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="7a7b1-105">구문</span><span class="sxs-lookup"><span data-stu-id="7a7b1-105">Syntax</span></span>  
  
```xml  
<clientCertificate findValue="String"
                   storeLocation="LocalMachine/CurrentUser"
                   storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                   X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a7b1-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7a7b1-106">Attributes and Elements</span></span>  

 <span data-ttu-id="7a7b1-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a7b1-108">특성</span><span class="sxs-lookup"><span data-stu-id="7a7b1-108">Attributes</span></span>  
  
|<span data-ttu-id="7a7b1-109">attribute</span><span class="sxs-lookup"><span data-stu-id="7a7b1-109">Attribute</span></span>|<span data-ttu-id="7a7b1-110">설명</span><span class="sxs-lookup"><span data-stu-id="7a7b1-110">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="7a7b1-111">X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-111">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="7a7b1-112">이 특성에 포함된 형식은 `X509FindType` 특성 값의 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-112">The type contained in the attribute must satisfy the requirements of the `X509FindType` attribute value.</span></span> <span data-ttu-id="7a7b1-113">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-113">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="7a7b1-114">클라이언트가 서비스에 자신을 인증하는 데 사용하는 X.509 인증서의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-114">Specifies the location of the X.509 certificate that the client uses to authenticate itself to the service.</span></span> <span data-ttu-id="7a7b1-115">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-115">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7a7b1-116">-LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-116">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="7a7b1-117">-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-117">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="7a7b1-118">기본값은 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-118">The default is LocalMachine.</span></span> <span data-ttu-id="7a7b1-119">이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-119">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
|`storeName`|<span data-ttu-id="7a7b1-120">검색할 X.509 인증서 저장소의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-120">Specifies the name of the X.509 certificate store to search.</span></span> <span data-ttu-id="7a7b1-121">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7a7b1-122">-AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-122">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="7a7b1-123">-AuthRoot: 타사 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-123">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="7a7b1-124">-CertificateAuthority: 중개 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-124">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="7a7b1-125">-허용 안 함: 해지 된 인증서의 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-125">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="7a7b1-126">-My: 개인 인증서용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-126">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="7a7b1-127">-Root: 신뢰할 수 있는 루트 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-127">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="7a7b1-128">-개인 사용자: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-128">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="7a7b1-129">-신뢰할 수 있는 게시자: 직접 신뢰할 수 있는 게시자 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-129">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="7a7b1-130">기본값은 My입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-130">The default is My.</span></span> <span data-ttu-id="7a7b1-131">이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreName> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-131">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreName>.</span></span>|  
|<span data-ttu-id="7a7b1-132">X509FindType</span><span class="sxs-lookup"><span data-stu-id="7a7b1-132">X509FindType</span></span>|<span data-ttu-id="7a7b1-133">실행할 X.509 검색의 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-133">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="7a7b1-134">`findValue` 특성에 포함된 형식은 이 특성의 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-134">The type contained in the `findValue` attribute must satisfy the requirements of this attribute.</span></span> <span data-ttu-id="7a7b1-135">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-135">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7a7b1-136">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="7a7b1-136">-   FindByThumbPrint</span></span><br /><span data-ttu-id="7a7b1-137">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="7a7b1-137">-   FindBySubjectName</span></span><br /><span data-ttu-id="7a7b1-138">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="7a7b1-138">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="7a7b1-139">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="7a7b1-139">-   FindByIssuerName</span></span><br /><span data-ttu-id="7a7b1-140">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="7a7b1-140">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="7a7b1-141">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="7a7b1-141">-   FindBySerialNumber</span></span><br /><span data-ttu-id="7a7b1-142">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="7a7b1-142">-   FindByTimeValid</span></span><br /><span data-ttu-id="7a7b1-143">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="7a7b1-143">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="7a7b1-144">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="7a7b1-144">-   FindByTemplateName</span></span><br /><span data-ttu-id="7a7b1-145">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="7a7b1-145">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="7a7b1-146">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="7a7b1-146">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="7a7b1-147">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="7a7b1-147">-   FindByExtension</span></span><br /><span data-ttu-id="7a7b1-148">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="7a7b1-148">-   FindByKeyUsage</span></span><br /><span data-ttu-id="7a7b1-149">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="7a7b1-149">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="7a7b1-150">기본값은 FindBySubjectDistinguishedName입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-150">The default value is FindBySubjectDistinguishedName.</span></span> <span data-ttu-id="7a7b1-151">이 특성은 <xref:System.Security.Cryptography.X509Certificates.X509FindType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-151">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a7b1-152">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7a7b1-152">Child Elements</span></span>  

 <span data-ttu-id="7a7b1-153">없음</span><span class="sxs-lookup"><span data-stu-id="7a7b1-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7a7b1-154">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7a7b1-154">Parent Elements</span></span>  
  
|<span data-ttu-id="7a7b1-155">요소</span><span class="sxs-lookup"><span data-stu-id="7a7b1-155">Element</span></span>|<span data-ttu-id="7a7b1-156">설명</span><span class="sxs-lookup"><span data-stu-id="7a7b1-156">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="7a7b1-157">클라이언트를 서비스에 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-157">Specifies the credentials used to authenticate the client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a7b1-158">설명</span><span class="sxs-lookup"><span data-stu-id="7a7b1-158">Remarks</span></span>  

 <span data-ttu-id="7a7b1-159">이 구성 요소는 이 요소로 클라이언트를 인증하는 데 사용하는 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-159">This configuration element specifies the certificate used to authenticate the client with this element.</span></span> <span data-ttu-id="7a7b1-160">자세한 내용은 [방법: 클라이언트 자격 증명 값 지정을](../../../wcf/how-to-specify-client-credential-values.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7a7b1-160">For more information, see [How to: Specify Client Credential Values](../../../wcf/how-to-specify-client-credential-values.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a7b1-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a7b1-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [<span data-ttu-id="7a7b1-162">보안 동작</span><span class="sxs-lookup"><span data-stu-id="7a7b1-162">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7a7b1-163">방법: 클라이언트 자격 증명 값 지정</span><span class="sxs-lookup"><span data-stu-id="7a7b1-163">How to: Specify Client Credential Values</span></span>](../../../wcf/how-to-specify-client-credential-values.md)
- [<span data-ttu-id="7a7b1-164">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="7a7b1-164">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="7a7b1-165">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="7a7b1-165">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="7a7b1-166">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="7a7b1-166">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
