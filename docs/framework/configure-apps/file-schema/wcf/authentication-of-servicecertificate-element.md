---
description: '다음에 대 한 자세한 정보: <authentication> <serviceCertificate> 요소'
title: <authentication> of <serviceCertificate> 요소
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 35a94f4f9c089f86aef38e7e9a1115a7cd22a325
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749885"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="7dc54-103">\<authentication> of \<serviceCertificate> 요소</span><span class="sxs-lookup"><span data-stu-id="7dc54-103">\<authentication> of \<serviceCertificate> Element</span></span>

<span data-ttu-id="7dc54-104">SSL/TLS 협상을 사용하여 가져온 서비스 인증서를 인증하기 위해 클라이언트 프록시에서 사용하는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-104">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
## <a name="syntax"></a><span data-ttu-id="7dc54-105">구문</span><span class="sxs-lookup"><span data-stu-id="7dc54-105">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7dc54-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7dc54-106">Attributes and Elements</span></span>  

 <span data-ttu-id="7dc54-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7dc54-108">특성</span><span class="sxs-lookup"><span data-stu-id="7dc54-108">Attributes</span></span>  
  
|<span data-ttu-id="7dc54-109">attribute</span><span class="sxs-lookup"><span data-stu-id="7dc54-109">Attribute</span></span>|<span data-ttu-id="7dc54-110">설명</span><span class="sxs-lookup"><span data-stu-id="7dc54-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7dc54-111">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="7dc54-111">customCertificateValidatorType</span></span>|<span data-ttu-id="7dc54-112">문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-112">String.</span></span> <span data-ttu-id="7dc54-113">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-113">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="7dc54-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="7dc54-114">certificateValidationMode</span></span>|<span data-ttu-id="7dc54-115">자격 증명의 유효성을 검사하는 데 사용되는 세 가지 모드 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-115">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="7dc54-116">`Custom`으로 설정되면 customCertificateValidator도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-116">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="7dc54-117">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-117">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="7dc54-118">revocationMode</span><span class="sxs-lookup"><span data-stu-id="7dc54-118">revocationMode</span></span>|<span data-ttu-id="7dc54-119">CRL(해지된 인증서 목록)을 검사하는 데 사용되는 모드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-119">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="7dc54-120">기본값은 `Online`입니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-120">The default is `Online`.</span></span>|  
|<span data-ttu-id="7dc54-121">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="7dc54-121">trustedStoreLocation</span></span>|<span data-ttu-id="7dc54-122">시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-122">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="7dc54-123">서비스 인증서가 클라이언트와 협상될 때 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-123">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="7dc54-124">지정 된 저장소 위치에 있는 **신뢰할 수 있는 사용자** 저장소에 대해 유효성 검사가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-124">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="7dc54-125">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-125">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="7dc54-126">customCertificateValidator 특성</span><span class="sxs-lookup"><span data-stu-id="7dc54-126">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="7dc54-127">값</span><span class="sxs-lookup"><span data-stu-id="7dc54-127">Value</span></span>|<span data-ttu-id="7dc54-128">Description</span><span class="sxs-lookup"><span data-stu-id="7dc54-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7dc54-129">String</span><span class="sxs-lookup"><span data-stu-id="7dc54-129">String</span></span>|<span data-ttu-id="7dc54-130">형식 이름 및 어셈블리와 형식을 찾는 데 사용되는 기타 데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-130">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="7dc54-131">certificateValidationMode 특성</span><span class="sxs-lookup"><span data-stu-id="7dc54-131">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="7dc54-132">값</span><span class="sxs-lookup"><span data-stu-id="7dc54-132">Value</span></span>|<span data-ttu-id="7dc54-133">설명</span><span class="sxs-lookup"><span data-stu-id="7dc54-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7dc54-134">열거형</span><span class="sxs-lookup"><span data-stu-id="7dc54-134">Enumeration</span></span>|<span data-ttu-id="7dc54-135">None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-135">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="7dc54-136">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-136">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="7dc54-137">revocationMode 특성</span><span class="sxs-lookup"><span data-stu-id="7dc54-137">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="7dc54-138">값</span><span class="sxs-lookup"><span data-stu-id="7dc54-138">Value</span></span>|<span data-ttu-id="7dc54-139">설명</span><span class="sxs-lookup"><span data-stu-id="7dc54-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7dc54-140">열거형</span><span class="sxs-lookup"><span data-stu-id="7dc54-140">Enumeration</span></span>|<span data-ttu-id="7dc54-141">NoCheck, Online, Offline 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-141">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="7dc54-142">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="7dc54-143">trustedStoreLocation 특성</span><span class="sxs-lookup"><span data-stu-id="7dc54-143">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="7dc54-144">값</span><span class="sxs-lookup"><span data-stu-id="7dc54-144">Value</span></span>|<span data-ttu-id="7dc54-145">설명</span><span class="sxs-lookup"><span data-stu-id="7dc54-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7dc54-146">열거형</span><span class="sxs-lookup"><span data-stu-id="7dc54-146">Enumeration</span></span>|<span data-ttu-id="7dc54-147">LocalMachine 또는 CurrentUser 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-147">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="7dc54-148">기본값은 CurrentUser입니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-148">The default is CurrentUser.</span></span> <span data-ttu-id="7dc54-149">시스템 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 LocalMachine에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-149">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="7dc54-150">사용자 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 CurrentUser에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-150">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7dc54-151">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7dc54-151">Child Elements</span></span>  

 <span data-ttu-id="7dc54-152">없음</span><span class="sxs-lookup"><span data-stu-id="7dc54-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7dc54-153">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7dc54-153">Parent Elements</span></span>  
  
