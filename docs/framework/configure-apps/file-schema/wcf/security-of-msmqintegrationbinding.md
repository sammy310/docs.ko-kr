---
title: <msmqIntegrationBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: be2f48f7d9c3be4ea0a5fe95436930b3f23c7551
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170066"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="98f4e-102">\<msmqIntegrationBinding>의 \<security></span><span class="sxs-lookup"><span data-stu-id="98f4e-102">\<security> of \<msmqIntegrationBinding></span></span>

<span data-ttu-id="98f4e-103">MSMQ(메시지 큐) 통합 채널을 위한 전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="98f4e-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="98f4e-104">구문</span><span class="sxs-lookup"><span data-stu-id="98f4e-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98f4e-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="98f4e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="98f4e-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="98f4e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98f4e-107">특성</span><span class="sxs-lookup"><span data-stu-id="98f4e-107">Attributes</span></span>  
  
|<span data-ttu-id="98f4e-108">attribute</span><span class="sxs-lookup"><span data-stu-id="98f4e-108">Attribute</span></span>|<span data-ttu-id="98f4e-109">설명</span><span class="sxs-lookup"><span data-stu-id="98f4e-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="98f4e-110">mode</span><span class="sxs-lookup"><span data-stu-id="98f4e-110">mode</span></span>|<span data-ttu-id="98f4e-111">메시지 큐 통합 채널로 무결성, 기밀성 및 인증을 제어하는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="98f4e-111">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="98f4e-112">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="98f4e-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="98f4e-113">-없음: 보안을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98f4e-113">-   None: This disables security.</span></span><br /><span data-ttu-id="98f4e-114">-전송: 전송에서 보호 및 인증을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98f4e-114">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="98f4e-115">이는 두 큐 관리자 간의 메시지 보안에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="98f4e-115">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="98f4e-116">애플리케이션과 큐 관리자 간에는 보안이 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98f4e-116">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="98f4e-117">기존 Msmq 애플리케이션이 이러한 보안 모드 형식과 동일한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="98f4e-117">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="98f4e-118">기본값은 `Transport`입니다.</span><span class="sxs-lookup"><span data-stu-id="98f4e-118">The default value is `Transport`.</span></span> <span data-ttu-id="98f4e-119">이 특성은 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="98f4e-119">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="98f4e-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="98f4e-120">Child Elements</span></span>  
  
|<span data-ttu-id="98f4e-121">요소</span><span class="sxs-lookup"><span data-stu-id="98f4e-121">Element</span></span>|<span data-ttu-id="98f4e-122">설명</span><span class="sxs-lookup"><span data-stu-id="98f4e-122">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="98f4e-123">메시지 큐 통합 전송을 위한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="98f4e-123">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="98f4e-124">이 요소는 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="98f4e-124">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="98f4e-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="98f4e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="98f4e-126">요소</span><span class="sxs-lookup"><span data-stu-id="98f4e-126">Element</span></span>|<span data-ttu-id="98f4e-127">설명</span><span class="sxs-lookup"><span data-stu-id="98f4e-127">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="98f4e-128">의 바인딩 요소 [\<msmqIntegrationBinding>](msmqintegrationbinding.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="98f4e-128">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="98f4e-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98f4e-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="98f4e-130">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="98f4e-130">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="98f4e-131">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="98f4e-131">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="98f4e-132">바인딩하</span><span class="sxs-lookup"><span data-stu-id="98f4e-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="98f4e-133">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="98f4e-133">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="98f4e-134">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="98f4e-134">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [\<msmqIntegrationBinding>](msmqintegrationbinding.md)
