---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: bd04e4ebdf5c58adaeea0ff0ca5993d7d9ce38f1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252178"
---
# <a name="audienceuris"></a><span data-ttu-id="b5df7-101">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="b5df7-101">\<audienceUris></span></span>
<span data-ttu-id="b5df7-102">RP (신뢰 당사자)에 허용 되는 식별자를 지정 하는 Uri 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="b5df7-103">허용 되는 대상 Uri 중 하나에 대해 범위가 지정 되지 않는 한 토큰을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
<span data-ttu-id="b5df7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b5df7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b5df7-105">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="b5df7-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="b5df7-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="b5df7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="b5df7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="b5df7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="b5df7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="b5df7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="b5df7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<audienceUris >**</span><span class="sxs-lookup"><span data-stu-id="b5df7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5df7-110">구문</span><span class="sxs-lookup"><span data-stu-id="b5df7-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5df7-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b5df7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b5df7-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5df7-113">특성</span><span class="sxs-lookup"><span data-stu-id="b5df7-113">Attributes</span></span>  
  
|<span data-ttu-id="b5df7-114">특성</span><span class="sxs-lookup"><span data-stu-id="b5df7-114">Attribute</span></span>|<span data-ttu-id="b5df7-115">Description</span><span class="sxs-lookup"><span data-stu-id="b5df7-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b5df7-116">모드</span><span class="sxs-lookup"><span data-stu-id="b5df7-116">mode</span></span>|<span data-ttu-id="b5df7-117">대상 제한이 들어오는 토큰에 적용 되어야 하는지 여부를 지정 하는 값입니다.<xref:System.IdentityModel.Selectors.AudienceUriMode></span><span class="sxs-lookup"><span data-stu-id="b5df7-117">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="b5df7-118">가능한 값은 "Always", "Never" 및 "BearerKeyOnly"입니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-118">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="b5df7-119">기본값은 "Always"입니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-119">The default is "Always".</span></span> <span data-ttu-id="b5df7-120">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5df7-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b5df7-121">Child Elements</span></span>  
  
|<span data-ttu-id="b5df7-122">요소</span><span class="sxs-lookup"><span data-stu-id="b5df7-122">Element</span></span>|<span data-ttu-id="b5df7-123">Description</span><span class="sxs-lookup"><span data-stu-id="b5df7-123">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="b5df7-124">`value` 특성에 지정 된 URI를 audienceUris 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-124">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="b5df7-125">`value` 특성은 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-125">The `value` attribute is required.</span></span> <span data-ttu-id="b5df7-126">URI는 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-126">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="b5df7-127">AudienceUris 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-127">Clears the audienceUris collection.</span></span> <span data-ttu-id="b5df7-128">모든 식별자는 컬렉션에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-128">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="b5df7-129">AudienceUris collection에서 `value` 특성으로 지정 된 URI를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-129">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="b5df7-130">`value` 특성은 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-130">The `value` attribute is required.</span></span> <span data-ttu-id="b5df7-131">URI는 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-131">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b5df7-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b5df7-132">Parent Elements</span></span>  
  
|<span data-ttu-id="b5df7-133">요소</span><span class="sxs-lookup"><span data-stu-id="b5df7-133">Element</span></span>|<span data-ttu-id="b5df7-134">설명</span><span class="sxs-lookup"><span data-stu-id="b5df7-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5df7-135">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="b5df7-135">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="b5df7-136">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-136">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5df7-137">설명</span><span class="sxs-lookup"><span data-stu-id="b5df7-137">Remarks</span></span>  
 <span data-ttu-id="b5df7-138">기본적으로 컬렉션은 비어 있습니다. , `<add>` 및요소`<remove>` 를 사용 하 여 컬렉션을 수정 합니다. `<clear>`</span><span class="sxs-lookup"><span data-stu-id="b5df7-138">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="b5df7-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>및 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 개체는 대상 uri 컬렉션의 값을 사용 하 여 개체에서 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 허용 되는 대상 uri 제한을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="b5df7-140">합니다 `<audienceUris>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-140">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="b5df7-141">컬렉션에 추가 된 개별 URI는 <xref:System.IdentityModel.Configuration.AudienceUriElement> 클래스로 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-141">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b5df7-142">IdentityConfiguration > 요소의 자식 `<audienceUris>` 요소로 [요소를 사용 하는 것은 더 이상 사용 되지 않지만 이전 버전과의 호환성을 위해 계속 지원 됩니다. \<](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="b5df7-142">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="b5df7-143">요소의 설정은 `<identityConfiguration>` 요소의 설정을 재정의 합니다. `<securityTokenHandlerConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="b5df7-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5df7-144">예제</span><span class="sxs-lookup"><span data-stu-id="b5df7-144">Example</span></span>  
 <span data-ttu-id="b5df7-145">다음 XML에서는 응용 프로그램에 대 한 허용 가능한 대상 Uri를 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-145">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="b5df7-146">이 예제에서는 단일 URI를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-146">This example configures a single URI.</span></span> <span data-ttu-id="b5df7-147">이 URI에 대해 범위가 지정 된 토큰은 수락 되며 다른 모든 토큰은 거부 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5df7-147">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
