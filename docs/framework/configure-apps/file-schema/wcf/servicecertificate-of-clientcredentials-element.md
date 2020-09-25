---
title: <serviceCertificate> of <clientCredentials> 요소
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 502452c664f2dcb0856f72e25ff8b1517f432919
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172894"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="2b940-102">\<serviceCertificate> of \<clientCredentials> 요소</span><span class="sxs-lookup"><span data-stu-id="2b940-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>

<span data-ttu-id="2b940-103">클라이언트에 대해 서비스를 인증할 때 사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b940-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="2b940-104">구문</span><span class="sxs-lookup"><span data-stu-id="2b940-104">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b940-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2b940-105">Attributes and Elements</span></span>  

 <span data-ttu-id="2b940-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2b940-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b940-107">특성</span><span class="sxs-lookup"><span data-stu-id="2b940-107">Attributes</span></span>  

 <span data-ttu-id="2b940-108">없음</span><span class="sxs-lookup"><span data-stu-id="2b940-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2b940-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2b940-109">Child Elements</span></span>  
  
|<span data-ttu-id="2b940-110">요소</span><span class="sxs-lookup"><span data-stu-id="2b940-110">Element</span></span>|<span data-ttu-id="2b940-111">설명</span><span class="sxs-lookup"><span data-stu-id="2b940-111">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultCertificate>](defaultcertificate-element.md)|<span data-ttu-id="2b940-112">서비스 또는 STS가 협상 프로토콜을 통해 인증서를 제공하지 않을 때 사용할 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b940-112">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="2b940-113">인증에 대해 범위가 지정된 특정 서비스가 제공하는 X.509 인증서 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b940-113">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="2b940-114">이 컬렉션은 일반적으로 연합 시나리오에서 보안 토큰 서비스에 대한 서비스 인증서를 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b940-114">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[\<authentication>](authentication-of-servicecertificate-element.md)|<span data-ttu-id="2b940-115">클라이언트에 사용되는 서비스 인증서의 인증 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b940-115">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2b940-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2b940-116">Parent Elements</span></span>  
  
|<span data-ttu-id="2b940-117">요소</span><span class="sxs-lookup"><span data-stu-id="2b940-117">Element</span></span>|<span data-ttu-id="2b940-118">설명</span><span class="sxs-lookup"><span data-stu-id="2b940-118">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="2b940-119">클라이언트가 서비스에 자신을 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b940-119">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b940-120">설명</span><span class="sxs-lookup"><span data-stu-id="2b940-120">Remarks</span></span>  

 <span data-ttu-id="2b940-121">이 구성 요소는 SSL 인증을 사용하여 서비스에서 표시한 인증서의 유효성을 검사하기 위해 클라이언트에서 사용되는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b940-121">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="2b940-122">여기에는 메시지 보안을 사용하여 서비스에 보내는 메시지를 암호화하는 데 사용하기 위해 클라이언트에서 명시적으로 구성되는 서비스에 대한 인증서도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b940-122">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="2b940-123">요소의 특성은 `serviceCertificate` 의 특성과 동일 합니다 [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md) .</span><span class="sxs-lookup"><span data-stu-id="2b940-123">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b940-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b940-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="2b940-125">보안 동작</span><span class="sxs-lookup"><span data-stu-id="2b940-125">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="2b940-126">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="2b940-126">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="2b940-127">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="2b940-127">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="2b940-128">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="2b940-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
