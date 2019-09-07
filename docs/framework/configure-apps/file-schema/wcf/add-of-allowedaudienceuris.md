---
title: <allowedAudienceUris>의 <add>
ms.date: 03/30/2017
ms.assetid: 4e7b7637-e0ea-4a91-988f-6b6ef28d9fc3
ms.openlocfilehash: e15cb2d3e525d39a321bbe9760ddb8d72b02fffa
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398353"
---
# <a name="add-of-allowedaudienceuris"></a><span data-ttu-id="efb18-102">\<\<allowedAudienceUris > > 추가</span><span class="sxs-lookup"><span data-stu-id="efb18-102">\<add> of \<allowedAudienceUris></span></span>
<span data-ttu-id="efb18-103"><xref:System.IdentityModel.Tokens.SamlSecurityToken> 인스턴스에서 유효한 대상으로 지정할 수 있는 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 보안 토큰의 대상 URI를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="efb18-103">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
<span data-ttu-id="efb18-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="efb18-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="efb18-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="efb18-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="efb18-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="efb18-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="efb18-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="efb18-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="efb18-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="efb18-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="efb18-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="efb18-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="efb18-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenAuthentication >** ](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="efb18-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)</span></span>\
<span data-ttu-id="efb18-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<allowedAudienceUris >** ](allowedaudienceuris.md)</span><span class="sxs-lookup"><span data-stu-id="efb18-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowedAudienceUris>**](allowedaudienceuris.md)</span></span>\
<span data-ttu-id="efb18-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="efb18-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efb18-113">구문</span><span class="sxs-lookup"><span data-stu-id="efb18-113">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efb18-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="efb18-114">Attributes and Elements</span></span>  
 <span data-ttu-id="efb18-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="efb18-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="efb18-116">특성</span><span class="sxs-lookup"><span data-stu-id="efb18-116">Attributes</span></span>  
  
|<span data-ttu-id="efb18-117">특성</span><span class="sxs-lookup"><span data-stu-id="efb18-117">Attribute</span></span>|<span data-ttu-id="efb18-118">설명</span><span class="sxs-lookup"><span data-stu-id="efb18-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="efb18-119">allowedAudienceUri</span><span class="sxs-lookup"><span data-stu-id="efb18-119">allowedAudienceUri</span></span>|<span data-ttu-id="efb18-120"><xref:System.IdentityModel.Tokens.SamlSecurityToken> 인스턴스에서 유효한 대상으로 지정할 수 있는 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 보안 토큰의 대상 URI를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="efb18-120">A string that contains a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="efb18-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="efb18-121">Child Elements</span></span>  
 <span data-ttu-id="efb18-122">없음</span><span class="sxs-lookup"><span data-stu-id="efb18-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="efb18-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="efb18-123">Parent Elements</span></span>  
  
|<span data-ttu-id="efb18-124">요소</span><span class="sxs-lookup"><span data-stu-id="efb18-124">Element</span></span>|<span data-ttu-id="efb18-125">Description</span><span class="sxs-lookup"><span data-stu-id="efb18-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="efb18-126">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="efb18-126">\<allowedAudienceUris></span></span>](allowedaudienceuris.md)|<span data-ttu-id="efb18-127"><xref:System.IdentityModel.Tokens.SamlSecurityToken> 인스턴스에서 유효한 대상으로 지정할 수 있는 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 보안 토큰의 대상 URI 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="efb18-127">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efb18-128">설명</span><span class="sxs-lookup"><span data-stu-id="efb18-128">Remarks</span></span>  
 <span data-ttu-id="efb18-129">STS(보안 토큰 서비스)를 사용하여 <xref:System.IdentityModel.Tokens.SamlSecurityToken> 보안 토큰을 발급하는 페더레이션 애플리케이션에서는 이 컬렉션을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb18-129">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="efb18-130">STS는 보안 토큰을 발급할 때 보안 토큰에 <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>을 추가하여 보안 토큰을 사용할 웹 서비스의 URI를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb18-130">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="efb18-131">따라서 발급된 보안 토큰이 해당 웹 서비스용인지 검사하도록 지정하여 수신자 웹 서비스의 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>가 이를 확인하도록 할 수 있습니다. 이렇게 하려면 다음을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="efb18-131">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
- <span data-ttu-id="efb18-132">`audienceUriMode`의 `<issuedTokenAuthentication>` 특성을 <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> 또는 <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="efb18-132">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
- <span data-ttu-id="efb18-133">이 컬렉션에 URI를 추가하여 유효한 URI 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="efb18-133">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="efb18-134">자세한 내용은 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efb18-134">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="efb18-135">이 구성 요소를 [사용 하는 방법에 대 한 자세한 내용은 방법: 페더레이션 서비스](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)에 대 한 자격 증명을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb18-135">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb18-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="efb18-136">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [<span data-ttu-id="efb18-137">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="efb18-137">\<allowedAudienceUris></span></span>](allowedaudienceuris.md)
- [<span data-ttu-id="efb18-138">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="efb18-138">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="efb18-139">보안 동작</span><span class="sxs-lookup"><span data-stu-id="efb18-139">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="efb18-140">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="efb18-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="efb18-141">방법: 페더레이션 서비스에 대 한 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="efb18-141">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
