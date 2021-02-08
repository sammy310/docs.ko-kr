---
description: '다음에 대 한 자세한 정보:: <security><netMsmqBinding>'
title: <netMsmqBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 1b60d9e390e371555f4c3abf4988e79bb0f04fe8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786852"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="53240-103">\<netMsmqBinding>의 \<security></span><span class="sxs-lookup"><span data-stu-id="53240-103">\<security> of \<netMsmqBinding></span></span>

<span data-ttu-id="53240-104">MSMQ 바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="53240-104">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="53240-105">이 클래스는 전송 또는 SOAP 보안의 사용 여부 그리고 보안이 사용된다면 어떤 인증 모드 및 보호 수준을 사용하는지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="53240-105">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="53240-106">구문</span><span class="sxs-lookup"><span data-stu-id="53240-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53240-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="53240-107">Attributes and Elements</span></span>  

 <span data-ttu-id="53240-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="53240-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53240-109">특성</span><span class="sxs-lookup"><span data-stu-id="53240-109">Attributes</span></span>  
  
|<span data-ttu-id="53240-110">attribute</span><span class="sxs-lookup"><span data-stu-id="53240-110">Attribute</span></span>|<span data-ttu-id="53240-111">설명</span><span class="sxs-lookup"><span data-stu-id="53240-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53240-112">mode</span><span class="sxs-lookup"><span data-stu-id="53240-112">mode</span></span>|<span data-ttu-id="53240-113">무결성, 기밀성 및 인증을 제어하는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="53240-113">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="53240-114">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="53240-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="53240-115">-없음: 보안을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53240-115">-   None: This disables security.</span></span><br /><span data-ttu-id="53240-116">-전송: 전송에서 보호 및 인증을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="53240-116">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="53240-117">이는 두 큐 관리자 간의 메시지 보안에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="53240-117">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="53240-118">애플리케이션과 큐 관리자 간에는 보안이 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53240-118">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="53240-119">기존 Msmq 애플리케이션이 이러한 보안 모드 형식과 동일한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="53240-119">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="53240-120">-Message: 종단 간 응용 프로그램 보안을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="53240-120">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="53240-121">전송 계층에는 보안이 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53240-121">There is no security offered at the transport layer.</span></span> <span data-ttu-id="53240-122">이는 다른 표준 바인딩에서 제공하는 보안과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="53240-122">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="53240-123">-Both: 전송 및 SOAP 메시징 계층 모두에서 보안을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="53240-123">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="53240-124">두 수준 모두에서 동일한 자격 증명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="53240-124">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="53240-125">기본값은 Transport입니다.</span><span class="sxs-lookup"><span data-stu-id="53240-125">The default value is Transport.</span></span> <span data-ttu-id="53240-126">이 특성은 <xref:System.ServiceModel.NetMsmqSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="53240-126">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53240-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="53240-127">Child Elements</span></span>  
  
|<span data-ttu-id="53240-128">요소</span><span class="sxs-lookup"><span data-stu-id="53240-128">Element</span></span>|<span data-ttu-id="53240-129">설명</span><span class="sxs-lookup"><span data-stu-id="53240-129">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-netmsmqbinding.md)|<span data-ttu-id="53240-130">SOAP 메시지 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="53240-130">Defines the SOAP message security settings.</span></span> <span data-ttu-id="53240-131">이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="53240-131">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[\<transport>](transport-of-netmsmqbinding.md)|<span data-ttu-id="53240-132">MSMQ 전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="53240-132">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="53240-133">이 요소는 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="53240-133">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="53240-134">부모 요소</span><span class="sxs-lookup"><span data-stu-id="53240-134">Parent Elements</span></span>  
  
|<span data-ttu-id="53240-135">요소</span><span class="sxs-lookup"><span data-stu-id="53240-135">Element</span></span>|<span data-ttu-id="53240-136">설명</span><span class="sxs-lookup"><span data-stu-id="53240-136">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="53240-137">바인딩</span><span class="sxs-lookup"><span data-stu-id="53240-137">binding</span></span>|<span data-ttu-id="53240-138">의 바인딩 요소입니다. [\<netMsmqBinding>](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="53240-138">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53240-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53240-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="53240-140">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="53240-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="53240-141">바인딩</span><span class="sxs-lookup"><span data-stu-id="53240-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="53240-142">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="53240-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="53240-143">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="53240-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="53240-144">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="53240-144">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
