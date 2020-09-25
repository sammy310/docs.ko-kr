---
title: <authentication> of <serviceCertificate> 요소
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: c6f2578d85971740e5bd3d75151305a475187492
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201592"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="2b8a8-102">\<authentication> of \<serviceCertificate> 요소</span><span class="sxs-lookup"><span data-stu-id="2b8a8-102">\<authentication> of \<serviceCertificate> Element</span></span>

<span data-ttu-id="2b8a8-103">SSL/TLS 협상을 사용하여 가져온 서비스 인증서를 인증하기 위해 클라이언트 프록시에서 사용하는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
## <a name="syntax"></a><span data-ttu-id="2b8a8-104">구문</span><span class="sxs-lookup"><span data-stu-id="2b8a8-104">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b8a8-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2b8a8-105">Attributes and Elements</span></span>  

 <span data-ttu-id="2b8a8-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b8a8-107">특성</span><span class="sxs-lookup"><span data-stu-id="2b8a8-107">Attributes</span></span>  
  
|<span data-ttu-id="2b8a8-108">attribute</span><span class="sxs-lookup"><span data-stu-id="2b8a8-108">Attribute</span></span>|<span data-ttu-id="2b8a8-109">설명</span><span class="sxs-lookup"><span data-stu-id="2b8a8-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2b8a8-110">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="2b8a8-110">customCertificateValidatorType</span></span>|<span data-ttu-id="2b8a8-111">문자열.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-111">String.</span></span> <span data-ttu-id="2b8a8-112">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-112">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="2b8a8-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="2b8a8-113">certificateValidationMode</span></span>|<span data-ttu-id="2b8a8-114">자격 증명의 유효성을 검사하는 데 사용되는 세 가지 모드 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-114">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="2b8a8-115">`Custom`으로 설정되면 customCertificateValidator도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-115">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="2b8a8-116">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-116">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="2b8a8-117">revocationMode</span><span class="sxs-lookup"><span data-stu-id="2b8a8-117">revocationMode</span></span>|<span data-ttu-id="2b8a8-118">CRL(해지된 인증서 목록)을 검사하는 데 사용되는 모드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-118">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="2b8a8-119">기본값은 `Online`입니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-119">The default is `Online`.</span></span>|  
|<span data-ttu-id="2b8a8-120">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="2b8a8-120">trustedStoreLocation</span></span>|<span data-ttu-id="2b8a8-121">시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-121">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="2b8a8-122">서비스 인증서가 클라이언트와 협상될 때 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-122">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="2b8a8-123">지정 된 저장소 위치에 있는 **신뢰할 수 있는 사용자** 저장소에 대해 유효성 검사가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-123">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="2b8a8-124">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-124">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="2b8a8-125">customCertificateValidator 특성</span><span class="sxs-lookup"><span data-stu-id="2b8a8-125">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="2b8a8-126">Value</span><span class="sxs-lookup"><span data-stu-id="2b8a8-126">Value</span></span>|<span data-ttu-id="2b8a8-127">Description</span><span class="sxs-lookup"><span data-stu-id="2b8a8-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2b8a8-128">String</span><span class="sxs-lookup"><span data-stu-id="2b8a8-128">String</span></span>|<span data-ttu-id="2b8a8-129">형식 이름 및 어셈블리와 형식을 찾는 데 사용되는 기타 데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-129">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="2b8a8-130">certificateValidationMode 특성</span><span class="sxs-lookup"><span data-stu-id="2b8a8-130">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="2b8a8-131">Value</span><span class="sxs-lookup"><span data-stu-id="2b8a8-131">Value</span></span>|<span data-ttu-id="2b8a8-132">설명</span><span class="sxs-lookup"><span data-stu-id="2b8a8-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2b8a8-133">열거형</span><span class="sxs-lookup"><span data-stu-id="2b8a8-133">Enumeration</span></span>|<span data-ttu-id="2b8a8-134">None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-134">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="2b8a8-135">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-135">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="2b8a8-136">revocationMode 특성</span><span class="sxs-lookup"><span data-stu-id="2b8a8-136">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="2b8a8-137">Value</span><span class="sxs-lookup"><span data-stu-id="2b8a8-137">Value</span></span>|<span data-ttu-id="2b8a8-138">설명</span><span class="sxs-lookup"><span data-stu-id="2b8a8-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2b8a8-139">열거형</span><span class="sxs-lookup"><span data-stu-id="2b8a8-139">Enumeration</span></span>|<span data-ttu-id="2b8a8-140">NoCheck, Online, Offline 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-140">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="2b8a8-141">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-141">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="2b8a8-142">trustedStoreLocation 특성</span><span class="sxs-lookup"><span data-stu-id="2b8a8-142">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="2b8a8-143">Value</span><span class="sxs-lookup"><span data-stu-id="2b8a8-143">Value</span></span>|<span data-ttu-id="2b8a8-144">설명</span><span class="sxs-lookup"><span data-stu-id="2b8a8-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2b8a8-145">열거형</span><span class="sxs-lookup"><span data-stu-id="2b8a8-145">Enumeration</span></span>|<span data-ttu-id="2b8a8-146">LocalMachine 또는 CurrentUser 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-146">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="2b8a8-147">기본값은 CurrentUser입니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-147">The default is CurrentUser.</span></span> <span data-ttu-id="2b8a8-148">시스템 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 LocalMachine에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-148">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="2b8a8-149">사용자 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 CurrentUser에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-149">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b8a8-150">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2b8a8-150">Child Elements</span></span>  

 <span data-ttu-id="2b8a8-151">없음</span><span class="sxs-lookup"><span data-stu-id="2b8a8-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2b8a8-152">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2b8a8-152">Parent Elements</span></span>  
  
