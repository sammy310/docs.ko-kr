---
description: '다음에 대 한 자세한 정보:: <clientCertificate><serviceCredentials>'
title: <serviceCredentials>의 <clientCertificate>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: c3e6378f9646ec30188e2de3d1c832f363904ad0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638823"
---
# <a name="clientcertificate-of-servicecredentials"></a><span data-ttu-id="eeb8d-103">\<serviceCredentials>의 \<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="eeb8d-103">\<clientCertificate> of \<serviceCredentials></span></span>

<span data-ttu-id="eeb8d-104">이중 통신 패턴에서 서비스의 클라이언트에 대한 메시지를 서명 및 암호화하는 데 사용하는 X.509 인증서를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb8d-104">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="eeb8d-105">구문</span><span class="sxs-lookup"><span data-stu-id="eeb8d-105">Syntax</span></span>  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eeb8d-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="eeb8d-106">Attributes and Elements</span></span>  

 <span data-ttu-id="eeb8d-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb8d-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eeb8d-108">특성</span><span class="sxs-lookup"><span data-stu-id="eeb8d-108">Attributes</span></span>  

 <span data-ttu-id="eeb8d-109">없음</span><span class="sxs-lookup"><span data-stu-id="eeb8d-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eeb8d-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="eeb8d-110">Child Elements</span></span>  
  
|<span data-ttu-id="eeb8d-111">요소</span><span class="sxs-lookup"><span data-stu-id="eeb8d-111">Element</span></span>|<span data-ttu-id="eeb8d-112">설명</span><span class="sxs-lookup"><span data-stu-id="eeb8d-112">Description</span></span>|  
|-------------|-----------------|  
|[\<authentication>](authentication-of-clientcertificate-element.md)|<span data-ttu-id="eeb8d-113">클라이언트 인증서의 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb8d-113">Specifies authentication options for the client certificate.</span></span>|  
|[\<certificate>](certificate-of-clientcertificate-element.md)|<span data-ttu-id="eeb8d-114">사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb8d-114">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eeb8d-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="eeb8d-115">Parent Elements</span></span>  
  
|<span data-ttu-id="eeb8d-116">요소</span><span class="sxs-lookup"><span data-stu-id="eeb8d-116">Element</span></span>|<span data-ttu-id="eeb8d-117">설명</span><span class="sxs-lookup"><span data-stu-id="eeb8d-117">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="eeb8d-118">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb8d-118">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eeb8d-119">설명</span><span class="sxs-lookup"><span data-stu-id="eeb8d-119">Remarks</span></span>  

 <span data-ttu-id="eeb8d-120">이 요소는 서비스가 클라이언트와 안전하게 통신하기 위해 클라이언트의 인증서가 필요한 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeb8d-120">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="eeb8d-121">이는 양방향 통신 패턴을 사용하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb8d-121">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="eeb8d-122">대부분의 일반적인 요청/응답 패턴의 경우 클라이언트는 요청 시 서비스가 클라이언트에게 해당 응답을 암호화 및 서명하는 데 사용하는 인증서를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb8d-122">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="eeb8d-123">그러나 이중 통신 패턴에서는 서비스에 클라이언트의 요청이 없으므로 클라이언트에게 보내는 메시지 보안을 위해 클라이언트의 인증서가 사전에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb8d-123">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="eeb8d-124">따라서 클라이언트 인증서를 out-of-band 협상 방식으로 가져와서 이 요소를 사용하여 인증서를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb8d-124">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="eeb8d-125">이중 서비스에 대 한 자세한 내용은 [방법: 이중 계약 만들기](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eeb8d-125">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="eeb8d-126">이 요소에 설정된 인증서는 `MutualCertificateDuplex` 메시지 보안 인증 모드와 함께 구성되는 바인딩용 클라이언트에 보내는 메시지를 암호화하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb8d-126">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeb8d-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eeb8d-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [<span data-ttu-id="eeb8d-128">방법: 이중 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="eeb8d-128">How to: Create a Duplex Contract</span></span>](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="eeb8d-129">보안 동작</span><span class="sxs-lookup"><span data-stu-id="eeb8d-129">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="eeb8d-130">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="eeb8d-130">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
