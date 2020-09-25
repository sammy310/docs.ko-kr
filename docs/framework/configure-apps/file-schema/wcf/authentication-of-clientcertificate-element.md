---
title: <authentication> of <clientCertificate> 요소
ms.date: 03/30/2017
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
ms.openlocfilehash: 13296dbc2b3bc8836770197a1549586c841b4635
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201605"
---
# <a name="authentication-of-clientcertificate-element"></a><span data-ttu-id="90ba5-102">\<authentication> of \<clientCertificate> 요소</span><span class="sxs-lookup"><span data-stu-id="90ba5-102">\<authentication> of \<clientCertificate> Element</span></span>

<span data-ttu-id="90ba5-103">서비스에서 사용되는 클라이언트 인증서에 대한 인증 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-103">Specifies authentication behaviors for client certificates used by a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
## <a name="syntax"></a><span data-ttu-id="90ba5-104">구문</span><span class="sxs-lookup"><span data-stu-id="90ba5-104">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                includeWindowsGroups="Boolean"
                mapClientCertificateToWindowsAccount="Boolean"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90ba5-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="90ba5-105">Attributes and Elements</span></span>  

 <span data-ttu-id="90ba5-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90ba5-107">특성</span><span class="sxs-lookup"><span data-stu-id="90ba5-107">Attributes</span></span>  
  
