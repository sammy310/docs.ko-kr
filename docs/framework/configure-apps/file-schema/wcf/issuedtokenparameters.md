---
description: 다음에 대해 자세히 알아보세요. <issuedTokenParameters>
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 92c8f5aa25ddb71561eb702ba3eb0396456008a6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725664"
---
# \<issuedTokenParameters>

<span data-ttu-id="f1fc4-102">페더레이션 보안 시나리오에서 발급된 보안 토큰에 대한 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-102">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenParameters>**  
  
## <a name="syntax"></a><span data-ttu-id="f1fc4-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1fc4-103">Syntax</span></span>  
  
```xml  
<issuedTokenParameters defaultMessageSecurityVersion="System.ServiceModel.MessageSecurityVersion"
                       inclusionMode="AlwaysToInitiator/AlwaysToRecipient/Never/Once"
                       keySize="Integer"
                       keyType="AsymmetricKey/BearerKey/SymmetricKey"
                       tokenType="String">
  <additionalRequestParameters />
  <claimTypeRequirements>
    <add claimType="URI"
         isOptional="Boolean" />
  </claimTypeRequirements>
  <issuer address="String"
          binding="" />
  <issuerMetadata address="String" />
</issuedTokenParameters>
```  
  
## <a name="type"></a><span data-ttu-id="f1fc4-104">Type</span><span class="sxs-lookup"><span data-stu-id="f1fc4-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1fc4-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f1fc4-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f1fc4-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1fc4-107">특성</span><span class="sxs-lookup"><span data-stu-id="f1fc4-107">Attributes</span></span>  
  
|<span data-ttu-id="f1fc4-108">attribute</span><span class="sxs-lookup"><span data-stu-id="f1fc4-108">Attribute</span></span>|<span data-ttu-id="f1fc4-109">설명</span><span class="sxs-lookup"><span data-stu-id="f1fc4-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f1fc4-110">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="f1fc4-110">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="f1fc4-111">바인딩에서 지원해야 하는 보안 사양(WS-Security, WS-Trust, WS-Secure Conversation, WS-Security Policy) 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-111">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="f1fc4-112">이 값은 <xref:System.ServiceModel.MessageSecurityVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-112">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="f1fc4-113">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="f1fc4-113">inclusionMode</span></span>|<span data-ttu-id="f1fc4-114">토큰 포함 요구 사항을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-114">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="f1fc4-115">이 특성은 <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-115">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="f1fc4-116">keySize</span><span class="sxs-lookup"><span data-stu-id="f1fc4-116">keySize</span></span>|<span data-ttu-id="f1fc4-117">토큰 키 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-117">An integer that specifies the token key size.</span></span> <span data-ttu-id="f1fc4-118">기본값은 256입니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-118">The default value is 256.</span></span>|  
|<span data-ttu-id="f1fc4-119">keyType</span><span class="sxs-lookup"><span data-stu-id="f1fc4-119">keyType</span></span>|<span data-ttu-id="f1fc4-120">키 형식을 지정하는 유효한 <xref:System.IdentityModel.Tokens.SecurityKeyType> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-120">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="f1fc4-121">기본값은 `SymmetricKey`입니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-121">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="f1fc4-122">tokenType</span><span class="sxs-lookup"><span data-stu-id="f1fc4-122">tokenType</span></span>|<span data-ttu-id="f1fc4-123">토큰 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-123">A string that specifies the token type.</span></span> <span data-ttu-id="f1fc4-124">기본값은 "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML"입니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-124">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f1fc4-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f1fc4-125">Child Elements</span></span>  
  
|<span data-ttu-id="f1fc4-126">요소</span><span class="sxs-lookup"><span data-stu-id="f1fc4-126">Element</span></span>|<span data-ttu-id="f1fc4-127">설명</span><span class="sxs-lookup"><span data-stu-id="f1fc4-127">Description</span></span>|  
|-------------|-----------------|  
|[\<additionalRequestParameters>](additionalrequestparameters-element.md)|<span data-ttu-id="f1fc4-128">추가 요청 매개 변수를 지정하는 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-128">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="f1fc4-129">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-129">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="f1fc4-130">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-130">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="f1fc4-131">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-131">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="f1fc4-132">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-132">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[\<issuer>](issuer-of-issuedtokenparameters.md)|<span data-ttu-id="f1fc4-133">현재 토큰을 발급하는 엔드포인트를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-133">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[\<issuerMetadata>](issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="f1fc4-134">토큰 발급자의 메타데이터의 엔드포인트 주소를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-134">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f1fc4-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f1fc4-135">Parent Elements</span></span>  
  
|<span data-ttu-id="f1fc4-136">요소</span><span class="sxs-lookup"><span data-stu-id="f1fc4-136">Element</span></span>|<span data-ttu-id="f1fc4-137">설명</span><span class="sxs-lookup"><span data-stu-id="f1fc4-137">Description</span></span>|  
|-------------|-----------------|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|<span data-ttu-id="f1fc4-138">보안 대화 서비스 개시에 사용되는 기본값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-138">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="f1fc4-139">사용자 지정 바인딩에 대한 보안 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1fc4-139">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f1fc4-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1fc4-140">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f1fc4-141">바인딩</span><span class="sxs-lookup"><span data-stu-id="f1fc4-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f1fc4-142">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="f1fc4-142">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f1fc4-143">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="f1fc4-143">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="f1fc4-144">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="f1fc4-144">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="f1fc4-145">Custom Binding Security</span><span class="sxs-lookup"><span data-stu-id="f1fc4-145">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="f1fc4-146">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="f1fc4-146">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f1fc4-147">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="f1fc4-147">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f1fc4-148">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="f1fc4-148">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="f1fc4-149">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="f1fc4-149">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