|<span data-ttu-id="2b8a8-153">요소</span><span class="sxs-lookup"><span data-stu-id="2b8a8-153">Element</span></span>|<span data-ttu-id="2b8a8-154">설명</span><span class="sxs-lookup"><span data-stu-id="2b8a8-154">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="2b8a8-155">클라이언트에 대해 서비스를 인증할 때 사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-155">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b8a8-156">설명</span><span class="sxs-lookup"><span data-stu-id="2b8a8-156">Remarks</span></span>  

 <span data-ttu-id="2b8a8-157">이 구성 요소의 `certificateValidationMode` 특성은 인증서를 인증하는 데 사용되는 신뢰 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-157">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="2b8a8-158">기본적으로 수준은 `ChainTrust`로 설정되며 이는 각 인증서가 체인 맨 위의 신뢰할 수 있는 인증 기관에서 종료되는 인증서 계층 구조에 있어야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-158">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="2b8a8-159">이 모드가 가장 안전한 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-159">This is the most secure mode.</span></span> <span data-ttu-id="2b8a8-160">또한 값을 `PeerOrChainTrust`로 설정할 수 있으며, 이는 자체 발급된 인증서(신뢰 피어)가 신뢰 체인에 있는 인증서와 함께 수락됨을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-160">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="2b8a8-161">자체 발급 인증서를 신뢰할 수 있는 기관에서 구입할 필요 없기 때문에 클라이언트 및 서비스를 개발 및 디버깅하는 경우 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-161">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="2b8a8-162">클라이언트를 배포하는 경우 `ChainTrust` 값을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-162">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="2b8a8-163">또한 값을 `Custom` 또는 `None`으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-163">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="2b8a8-164">`Custom` 값을 사용하려면 `customCertificateValidator` 특성을 인증서의 유효성을 검사하는 데 사용된 어셈블리 및 형식으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-164">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="2b8a8-165">사용자 지정 유효성 검사기를 직접 만들려면 추상 X509CertificateValidator 클래스에서 상속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-165">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="2b8a8-166">자세한 내용은 [방법: 사용자 지정 인증서 유효성 검사기를 사용 하는 서비스 만들기](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-166">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="2b8a8-167">`revocationMode` 특성은 해지를 위해 인증서를 검사하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-167">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="2b8a8-168">기본값은 `online`이며, 이는 인증서가 해지를 위해 자동으로 검사됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-168">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="2b8a8-169">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-169">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b8a8-170">예제</span><span class="sxs-lookup"><span data-stu-id="2b8a8-170">Example</span></span>  

 <span data-ttu-id="2b8a8-171">다음 예제에서는 두 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-171">The following example does two tasks.</span></span> <span data-ttu-id="2b8a8-172">먼저 클라이언트에서 HTTP 프로토콜을 통해 도메인 이름이 인 끝점과 통신할 때 사용할 서비스 인증서를 지정 합니다 `www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="2b8a8-172">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="2b8a8-173">그런 다음 인증 중에 사용되는 해지 모드 및 저장소 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8a8-173">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2b8a8-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b8a8-174">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="2b8a8-175">보안 동작</span><span class="sxs-lookup"><span data-stu-id="2b8a8-175">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="2b8a8-176">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="2b8a8-176">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="2b8a8-177">방법: 사용자 지정 인증서 유효성 검사기를 사용하는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="2b8a8-177">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="2b8a8-178">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="2b8a8-178">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="2b8a8-179">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="2b8a8-179">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
