---
title: <ws2007FederationHttpBinding>의 <security> 요소
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: b85c54c6507313522286e0c66504cfd0c8afb2b0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738728"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="0f4d7-102">\<ws2007FederationHttpBinding의 \<security > 요소 ></span><span class="sxs-lookup"><span data-stu-id="0f4d7-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="0f4d7-103">[\<ws2007FederationHttpBinding >](ws2007federationhttpbinding.md) 요소의 보안 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4d7-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
<span data-ttu-id="0f4d7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0f4d7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0f4d7-105">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="0f4d7-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0f4d7-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="0f4d7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="0f4d7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007FederationHttpBinding >** ](ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="0f4d7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="0f4d7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="0f4d7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="0f4d7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**보안 >**</span><span class="sxs-lookup"><span data-stu-id="0f4d7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f4d7-110">구문</span><span class="sxs-lookup"><span data-stu-id="0f4d7-110">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/  Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               defaultProtectionLevel="none/sign/EncryptAndSign"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f4d7-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0f4d7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0f4d7-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4d7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f4d7-113">특성</span><span class="sxs-lookup"><span data-stu-id="0f4d7-113">Attributes</span></span>  
  
|<span data-ttu-id="0f4d7-114">특성</span><span class="sxs-lookup"><span data-stu-id="0f4d7-114">Attribute</span></span>|<span data-ttu-id="0f4d7-115">설명</span><span class="sxs-lookup"><span data-stu-id="0f4d7-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="0f4d7-116">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="0f4d7-116">Optional.</span></span> <span data-ttu-id="0f4d7-117">적용 되는 보안 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4d7-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="0f4d7-118">기본값은 `Message`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4d7-118">The default value is `Message`.</span></span> <span data-ttu-id="0f4d7-119">이 특성은 <xref:System.ServiceModel.WSFederationHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0f4d7-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="0f4d7-120">mode 특성</span><span class="sxs-lookup"><span data-stu-id="0f4d7-120">mode Attribute</span></span>  
  
|<span data-ttu-id="0f4d7-121">값</span><span class="sxs-lookup"><span data-stu-id="0f4d7-121">Value</span></span>|<span data-ttu-id="0f4d7-122">설명</span><span class="sxs-lookup"><span data-stu-id="0f4d7-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f4d7-123">없음</span><span class="sxs-lookup"><span data-stu-id="0f4d7-123">None</span></span>|<span data-ttu-id="0f4d7-124">SOAP 메시지는 전송 중에는 안전 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f4d7-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="0f4d7-125">메시지</span><span class="sxs-lookup"><span data-stu-id="0f4d7-125">Message</span></span>|<span data-ttu-id="0f4d7-126">SOAP 메시지 보안을 사용 하 여 무결성, 기밀성, 서버 인증 및 클라이언트 인증을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4d7-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="0f4d7-127">기본적으로 본문은 암호화 되 고 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f4d7-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="0f4d7-128">인증서를 사용하여 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4d7-128">The service must be configured with a certificate.</span></span> <span data-ttu-id="0f4d7-129">클라이언트 인증은 보안 토큰 서비스에 의해 클라이언트에 발급 된 토큰을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4d7-129">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="0f4d7-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="0f4d7-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="0f4d7-131">HTTPS를 사용하여 무결성, 기밀성 및 서버 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4d7-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="0f4d7-132">인증서를 사용하여 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4d7-132">The service must be configured with a certificate.</span></span> <span data-ttu-id="0f4d7-133">클라이언트 인증은 SOAP 메시지 보안을 통해 제공 되며 보안 토큰 서비스가 클라이언트에 발급 한 토큰을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4d7-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f4d7-134">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0f4d7-134">Child Elements</span></span>  
  
|<span data-ttu-id="0f4d7-135">요소</span><span class="sxs-lookup"><span data-stu-id="0f4d7-135">Element</span></span>|<span data-ttu-id="0f4d7-136">설명</span><span class="sxs-lookup"><span data-stu-id="0f4d7-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f4d7-137">\<message ></span><span class="sxs-lookup"><span data-stu-id="0f4d7-137">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="0f4d7-138">메시지 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4d7-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="0f4d7-139">이 요소는 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0f4d7-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0f4d7-140">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0f4d7-140">Parent Elements</span></span>  
  
|<span data-ttu-id="0f4d7-141">요소</span><span class="sxs-lookup"><span data-stu-id="0f4d7-141">Element</span></span>|<span data-ttu-id="0f4d7-142">설명</span><span class="sxs-lookup"><span data-stu-id="0f4d7-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f4d7-143">\<binding ></span><span class="sxs-lookup"><span data-stu-id="0f4d7-143">\<binding></span></span>](bindings.md)|<span data-ttu-id="0f4d7-144">[\<wsDualHttpBinding >](wsdualhttpbinding.md)의 모든 바인딩 기능을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4d7-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f4d7-145">참조</span><span class="sxs-lookup"><span data-stu-id="0f4d7-145">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="0f4d7-146">방법: WSFederationHttpBinding 만들기</span><span class="sxs-lookup"><span data-stu-id="0f4d7-146">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="0f4d7-147">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="0f4d7-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0f4d7-148">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="0f4d7-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="0f4d7-149">바인딩</span><span class="sxs-lookup"><span data-stu-id="0f4d7-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0f4d7-150">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="0f4d7-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0f4d7-151">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="0f4d7-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="0f4d7-152">\<binding ></span><span class="sxs-lookup"><span data-stu-id="0f4d7-152">\<binding></span></span>](bindings.md)
