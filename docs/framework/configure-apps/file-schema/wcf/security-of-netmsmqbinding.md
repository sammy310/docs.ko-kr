---
title: <netMsmqBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 7877fd59aff581eee5b62a1ca224dbf51c956069
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738674"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="6072f-102">\<netMsmqBinding>의 \<security></span><span class="sxs-lookup"><span data-stu-id="6072f-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="6072f-103">MSMQ 바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="6072f-104">이 클래스는 전송 또는 SOAP 보안의 사용 여부 그리고 보안이 사용된다면 어떤 인증 모드 및 보호 수준을 사용하는지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="6072f-105">구문</span><span class="sxs-lookup"><span data-stu-id="6072f-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6072f-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6072f-106">Attributes and Elements</span></span>  
 <span data-ttu-id="6072f-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6072f-108">특성</span><span class="sxs-lookup"><span data-stu-id="6072f-108">Attributes</span></span>  
  
|<span data-ttu-id="6072f-109">attribute</span><span class="sxs-lookup"><span data-stu-id="6072f-109">Attribute</span></span>|<span data-ttu-id="6072f-110">Description</span><span class="sxs-lookup"><span data-stu-id="6072f-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6072f-111">mode</span><span class="sxs-lookup"><span data-stu-id="6072f-111">mode</span></span>|<span data-ttu-id="6072f-112">무결성, 기밀성 및 인증을 제어하는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-112">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="6072f-113">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-113">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6072f-114">-없음: 보안을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-114">-   None: This disables security.</span></span><br /><span data-ttu-id="6072f-115">-전송: 전송에서 보호 및 인증을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-115">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="6072f-116">이는 두 큐 관리자 간의 메시지 보안에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-116">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="6072f-117">애플리케이션과 큐 관리자 간에는 보안이 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-117">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="6072f-118">기존 Msmq 애플리케이션이 이러한 보안 모드 형식과 동일한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-118">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="6072f-119">-Message: 종단 간 응용 프로그램 보안을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-119">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="6072f-120">전송 계층에는 보안이 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-120">There is no security offered at the transport layer.</span></span> <span data-ttu-id="6072f-121">이는 다른 표준 바인딩에서 제공하는 보안과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-121">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="6072f-122">-Both: 전송 및 SOAP 메시징 계층 모두에서 보안을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-122">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="6072f-123">두 수준 모두에서 동일한 자격 증명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-123">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="6072f-124">기본값은 Transport입니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-124">The default value is Transport.</span></span> <span data-ttu-id="6072f-125">이 특성은 <xref:System.ServiceModel.NetMsmqSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-125">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6072f-126">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6072f-126">Child Elements</span></span>  
  
|<span data-ttu-id="6072f-127">요소</span><span class="sxs-lookup"><span data-stu-id="6072f-127">Element</span></span>|<span data-ttu-id="6072f-128">Description</span><span class="sxs-lookup"><span data-stu-id="6072f-128">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-netmsmqbinding.md)|<span data-ttu-id="6072f-129">SOAP 메시지 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-129">Defines the SOAP message security settings.</span></span> <span data-ttu-id="6072f-130">이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-130">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[\<transport>](transport-of-netmsmqbinding.md)|<span data-ttu-id="6072f-131">MSMQ 전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-131">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="6072f-132">이 요소는 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6072f-132">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6072f-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6072f-133">Parent Elements</span></span>  
  
|<span data-ttu-id="6072f-134">요소</span><span class="sxs-lookup"><span data-stu-id="6072f-134">Element</span></span>|<span data-ttu-id="6072f-135">Description</span><span class="sxs-lookup"><span data-stu-id="6072f-135">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6072f-136">바인딩</span><span class="sxs-lookup"><span data-stu-id="6072f-136">binding</span></span>|<span data-ttu-id="6072f-137">의 바인딩 요소입니다.[\<netMsmqBinding>](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6072f-137">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6072f-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6072f-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="6072f-139">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="6072f-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6072f-140">바인딩</span><span class="sxs-lookup"><span data-stu-id="6072f-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6072f-141">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="6072f-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6072f-142">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="6072f-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="6072f-143">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="6072f-143">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
