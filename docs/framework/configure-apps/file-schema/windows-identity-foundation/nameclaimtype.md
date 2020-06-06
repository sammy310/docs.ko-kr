---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 4bf8ad2f70499edfc72dd9fcd9a5d8a0aafbbc66
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251934"
---
# \<nameClaimType>
<span data-ttu-id="e65c8-101">속성을 지정 하는 클레임 유형을 설정 합니다 <xref:System.Security.Principal.IIdentity.Name%2A> .</span><span class="sxs-lookup"><span data-stu-id="e65c8-101">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="e65c8-102">클레임 형식은 <xref:System.Security.Claims.Claim> <xref:System.Security.Claims.ClaimsIdentity> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> 이 토큰 처리기의 메서드에서 반환 하는 개체의 컬렉션에서를 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e65c8-102">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="e65c8-103">그런 다음 일치 하는 클레임의 값 <xref:System.Security.Principal.IIdentity> 이이 토큰 처리기에서 생성 된의 이름으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e65c8-103">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameClaimType>**  
  
## <a name="syntax"></a><span data-ttu-id="e65c8-104">구문</span><span class="sxs-lookup"><span data-stu-id="e65c8-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e65c8-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e65c8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e65c8-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e65c8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e65c8-107">특성</span><span class="sxs-lookup"><span data-stu-id="e65c8-107">Attributes</span></span>  
  
|<span data-ttu-id="e65c8-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e65c8-108">Attribute</span></span>|<span data-ttu-id="e65c8-109">Description</span><span class="sxs-lookup"><span data-stu-id="e65c8-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e65c8-110">값</span><span class="sxs-lookup"><span data-stu-id="e65c8-110">value</span></span>|<span data-ttu-id="e65c8-111">속성에 사용할 클레임의 클레임 형식을 나타내는 URI를 지정 하는 문자열입니다 <xref:System.Security.Principal.IIdentity.Name%2A> .</span><span class="sxs-lookup"><span data-stu-id="e65c8-111">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="e65c8-112">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="e65c8-112">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e65c8-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e65c8-113">Child Elements</span></span>  
 <span data-ttu-id="e65c8-114">None</span><span class="sxs-lookup"><span data-stu-id="e65c8-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e65c8-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e65c8-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e65c8-116">요소</span><span class="sxs-lookup"><span data-stu-id="e65c8-116">Element</span></span>|<span data-ttu-id="e65c8-117">Description</span><span class="sxs-lookup"><span data-stu-id="e65c8-117">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="e65c8-118"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>클래스, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스 또는 이러한 클래스 중 하나의 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e65c8-118">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e65c8-119">설명</span><span class="sxs-lookup"><span data-stu-id="e65c8-119">Remarks</span></span>  
 <span data-ttu-id="e65c8-120">`<nameClaimType>`요소는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 개체가 구성에서 초기화 될 때 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e65c8-120">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e65c8-121">예제</span><span class="sxs-lookup"><span data-stu-id="e65c8-121">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e65c8-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e65c8-122">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
