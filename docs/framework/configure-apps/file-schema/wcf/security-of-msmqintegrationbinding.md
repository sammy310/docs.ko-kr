---
title: <msmqIntegrationBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 2268bf48a2b86c3b3b25db006e6f8f55ea33af73
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738687"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="b6ea8-102">\<보안 > \<msmqIntegrationBinding ></span><span class="sxs-lookup"><span data-stu-id="b6ea8-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="b6ea8-103">MSMQ(메시지 큐) 통합 채널을 위한 전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ea8-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
<span data-ttu-id="b6ea8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6ea8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b6ea8-105">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="b6ea8-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b6ea8-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="b6ea8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="b6ea8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<msmqIntegrationBinding >** ](msmqintegrationbinding.md)</span><span class="sxs-lookup"><span data-stu-id="b6ea8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)</span></span>\
<span data-ttu-id="b6ea8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="b6ea8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="b6ea8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**보안 >**</span><span class="sxs-lookup"><span data-stu-id="b6ea8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6ea8-110">구문</span><span class="sxs-lookup"><span data-stu-id="b6ea8-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6ea8-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b6ea8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b6ea8-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ea8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6ea8-113">특성</span><span class="sxs-lookup"><span data-stu-id="b6ea8-113">Attributes</span></span>  
  
|<span data-ttu-id="b6ea8-114">특성</span><span class="sxs-lookup"><span data-stu-id="b6ea8-114">Attribute</span></span>|<span data-ttu-id="b6ea8-115">설명</span><span class="sxs-lookup"><span data-stu-id="b6ea8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b6ea8-116">모드</span><span class="sxs-lookup"><span data-stu-id="b6ea8-116">mode</span></span>|<span data-ttu-id="b6ea8-117">메시지 큐 통합 채널로 무결성, 기밀성 및 인증을 제어하는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ea8-117">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="b6ea8-118">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ea8-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b6ea8-119">-없음: 보안을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ea8-119">-   None: This disables security.</span></span><br /><span data-ttu-id="b6ea8-120">-전송: 전송에서 보호 및 인증을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ea8-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="b6ea8-121">이는 두 큐 관리자 간의 메시지 보안에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6ea8-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="b6ea8-122">애플리케이션과 큐 관리자 간에는 보안이 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ea8-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="b6ea8-123">기존 Msmq 애플리케이션이 이러한 보안 모드 형식과 동일한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b6ea8-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="b6ea8-124">기본값은 `Transport`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ea8-124">The default value is `Transport`.</span></span> <span data-ttu-id="b6ea8-125">이 특성은 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b6ea8-125">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6ea8-126">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b6ea8-126">Child Elements</span></span>  
  
|<span data-ttu-id="b6ea8-127">요소</span><span class="sxs-lookup"><span data-stu-id="b6ea8-127">Element</span></span>|<span data-ttu-id="b6ea8-128">설명</span><span class="sxs-lookup"><span data-stu-id="b6ea8-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6ea8-129">\<전송 ></span><span class="sxs-lookup"><span data-stu-id="b6ea8-129">\<transport></span></span>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="b6ea8-130">메시지 큐 통합 전송을 위한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ea8-130">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="b6ea8-131">이 요소는 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b6ea8-131">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6ea8-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b6ea8-132">Parent Elements</span></span>  
  
|<span data-ttu-id="b6ea8-133">요소</span><span class="sxs-lookup"><span data-stu-id="b6ea8-133">Element</span></span>|<span data-ttu-id="b6ea8-134">설명</span><span class="sxs-lookup"><span data-stu-id="b6ea8-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6ea8-135">\<binding ></span><span class="sxs-lookup"><span data-stu-id="b6ea8-135">\<binding></span></span>](bindings.md)|<span data-ttu-id="b6ea8-136">[\<msmqIntegrationBinding >](msmqintegrationbinding.md)의 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b6ea8-136">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6ea8-137">참조</span><span class="sxs-lookup"><span data-stu-id="b6ea8-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="b6ea8-138">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="b6ea8-138">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="b6ea8-139">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="b6ea8-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b6ea8-140">바인딩</span><span class="sxs-lookup"><span data-stu-id="b6ea8-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b6ea8-141">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="b6ea8-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b6ea8-142">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="b6ea8-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b6ea8-143">\<binding ></span><span class="sxs-lookup"><span data-stu-id="b6ea8-143">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="b6ea8-144">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="b6ea8-144">\<msmqIntegrationBinding></span></span>](msmqintegrationbinding.md)
