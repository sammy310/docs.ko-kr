---
title: <msmqIntegrationBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: e4f10ab994429c6cbb690caef38114b8340e6839
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399862"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="9ec5d-102">\<msmqIntegrationBinding >의 \<보안 ></span><span class="sxs-lookup"><span data-stu-id="9ec5d-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="9ec5d-103">MSMQ(메시지 큐) 통합 채널을 위한 전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec5d-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
<span data-ttu-id="9ec5d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9ec5d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9ec5d-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9ec5d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9ec5d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="9ec5d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="9ec5d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<msmqIntegrationBinding >** ](msmqintegrationbinding.md)</span><span class="sxs-lookup"><span data-stu-id="9ec5d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)</span></span>\
<span data-ttu-id="9ec5d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="9ec5d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="9ec5d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<보안 >**</span><span class="sxs-lookup"><span data-stu-id="9ec5d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ec5d-110">구문</span><span class="sxs-lookup"><span data-stu-id="9ec5d-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ec5d-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9ec5d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9ec5d-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec5d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ec5d-113">특성</span><span class="sxs-lookup"><span data-stu-id="9ec5d-113">Attributes</span></span>  
  
|<span data-ttu-id="9ec5d-114">특성</span><span class="sxs-lookup"><span data-stu-id="9ec5d-114">Attribute</span></span>|<span data-ttu-id="9ec5d-115">Description</span><span class="sxs-lookup"><span data-stu-id="9ec5d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ec5d-116">모드</span><span class="sxs-lookup"><span data-stu-id="9ec5d-116">mode</span></span>|<span data-ttu-id="9ec5d-117">메시지 큐 통합 채널로 무결성, 기밀성 및 인증을 제어하는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec5d-117">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="9ec5d-118">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec5d-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9ec5d-119">없음을 이렇게 하면 보안이 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ec5d-119">-   None: This disables security.</span></span><br /><span data-ttu-id="9ec5d-120">트랜스포트가 전송에서 보호 및 인증을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec5d-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="9ec5d-121">이는 두 큐 관리자 간의 메시지 보안에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ec5d-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="9ec5d-122">애플리케이션과 큐 관리자 간에는 보안이 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec5d-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="9ec5d-123">기존 Msmq 애플리케이션이 이러한 보안 모드 형식과 동일한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9ec5d-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="9ec5d-124">기본값은 `Transport`입니다.</span><span class="sxs-lookup"><span data-stu-id="9ec5d-124">The default value is `Transport`.</span></span> <span data-ttu-id="9ec5d-125">이 특성은 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9ec5d-125">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ec5d-126">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9ec5d-126">Child Elements</span></span>  
  
|<span data-ttu-id="9ec5d-127">요소</span><span class="sxs-lookup"><span data-stu-id="9ec5d-127">Element</span></span>|<span data-ttu-id="9ec5d-128">설명</span><span class="sxs-lookup"><span data-stu-id="9ec5d-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ec5d-129">\<transport></span><span class="sxs-lookup"><span data-stu-id="9ec5d-129">\<transport></span></span>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="9ec5d-130">메시지 큐 통합 전송을 위한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec5d-130">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="9ec5d-131">이 요소는 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9ec5d-131">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ec5d-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9ec5d-132">Parent Elements</span></span>  
  
|<span data-ttu-id="9ec5d-133">요소</span><span class="sxs-lookup"><span data-stu-id="9ec5d-133">Element</span></span>|<span data-ttu-id="9ec5d-134">설명</span><span class="sxs-lookup"><span data-stu-id="9ec5d-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ec5d-135">\<binding></span><span class="sxs-lookup"><span data-stu-id="9ec5d-135">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="9ec5d-136">[ \<MsmqIntegrationBinding >](msmqintegrationbinding.md)의 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9ec5d-136">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ec5d-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="9ec5d-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="9ec5d-138">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="9ec5d-138">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="9ec5d-139">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="9ec5d-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9ec5d-140">바인딩</span><span class="sxs-lookup"><span data-stu-id="9ec5d-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9ec5d-141">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="9ec5d-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9ec5d-142">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="9ec5d-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9ec5d-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="9ec5d-143">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="9ec5d-144">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="9ec5d-144">\<msmqIntegrationBinding></span></span>](msmqintegrationbinding.md)
