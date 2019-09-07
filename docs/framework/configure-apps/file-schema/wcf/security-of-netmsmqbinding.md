---
title: <netMsmqBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: c780b157d0d566e24c6826c253401a51fbfab69d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399835"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="b82d4-102">\<netMsmqBinding >의 \<보안 ></span><span class="sxs-lookup"><span data-stu-id="b82d4-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="b82d4-103">MSMQ 바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="b82d4-104">이 클래스는 전송 또는 SOAP 보안의 사용 여부 그리고 보안이 사용된다면 어떤 인증 모드 및 보호 수준을 사용하는지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
<span data-ttu-id="b82d4-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b82d4-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b82d4-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b82d4-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b82d4-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="b82d4-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="b82d4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netMsmqBinding >** ](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="b82d4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="b82d4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="b82d4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="b82d4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<보안 >**</span><span class="sxs-lookup"><span data-stu-id="b82d4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b82d4-111">구문</span><span class="sxs-lookup"><span data-stu-id="b82d4-111">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
             clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b82d4-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b82d4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b82d4-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b82d4-114">특성</span><span class="sxs-lookup"><span data-stu-id="b82d4-114">Attributes</span></span>  
  
|<span data-ttu-id="b82d4-115">특성</span><span class="sxs-lookup"><span data-stu-id="b82d4-115">Attribute</span></span>|<span data-ttu-id="b82d4-116">Description</span><span class="sxs-lookup"><span data-stu-id="b82d4-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b82d4-117">모드</span><span class="sxs-lookup"><span data-stu-id="b82d4-117">mode</span></span>|<span data-ttu-id="b82d4-118">무결성, 기밀성 및 인증을 제어하는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-118">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="b82d4-119">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b82d4-120">없음을 이렇게 하면 보안이 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-120">-   None: This disables security.</span></span><br /><span data-ttu-id="b82d4-121">트랜스포트가 전송에서 보호 및 인증을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-121">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="b82d4-122">이는 두 큐 관리자 간의 메시지 보안에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-122">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="b82d4-123">애플리케이션과 큐 관리자 간에는 보안이 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-123">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="b82d4-124">기존 Msmq 애플리케이션이 이러한 보안 모드 형식과 동일한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-124">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="b82d4-125">메시지나 종단 간 응용 프로그램 보안을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-125">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="b82d4-126">전송 계층에는 보안이 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-126">There is no security offered at the transport layer.</span></span> <span data-ttu-id="b82d4-127">이는 다른 표준 바인딩에서 제공하는 보안과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-127">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="b82d4-128">양방향 전송 및 SOAP 메시징 계층 모두에서 보안을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-128">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="b82d4-129">두 수준 모두에서 동일한 자격 증명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-129">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="b82d4-130">기본값은 Transport입니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-130">The default value is Transport.</span></span> <span data-ttu-id="b82d4-131">이 특성은 <xref:System.ServiceModel.NetMsmqSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-131">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b82d4-132">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b82d4-132">Child Elements</span></span>  
  
|<span data-ttu-id="b82d4-133">요소</span><span class="sxs-lookup"><span data-stu-id="b82d4-133">Element</span></span>|<span data-ttu-id="b82d4-134">설명</span><span class="sxs-lookup"><span data-stu-id="b82d4-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b82d4-135">\<message></span><span class="sxs-lookup"><span data-stu-id="b82d4-135">\<message></span></span>](message-of-netmsmqbinding.md)|<span data-ttu-id="b82d4-136">SOAP 메시지 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-136">Defines the SOAP message security settings.</span></span> <span data-ttu-id="b82d4-137">이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-137">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="b82d4-138">\<transport></span><span class="sxs-lookup"><span data-stu-id="b82d4-138">\<transport></span></span>](transport-of-netmsmqbinding.md)|<span data-ttu-id="b82d4-139">MSMQ 전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-139">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="b82d4-140">이 요소는 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b82d4-140">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b82d4-141">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b82d4-141">Parent Elements</span></span>  
  
|<span data-ttu-id="b82d4-142">요소</span><span class="sxs-lookup"><span data-stu-id="b82d4-142">Element</span></span>|<span data-ttu-id="b82d4-143">설명</span><span class="sxs-lookup"><span data-stu-id="b82d4-143">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b82d4-144">바인딩(binding)</span><span class="sxs-lookup"><span data-stu-id="b82d4-144">binding</span></span>|<span data-ttu-id="b82d4-145">NetMsmqBinding >의 바인딩 요소입니다. [ \<](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="b82d4-145">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b82d4-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="b82d4-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="b82d4-147">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="b82d4-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b82d4-148">바인딩</span><span class="sxs-lookup"><span data-stu-id="b82d4-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b82d4-149">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="b82d4-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b82d4-150">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="b82d4-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b82d4-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="b82d4-151">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="b82d4-152">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="b82d4-152">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
