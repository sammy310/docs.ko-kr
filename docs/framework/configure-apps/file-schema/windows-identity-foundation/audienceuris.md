---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: bd04e4ebdf5c58adaeea0ff0ca5993d7d9ce38f1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252178"
---
# \<audienceUris>
<span data-ttu-id="dad6e-101">RP (신뢰 당사자)에 허용 되는 식별자를 지정 하는 Uri 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-101">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="dad6e-102">허용 되는 대상 Uri 중 하나에 대해 범위가 지정 되지 않는 한 토큰을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-102">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**  
  
## <a name="syntax"></a><span data-ttu-id="dad6e-103">구문</span><span class="sxs-lookup"><span data-stu-id="dad6e-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dad6e-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dad6e-104">Attributes and Elements</span></span>  
 <span data-ttu-id="dad6e-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dad6e-106">특성</span><span class="sxs-lookup"><span data-stu-id="dad6e-106">Attributes</span></span>  
  
|<span data-ttu-id="dad6e-107">attribute</span><span class="sxs-lookup"><span data-stu-id="dad6e-107">Attribute</span></span>|<span data-ttu-id="dad6e-108">Description</span><span class="sxs-lookup"><span data-stu-id="dad6e-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dad6e-109">mode</span><span class="sxs-lookup"><span data-stu-id="dad6e-109">mode</span></span>|<span data-ttu-id="dad6e-110"><xref:System.IdentityModel.Selectors.AudienceUriMode>대상 제한이 들어오는 토큰에 적용 되어야 하는지 여부를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-110">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="dad6e-111">가능한 값은 "Always", "Never" 및 "BearerKeyOnly"입니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-111">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="dad6e-112">기본값은 "Always"입니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-112">The default is "Always".</span></span> <span data-ttu-id="dad6e-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-113">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dad6e-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dad6e-114">Child Elements</span></span>  
  
|<span data-ttu-id="dad6e-115">요소</span><span class="sxs-lookup"><span data-stu-id="dad6e-115">Element</span></span>|<span data-ttu-id="dad6e-116">Description</span><span class="sxs-lookup"><span data-stu-id="dad6e-116">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="dad6e-117">특성에 지정 된 URI를 `value` audienceUris 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-117">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="dad6e-118">`value` 특성은 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-118">The `value` attribute is required.</span></span> <span data-ttu-id="dad6e-119">URI는 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-119">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="dad6e-120">AudienceUris 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-120">Clears the audienceUris collection.</span></span> <span data-ttu-id="dad6e-121">모든 식별자는 컬렉션에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-121">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="dad6e-122">AudienceUris collection에서 특성으로 지정 된 URI를 제거 합니다 `value` .</span><span class="sxs-lookup"><span data-stu-id="dad6e-122">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="dad6e-123">`value` 특성은 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-123">The `value` attribute is required.</span></span> <span data-ttu-id="dad6e-124">URI는 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-124">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dad6e-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dad6e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="dad6e-126">요소</span><span class="sxs-lookup"><span data-stu-id="dad6e-126">Element</span></span>|<span data-ttu-id="dad6e-127">Description</span><span class="sxs-lookup"><span data-stu-id="dad6e-127">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="dad6e-128">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dad6e-129">설명</span><span class="sxs-lookup"><span data-stu-id="dad6e-129">Remarks</span></span>  
 <span data-ttu-id="dad6e-130">기본적으로 컬렉션은 비어 있습니다. `<add>`, `<clear>` 및 요소를 사용 하 여 컬렉션을 `<remove>` 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-130">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="dad6e-131"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>및 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 개체는 대상 uri 컬렉션의 값을 사용 하 여 개체에서 허용 되는 대상 uri 제한을 구성 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 합니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-131"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="dad6e-132">합니다 `<audienceUris>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-132">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="dad6e-133">컬렉션에 추가 된 개별 URI는 클래스로 표현 됩니다 <xref:System.IdentityModel.Configuration.AudienceUriElement> .</span><span class="sxs-lookup"><span data-stu-id="dad6e-133">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dad6e-134">요소를 `<audienceUris>` 요소의 자식 요소로 사용 하는 것은 [\<identityConfiguration>](identityconfiguration.md) 더 이상 사용 되지 않지만 이전 버전과의 호환성을 위해 계속 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-134">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="dad6e-135">`<securityTokenHandlerConfiguration>`요소의 설정은 요소의 설정을 재정의 `<identityConfiguration>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dad6e-136">예제</span><span class="sxs-lookup"><span data-stu-id="dad6e-136">Example</span></span>  
 <span data-ttu-id="dad6e-137">다음 XML에서는 응용 프로그램에 대 한 허용 가능한 대상 Uri를 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-137">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="dad6e-138">이 예제에서는 단일 URI를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-138">This example configures a single URI.</span></span> <span data-ttu-id="dad6e-139">이 URI에 대해 범위가 지정 된 토큰은 수락 되며 다른 모든 토큰은 거부 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dad6e-139">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
