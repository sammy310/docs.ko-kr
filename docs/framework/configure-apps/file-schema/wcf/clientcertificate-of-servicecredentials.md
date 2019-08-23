---
title: <serviceCredentials>의 <clientCertificate>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: 277e5e33bcc7f9d417da7ce24caa4c6200c23e23
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919547"
---
# <a name="clientcertificate-of-servicecredentials"></a><span data-ttu-id="d4f91-102">\<serviceCredentials의 \<clientCertificate > ></span><span class="sxs-lookup"><span data-stu-id="d4f91-102">\<clientCertificate> of \<serviceCredentials></span></span>
<span data-ttu-id="d4f91-103">이중 통신 패턴에서 서비스의 클라이언트에 대한 메시지를 서명 및 암호화하는 데 사용하는 X.509 인증서를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f91-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
 <span data-ttu-id="d4f91-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d4f91-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d4f91-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="d4f91-105">\<behaviors></span></span>  
<span data-ttu-id="d4f91-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="d4f91-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d4f91-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="d4f91-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="d4f91-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d4f91-108">\<behavior></span></span>  
<span data-ttu-id="d4f91-109">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="d4f91-109">\<serviceCredentials></span></span>  
<span data-ttu-id="d4f91-110">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="d4f91-110">\<clientCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4f91-111">구문</span><span class="sxs-lookup"><span data-stu-id="d4f91-111">Syntax</span></span>  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4f91-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d4f91-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d4f91-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f91-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4f91-114">특성</span><span class="sxs-lookup"><span data-stu-id="d4f91-114">Attributes</span></span>  
 <span data-ttu-id="d4f91-115">없음</span><span class="sxs-lookup"><span data-stu-id="d4f91-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d4f91-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d4f91-116">Child Elements</span></span>  
  
|<span data-ttu-id="d4f91-117">요소</span><span class="sxs-lookup"><span data-stu-id="d4f91-117">Element</span></span>|<span data-ttu-id="d4f91-118">Description</span><span class="sxs-lookup"><span data-stu-id="d4f91-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4f91-119">\<authentication></span><span class="sxs-lookup"><span data-stu-id="d4f91-119">\<authentication></span></span>](authentication-of-clientcertificate-element.md)|<span data-ttu-id="d4f91-120">클라이언트 인증서의 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f91-120">Specifies authentication options for the client certificate.</span></span>|  
|[<span data-ttu-id="d4f91-121">\<certificate></span><span class="sxs-lookup"><span data-stu-id="d4f91-121">\<certificate></span></span>](certificate-of-clientcertificate-element.md)|<span data-ttu-id="d4f91-122">사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f91-122">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d4f91-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d4f91-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d4f91-124">요소</span><span class="sxs-lookup"><span data-stu-id="d4f91-124">Element</span></span>|<span data-ttu-id="d4f91-125">Description</span><span class="sxs-lookup"><span data-stu-id="d4f91-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4f91-126">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="d4f91-126">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="d4f91-127">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f91-127">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4f91-128">설명</span><span class="sxs-lookup"><span data-stu-id="d4f91-128">Remarks</span></span>  
 <span data-ttu-id="d4f91-129">이 요소는 서비스가 클라이언트와 안전하게 통신하기 위해 클라이언트의 인증서가 필요한 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4f91-129">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="d4f91-130">이는 양방향 통신 패턴을 사용하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f91-130">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="d4f91-131">대부분의 일반적인 요청/응답 패턴의 경우 클라이언트는 요청 시 서비스가 클라이언트에게 해당 응답을 암호화 및 서명하는 데 사용하는 인증서를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f91-131">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="d4f91-132">그러나 이중 통신 패턴에서는 서비스에 클라이언트의 요청이 없으므로 클라이언트에게 보내는 메시지 보안을 위해 클라이언트의 인증서가 사전에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f91-132">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="d4f91-133">따라서 클라이언트 인증서를 out-of-band 협상 방식으로 가져와서 이 요소를 사용하여 인증서를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f91-133">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="d4f91-134">이중 서비스 [에 대 한 자세한 내용은 방법: 이중 계약](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d4f91-134">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="d4f91-135">이 요소에 설정된 인증서는 `MutualCertificateDuplex` 메시지 보안 인증 모드와 함께 구성되는 바인딩용 클라이언트에 보내는 메시지를 암호화하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f91-135">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f91-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="d4f91-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [<span data-ttu-id="d4f91-137">방법: 이중 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="d4f91-137">How to: Create a Duplex Contract</span></span>](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="d4f91-138">보안 동작</span><span class="sxs-lookup"><span data-stu-id="d4f91-138">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="d4f91-139">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="d4f91-139">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
