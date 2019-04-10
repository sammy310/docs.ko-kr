---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 6bdf56e3d2084dec8d44e1c4d3f0c1e50b711b92
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153142"
---
# <a name="issuedtokenparameters"></a><span data-ttu-id="6aa0b-101">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="6aa0b-101">\<issuedTokenParameters></span></span>
<span data-ttu-id="6aa0b-102">페더레이션 보안 시나리오에서 발급된 보안 토큰에 대한 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-102">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="6aa0b-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6aa0b-103">\<system.serviceModel></span></span>  
<span data-ttu-id="6aa0b-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="6aa0b-104">\<bindings></span></span>  
<span data-ttu-id="6aa0b-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="6aa0b-105">\<customBinding></span></span>  
<span data-ttu-id="6aa0b-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="6aa0b-106">\<binding></span></span>  
<span data-ttu-id="6aa0b-107">\<security></span><span class="sxs-lookup"><span data-stu-id="6aa0b-107">\<security></span></span>  
<span data-ttu-id="6aa0b-108">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="6aa0b-108">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aa0b-109">구문</span><span class="sxs-lookup"><span data-stu-id="6aa0b-109">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="6aa0b-110">형식</span><span class="sxs-lookup"><span data-stu-id="6aa0b-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6aa0b-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6aa0b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6aa0b-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6aa0b-113">특성</span><span class="sxs-lookup"><span data-stu-id="6aa0b-113">Attributes</span></span>  
  
|<span data-ttu-id="6aa0b-114">특성</span><span class="sxs-lookup"><span data-stu-id="6aa0b-114">Attribute</span></span>|<span data-ttu-id="6aa0b-115">설명</span><span class="sxs-lookup"><span data-stu-id="6aa0b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6aa0b-116">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="6aa0b-116">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="6aa0b-117">바인딩에서 지원해야 하는 보안 사양(WS-Security, WS-Trust, WS-Secure Conversation, WS-Security Policy) 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-117">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="6aa0b-118">이 값은 <xref:System.ServiceModel.MessageSecurityVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-118">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="6aa0b-119">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="6aa0b-119">inclusionMode</span></span>|<span data-ttu-id="6aa0b-120">토큰 포함 요구 사항을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-120">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="6aa0b-121">이 특성은 <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-121">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="6aa0b-122">keySize</span><span class="sxs-lookup"><span data-stu-id="6aa0b-122">keySize</span></span>|<span data-ttu-id="6aa0b-123">토큰 키 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-123">An integer that specifies the token key size.</span></span> <span data-ttu-id="6aa0b-124">기본값은 256입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-124">The default value is 256.</span></span>|  
|<span data-ttu-id="6aa0b-125">keyType</span><span class="sxs-lookup"><span data-stu-id="6aa0b-125">keyType</span></span>|<span data-ttu-id="6aa0b-126">키 형식을 지정하는 유효한 <xref:System.IdentityModel.Tokens.SecurityKeyType> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-126">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="6aa0b-127">기본값은 `SymmetricKey`입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-127">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="6aa0b-128">tokenType</span><span class="sxs-lookup"><span data-stu-id="6aa0b-128">tokenType</span></span>|<span data-ttu-id="6aa0b-129">토큰 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-129">A string that specifies the token type.</span></span> <span data-ttu-id="6aa0b-130">기본값은 "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML"입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-130">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6aa0b-131">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6aa0b-131">Child Elements</span></span>  
  
|<span data-ttu-id="6aa0b-132">요소</span><span class="sxs-lookup"><span data-stu-id="6aa0b-132">Element</span></span>|<span data-ttu-id="6aa0b-133">설명</span><span class="sxs-lookup"><span data-stu-id="6aa0b-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6aa0b-134">\<additionalRequestParameters></span><span class="sxs-lookup"><span data-stu-id="6aa0b-134">\<additionalRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|<span data-ttu-id="6aa0b-135">추가 요청 매개 변수를 지정하는 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-135">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="6aa0b-136">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="6aa0b-136">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="6aa0b-137">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-137">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="6aa0b-138">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-138">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="6aa0b-139">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-139">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="6aa0b-140">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-140">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="6aa0b-141">\<issuer></span><span class="sxs-lookup"><span data-stu-id="6aa0b-141">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|<span data-ttu-id="6aa0b-142">현재 토큰을 발급하는 엔드포인트를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-142">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="6aa0b-143">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="6aa0b-143">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="6aa0b-144">토큰 발급자의 메타데이터의 엔드포인트 주소를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-144">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6aa0b-145">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6aa0b-145">Parent Elements</span></span>  
  
|<span data-ttu-id="6aa0b-146">요소</span><span class="sxs-lookup"><span data-stu-id="6aa0b-146">Element</span></span>|<span data-ttu-id="6aa0b-147">설명</span><span class="sxs-lookup"><span data-stu-id="6aa0b-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6aa0b-148">\<secureConversationBootstrap></span><span class="sxs-lookup"><span data-stu-id="6aa0b-148">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="6aa0b-149">보안 대화 서비스 개시에 사용되는 기본값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-149">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="6aa0b-150">\<security></span><span class="sxs-lookup"><span data-stu-id="6aa0b-150">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="6aa0b-151">사용자 지정 바인딩에 대한 보안 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa0b-151">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6aa0b-152">참고자료</span><span class="sxs-lookup"><span data-stu-id="6aa0b-152">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="6aa0b-153">바인딩</span><span class="sxs-lookup"><span data-stu-id="6aa0b-153">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="6aa0b-154">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="6aa0b-154">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="6aa0b-155">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="6aa0b-155">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="6aa0b-156">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="6aa0b-156">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="6aa0b-157">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="6aa0b-157">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="6aa0b-158">Custom Binding Security</span><span class="sxs-lookup"><span data-stu-id="6aa0b-158">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="6aa0b-159">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="6aa0b-159">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="6aa0b-160">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="6aa0b-160">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="6aa0b-161">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="6aa0b-161">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="6aa0b-162">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="6aa0b-162">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
