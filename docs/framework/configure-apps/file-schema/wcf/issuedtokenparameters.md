---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 8432463ff62e4b5e54a491b574cc6a5285efe220
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397949"
---
# \<issuedTokenParameters>
<span data-ttu-id="5f573-101">페더레이션 보안 시나리오에서 발급된 보안 토큰에 대한 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-101">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenParameters>**  
  
## <a name="syntax"></a><span data-ttu-id="5f573-102">구문</span><span class="sxs-lookup"><span data-stu-id="5f573-102">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="5f573-103">Type</span><span class="sxs-lookup"><span data-stu-id="5f573-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f573-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5f573-104">Attributes and Elements</span></span>  
 <span data-ttu-id="5f573-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f573-106">특성</span><span class="sxs-lookup"><span data-stu-id="5f573-106">Attributes</span></span>  
  
|<span data-ttu-id="5f573-107">attribute</span><span class="sxs-lookup"><span data-stu-id="5f573-107">Attribute</span></span>|<span data-ttu-id="5f573-108">Description</span><span class="sxs-lookup"><span data-stu-id="5f573-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5f573-109">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="5f573-109">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="5f573-110">바인딩에서 지원해야 하는 보안 사양(WS-Security, WS-Trust, WS-Secure Conversation, WS-Security Policy) 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-110">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="5f573-111">이 값은 <xref:System.ServiceModel.MessageSecurityVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-111">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="5f573-112">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="5f573-112">inclusionMode</span></span>|<span data-ttu-id="5f573-113">토큰 포함 요구 사항을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-113">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="5f573-114">이 특성은 <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-114">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="5f573-115">keySize</span><span class="sxs-lookup"><span data-stu-id="5f573-115">keySize</span></span>|<span data-ttu-id="5f573-116">토큰 키 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-116">An integer that specifies the token key size.</span></span> <span data-ttu-id="5f573-117">기본값은 256입니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-117">The default value is 256.</span></span>|  
|<span data-ttu-id="5f573-118">keyType</span><span class="sxs-lookup"><span data-stu-id="5f573-118">keyType</span></span>|<span data-ttu-id="5f573-119">키 형식을 지정하는 유효한 <xref:System.IdentityModel.Tokens.SecurityKeyType> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-119">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="5f573-120">기본값은 `SymmetricKey`입니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-120">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="5f573-121">tokenType</span><span class="sxs-lookup"><span data-stu-id="5f573-121">tokenType</span></span>|<span data-ttu-id="5f573-122">토큰 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-122">A string that specifies the token type.</span></span> <span data-ttu-id="5f573-123">기본값은 "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML"입니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-123">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5f573-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5f573-124">Child Elements</span></span>  
  
|<span data-ttu-id="5f573-125">요소</span><span class="sxs-lookup"><span data-stu-id="5f573-125">Element</span></span>|<span data-ttu-id="5f573-126">Description</span><span class="sxs-lookup"><span data-stu-id="5f573-126">Description</span></span>|  
|-------------|-----------------|  
|[\<additionalRequestParameters>](additionalrequestparameters-element.md)|<span data-ttu-id="5f573-127">추가 요청 매개 변수를 지정하는 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-127">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="5f573-128">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-128">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="5f573-129">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-129">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="5f573-130">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-130">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="5f573-131">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-131">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[\<issuer>](issuer-of-issuedtokenparameters.md)|<span data-ttu-id="5f573-132">현재 토큰을 발급하는 엔드포인트를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-132">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[\<issuerMetadata>](issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="5f573-133">토큰 발급자의 메타데이터의 엔드포인트 주소를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-133">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5f573-134">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5f573-134">Parent Elements</span></span>  
  
|<span data-ttu-id="5f573-135">요소</span><span class="sxs-lookup"><span data-stu-id="5f573-135">Element</span></span>|<span data-ttu-id="5f573-136">Description</span><span class="sxs-lookup"><span data-stu-id="5f573-136">Description</span></span>|  
|-------------|-----------------|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|<span data-ttu-id="5f573-137">보안 대화 서비스 개시에 사용되는 기본값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-137">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="5f573-138">사용자 지정 바인딩에 대한 보안 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f573-138">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f573-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f573-139">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="5f573-140">바인딩</span><span class="sxs-lookup"><span data-stu-id="5f573-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5f573-141">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="5f573-141">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5f573-142">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="5f573-142">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="5f573-143">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="5f573-143">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="5f573-144">Custom Binding Security</span><span class="sxs-lookup"><span data-stu-id="5f573-144">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="5f573-145">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="5f573-145">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="5f573-146">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="5f573-146">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5f573-147">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="5f573-147">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="5f573-148">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="5f573-148">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
