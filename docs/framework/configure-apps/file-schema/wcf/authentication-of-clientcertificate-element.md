---
description: '다음에 대 한 자세한 정보: <authentication> <clientCertificate> 요소'
title: <authentication> of <clientCertificate> 요소
ms.date: 03/30/2017
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
ms.openlocfilehash: 346e1012fd9d799b093be15381aebbc026ea2591
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749898"
---
# <a name="authentication-of-clientcertificate-element"></a><span data-ttu-id="2f795-103">\<authentication> of \<clientCertificate> 요소</span><span class="sxs-lookup"><span data-stu-id="2f795-103">\<authentication> of \<clientCertificate> Element</span></span>

<span data-ttu-id="2f795-104">서비스에서 사용되는 클라이언트 인증서에 대한 인증 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-104">Specifies authentication behaviors for client certificates used by a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
## <a name="syntax"></a><span data-ttu-id="2f795-105">구문</span><span class="sxs-lookup"><span data-stu-id="2f795-105">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                includeWindowsGroups="Boolean"
                mapClientCertificateToWindowsAccount="Boolean"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f795-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2f795-106">Attributes and Elements</span></span>  

 <span data-ttu-id="2f795-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f795-108">특성</span><span class="sxs-lookup"><span data-stu-id="2f795-108">Attributes</span></span>  
  
|<span data-ttu-id="2f795-109">attribute</span><span class="sxs-lookup"><span data-stu-id="2f795-109">Attribute</span></span>|<span data-ttu-id="2f795-110">설명</span><span class="sxs-lookup"><span data-stu-id="2f795-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2f795-111">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="2f795-111">customCertificateValidatorType</span></span>|<span data-ttu-id="2f795-112">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-112">Optional string.</span></span> <span data-ttu-id="2f795-113">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-113">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="2f795-114">이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-114">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="2f795-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="2f795-115">certificateValidationMode</span></span>|<span data-ttu-id="2f795-116">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-116">Optional enumeration.</span></span> <span data-ttu-id="2f795-117">자격 증명의 유효성을 검사하는 데 사용되는 모드 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-117">Specifies one of the modes used to validate credentials.</span></span> <span data-ttu-id="2f795-118">이 특성은 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-118">This attribute is of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> type.</span></span> <span data-ttu-id="2f795-119"><xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>으로 설정되면 `customCertificateValidator`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-119">If set to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="2f795-120">기본값은 <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-120">The default is <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span></span>|  
|<span data-ttu-id="2f795-121">includeWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="2f795-121">includeWindowsGroups</span></span>|<span data-ttu-id="2f795-122">선택적 부울입니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-122">Optional Boolean.</span></span> <span data-ttu-id="2f795-123">Windows 그룹이 보안 컨텍스트에 포함될지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-123">Specifies if Windows groups are included in the security context.</span></span> <span data-ttu-id="2f795-124">이 특성을 `true`로 설정하면 전체 그룹이 확장되므로 성능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-124">Setting this attribute to `true` has a performance impact, as it results in a full group expansion.</span></span> <span data-ttu-id="2f795-125">사용자가 속한 그룹의 목록을 설정할 필요가 없으면 이 특성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-125">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|<span data-ttu-id="2f795-126">mapClientCertificateToWindowsAccount</span><span class="sxs-lookup"><span data-stu-id="2f795-126">mapClientCertificateToWindowsAccount</span></span>|<span data-ttu-id="2f795-127">부울.</span><span class="sxs-lookup"><span data-stu-id="2f795-127">Boolean.</span></span> <span data-ttu-id="2f795-128">클라이언트가 인증서를 사용하여 Windows ID에 매핑될 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-128">Specifies whether the client can be mapped to a Windows identity using the certificate.</span></span> <span data-ttu-id="2f795-129">이 작업을 위해서는 Active Directory를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-129">Active Directory must be enabled to do this.</span></span>|  
|<span data-ttu-id="2f795-130">revocationMode</span><span class="sxs-lookup"><span data-stu-id="2f795-130">revocationMode</span></span>|<span data-ttu-id="2f795-131">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-131">Optional enumeration.</span></span> <span data-ttu-id="2f795-132">RCL(해지된 인증서 목록)을 검사하는 데 사용되는 모드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-132">One of the modes used to check for a revoked certificate lists (RCL).</span></span> <span data-ttu-id="2f795-133">기본값은 `Online`입니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-133">The default is `Online`.</span></span> <span data-ttu-id="2f795-134">이 값은 HTTP 전송 보안을 사용할 때 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-134">This value is ignored when using HTTP transport security.</span></span>|  
|<span data-ttu-id="2f795-135">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="2f795-135">trustedStoreLocation</span></span>|<span data-ttu-id="2f795-136">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-136">Optional enumeration.</span></span> <span data-ttu-id="2f795-137">시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-137">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="2f795-138">서비스 인증서가 클라이언트와 협상될 때 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-138">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="2f795-139">지정 된 저장소 위치에 있는 **신뢰할 수 있는 사용자** 저장소에 대해 유효성 검사가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-139">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="2f795-140">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-140">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="2f795-141">customCertificateValidatorType 특성</span><span class="sxs-lookup"><span data-stu-id="2f795-141">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="2f795-142">값</span><span class="sxs-lookup"><span data-stu-id="2f795-142">Value</span></span>|<span data-ttu-id="2f795-143">Description</span><span class="sxs-lookup"><span data-stu-id="2f795-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2f795-144">String</span><span class="sxs-lookup"><span data-stu-id="2f795-144">String</span></span>|<span data-ttu-id="2f795-145">형식 이름 및 어셈블리와 형식을 찾는 데 사용되는 기타 데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-145">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="2f795-146">certificateValidationMode 특성</span><span class="sxs-lookup"><span data-stu-id="2f795-146">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="2f795-147">값</span><span class="sxs-lookup"><span data-stu-id="2f795-147">Value</span></span>|<span data-ttu-id="2f795-148">설명</span><span class="sxs-lookup"><span data-stu-id="2f795-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2f795-149">열거형</span><span class="sxs-lookup"><span data-stu-id="2f795-149">Enumeration</span></span>|<span data-ttu-id="2f795-150">None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-150">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="2f795-151">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-151">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="2f795-152">revocationMode 특성</span><span class="sxs-lookup"><span data-stu-id="2f795-152">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="2f795-153">값</span><span class="sxs-lookup"><span data-stu-id="2f795-153">Value</span></span>|<span data-ttu-id="2f795-154">설명</span><span class="sxs-lookup"><span data-stu-id="2f795-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2f795-155">열거형</span><span class="sxs-lookup"><span data-stu-id="2f795-155">Enumeration</span></span>|<span data-ttu-id="2f795-156">NoCheck, Online, Offline 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-156">One of the following values: NoCheck, Online, Offline.</span></span> <span data-ttu-id="2f795-157">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-157">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="2f795-158">trustedStoreLocation 특성</span><span class="sxs-lookup"><span data-stu-id="2f795-158">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="2f795-159">값</span><span class="sxs-lookup"><span data-stu-id="2f795-159">Value</span></span>|<span data-ttu-id="2f795-160">설명</span><span class="sxs-lookup"><span data-stu-id="2f795-160">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2f795-161">열거형</span><span class="sxs-lookup"><span data-stu-id="2f795-161">Enumeration</span></span>|<span data-ttu-id="2f795-162">`LocalMachine` 또는 `CurrentUser` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-162">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="2f795-163">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-163">The default is `CurrentUser`.</span></span> <span data-ttu-id="2f795-164">시스템 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 `LocalMachine`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-164">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="2f795-165">사용자 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 `CurrentUser`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-165">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f795-166">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2f795-166">Child Elements</span></span>  

 <span data-ttu-id="2f795-167">없음</span><span class="sxs-lookup"><span data-stu-id="2f795-167">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f795-168">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2f795-168">Parent Elements</span></span>  
  
