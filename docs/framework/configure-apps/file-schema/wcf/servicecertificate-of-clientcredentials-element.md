---
title: <serviceCertificate> <clientCredentials> 요소
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4fe196ef8737c7abde939e36c2bb7afd5a0d86b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145342"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="c6e61-102">\<serviceCertificate >의 \<clientCredentials > 요소</span><span class="sxs-lookup"><span data-stu-id="c6e61-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>
<span data-ttu-id="c6e61-103">클라이언트에 대해 서비스를 인증할 때 사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e61-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
 <span data-ttu-id="c6e61-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c6e61-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c6e61-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="c6e61-105">\<behaviors></span></span>  
<span data-ttu-id="c6e61-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="c6e61-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="c6e61-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c6e61-107">\<behavior></span></span>  
<span data-ttu-id="c6e61-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="c6e61-108">\<clientCredentials></span></span>  
<span data-ttu-id="c6e61-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="c6e61-109">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6e61-110">구문</span><span class="sxs-lookup"><span data-stu-id="c6e61-110">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6e61-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c6e61-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c6e61-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e61-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6e61-113">특성</span><span class="sxs-lookup"><span data-stu-id="c6e61-113">Attributes</span></span>  
 <span data-ttu-id="c6e61-114">없음</span><span class="sxs-lookup"><span data-stu-id="c6e61-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c6e61-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c6e61-115">Child Elements</span></span>  
  
|<span data-ttu-id="c6e61-116">요소</span><span class="sxs-lookup"><span data-stu-id="c6e61-116">Element</span></span>|<span data-ttu-id="c6e61-117">설명</span><span class="sxs-lookup"><span data-stu-id="c6e61-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6e61-118">\<defaultCertificate></span><span class="sxs-lookup"><span data-stu-id="c6e61-118">\<defaultCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md)|<span data-ttu-id="c6e61-119">서비스 또는 STS가 협상 프로토콜을 통해 인증서를 제공하지 않을 때 사용할 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e61-119">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[<span data-ttu-id="c6e61-120">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="c6e61-120">\<scopedCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|<span data-ttu-id="c6e61-121">인증에 대해 범위가 지정된 특정 서비스가 제공하는 X.509 인증서 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c6e61-121">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="c6e61-122">이 컬렉션은 일반적으로 연합 시나리오에서 보안 토큰 서비스에 대한 서비스 인증서를 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e61-122">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[<span data-ttu-id="c6e61-123">\<authentication></span><span class="sxs-lookup"><span data-stu-id="c6e61-123">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)|<span data-ttu-id="c6e61-124">클라이언트에 사용되는 서비스 인증서의 인증 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e61-124">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c6e61-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c6e61-125">Parent Elements</span></span>  
  
|<span data-ttu-id="c6e61-126">요소</span><span class="sxs-lookup"><span data-stu-id="c6e61-126">Element</span></span>|<span data-ttu-id="c6e61-127">설명</span><span class="sxs-lookup"><span data-stu-id="c6e61-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6e61-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="c6e61-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="c6e61-129">클라이언트가 서비스에 자신을 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e61-129">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6e61-130">설명</span><span class="sxs-lookup"><span data-stu-id="c6e61-130">Remarks</span></span>  
 <span data-ttu-id="c6e61-131">이 구성 요소는 SSL 인증을 사용하여 서비스에서 표시한 인증서의 유효성을 검사하기 위해 클라이언트에서 사용되는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e61-131">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="c6e61-132">여기에는 메시지 보안을 사용하여 서비스에 보내는 메시지를 암호화하는 데 사용하기 위해 클라이언트에서 명시적으로 구성되는 서비스에 대한 인증서도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e61-132">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="c6e61-133">특성을 `serviceCertificate` 요소의 특성과 동일 합니다 [ \<clientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="c6e61-133">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e61-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="c6e61-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="c6e61-135">보안 동작</span><span class="sxs-lookup"><span data-stu-id="c6e61-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="c6e61-136">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="c6e61-136">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="c6e61-137">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="c6e61-137">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="c6e61-138">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="c6e61-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