|<span data-ttu-id="7dc54-154">요소</span><span class="sxs-lookup"><span data-stu-id="7dc54-154">Element</span></span>|<span data-ttu-id="7dc54-155">설명</span><span class="sxs-lookup"><span data-stu-id="7dc54-155">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="7dc54-156">클라이언트에 대해 서비스를 인증할 때 사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-156">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7dc54-157">설명</span><span class="sxs-lookup"><span data-stu-id="7dc54-157">Remarks</span></span>  

 <span data-ttu-id="7dc54-158">이 구성 요소의 `certificateValidationMode` 특성은 인증서를 인증하는 데 사용되는 신뢰 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-158">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="7dc54-159">기본적으로 수준은 `ChainTrust`로 설정되며 이는 각 인증서가 체인 맨 위의 신뢰할 수 있는 인증 기관에서 종료되는 인증서 계층 구조에 있어야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-159">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="7dc54-160">이 모드가 가장 안전한 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-160">This is the most secure mode.</span></span> <span data-ttu-id="7dc54-161">또한 값을 `PeerOrChainTrust`로 설정할 수 있으며, 이는 자체 발급된 인증서(신뢰 피어)가 신뢰 체인에 있는 인증서와 함께 수락됨을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-161">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="7dc54-162">자체 발급 인증서를 신뢰할 수 있는 기관에서 구입할 필요 없기 때문에 클라이언트 및 서비스를 개발 및 디버깅하는 경우 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-162">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="7dc54-163">클라이언트를 배포하는 경우 `ChainTrust` 값을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-163">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="7dc54-164">또한 값을 `Custom` 또는 `None`으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-164">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="7dc54-165">`Custom` 값을 사용하려면 `customCertificateValidator` 특성을 인증서의 유효성을 검사하는 데 사용된 어셈블리 및 형식으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-165">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="7dc54-166">사용자 지정 유효성 검사기를 직접 만들려면 추상 X509CertificateValidator 클래스에서 상속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-166">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="7dc54-167">자세한 내용은 [방법: 사용자 지정 인증서 유효성 검사기를 사용 하는 서비스 만들기](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-167">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="7dc54-168">`revocationMode` 특성은 해지를 위해 인증서를 검사하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-168">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="7dc54-169">기본값은 `online`이며, 이는 인증서가 해지를 위해 자동으로 검사됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-169">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="7dc54-170">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-170">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dc54-171">예제</span><span class="sxs-lookup"><span data-stu-id="7dc54-171">Example</span></span>  

 <span data-ttu-id="7dc54-172">다음 예제에서는 두 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-172">The following example does two tasks.</span></span> <span data-ttu-id="7dc54-173">먼저 클라이언트에서 HTTP 프로토콜을 통해 도메인 이름이 인 끝점과 통신할 때 사용할 서비스 인증서를 지정 합니다 `www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="7dc54-173">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="7dc54-174">그런 다음 인증 중에 사용되는 해지 모드 및 저장소 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7dc54-174">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7dc54-175">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7dc54-175">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="7dc54-176">보안 동작</span><span class="sxs-lookup"><span data-stu-id="7dc54-176">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7dc54-177">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="7dc54-177">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="7dc54-178">방법: 사용자 지정 인증서 유효성 검사기를 사용하는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="7dc54-178">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="7dc54-179">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="7dc54-179">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="7dc54-180">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="7dc54-180">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
