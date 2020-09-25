---
title: <clientCertificate> of <clientCredentials> 요소
ms.date: 03/30/2017
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
ms.openlocfilehash: 74209c43dcafb1e27bb1d7943ee7832eaea0ef57
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204946"
---
# <a name="clientcertificate-of-clientcredentials-element"></a><span data-ttu-id="a1977-102">\<clientCertificate> of \<clientCredentials> 요소</span><span class="sxs-lookup"><span data-stu-id="a1977-102">\<clientCertificate> of \<clientCredentials> Element</span></span>

<span data-ttu-id="a1977-103">서비스에 클라이언트를 인증하는 데 사용되는 X.509 인증서를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-103">Defines an X.509 certificate used to authenticate a client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="a1977-104">구문</span><span class="sxs-lookup"><span data-stu-id="a1977-104">Syntax</span></span>  
  
```xml  
<clientCertificate findValue="String"
                   storeLocation="LocalMachine/CurrentUser"
                   storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                   X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1977-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a1977-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a1977-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1977-107">특성</span><span class="sxs-lookup"><span data-stu-id="a1977-107">Attributes</span></span>  
  
|<span data-ttu-id="a1977-108">attribute</span><span class="sxs-lookup"><span data-stu-id="a1977-108">Attribute</span></span>|<span data-ttu-id="a1977-109">설명</span><span class="sxs-lookup"><span data-stu-id="a1977-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="a1977-110">X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="a1977-111">이 특성에 포함된 형식은 `X509FindType` 특성 값의 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-111">The type contained in the attribute must satisfy the requirements of the `X509FindType` attribute value.</span></span> <span data-ttu-id="a1977-112">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="a1977-113">클라이언트가 서비스에 자신을 인증하는 데 사용하는 X.509 인증서의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-113">Specifies the location of the X.509 certificate that the client uses to authenticate itself to the service.</span></span> <span data-ttu-id="a1977-114">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a1977-115">-LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="a1977-116">-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="a1977-117">기본값은 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-117">The default is LocalMachine.</span></span> <span data-ttu-id="a1977-118">이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-118">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
|`storeName`|<span data-ttu-id="a1977-119">검색할 X.509 인증서 저장소의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-119">Specifies the name of the X.509 certificate store to search.</span></span> <span data-ttu-id="a1977-120">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a1977-121">-AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-121">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="a1977-122">-AuthRoot: 타사 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-122">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="a1977-123">-CertificateAuthority: 중개 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-123">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="a1977-124">-허용 안 함: 해지 된 인증서의 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-124">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="a1977-125">-My: 개인 인증서용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-125">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="a1977-126">-Root: 신뢰할 수 있는 루트 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-126">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="a1977-127">-개인 사용자: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-127">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="a1977-128">-신뢰할 수 있는 게시자: 직접 신뢰할 수 있는 게시자 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-128">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="a1977-129">기본값은 My입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-129">The default is My.</span></span> <span data-ttu-id="a1977-130">이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreName> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreName>.</span></span>|  
|<span data-ttu-id="a1977-131">X509FindType</span><span class="sxs-lookup"><span data-stu-id="a1977-131">X509FindType</span></span>|<span data-ttu-id="a1977-132">실행할 X.509 검색의 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-132">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="a1977-133">`findValue` 특성에 포함된 형식은 이 특성의 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-133">The type contained in the `findValue` attribute must satisfy the requirements of this attribute.</span></span> <span data-ttu-id="a1977-134">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-134">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a1977-135">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="a1977-135">-   FindByThumbPrint</span></span><br /><span data-ttu-id="a1977-136">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="a1977-136">-   FindBySubjectName</span></span><br /><span data-ttu-id="a1977-137">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="a1977-137">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="a1977-138">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="a1977-138">-   FindByIssuerName</span></span><br /><span data-ttu-id="a1977-139">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="a1977-139">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="a1977-140">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="a1977-140">-   FindBySerialNumber</span></span><br /><span data-ttu-id="a1977-141">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="a1977-141">-   FindByTimeValid</span></span><br /><span data-ttu-id="a1977-142">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="a1977-142">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="a1977-143">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="a1977-143">-   FindByTemplateName</span></span><br /><span data-ttu-id="a1977-144">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="a1977-144">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="a1977-145">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="a1977-145">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="a1977-146">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="a1977-146">-   FindByExtension</span></span><br /><span data-ttu-id="a1977-147">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="a1977-147">-   FindByKeyUsage</span></span><br /><span data-ttu-id="a1977-148">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="a1977-148">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="a1977-149">기본값은 FindBySubjectDistinguishedName입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-149">The default value is FindBySubjectDistinguishedName.</span></span> <span data-ttu-id="a1977-150">이 특성은 <xref:System.Security.Cryptography.X509Certificates.X509FindType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-150">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1977-151">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a1977-151">Child Elements</span></span>  

 <span data-ttu-id="a1977-152">없음</span><span class="sxs-lookup"><span data-stu-id="a1977-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1977-153">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a1977-153">Parent Elements</span></span>  
  
|<span data-ttu-id="a1977-154">요소</span><span class="sxs-lookup"><span data-stu-id="a1977-154">Element</span></span>|<span data-ttu-id="a1977-155">설명</span><span class="sxs-lookup"><span data-stu-id="a1977-155">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="a1977-156">클라이언트를 서비스에 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-156">Specifies the credentials used to authenticate the client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1977-157">설명</span><span class="sxs-lookup"><span data-stu-id="a1977-157">Remarks</span></span>  

 <span data-ttu-id="a1977-158">이 구성 요소는 이 요소로 클라이언트를 인증하는 데 사용하는 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1977-158">This configuration element specifies the certificate used to authenticate the client with this element.</span></span> <span data-ttu-id="a1977-159">자세한 내용은 [방법: 클라이언트 자격 증명 값 지정을](../../../wcf/how-to-specify-client-credential-values.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1977-159">For more information, see [How to: Specify Client Credential Values](../../../wcf/how-to-specify-client-credential-values.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1977-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1977-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [<span data-ttu-id="a1977-161">보안 동작</span><span class="sxs-lookup"><span data-stu-id="a1977-161">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="a1977-162">방법: 클라이언트 자격 증명 값 지정</span><span class="sxs-lookup"><span data-stu-id="a1977-162">How to: Specify Client Credential Values</span></span>](../../../wcf/how-to-specify-client-credential-values.md)
- [<span data-ttu-id="a1977-163">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="a1977-163">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="a1977-164">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="a1977-164">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="a1977-165">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="a1977-165">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
