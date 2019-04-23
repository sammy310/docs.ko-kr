---
title: <allowedAudienceUris>의 <add>
ms.date: 03/30/2017
ms.assetid: 4e7b7637-e0ea-4a91-988f-6b6ef28d9fc3
ms.openlocfilehash: a3ad50462cfa268a1826b62603110be3c5ba33db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148280"
---
# <a name="add-of-allowedaudienceuris"></a><span data-ttu-id="c275d-102">\<add> of \<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="c275d-102">\<add> of \<allowedAudienceUris></span></span>
<span data-ttu-id="c275d-103"><xref:System.IdentityModel.Tokens.SamlSecurityToken> 인스턴스에서 유효한 대상으로 지정할 수 있는 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 보안 토큰의 대상 URI를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c275d-103">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="c275d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c275d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c275d-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="c275d-105">\<behaviors></span></span>  
<span data-ttu-id="c275d-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c275d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="c275d-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c275d-107">\<behavior></span></span>  
<span data-ttu-id="c275d-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="c275d-108">\<serviceCredentials></span></span>  
<span data-ttu-id="c275d-109">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="c275d-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="c275d-110">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="c275d-110">\<allowedAudienceUris></span></span>  
<span data-ttu-id="c275d-111">\<추가 > 요소에 대 한 \<a d ></span><span class="sxs-lookup"><span data-stu-id="c275d-111">\<add> element for \<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c275d-112">구문</span><span class="sxs-lookup"><span data-stu-id="c275d-112">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c275d-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c275d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c275d-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c275d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c275d-115">특성</span><span class="sxs-lookup"><span data-stu-id="c275d-115">Attributes</span></span>  
  
|<span data-ttu-id="c275d-116">특성</span><span class="sxs-lookup"><span data-stu-id="c275d-116">Attribute</span></span>|<span data-ttu-id="c275d-117">설명</span><span class="sxs-lookup"><span data-stu-id="c275d-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c275d-118">allowedAudienceUri</span><span class="sxs-lookup"><span data-stu-id="c275d-118">allowedAudienceUri</span></span>|<span data-ttu-id="c275d-119"><xref:System.IdentityModel.Tokens.SamlSecurityToken> 인스턴스에서 유효한 대상으로 지정할 수 있는 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 보안 토큰의 대상 URI를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c275d-119">A string that contains a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c275d-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c275d-120">Child Elements</span></span>  
 <span data-ttu-id="c275d-121">없음</span><span class="sxs-lookup"><span data-stu-id="c275d-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c275d-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c275d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c275d-123">요소</span><span class="sxs-lookup"><span data-stu-id="c275d-123">Element</span></span>|<span data-ttu-id="c275d-124">설명</span><span class="sxs-lookup"><span data-stu-id="c275d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c275d-125">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="c275d-125">\<allowedAudienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md)|<span data-ttu-id="c275d-126"><xref:System.IdentityModel.Tokens.SamlSecurityToken> 인스턴스에서 유효한 대상으로 지정할 수 있는 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 보안 토큰의 대상 URI 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c275d-126">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c275d-127">설명</span><span class="sxs-lookup"><span data-stu-id="c275d-127">Remarks</span></span>  
 <span data-ttu-id="c275d-128">STS(보안 토큰 서비스)를 사용하여 <xref:System.IdentityModel.Tokens.SamlSecurityToken> 보안 토큰을 발급하는 페더레이션 응용 프로그램에서는 이 컬렉션을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c275d-128">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="c275d-129">STS는 보안 토큰을 발급할 때 보안 토큰에 <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>을 추가하여 보안 토큰을 사용할 웹 서비스의 URI를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c275d-129">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="c275d-130">따라서 발급된 보안 토큰이 해당 웹 서비스용인지 검사하도록 지정하여 수신자 웹 서비스의 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>가 이를 확인하도록 할 수 있습니다. 이렇게 하려면 다음을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="c275d-130">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
-   <span data-ttu-id="c275d-131">`audienceUriMode`의 `<issuedTokenAuthentication>` 특성을 <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> 또는 <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c275d-131">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
-   <span data-ttu-id="c275d-132">이 컬렉션에 URI를 추가하여 유효한 URI 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c275d-132">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="c275d-133">자세한 내용은 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c275d-133">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="c275d-134">이 구성 요소 사용에 대 한 자세한 내용은 참조 하세요. [방법: 페더레이션 서비스에서 자격 증명 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c275d-134">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c275d-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="c275d-135">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [<span data-ttu-id="c275d-136">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="c275d-136">\<allowedAudienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md)
- [<span data-ttu-id="c275d-137">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="c275d-137">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="c275d-138">보안 동작</span><span class="sxs-lookup"><span data-stu-id="c275d-138">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="c275d-139">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="c275d-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c275d-140">방법: 페더레이션 서비스에서 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="c275d-140">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