|<span data-ttu-id="2f795-169">요소</span><span class="sxs-lookup"><span data-stu-id="2f795-169">Element</span></span>|<span data-ttu-id="2f795-170">설명</span><span class="sxs-lookup"><span data-stu-id="2f795-170">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="2f795-171">서비스에 클라이언트를 인증하는 데 사용되는 X.509 인증서를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-171">Defines an X.509 certificate used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f795-172">설명</span><span class="sxs-lookup"><span data-stu-id="2f795-172">Remarks</span></span>  

 <span data-ttu-id="2f795-173">`<authentication>` 요소는 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> 클래스에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-173">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="2f795-174">이것은 클라이언트가 인증되는 방법을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-174">It enables you to customize how clients are authenticated.</span></span> <span data-ttu-id="2f795-175">`certificateValidationMode` 특성을 `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` 또는 `Custom`으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-175">You can set the `certificateValidationMode` attribute to `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust`, or `Custom`.</span></span> <span data-ttu-id="2f795-176">기본적으로 수준은로 설정 되며,이 `ChainTrust` 는 각 인증서가 체인 맨 위의 *루트 기관* 에서 종료 되는 인증서의 계층 구조에 있어야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-176">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a *root authority* at the top of the chain.</span></span> <span data-ttu-id="2f795-177">이 모드가 가장 안전한 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-177">This is the most secure mode.</span></span> <span data-ttu-id="2f795-178">또한 값을 `PeerOrChainTrust`로 설정할 수 있으며, 이는 자체 발급된 인증서(신뢰 피어)가 신뢰 체인에 있는 인증서와 함께 수락됨을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-178">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="2f795-179">자체 발급 인증서를 신뢰할 수 있는 기관에서 구입할 필요 없기 때문에 클라이언트 및 서비스를 개발 및 디버깅하는 경우 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-179">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="2f795-180">클라이언트를 배포하는 경우 `ChainTrust` 값을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-180">When deploying a client, use the `ChainTrust` value instead.</span></span>  
  
 <span data-ttu-id="2f795-181">또한 값을 `Custom`으로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-181">You can also set the value to `Custom`.</span></span> <span data-ttu-id="2f795-182">`Custom` 값으로 설정할 경우 `customCertificateValidatorType` 특성도 인증서 유효성을 검사하는 데 사용되는 어셈블리 및 형식으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-182">When set to the `Custom` value, you must also set the `customCertificateValidatorType` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="2f795-183">사용자 지정 유효성 검사기를 만들려면 추상 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 클래스에서 상속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-183">To create your own custom validator, you must inherit from the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="2f795-184">자세한 내용은 [방법: 사용자 지정 인증서 유효성 검사기를 사용 하는 서비스 만들기](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-184">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f795-185">예제</span><span class="sxs-lookup"><span data-stu-id="2f795-185">Example</span></span>  

 <span data-ttu-id="2f795-186">다음 코드에서는 X.509 인증서와 `<authentication>` 요소의 사용자 지정 유효성 검사 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f795-186">The following code specifies an X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2f795-187">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f795-187">See also</span></span>

- <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>
- <xref:System.ServiceModel.Security.X509CertificateValidationMode>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>
- [<span data-ttu-id="2f795-188">보안 동작</span><span class="sxs-lookup"><span data-stu-id="2f795-188">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="2f795-189">방법: 사용자 지정 인증서 유효성 검사기를 사용하는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="2f795-189">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="2f795-190">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="2f795-190">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
