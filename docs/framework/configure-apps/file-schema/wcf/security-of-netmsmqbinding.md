---
title: <netMsmqBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 7877fd59aff581eee5b62a1ca224dbf51c956069
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738674"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="0e70d-102">\<보안 > \<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="0e70d-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="0e70d-103">MSMQ 바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="0e70d-104">전송 또는 SOAP 보안이 사용 되는지 여부를 지정 하 고, 필요한 경우 사용 중인 인증 모드 및 보호 수준을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
<span data-ttu-id="0e70d-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0e70d-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0e70d-106">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="0e70d-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0e70d-107">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="0e70d-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="0e70d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netMsmqBinding >** ](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="0e70d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="0e70d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="0e70d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="0e70d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**보안 >**</span><span class="sxs-lookup"><span data-stu-id="0e70d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e70d-111">구문</span><span class="sxs-lookup"><span data-stu-id="0e70d-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e70d-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0e70d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0e70d-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e70d-114">특성</span><span class="sxs-lookup"><span data-stu-id="0e70d-114">Attributes</span></span>  
  
|<span data-ttu-id="0e70d-115">특성</span><span class="sxs-lookup"><span data-stu-id="0e70d-115">Attribute</span></span>|<span data-ttu-id="0e70d-116">설명</span><span class="sxs-lookup"><span data-stu-id="0e70d-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0e70d-117">모드</span><span class="sxs-lookup"><span data-stu-id="0e70d-117">mode</span></span>|<span data-ttu-id="0e70d-118">무결성, 기밀성 및 인증을 제어하는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-118">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="0e70d-119">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0e70d-120">-없음: 보안을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-120">-   None: This disables security.</span></span><br /><span data-ttu-id="0e70d-121">-전송: 전송에서 보호 및 인증을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-121">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="0e70d-122">이는 두 큐 관리자 간의 메시지 보안에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-122">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="0e70d-123">애플리케이션과 큐 관리자 간에는 보안이 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-123">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="0e70d-124">기존 Msmq 애플리케이션이 이러한 보안 모드 형식과 동일한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-124">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="0e70d-125">-Message: 종단 간 응용 프로그램 보안을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-125">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="0e70d-126">전송 계층에는 보안이 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-126">There is no security offered at the transport layer.</span></span> <span data-ttu-id="0e70d-127">이는 다른 표준 바인딩에서 제공하는 보안과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-127">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="0e70d-128">-Both: 전송 및 SOAP 메시징 계층 모두에서 보안을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-128">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="0e70d-129">두 수준 모두에서 동일한 자격 증명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-129">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="0e70d-130">기본값은 Transport입니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-130">The default value is Transport.</span></span> <span data-ttu-id="0e70d-131">이 특성은 <xref:System.ServiceModel.NetMsmqSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-131">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e70d-132">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0e70d-132">Child Elements</span></span>  
  
|<span data-ttu-id="0e70d-133">요소</span><span class="sxs-lookup"><span data-stu-id="0e70d-133">Element</span></span>|<span data-ttu-id="0e70d-134">설명</span><span class="sxs-lookup"><span data-stu-id="0e70d-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e70d-135">\<message ></span><span class="sxs-lookup"><span data-stu-id="0e70d-135">\<message></span></span>](message-of-netmsmqbinding.md)|<span data-ttu-id="0e70d-136">SOAP 메시지 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-136">Defines the SOAP message security settings.</span></span> <span data-ttu-id="0e70d-137">이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-137">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="0e70d-138">\<전송 ></span><span class="sxs-lookup"><span data-stu-id="0e70d-138">\<transport></span></span>](transport-of-netmsmqbinding.md)|<span data-ttu-id="0e70d-139">MSMQ 전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-139">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="0e70d-140">이 요소는 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0e70d-140">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0e70d-141">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0e70d-141">Parent Elements</span></span>  
  
|<span data-ttu-id="0e70d-142">요소</span><span class="sxs-lookup"><span data-stu-id="0e70d-142">Element</span></span>|<span data-ttu-id="0e70d-143">설명</span><span class="sxs-lookup"><span data-stu-id="0e70d-143">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e70d-144">바인딩</span><span class="sxs-lookup"><span data-stu-id="0e70d-144">binding</span></span>|<span data-ttu-id="0e70d-145">[\<netMsmqBinding](netmsmqbinding.md) 의 바인딩 요소 ></span><span class="sxs-lookup"><span data-stu-id="0e70d-145">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e70d-146">참조</span><span class="sxs-lookup"><span data-stu-id="0e70d-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="0e70d-147">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="0e70d-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0e70d-148">바인딩</span><span class="sxs-lookup"><span data-stu-id="0e70d-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0e70d-149">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="0e70d-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0e70d-150">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="0e70d-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="0e70d-151">\<binding ></span><span class="sxs-lookup"><span data-stu-id="0e70d-151">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="0e70d-152">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="0e70d-152">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