|<span data-ttu-id="90ba5-108">attribute</span><span class="sxs-lookup"><span data-stu-id="90ba5-108">Attribute</span></span>|<span data-ttu-id="90ba5-109">설명</span><span class="sxs-lookup"><span data-stu-id="90ba5-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="90ba5-110">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="90ba5-110">customCertificateValidatorType</span></span>|<span data-ttu-id="90ba5-111">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-111">Optional string.</span></span> <span data-ttu-id="90ba5-112">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-112">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="90ba5-113">이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-113">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="90ba5-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="90ba5-114">certificateValidationMode</span></span>|<span data-ttu-id="90ba5-115">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-115">Optional enumeration.</span></span> <span data-ttu-id="90ba5-116">자격 증명의 유효성을 검사하는 데 사용되는 모드 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-116">Specifies one of the modes used to validate credentials.</span></span> <span data-ttu-id="90ba5-117">이 특성은 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-117">This attribute is of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> type.</span></span> <span data-ttu-id="90ba5-118"><xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>으로 설정되면 `customCertificateValidator`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-118">If set to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="90ba5-119">기본값은 <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-119">The default is <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span></span>|  
|<span data-ttu-id="90ba5-120">includeWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="90ba5-120">includeWindowsGroups</span></span>|<span data-ttu-id="90ba5-121">선택적 부울입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-121">Optional Boolean.</span></span> <span data-ttu-id="90ba5-122">Windows 그룹이 보안 컨텍스트에 포함될지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-122">Specifies if Windows groups are included in the security context.</span></span> <span data-ttu-id="90ba5-123">이 특성을 `true`로 설정하면 전체 그룹이 확장되므로 성능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-123">Setting this attribute to `true` has a performance impact, as it results in a full group expansion.</span></span> <span data-ttu-id="90ba5-124">사용자가 속한 그룹의 목록을 설정할 필요가 없으면 이 특성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-124">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|<span data-ttu-id="90ba5-125">mapClientCertificateToWindowsAccount</span><span class="sxs-lookup"><span data-stu-id="90ba5-125">mapClientCertificateToWindowsAccount</span></span>|<span data-ttu-id="90ba5-126">Boolean입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-126">Boolean.</span></span> <span data-ttu-id="90ba5-127">클라이언트가 인증서를 사용하여 Windows ID에 매핑될 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-127">Specifies whether the client can be mapped to a Windows identity using the certificate.</span></span> <span data-ttu-id="90ba5-128">이 작업을 위해서는 Active Directory를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-128">Active Directory must be enabled to do this.</span></span>|  
|<span data-ttu-id="90ba5-129">revocationMode</span><span class="sxs-lookup"><span data-stu-id="90ba5-129">revocationMode</span></span>|<span data-ttu-id="90ba5-130">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-130">Optional enumeration.</span></span> <span data-ttu-id="90ba5-131">RCL(해지된 인증서 목록)을 검사하는 데 사용되는 모드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-131">One of the modes used to check for a revoked certificate lists (RCL).</span></span> <span data-ttu-id="90ba5-132">기본값은 `Online`입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-132">The default is `Online`.</span></span> <span data-ttu-id="90ba5-133">이 값은 HTTP 전송 보안을 사용할 때 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-133">This value is ignored when using HTTP transport security.</span></span>|  
|<span data-ttu-id="90ba5-134">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="90ba5-134">trustedStoreLocation</span></span>|<span data-ttu-id="90ba5-135">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-135">Optional enumeration.</span></span> <span data-ttu-id="90ba5-136">시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-136">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="90ba5-137">서비스 인증서가 클라이언트와 협상될 때 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-137">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="90ba5-138">지정 된 저장소 위치에 있는 **신뢰할 수 있는 사용자** 저장소에 대해 유효성 검사가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-138">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="90ba5-139">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-139">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="90ba5-140">customCertificateValidatorType 특성</span><span class="sxs-lookup"><span data-stu-id="90ba5-140">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="90ba5-141">Value</span><span class="sxs-lookup"><span data-stu-id="90ba5-141">Value</span></span>|<span data-ttu-id="90ba5-142">Description</span><span class="sxs-lookup"><span data-stu-id="90ba5-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="90ba5-143">String</span><span class="sxs-lookup"><span data-stu-id="90ba5-143">String</span></span>|<span data-ttu-id="90ba5-144">형식 이름 및 어셈블리와 형식을 찾는 데 사용되는 기타 데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-144">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="90ba5-145">certificateValidationMode 특성</span><span class="sxs-lookup"><span data-stu-id="90ba5-145">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="90ba5-146">Value</span><span class="sxs-lookup"><span data-stu-id="90ba5-146">Value</span></span>|<span data-ttu-id="90ba5-147">설명</span><span class="sxs-lookup"><span data-stu-id="90ba5-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="90ba5-148">열거형</span><span class="sxs-lookup"><span data-stu-id="90ba5-148">Enumeration</span></span>|<span data-ttu-id="90ba5-149">None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-149">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="90ba5-150">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-150">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="90ba5-151">revocationMode 특성</span><span class="sxs-lookup"><span data-stu-id="90ba5-151">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="90ba5-152">Value</span><span class="sxs-lookup"><span data-stu-id="90ba5-152">Value</span></span>|<span data-ttu-id="90ba5-153">설명</span><span class="sxs-lookup"><span data-stu-id="90ba5-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="90ba5-154">열거형</span><span class="sxs-lookup"><span data-stu-id="90ba5-154">Enumeration</span></span>|<span data-ttu-id="90ba5-155">NoCheck, Online, Offline 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-155">One of the following values: NoCheck, Online, Offline.</span></span> <span data-ttu-id="90ba5-156">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-156">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="90ba5-157">trustedStoreLocation 특성</span><span class="sxs-lookup"><span data-stu-id="90ba5-157">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="90ba5-158">Value</span><span class="sxs-lookup"><span data-stu-id="90ba5-158">Value</span></span>|<span data-ttu-id="90ba5-159">설명</span><span class="sxs-lookup"><span data-stu-id="90ba5-159">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="90ba5-160">열거형</span><span class="sxs-lookup"><span data-stu-id="90ba5-160">Enumeration</span></span>|<span data-ttu-id="90ba5-161">`LocalMachine` 또는 `CurrentUser` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-161">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="90ba5-162">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-162">The default is `CurrentUser`.</span></span> <span data-ttu-id="90ba5-163">시스템 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 `LocalMachine`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-163">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="90ba5-164">사용자 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 `CurrentUser`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-164">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90ba5-165">자식 요소</span><span class="sxs-lookup"><span data-stu-id="90ba5-165">Child Elements</span></span>  

 <span data-ttu-id="90ba5-166">없음</span><span class="sxs-lookup"><span data-stu-id="90ba5-166">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="90ba5-167">부모 요소</span><span class="sxs-lookup"><span data-stu-id="90ba5-167">Parent Elements</span></span>  
  
