---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 4bf8ad2f70499edfc72dd9fcd9a5d8a0aafbbc66
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251934"
---
# <a name="nameclaimtype"></a><span data-ttu-id="6b8c3-101">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="6b8c3-101">\<nameClaimType></span></span>
<span data-ttu-id="6b8c3-102">속성을 <xref:System.Security.Principal.IIdentity.Name%2A> 지정 하는 클레임 유형을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="6b8c3-103">클레임 형식은이 토큰 처리기의 <xref:System.Security.Claims.Claim> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> 메서드에서 반환 하는 개체의 <xref:System.Security.Claims.ClaimsIdentity> 컬렉션에서를 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="6b8c3-104">그런 다음 일치 하는 클레임의 값이이 토큰 처리기에서 <xref:System.Security.Principal.IIdentity> 생성 된의 이름으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
<span data-ttu-id="6b8c3-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6b8c3-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6b8c3-106">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="6b8c3-106">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="6b8c3-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="6b8c3-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="6b8c3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="6b8c3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="6b8c3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> 추가**](add.md)</span><span class="sxs-lookup"><span data-stu-id="6b8c3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="6b8c3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<samlSecurityTokenRequirement >** ](samlsecuritytokenrequirement.md)</span><span class="sxs-lookup"><span data-stu-id="6b8c3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)</span></span>\
<span data-ttu-id="6b8c3-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<nameClaimType >**</span><span class="sxs-lookup"><span data-stu-id="6b8c3-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameClaimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b8c3-112">구문</span><span class="sxs-lookup"><span data-stu-id="6b8c3-112">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b8c3-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6b8c3-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6b8c3-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b8c3-115">특성</span><span class="sxs-lookup"><span data-stu-id="6b8c3-115">Attributes</span></span>  
  
|<span data-ttu-id="6b8c3-116">특성</span><span class="sxs-lookup"><span data-stu-id="6b8c3-116">Attribute</span></span>|<span data-ttu-id="6b8c3-117">설명</span><span class="sxs-lookup"><span data-stu-id="6b8c3-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b8c3-118">value</span><span class="sxs-lookup"><span data-stu-id="6b8c3-118">value</span></span>|<span data-ttu-id="6b8c3-119"><xref:System.Security.Principal.IIdentity.Name%2A> 속성에 사용할 클레임의 클레임 형식을 나타내는 URI를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-119">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="6b8c3-120">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b8c3-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6b8c3-121">Child Elements</span></span>  
 <span data-ttu-id="6b8c3-122">없음</span><span class="sxs-lookup"><span data-stu-id="6b8c3-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b8c3-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6b8c3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6b8c3-124">요소</span><span class="sxs-lookup"><span data-stu-id="6b8c3-124">Element</span></span>|<span data-ttu-id="6b8c3-125">Description</span><span class="sxs-lookup"><span data-stu-id="6b8c3-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b8c3-126">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="6b8c3-126">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="6b8c3-127"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 클래스<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , 클래스 또는 이러한 클래스 중 하나의 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-127">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b8c3-128">설명</span><span class="sxs-lookup"><span data-stu-id="6b8c3-128">Remarks</span></span>  
 <span data-ttu-id="6b8c3-129">요소 `<nameClaimType>` 는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 개체가 구성 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> 에서 초기화 될 때 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-129">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b8c3-130">예제</span><span class="sxs-lookup"><span data-stu-id="6b8c3-130">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6b8c3-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="6b8c3-131">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
