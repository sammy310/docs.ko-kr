---
description: '다음에 대 한 자세한 정보:: <security><msmqIntegrationBinding>'
title: <msmqIntegrationBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 4ad4cb89599198661d764cfeb985609be027c0eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683205"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="f75b9-103">\<msmqIntegrationBinding>의 \<security></span><span class="sxs-lookup"><span data-stu-id="f75b9-103">\<security> of \<msmqIntegrationBinding></span></span>

<span data-ttu-id="f75b9-104">MSMQ(메시지 큐) 통합 채널을 위한 전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f75b9-104">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="f75b9-105">구문</span><span class="sxs-lookup"><span data-stu-id="f75b9-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f75b9-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f75b9-106">Attributes and Elements</span></span>  

 <span data-ttu-id="f75b9-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f75b9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f75b9-108">특성</span><span class="sxs-lookup"><span data-stu-id="f75b9-108">Attributes</span></span>  
  
|<span data-ttu-id="f75b9-109">attribute</span><span class="sxs-lookup"><span data-stu-id="f75b9-109">Attribute</span></span>|<span data-ttu-id="f75b9-110">설명</span><span class="sxs-lookup"><span data-stu-id="f75b9-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f75b9-111">mode</span><span class="sxs-lookup"><span data-stu-id="f75b9-111">mode</span></span>|<span data-ttu-id="f75b9-112">메시지 큐 통합 채널로 무결성, 기밀성 및 인증을 제어하는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f75b9-112">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="f75b9-113">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f75b9-113">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f75b9-114">-없음: 보안을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f75b9-114">-   None: This disables security.</span></span><br /><span data-ttu-id="f75b9-115">-전송: 전송에서 보호 및 인증을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f75b9-115">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="f75b9-116">이는 두 큐 관리자 간의 메시지 보안에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f75b9-116">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="f75b9-117">애플리케이션과 큐 관리자 간에는 보안이 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f75b9-117">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="f75b9-118">기존 Msmq 애플리케이션이 이러한 보안 모드 형식과 동일한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f75b9-118">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="f75b9-119">기본값은 `Transport`입니다.</span><span class="sxs-lookup"><span data-stu-id="f75b9-119">The default value is `Transport`.</span></span> <span data-ttu-id="f75b9-120">이 특성은 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f75b9-120">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f75b9-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f75b9-121">Child Elements</span></span>  
  
|<span data-ttu-id="f75b9-122">요소</span><span class="sxs-lookup"><span data-stu-id="f75b9-122">Element</span></span>|<span data-ttu-id="f75b9-123">설명</span><span class="sxs-lookup"><span data-stu-id="f75b9-123">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="f75b9-124">메시지 큐 통합 전송을 위한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f75b9-124">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="f75b9-125">이 요소는 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f75b9-125">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f75b9-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f75b9-126">Parent Elements</span></span>  
  
|<span data-ttu-id="f75b9-127">요소</span><span class="sxs-lookup"><span data-stu-id="f75b9-127">Element</span></span>|<span data-ttu-id="f75b9-128">설명</span><span class="sxs-lookup"><span data-stu-id="f75b9-128">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="f75b9-129">의 바인딩 요소 [\<msmqIntegrationBinding>](msmqintegrationbinding.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="f75b9-129">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f75b9-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f75b9-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="f75b9-131">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="f75b9-131">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="f75b9-132">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="f75b9-132">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f75b9-133">바인딩</span><span class="sxs-lookup"><span data-stu-id="f75b9-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f75b9-134">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="f75b9-134">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f75b9-135">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="f75b9-135">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [\<msmqIntegrationBinding>](msmqintegrationbinding.md)
