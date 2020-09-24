---
title: <serviceCredentials>의 <clientCertificate>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: 9df49777efc80f425cad3b353f95db523a027214
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148919"
---
# <a name="clientcertificate-of-servicecredentials"></a><span data-ttu-id="0b287-102">\<serviceCredentials>의 \<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="0b287-102">\<clientCertificate> of \<serviceCredentials></span></span>

<span data-ttu-id="0b287-103">이중 통신 패턴에서 서비스의 클라이언트에 대한 메시지를 서명 및 암호화하는 데 사용하는 X.509 인증서를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0b287-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="0b287-104">구문</span><span class="sxs-lookup"><span data-stu-id="0b287-104">Syntax</span></span>  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b287-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0b287-105">Attributes and Elements</span></span>  

 <span data-ttu-id="0b287-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b287-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b287-107">특성</span><span class="sxs-lookup"><span data-stu-id="0b287-107">Attributes</span></span>  

 <span data-ttu-id="0b287-108">없음</span><span class="sxs-lookup"><span data-stu-id="0b287-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0b287-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0b287-109">Child Elements</span></span>  
  
|<span data-ttu-id="0b287-110">요소</span><span class="sxs-lookup"><span data-stu-id="0b287-110">Element</span></span>|<span data-ttu-id="0b287-111">설명</span><span class="sxs-lookup"><span data-stu-id="0b287-111">Description</span></span>|  
|-------------|-----------------|  
|[\<authentication>](authentication-of-clientcertificate-element.md)|<span data-ttu-id="0b287-112">클라이언트 인증서의 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b287-112">Specifies authentication options for the client certificate.</span></span>|  
|[\<certificate>](certificate-of-clientcertificate-element.md)|<span data-ttu-id="0b287-113">사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b287-113">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0b287-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0b287-114">Parent Elements</span></span>  
  
|<span data-ttu-id="0b287-115">요소</span><span class="sxs-lookup"><span data-stu-id="0b287-115">Element</span></span>|<span data-ttu-id="0b287-116">설명</span><span class="sxs-lookup"><span data-stu-id="0b287-116">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="0b287-117">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b287-117">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b287-118">설명</span><span class="sxs-lookup"><span data-stu-id="0b287-118">Remarks</span></span>  

 <span data-ttu-id="0b287-119">이 요소는 서비스가 클라이언트와 안전하게 통신하기 위해 클라이언트의 인증서가 필요한 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b287-119">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="0b287-120">이는 양방향 통신 패턴을 사용하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0b287-120">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="0b287-121">대부분의 일반적인 요청/응답 패턴의 경우 클라이언트는 요청 시 서비스가 클라이언트에게 해당 응답을 암호화 및 서명하는 데 사용하는 인증서를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0b287-121">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="0b287-122">그러나 이중 통신 패턴에서는 서비스에 클라이언트의 요청이 없으므로 클라이언트에게 보내는 메시지 보안을 위해 클라이언트의 인증서가 사전에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0b287-122">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="0b287-123">따라서 클라이언트 인증서를 out-of-band 협상 방식으로 가져와서 이 요소를 사용하여 인증서를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b287-123">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="0b287-124">이중 서비스에 대 한 자세한 내용은 [방법: 이중 계약 만들기](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0b287-124">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="0b287-125">이 요소에 설정된 인증서는 `MutualCertificateDuplex` 메시지 보안 인증 모드와 함께 구성되는 바인딩용 클라이언트에 보내는 메시지를 암호화하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b287-125">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b287-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b287-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [<span data-ttu-id="0b287-127">방법: 이중 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="0b287-127">How to: Create a Duplex Contract</span></span>](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="0b287-128">보안 동작</span><span class="sxs-lookup"><span data-stu-id="0b287-128">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="0b287-129">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="0b287-129">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