|<span data-ttu-id="90ba5-168">요소</span><span class="sxs-lookup"><span data-stu-id="90ba5-168">Element</span></span>|<span data-ttu-id="90ba5-169">설명</span><span class="sxs-lookup"><span data-stu-id="90ba5-169">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="90ba5-170">서비스에 클라이언트를 인증하는 데 사용되는 X.509 인증서를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-170">Defines an X.509 certificate used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90ba5-171">설명</span><span class="sxs-lookup"><span data-stu-id="90ba5-171">Remarks</span></span>  

 <span data-ttu-id="90ba5-172">`<authentication>` 요소는 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> 클래스에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-172">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="90ba5-173">이것은 클라이언트가 인증되는 방법을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-173">It enables you to customize how clients are authenticated.</span></span> <span data-ttu-id="90ba5-174">`certificateValidationMode` 특성을 `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` 또는 `Custom`으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-174">You can set the `certificateValidationMode` attribute to `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust`, or `Custom`.</span></span> <span data-ttu-id="90ba5-175">기본적으로 수준은로 설정 되며,이 `ChainTrust` 는 각 인증서가 체인 맨 위의 *루트 기관* 에서 종료 되는 인증서의 계층 구조에 있어야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-175">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a *root authority* at the top of the chain.</span></span> <span data-ttu-id="90ba5-176">이 모드가 가장 안전한 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-176">This is the most secure mode.</span></span> <span data-ttu-id="90ba5-177">또한 값을 `PeerOrChainTrust`로 설정할 수 있으며, 이는 자체 발급된 인증서(신뢰 피어)가 신뢰 체인에 있는 인증서와 함께 수락됨을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-177">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="90ba5-178">자체 발급 인증서를 신뢰할 수 있는 기관에서 구입할 필요 없기 때문에 클라이언트 및 서비스를 개발 및 디버깅하는 경우 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-178">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="90ba5-179">클라이언트를 배포하는 경우 `ChainTrust` 값을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-179">When deploying a client, use the `ChainTrust` value instead.</span></span>  
  
 <span data-ttu-id="90ba5-180">또한 값을 `Custom`으로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-180">You can also set the value to `Custom`.</span></span> <span data-ttu-id="90ba5-181">`Custom` 값으로 설정할 경우 `customCertificateValidatorType` 특성도 인증서 유효성을 검사하는 데 사용되는 어셈블리 및 형식으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-181">When set to the `Custom` value, you must also set the `customCertificateValidatorType` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="90ba5-182">사용자 지정 유효성 검사기를 만들려면 추상 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 클래스에서 상속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-182">To create your own custom validator, you must inherit from the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="90ba5-183">자세한 내용은 [방법: 사용자 지정 인증서 유효성 검사기를 사용 하는 서비스 만들기](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-183">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="90ba5-184">예제</span><span class="sxs-lookup"><span data-stu-id="90ba5-184">Example</span></span>  

 <span data-ttu-id="90ba5-185">다음 코드에서는 X.509 인증서와 `<authentication>` 요소의 사용자 지정 유효성 검사 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="90ba5-185">The following code specifies an X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="90ba5-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90ba5-186">See also</span></span>

- <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>
- <xref:System.ServiceModel.Security.X509CertificateValidationMode>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>
- [<span data-ttu-id="90ba5-187">보안 동작</span><span class="sxs-lookup"><span data-stu-id="90ba5-187">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="90ba5-188">방법: 사용자 지정 인증서 유효성 검사기를 사용하는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="90ba5-188">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="90ba5-189">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="90ba5-189">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
