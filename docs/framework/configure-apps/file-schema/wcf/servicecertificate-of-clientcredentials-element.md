---
title: <serviceCertificate>of <clientCredentials> 요소
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4c7489a171bdd5cb4b747ca99f1b7ff6dd65517b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399678"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="7727a-102">\<\<clientCredentials > 요소의 serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="7727a-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>
<span data-ttu-id="7727a-103">클라이언트에 대해 서비스를 인증할 때 사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7727a-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
<span data-ttu-id="7727a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7727a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7727a-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7727a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7727a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7727a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="7727a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7727a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="7727a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7727a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="7727a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="7727a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="7727a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceCertificate >**</span><span class="sxs-lookup"><span data-stu-id="7727a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7727a-111">구문</span><span class="sxs-lookup"><span data-stu-id="7727a-111">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7727a-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7727a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7727a-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7727a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7727a-114">특성</span><span class="sxs-lookup"><span data-stu-id="7727a-114">Attributes</span></span>  
 <span data-ttu-id="7727a-115">없음</span><span class="sxs-lookup"><span data-stu-id="7727a-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7727a-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7727a-116">Child Elements</span></span>  
  
|<span data-ttu-id="7727a-117">요소</span><span class="sxs-lookup"><span data-stu-id="7727a-117">Element</span></span>|<span data-ttu-id="7727a-118">설명</span><span class="sxs-lookup"><span data-stu-id="7727a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7727a-119">\<defaultCertificate></span><span class="sxs-lookup"><span data-stu-id="7727a-119">\<defaultCertificate></span></span>](defaultcertificate-element.md)|<span data-ttu-id="7727a-120">서비스 또는 STS가 협상 프로토콜을 통해 인증서를 제공하지 않을 때 사용할 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7727a-120">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[<span data-ttu-id="7727a-121">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="7727a-121">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="7727a-122">인증에 대해 범위가 지정된 특정 서비스가 제공하는 X.509 인증서 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7727a-122">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="7727a-123">이 컬렉션은 일반적으로 연합 시나리오에서 보안 토큰 서비스에 대한 서비스 인증서를 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7727a-123">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[<span data-ttu-id="7727a-124">\<authentication></span><span class="sxs-lookup"><span data-stu-id="7727a-124">\<authentication></span></span>](authentication-of-servicecertificate-element.md)|<span data-ttu-id="7727a-125">클라이언트에 사용되는 서비스 인증서의 인증 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7727a-125">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7727a-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7727a-126">Parent Elements</span></span>  
  
|<span data-ttu-id="7727a-127">요소</span><span class="sxs-lookup"><span data-stu-id="7727a-127">Element</span></span>|<span data-ttu-id="7727a-128">Description</span><span class="sxs-lookup"><span data-stu-id="7727a-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7727a-129">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="7727a-129">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="7727a-130">클라이언트가 서비스에 자신을 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7727a-130">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7727a-131">설명</span><span class="sxs-lookup"><span data-stu-id="7727a-131">Remarks</span></span>  
 <span data-ttu-id="7727a-132">이 구성 요소는 SSL 인증을 사용하여 서비스에서 표시한 인증서의 유효성을 검사하기 위해 클라이언트에서 사용되는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7727a-132">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="7727a-133">여기에는 메시지 보안을 사용하여 서비스에 보내는 메시지를 암호화하는 데 사용하기 위해 클라이언트에서 명시적으로 구성되는 서비스에 대한 인증서도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7727a-133">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="7727a-134">`serviceCertificate` 요소의 특성은 [ \<clientCertificate >](clientcertificate-of-clientcredentials-element.md)의 특성과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="7727a-134">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7727a-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="7727a-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="7727a-136">보안 동작</span><span class="sxs-lookup"><span data-stu-id="7727a-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7727a-137">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="7727a-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="7727a-138">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="7727a-138">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="7727a-139">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="7727a-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
