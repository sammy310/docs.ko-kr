---
title: <msmqIntegrationBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 5b74c95ef2933fcf7e8d49aed89d95acbd288b80
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936702"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="56770-102">\<msmqIntegrationBinding >의 \<보안 ></span><span class="sxs-lookup"><span data-stu-id="56770-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="56770-103">MSMQ(메시지 큐) 통합 채널을 위한 전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="56770-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="56770-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="56770-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="56770-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="56770-105">\<bindings></span></span>  
<span data-ttu-id="56770-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="56770-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="56770-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="56770-107">\<binding></span></span>  
<span data-ttu-id="56770-108">\<security></span><span class="sxs-lookup"><span data-stu-id="56770-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56770-109">구문</span><span class="sxs-lookup"><span data-stu-id="56770-109">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>
  <binding>
    <security mode="None/Transport">
      <transport msmqAuthenticationMode="None/Windows/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
      <message algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               defaultProtectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</msmqIntegrationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56770-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="56770-110">Attributes and Elements</span></span>  
 <span data-ttu-id="56770-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="56770-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56770-112">특성</span><span class="sxs-lookup"><span data-stu-id="56770-112">Attributes</span></span>  
  
|<span data-ttu-id="56770-113">특성</span><span class="sxs-lookup"><span data-stu-id="56770-113">Attribute</span></span>|<span data-ttu-id="56770-114">Description</span><span class="sxs-lookup"><span data-stu-id="56770-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56770-115">모드</span><span class="sxs-lookup"><span data-stu-id="56770-115">mode</span></span>|<span data-ttu-id="56770-116">메시지 큐 통합 채널로 무결성, 기밀성 및 인증을 제어하는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="56770-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="56770-117">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="56770-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="56770-118">없음을 이렇게 하면 보안이 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56770-118">-   None: This disables security.</span></span><br /><span data-ttu-id="56770-119">트랜스포트가 전송에서 보호 및 인증을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="56770-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="56770-120">이는 두 큐 관리자 간의 메시지 보안에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="56770-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="56770-121">애플리케이션과 큐 관리자 간에는 보안이 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56770-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="56770-122">기존 Msmq 애플리케이션이 이러한 보안 모드 형식과 동일한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="56770-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="56770-123">기본값은 `Transport`입니다.</span><span class="sxs-lookup"><span data-stu-id="56770-123">The default value is `Transport`.</span></span> <span data-ttu-id="56770-124">이 특성은 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="56770-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56770-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="56770-125">Child Elements</span></span>  
  
|<span data-ttu-id="56770-126">요소</span><span class="sxs-lookup"><span data-stu-id="56770-126">Element</span></span>|<span data-ttu-id="56770-127">Description</span><span class="sxs-lookup"><span data-stu-id="56770-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56770-128">\<transport></span><span class="sxs-lookup"><span data-stu-id="56770-128">\<transport></span></span>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="56770-129">메시지 큐 통합 전송을 위한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="56770-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="56770-130">이 요소는 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="56770-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="56770-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="56770-131">Parent Elements</span></span>  
  
|<span data-ttu-id="56770-132">요소</span><span class="sxs-lookup"><span data-stu-id="56770-132">Element</span></span>|<span data-ttu-id="56770-133">설명</span><span class="sxs-lookup"><span data-stu-id="56770-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56770-134">\<binding></span><span class="sxs-lookup"><span data-stu-id="56770-134">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="56770-135">[ \<MsmqIntegrationBinding >](msmqintegrationbinding.md)의 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="56770-135">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56770-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="56770-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="56770-137">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="56770-137">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="56770-138">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="56770-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="56770-139">바인딩</span><span class="sxs-lookup"><span data-stu-id="56770-139">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="56770-140">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="56770-140">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="56770-141">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="56770-141">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="56770-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="56770-142">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="56770-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="56770-143">\<msmqIntegrationBinding></span></span>](msmqintegrationbinding.md)
