---
title: <authentication>of <serviceCertificate> 요소
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 29170f032469b4d55b50f57ca06ce403a5aeaf2c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398221"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="7d6f0-102">\<\<serviceCertificate > 요소의 인증 ></span><span class="sxs-lookup"><span data-stu-id="7d6f0-102">\<authentication> of \<serviceCertificate> Element</span></span>
<span data-ttu-id="7d6f0-103">SSL/TLS 협상을 사용하여 가져온 서비스 인증서를 인증하기 위해 클라이언트 프록시에서 사용하는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
<span data-ttu-id="7d6f0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7d6f0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7d6f0-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7d6f0-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7d6f0-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7d6f0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="7d6f0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7d6f0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="7d6f0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7d6f0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="7d6f0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="7d6f0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="7d6f0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate >** ](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="7d6f0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="7d6f0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<인증 >**</span><span class="sxs-lookup"><span data-stu-id="7d6f0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d6f0-112">구문</span><span class="sxs-lookup"><span data-stu-id="7d6f0-112">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d6f0-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7d6f0-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7d6f0-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d6f0-115">특성</span><span class="sxs-lookup"><span data-stu-id="7d6f0-115">Attributes</span></span>  
  
|<span data-ttu-id="7d6f0-116">특성</span><span class="sxs-lookup"><span data-stu-id="7d6f0-116">Attribute</span></span>|<span data-ttu-id="7d6f0-117">Description</span><span class="sxs-lookup"><span data-stu-id="7d6f0-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d6f0-118">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="7d6f0-118">customCertificateValidatorType</span></span>|<span data-ttu-id="7d6f0-119">문자열.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-119">String.</span></span> <span data-ttu-id="7d6f0-120">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-120">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="7d6f0-121">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="7d6f0-121">certificateValidationMode</span></span>|<span data-ttu-id="7d6f0-122">자격 증명의 유효성을 검사하는 데 사용되는 세 가지 모드 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="7d6f0-123">`Custom`으로 설정되면 customCertificateValidator도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-123">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="7d6f0-124">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-124">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="7d6f0-125">revocationMode</span><span class="sxs-lookup"><span data-stu-id="7d6f0-125">revocationMode</span></span>|<span data-ttu-id="7d6f0-126">CRL(해지된 인증서 목록)을 검사하는 데 사용되는 모드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="7d6f0-127">기본값은 `Online`입니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-127">The default is `Online`.</span></span>|  
|<span data-ttu-id="7d6f0-128">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="7d6f0-128">trustedStoreLocation</span></span>|<span data-ttu-id="7d6f0-129">시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="7d6f0-130">서비스 인증서가 클라이언트와 협상될 때 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="7d6f0-131">지정 된 저장소 위치에 있는 **신뢰할 수 있는 사용자** 저장소에 대해 유효성 검사가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="7d6f0-132">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="7d6f0-133">customCertificateValidator 특성</span><span class="sxs-lookup"><span data-stu-id="7d6f0-133">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="7d6f0-134">값</span><span class="sxs-lookup"><span data-stu-id="7d6f0-134">Value</span></span>|<span data-ttu-id="7d6f0-135">설명</span><span class="sxs-lookup"><span data-stu-id="7d6f0-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7d6f0-136">문자열</span><span class="sxs-lookup"><span data-stu-id="7d6f0-136">String</span></span>|<span data-ttu-id="7d6f0-137">형식 이름 및 어셈블리와 형식을 찾는 데 사용되는 기타 데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-137">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="7d6f0-138">certificateValidationMode 특성</span><span class="sxs-lookup"><span data-stu-id="7d6f0-138">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="7d6f0-139">값</span><span class="sxs-lookup"><span data-stu-id="7d6f0-139">Value</span></span>|<span data-ttu-id="7d6f0-140">설명</span><span class="sxs-lookup"><span data-stu-id="7d6f0-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7d6f0-141">열거형</span><span class="sxs-lookup"><span data-stu-id="7d6f0-141">Enumeration</span></span>|<span data-ttu-id="7d6f0-142">다음 값 중 하나입니다. None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom 중에서 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-142">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="7d6f0-143">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-143">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="7d6f0-144">revocationMode 특성</span><span class="sxs-lookup"><span data-stu-id="7d6f0-144">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="7d6f0-145">값</span><span class="sxs-lookup"><span data-stu-id="7d6f0-145">Value</span></span>|<span data-ttu-id="7d6f0-146">설명</span><span class="sxs-lookup"><span data-stu-id="7d6f0-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7d6f0-147">열거형</span><span class="sxs-lookup"><span data-stu-id="7d6f0-147">Enumeration</span></span>|<span data-ttu-id="7d6f0-148">다음 값 중 하나입니다. NoCheck, 온라인, 오프 라인.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-148">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="7d6f0-149">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-149">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="7d6f0-150">trustedStoreLocation 특성</span><span class="sxs-lookup"><span data-stu-id="7d6f0-150">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="7d6f0-151">값</span><span class="sxs-lookup"><span data-stu-id="7d6f0-151">Value</span></span>|<span data-ttu-id="7d6f0-152">설명</span><span class="sxs-lookup"><span data-stu-id="7d6f0-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7d6f0-153">열거형</span><span class="sxs-lookup"><span data-stu-id="7d6f0-153">Enumeration</span></span>|<span data-ttu-id="7d6f0-154">다음 값 중 하나입니다. LocalMachine 또는 CurrentUser입니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-154">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="7d6f0-155">기본값은 CurrentUser입니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-155">The default is CurrentUser.</span></span> <span data-ttu-id="7d6f0-156">시스템 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 LocalMachine에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-156">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="7d6f0-157">사용자 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 CurrentUser에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-157">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d6f0-158">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7d6f0-158">Child Elements</span></span>  
 <span data-ttu-id="7d6f0-159">없음</span><span class="sxs-lookup"><span data-stu-id="7d6f0-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7d6f0-160">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7d6f0-160">Parent Elements</span></span>  
  
|<span data-ttu-id="7d6f0-161">요소</span><span class="sxs-lookup"><span data-stu-id="7d6f0-161">Element</span></span>|<span data-ttu-id="7d6f0-162">Description</span><span class="sxs-lookup"><span data-stu-id="7d6f0-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d6f0-163">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="7d6f0-163">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="7d6f0-164">클라이언트에 대해 서비스를 인증할 때 사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-164">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d6f0-165">설명</span><span class="sxs-lookup"><span data-stu-id="7d6f0-165">Remarks</span></span>  
 <span data-ttu-id="7d6f0-166">이 구성 요소의 `certificateValidationMode` 특성은 인증서를 인증하는 데 사용되는 신뢰 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-166">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="7d6f0-167">기본적으로 수준은 `ChainTrust`로 설정되며 이는 각 인증서가 체인 맨 위의 신뢰할 수 있는 인증 기관에서 종료되는 인증서 계층 구조에 있어야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-167">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="7d6f0-168">이 모드가 가장 안전한 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-168">This is the most secure mode.</span></span> <span data-ttu-id="7d6f0-169">또한 값을 `PeerOrChainTrust`로 설정할 수 있으며, 이는 자체 발급된 인증서(신뢰 피어)가 신뢰 체인에 있는 인증서와 함께 수락됨을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-169">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="7d6f0-170">자체 발급 인증서를 신뢰할 수 있는 기관에서 구입할 필요 없기 때문에 클라이언트 및 서비스를 개발 및 디버깅하는 경우 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-170">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="7d6f0-171">클라이언트를 배포하는 경우 `ChainTrust` 값을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-171">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="7d6f0-172">또한 값을 `Custom` 또는 `None`으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-172">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="7d6f0-173">`Custom` 값을 사용하려면 `customCertificateValidator` 특성을 인증서의 유효성을 검사하는 데 사용된 어셈블리 및 형식으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-173">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="7d6f0-174">사용자 지정 유효성 검사기를 직접 만들려면 추상 X509CertificateValidator 클래스에서 상속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-174">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="7d6f0-175">자세한 내용은 [방법: 사용자 지정 인증서 유효성 검사기](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)를 채택 하는 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-175">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="7d6f0-176">`revocationMode` 특성은 해지를 위해 인증서를 검사하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-176">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="7d6f0-177">기본값은 `online`이며, 이는 인증서가 해지를 위해 자동으로 검사됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-177">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="7d6f0-178">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-178">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d6f0-179">예제</span><span class="sxs-lookup"><span data-stu-id="7d6f0-179">Example</span></span>  
 <span data-ttu-id="7d6f0-180">다음 예제에서는 두 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-180">The following example does two tasks.</span></span> <span data-ttu-id="7d6f0-181">먼저 클라이언트에서 HTTP 프로토콜을 `www.contoso.com` 통해 도메인 이름이 인 끝점과 통신할 때 사용할 서비스 인증서를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-181">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="7d6f0-182">그런 다음 인증 중에 사용되는 해지 모드 및 저장소 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6f0-182">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7d6f0-183">참고자료</span><span class="sxs-lookup"><span data-stu-id="7d6f0-183">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="7d6f0-184">보안 동작</span><span class="sxs-lookup"><span data-stu-id="7d6f0-184">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7d6f0-185">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="7d6f0-185">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="7d6f0-186">방법: 사용자 지정 인증서 유효성 검사기를 채택 하는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="7d6f0-186">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="7d6f0-187">\<authentication></span><span class="sxs-lookup"><span data-stu-id="7d6f0-187">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="7d6f0-188">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="7d6f0-188">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="7d6f0-189">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="7d6f0-189">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
