---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 8432463ff62e4b5e54a491b574cc6a5285efe220
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397949"
---
# <a name="issuedtokenparameters"></a><span data-ttu-id="c5e63-101">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="c5e63-101">\<issuedTokenParameters></span></span>
<span data-ttu-id="c5e63-102">페더레이션 보안 시나리오에서 발급된 보안 토큰에 대한 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-102">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
<span data-ttu-id="c5e63-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c5e63-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c5e63-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c5e63-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c5e63-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c5e63-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="c5e63-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="c5e63-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="c5e63-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="c5e63-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c5e63-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<보안 >** ](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="c5e63-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="c5e63-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuedTokenParameters >**</span><span class="sxs-lookup"><span data-stu-id="c5e63-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenParameters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5e63-110">구문</span><span class="sxs-lookup"><span data-stu-id="c5e63-110">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="c5e63-111">형식</span><span class="sxs-lookup"><span data-stu-id="c5e63-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5e63-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c5e63-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c5e63-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5e63-114">특성</span><span class="sxs-lookup"><span data-stu-id="c5e63-114">Attributes</span></span>  
  
|<span data-ttu-id="c5e63-115">특성</span><span class="sxs-lookup"><span data-stu-id="c5e63-115">Attribute</span></span>|<span data-ttu-id="c5e63-116">Description</span><span class="sxs-lookup"><span data-stu-id="c5e63-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c5e63-117">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="c5e63-117">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="c5e63-118">바인딩에서 지원해야 하는 보안 사양(WS-Security, WS-Trust, WS-Secure Conversation, WS-Security Policy) 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-118">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="c5e63-119">이 값은 <xref:System.ServiceModel.MessageSecurityVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-119">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="c5e63-120">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="c5e63-120">inclusionMode</span></span>|<span data-ttu-id="c5e63-121">토큰 포함 요구 사항을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-121">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="c5e63-122">이 특성은 <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-122">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="c5e63-123">keySize</span><span class="sxs-lookup"><span data-stu-id="c5e63-123">keySize</span></span>|<span data-ttu-id="c5e63-124">토큰 키 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-124">An integer that specifies the token key size.</span></span> <span data-ttu-id="c5e63-125">기본값은 256입니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-125">The default value is 256.</span></span>|  
|<span data-ttu-id="c5e63-126">keyType</span><span class="sxs-lookup"><span data-stu-id="c5e63-126">keyType</span></span>|<span data-ttu-id="c5e63-127">키 형식을 지정하는 유효한 <xref:System.IdentityModel.Tokens.SecurityKeyType> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-127">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="c5e63-128">기본값은 `SymmetricKey`입니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-128">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="c5e63-129">tokenType</span><span class="sxs-lookup"><span data-stu-id="c5e63-129">tokenType</span></span>|<span data-ttu-id="c5e63-130">토큰 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-130">A string that specifies the token type.</span></span> <span data-ttu-id="c5e63-131">기본값은 "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML"입니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-131">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5e63-132">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c5e63-132">Child Elements</span></span>  
  
|<span data-ttu-id="c5e63-133">요소</span><span class="sxs-lookup"><span data-stu-id="c5e63-133">Element</span></span>|<span data-ttu-id="c5e63-134">설명</span><span class="sxs-lookup"><span data-stu-id="c5e63-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5e63-135">\<additionalRequestParameters></span><span class="sxs-lookup"><span data-stu-id="c5e63-135">\<additionalRequestParameters></span></span>](additionalrequestparameters-element.md)|<span data-ttu-id="c5e63-136">추가 요청 매개 변수를 지정하는 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-136">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="c5e63-137">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="c5e63-137">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="c5e63-138">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-138">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="c5e63-139">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="c5e63-140">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="c5e63-141">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-141">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="c5e63-142">\<issuer></span><span class="sxs-lookup"><span data-stu-id="c5e63-142">\<issuer></span></span>](issuer-of-issuedtokenparameters.md)|<span data-ttu-id="c5e63-143">현재 토큰을 발급하는 엔드포인트를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-143">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="c5e63-144">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="c5e63-144">\<issuerMetadata></span></span>](issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="c5e63-145">토큰 발급자의 메타데이터의 엔드포인트 주소를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-145">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c5e63-146">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c5e63-146">Parent Elements</span></span>  
  
|<span data-ttu-id="c5e63-147">요소</span><span class="sxs-lookup"><span data-stu-id="c5e63-147">Element</span></span>|<span data-ttu-id="c5e63-148">Description</span><span class="sxs-lookup"><span data-stu-id="c5e63-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5e63-149">\<secureConversationBootstrap></span><span class="sxs-lookup"><span data-stu-id="c5e63-149">\<secureConversationBootstrap></span></span>](secureconversationbootstrap.md)|<span data-ttu-id="c5e63-150">보안 대화 서비스 개시에 사용되는 기본값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-150">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="c5e63-151">\<security></span><span class="sxs-lookup"><span data-stu-id="c5e63-151">\<security></span></span>](security-of-custombinding.md)|<span data-ttu-id="c5e63-152">사용자 지정 바인딩에 대한 보안 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e63-152">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5e63-153">참고자료</span><span class="sxs-lookup"><span data-stu-id="c5e63-153">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c5e63-154">바인딩</span><span class="sxs-lookup"><span data-stu-id="c5e63-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c5e63-155">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="c5e63-155">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c5e63-156">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="c5e63-156">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c5e63-157">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c5e63-157">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="c5e63-158">방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="c5e63-158">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="c5e63-159">사용자 지정 바인딩 보안</span><span class="sxs-lookup"><span data-stu-id="c5e63-159">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="c5e63-160">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="c5e63-160">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c5e63-161">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="c5e63-161">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c5e63-162">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="c5e63-162">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="c5e63-163">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="c5e63-163">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
