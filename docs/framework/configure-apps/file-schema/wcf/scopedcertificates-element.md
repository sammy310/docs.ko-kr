---
description: '다음에 대 한 자세한 정보: <scopedCertificates> 요소'
title: <scopedCertificates> 요소
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: 7aa108031831539396e8f737a214982655dd6bb1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683335"
---
# <a name="scopedcertificates-element"></a><span data-ttu-id="116dd-103">\<scopedCertificates> 요소</span><span class="sxs-lookup"><span data-stu-id="116dd-103">\<scopedCertificates> Element</span></span>

<span data-ttu-id="116dd-104">인증에 대해 범위가 지정된 특정 서비스가 제공하는 X.509 인증서 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="116dd-104">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="116dd-105">이 컬렉션은 일반적으로 연합 시나리오에서 보안 토큰 서비스에 대한 서비스 인증서를 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="116dd-105">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopedCertificates>**  
  
## <a name="syntax"></a><span data-ttu-id="116dd-106">구문</span><span class="sxs-lookup"><span data-stu-id="116dd-106">Syntax</span></span>  
  
```xml  
<scopedCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       targetUri="string"
       x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</scopedCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="116dd-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="116dd-107">Attributes and Elements</span></span>  

 <span data-ttu-id="116dd-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="116dd-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="116dd-109">특성</span><span class="sxs-lookup"><span data-stu-id="116dd-109">Attributes</span></span>  

 <span data-ttu-id="116dd-110">없음</span><span class="sxs-lookup"><span data-stu-id="116dd-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="116dd-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="116dd-111">Child Elements</span></span>  
  
|<span data-ttu-id="116dd-112">요소</span><span class="sxs-lookup"><span data-stu-id="116dd-112">Element</span></span>|<span data-ttu-id="116dd-113">설명</span><span class="sxs-lookup"><span data-stu-id="116dd-113">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-scopedcertificates-element.md)|<span data-ttu-id="116dd-114">범위가 지정된 인증서 컬렉션에 X.509 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="116dd-114">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="116dd-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="116dd-115">Parent Elements</span></span>  
  
|<span data-ttu-id="116dd-116">요소</span><span class="sxs-lookup"><span data-stu-id="116dd-116">Element</span></span>|<span data-ttu-id="116dd-117">설명</span><span class="sxs-lookup"><span data-stu-id="116dd-117">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="116dd-118">클라이언트에 대해 서비스를 인증할 때 사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="116dd-118">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="116dd-119">설명</span><span class="sxs-lookup"><span data-stu-id="116dd-119">Remarks</span></span>  

 <span data-ttu-id="116dd-120">이 컬렉션을 사용하면 클라이언트가 통신할 서비스의 URL을 기반으로 사용할 서비스 인증서를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="116dd-120">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="116dd-121">이는 클라이언트가 여러 서비스 (종료 서비스 및 중간 보안 토큰 서비스)와 통신할 수 있는 발급 된 토큰 시나리오에서 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="116dd-121">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="116dd-122">인증서 기반 메시지 보안을 사용 하는 바인딩의 경우이 인증서는 서비스에 대 한 메시지를 암호화 하는 데 사용 되며, 클라이언트에 응답을 서명 하는 데 서비스에서 사용 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="116dd-122">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="116dd-123">바인딩을 수행할 때 서비스용 인증서가 필요하고 서비스 URL에 대한 특정 인증서를 ScopedCertificates에서 찾을 수 없는 경우, 기본 인증서가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="116dd-123">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="116dd-124">자세한 내용은 [방법: 페더레이션된 클라이언트 만들기](../../../wcf/feature-details/how-to-create-a-federated-client.md)의 "범위 인증서" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="116dd-124">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="116dd-125">예제</span><span class="sxs-lookup"><span data-stu-id="116dd-125">Example</span></span>  

 <span data-ttu-id="116dd-126">다음 예제에서는 클라이언트에서 도메인 이름이 HTTP 프로토콜을 통한 끝점과 통신할 때 사용할 서비스 인증서를 지정 합니다 `http://www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="116dd-126">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is `http://www.contoso.com` over the HTTP protocol.</span></span>  
  
```xml  
<serviceCertificate>
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="116dd-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="116dd-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="116dd-128">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="116dd-128">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="116dd-129">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="116dd-129">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [\<add>](add-of-scopedcertificates-element.md)
- [<span data-ttu-id="116dd-130">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="116dd-130">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="116dd-131">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="116dd-131">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
